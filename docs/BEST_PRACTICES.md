> בס״ד

# ⭐ Best Practices

מדריך שיטות עבודה מומלצות לשימוש יעיל ואתי ב-Diablo.

## 📋 תוכן עניינים

- [אתיקה ומשפטיות](#אתיקה-ומשפטיות)
- [תכנון וביצוע](#תכנון-וביצוע)
- [אבטחת מידע](#אבטחת-מידע)
- [תיעוד ודוחות](#תיעוד-ודוחות)
- [אופטימיזציה](#אופטימיזציה)

## ⚖️ אתיקה ומשפטיות

### רכישת הרשאות

#### לפני התחלה
✅ **הכרחי:**
- הרשאה בכתב מהבעלים
- תיאום מול צוות IT
- הסכם SOW (Statement of Work)
- הגדרת scope מדויק

❌ **אסור:**
- סריקות ללא הרשאה
- חריגה מ-scope
- גישה למידע לא רלוונטי

### דוגמאות להסכמים

```markdown
PenTest Agreement Example:
- Target: 192.168.1.0/24
- Scope: Web servers, API endpoints
- Excluded: Database servers, backup systems
- Duration: Oct 28 - Oct 30, 2025
- Team: AnLoMinus, 2 analysts
- Deliverable: Report by Nov 5
```

### הפרות אבטחה

```bash
# אם מוצאת בעיה בינונית/גבוהה:
1. תיעוד מיידי
2. דיווח ללקוח
3. בדיקת אם exploitation אפשרי
4. ניטור logs
```

## 🎯 תכנון וביצוע

### שלב התכנון

#### 1. Information Gathering
```bash
# לפני סריקות חזקות
./Diablo
[p] → Planning
# תעד:
# - IP ranges
# - Domains
# - Technologies
# - Business context
```

#### 2. Scope Definition
```yaml
In-Scope:
  - Web applications
  - API endpoints
  - Network infrastructure
  - End user systems

Out-of-Scope:
  - Social engineering
  - Physical security
  - Third-party services
  - Production databases
```

#### 3. Time Management
```
Day 1: Planning + Initial reconnaissance
Day 2: Network + Web scanning
Day 3: Vulnerability assessment + Exploitation testing
Day 4: Reporting + Review
```

### שלב הביצוע

#### סדר עדיפויות
```bash
# 1. Quick reconnaissance
ping + traceroute + basic nmap

# 2. Deep scanning
Full nmap + DNS enumeration

# 3. Service-specific
Web enumeration + API testing
```

#### ניהול זמן
```bash
# צור תיקיות לפי תאריך
mkdir -p 2025-10-28/{morning,afternoon,evening}

# כל 2 שעות
# [p] → New sub-project
# בהמשך: merge reports
```

## 🔐 אבטחת מידע

### נתונים רגישים

#### איך לזהות?
```bash
# בדוח Markdown
grep -i "password\|secret\|key\|token\|credential" \
  *.md

# הסר או השחלף
sed -i 's/password:.*/password: [REDACTED]/g' report.md
```

#### שמירה בטוחה
```bash
# הצפנה
gpg -c ClientWebsite-Diablo-Log.md
# Delete original
rm ClientWebsite-Diablo-Log.md

# או
# tar + encryption
tar czf - ClientWebsite-Diablo-Log.md | \
  gpg -c > report.tar.gz.gpg
```

### אבטחת תקשורת

```bash
# VPN + Diablo anonymity
./Diablo
[a] → [2]  # Start anonsurf

# או VPN נפרד
sudo openvpn client.ovpn
./Diablo
```

### הצפנת דוחות

```bash
# GPG Encryption
# Generate key if needed
gpg --generate-key

# Encrypt report
gpg --encrypt --recipient your@email.com \
  ClientWebsite-Diablo-Log.md

# Decrypt later
gpg --decrypt \
  ClientWebsite-Diablo-Log.md.gpg > report.md
```

## 📝 תיעוד ודוחות

### מבנה דוח אידיאלי

```markdown
# Executive Summary
- מה נבדק?
- תקציר ממצאים
- המלצות עיקריות

# Methodology
- כלים ותהליכים
- Scope מתואר

# Findings
- High/Medium/Low
- CVSS scores
- Proof of concept

# Recommendations
- תיקון קצר טווח
- שיפורי אבטחה
- בדיקות המשך

# Appendix
- Raw scan results
- Screenshots
- Logs
```

### כתיבה מקצועית

#### Do ✅
```markdown
Vulnerability: SQL Injection in Login Form
Severity: High (CVSS 8.5)
Impact: Full database compromise
Evidence: [screenshot]
Recommendation: Parameterized queries
```

#### Don't ❌
```markdown
This is broken and can be hacked!
```

### ויזואליזציה

```bash
# Charts from data
# Extract open ports
grep -E "^\d+/tcp" report.md | \
  awk '{print $3}' | sort | uniq -c | \
  sort -rn | head -10

# או Python + matplotlib
python3 visualize-port-data.py report.md
```

## ⚡ אופטימיזציה

### ביצועים

#### סריקות מקבילות
```bash
# בסיס: sequential
nmap target1; nmap target2

# מתקדם: parallel
nmap target1 &
nmap target2 &
wait
```

#### Rate Limiting
```bash
# להגנה על רשתות
nmap --max-rate 1000 target

# masscan
masscan target -p0-65535 --max-rate 500
```

### אוטומציה

#### סקריפטי wrapper
```bash
#!/bin/bash
# auto-pentest.sh

TARGETS=("192.168.1.1" "192.168.1.2")

for TARGET in "${TARGETS[@]}"; do
    echo "Scanning $TARGET..."
    nmap -sV $TARGET >> report.log
    sleep 60  # Rate limiting
done
```

#### Cron Jobs
```bash
# שבועי
0 2 * * 1 /path/to/weekly-scan.sh

# חשוב: רק עם הרשאה!
```

### ניהול משאבים

#### זיכרון
```bash
# Clean old reports
find ~/pentest-reports -mtime +90 -delete

# Compress
tar czf old-reports.tar.gz ~/old-reports/
```

#### דיסק
```bash
# Monitor space
df -h

# Clean logs
journalctl --vacuum-time=7d
```

## 🔄 תהליך איכות

### Review דוח

```bash
# Checklist
- [ ] כל ממצא מתועד
- [ ] CVSS scores מדויקים
- [ ] ללא נתונים רגישים
- [ ] המלצות מעשיות
- [ ] Executive summary ברור
```

### Peer Review

```bash
# לפני מסירה ללקוח
# 1. Self-review
# 2. Peer review
# 3. Manager sign-off
```

### עדכון כלים

```bash
# Weekly
sudo apt update && sudo apt upgrade

# Check CVE databases
# Update wordlists
```

## 📊 מטריקות

### מדידת הצלחה

```yaml
Metrics:
  Reconnaissance:
    - Targets discovered
    - Services identified
    - Technologies mapped
  
  Vulnerabilities:
    - Total findings
    - By severity
    - By category
  
  Remediation:
    - Acceptance rate
    - Time to fix
    - Re-scan results
```

## 🌍 סביבות

### Dev/Staging/Prod

```bash
# תמיד בדוק בסביבות נכונות
if [[ $TARGET == *"prod"* ]]; then
    echo "⚠️ Production target - extra caution!"
    read -p "Confirm: " confirm
fi
```

## 📚 משאבים

### למידה מתמשכת

- **OWASP** - מדריכי אבטחה
- **PTES** - Penetration Testing Execution Standard
- **NIST** - Cybersecurity Framework
- **Bug Bounty** platforms

### קהילה

- GitHub Discussions
- Reddit /r/netsec
- Information Security forums
- Local meetups

---

## 🎓 סיכום

✅ **תמיד:**
- קיבל הרשאה מראש
- תיעד הכל
- שמור מידע רגיש
- עבוד מובנה
- למד מתמיד

❌ **לעולם לא:**
- סריקות לא מורשות
- חסר מידע חשוב בדוחות
- חשוף מידע ללקוחות
- עבוד חסר סדר
- תמנע מלעדכן ידע

---

**זכור: PenTest הוא אחריות, לא רק תפקיד** ⚖️

> בס״ד - מגדל בסייעתא דשמיא

