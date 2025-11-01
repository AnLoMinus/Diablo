> בס״ד

# 🔐 Security Model

מסמך זה מתאר את מודל האבטחה של Diablo ואת ההתחשבויות האבטחתיות בעת שימוש בכלי.

## 📋 תוכן עניינים

- [מודל האמון](#מודל-האמון)
- [הרשאות מערכת](#הרשאות-מערכת)
- [פרטיות ומניעת חשיפה](#פרטיות-ומניעת-חשיפה)
- [אבטחת תקשורת](#אבטחת-תקשורת)
- [ניהול נתונים](#ניהול-נתונים)
- [אחריות משתמש](#אחריות-משתמש)

## 🤝 מודל האמון

### דגם ארכיטקטוני

```
┌─────────────────────────────────────┐
│         User (Pentester)             │
│                                      │
│         ./Diablo Script              │
│         (Local execution)            │
└───────────────┬──────────────────────┘
                │
        ┌───────┴────────┐
        │                │
┌───────▼──────┐  ┌──────▼────────┐
│ PenTesting   │  │  Local File   │
│  Tools       │  │  System       │
│  (nmap, etc) │  │               │
└──────────────┘  └───────────────┘
```

### הנחות אמון

#### ✅ נאמן לחלוטין
- **הקוד המקורי:** Repository זה
- **מקורות:** GitHub.com/Anlominus/Diablo

#### ⚠️ דורש בדיקה
- **כלי PenTest:** nmap, masscan, dirb ועוד
- **תלות חיצונית:** HacKingPro (אם קיים)
- **Package Managers:** apt, brew, pkg

### Threat Model

#### התקפות פוטנציאליות

```yaml
Threats:
  Supply_Chain:
    - Modified repository clone
    - Trojaned tools
    - Backdoored packages
    
  Execution:
    - Privilege escalation
    - Data leakage
    - Resource exhaustion
    
  Data:
    - Unauthorized access
    - Log exposure
    - Credential theft
```

## 🔑 הרשאות מערכת

### דרישות הרשאה

#### רגיל
```bash
# רוב הפונקציות
./Diablo  # No sudo needed
nmap -sV target  # Normal scan
```

#### מיוחד
```bash
# חלק מהסריקות
sudo nmap -sS target  # SYN scan
sudo masscan target  # Raw sockets
```

### עקרון Least Privilege

```bash
# ✅ נכון
sudo nmap -sV target

# ❌ לא נכון
sudo su
# ... הכל בתור root
```

## 🔒 פרטיות ומניעת חשיפה

### נתונים רגישים

#### מיושמים בכיף

```yaml
What_Diablo_Collects:
  - Target IP addresses
  - Scan results
  - Network topology
  - Service banners
  
What_Diablo_Does_NOT:
  - User credentials
  - Personal data
  - Credit cards
  - Internal communications
```

#### ניהול וחסימה

```markdown
# בדיוק כמו ב-Best Practices
- גילוי מיידי
- השחרה/מיון
- שמירה מוצפנת
- מחיקה בתום תקופה
```

### Logging & Tracing

```bash
# Diablo לא שולח נתונים חיצוניים
# כל העיבוד מקומי
```

## 📡 אבטחת תקשורת

### רשת

#### כמויות שמשתמשות

```bash
# DDoS protection
nmap --max-rate 1000 target  # Limit packets/sec
```

#### Anonymity

```bash
# עקב after check-anonsurf
./Diablo → [a] → [2]  # Start anonsurf
```

### VPN ו-NAT

```bash
# למקרה של proxy/VPN
# Diablo לא משנה הגדרות רשת
# כל כלי ש"נקרא" צריך הגדרת proxy משלו
```

## 💾 ניהול נתונים

### שמירה

```
┌──────────────────────────────────┐
│  ClientWebsite-Diablo-Log.md      │
│  (Unencrypted by default)        │
└──────────────────────────────────┘

אחריות המשתמש להצפין במידת הצורך
```

### מחיקה

```bash
# Cleanup scripts
find ~/pentest-reports -mtime +90 -delete
```

### גיבוי

```bash
# Secure backup
tar czf - *.md | gpg -c > backup.tar.gz.gpg
```

## ⚖️ אחריות משתמש

### חובות

```yaml
User_Responsibility:
  Legal:
    - Obtain written authorization
    - Comply with local laws
    - Respect scope boundaries
    
  Ethical:
    - No unauthorized testing
    - Responsible disclosure
    - Protect sensitive data
    
  Technical:
    - Verify tool sources
    - Keep tools updated
    - Secure generated reports
```

### מגבלות

```yaml
Limitations:
  Software:
    - Diablo is tool agnostic
    - No input validation for targets
    - No built-in encryption
    
  Legal:
    - No warranties
    - Use at own risk
    - Author not liable for misuse
```

## 🔐 Best Security Practices

### התקנה

```bash
# Verify checksums
wget https://github.com/Anlominus/Diablo/releases/download/v1.0.0/Diablo
wget https://github.com/Anlominus/Diablo/releases/download/v1.0.0/checksums.txt

# Verify
sha256sum -c checksums.txt
```

### שימוש יומיומי

```bash
# 1. Check integrity
git clone https://github.com/Anlominus/Diablo.git
cd Diablo
git verify-commit HEAD

# 2. Review before use
head -50 Diablo  # Quick review

# 3. Use safely
./Diablo  # With authorization only
```

### תחזוקה

```bash
# Weekly updates
cd Diablo
git pull origin main

# Tool updates
sudo apt update && sudo apt upgrade
```

## 🚨 Incident Response

### אם מופיעה בעיה באבטחה

```bash
1. Stop using Diablo immediately
2. Isolate affected systems
3. Check GitHub Issues for known problems
4. Report to security@anlominus.github.io
5. Review recent changes
```

### Recovery

```bash
# Clean system
rm -rf /path/to/Diablo

# Reinstall from verified source
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo
chmod +x Diablo
```

## 📊 Security Metrics

### Tracking

```yaml
Metrics:
  Vulnerability_Reports: 0
  Security_Incidents: 0
  Code_Reviews: Monthly
  Dependency_Updates: Automated
```

### Compliance

```yaml
Standards:
  - OWASP ASVS
  - ISO 27001 (tool usage)
  - NIST Cybersecurity Framework
  - PenTest guidelines
```

## 🔗 References

- [SECURITY.md](../SECURITY.md) - Security policy
- [README.md](../README.md) - Main documentation
- [Best Practices](./BEST_PRACTICES.md) - Usage guidelines

---

## ✅ Checklist

לפני שימוש ב-Diablo:

- [ ] קראתי SECURITY.md
- [ ] הבנתי את מודל האמון
- [ ] יש לי הרשאה מפורשת
- [ ] כלי PenTest מקוריים
- [ ] תיקנתי את סביבתי
- [ ] יש לי backup strategy
- [ ] אני מבין את הסיכונים

---

**אבטחה היא תהליך, לא תוצאה** 🔐

> בס״ד - מגדל בסייעתא דשמיא

