> בס״ד

# 📖 Usage Guide

מדריך שימוש מפורט לכל התכונות של Diablo.

## 🎯 תוכן עניינים

- [תפריט ראשי](#תפריט-ראשי)
- [Planning and Scoping](#planning-and-scoping)
- [Reconnaissance](#reconnaissance)
- [Anonymity Surfing](#anonymity-surfing)
- [דוחות](#דוחות)
- [טיפים מתקדמים](#טיפים-מתקדמים)

## 📜 תפריט ראשי

לאחר הפעלת `./Diablo`, תראה תפריט עם האפשרויות הבאות:

```
┌──[ AnLoMinus 👽 Diablo $~]
└──╼

[#] 📜 Menu

[#] 📜 Target IP: 
[#] 📜 Target Project Name: 
[#] 📜 Target Domain Name: 

[a] - Anonymity Surfing
[1] - Planning and Scoping
[2] - Reconnaissance & Vulnerability Assessment
[3] - Gaining Access & Maintaining Access
[4] - Covering tracks
[5] - Analysis & Reporting

[x] - Exit / Quit / Close
```

## 🎯 Planning and Scoping

### אתחול פרויקט חדש

בחר `[p]` או `[P]` או הקלד `plan`:

```bash
./Diablo
# בתפריט בחר: p
```

### הגדרת מטרה

תתבקש להזין:
1. **Target IP** - כתובת IP של המטרה
2. **Project Name** - שם הפרויקט/דוח
3. **Domain Name** - Domain (אם רלוונטי)

דוגמה:
```
Target IP: 192.168.1.100
Project Name: ClientWebsite
Domain: client.example.com
```

### יצירת דוח

לאחר הגדרת הפרמטרים, נוצר קובץ דוח:
```
ClientWebsite-Diablo-Log.md
```

## 🔍 Reconnaissance & Vulnerability Assessment

לאחר הגדרת מטרה, בחר `[2]` לתחילת סריקות.

### Network Analysis

#### Arp Scan
```bash
arp -an
```
- טבלת ARP מקומית

#### Traceroute
```bash
traceroute 192.168.1.100
```
- מסלול IP
- זיהוי נתבים

#### Ping
```bash
ping 192.168.1.100 -c4
```
- בדיקת שירותיות
- זיהוי latency

#### Masscan
```bash
masscan 192.168.1.100 -p0-65535 --max-rate 1000
```
- סריקת פורטים מהירה
- נוח למטרות גדולות

### Port Scanning

#### Nmap Full Scan
```bash
nmap -sV -sC -O -p- 192.168.1.100
```
- זיהוי שירותים וגרסאות
- בדיקות אבטחה בסיסיות
- זיהוי OS

### DNS Enumeration

#### Basic DNS
```bash
dig 192.168.1.100 all
nslookup 192.168.1.100
whois 192.168.1.100
```

#### Advanced DNS
```bash
dnsenum client.example.com
fierce --domain client.example.com
dnsrecon -d client.example.com
```
- חילוץ תת-דומיינים
- חקירת DNS מקיפה

### Web Enumeration

#### Dirb
```bash
dirb http://client.example.com
```
- גילוי דירקטוריות
- מציאת קבצים חשופים

#### Nikto
```bash
nikto -h 192.168.1.100
```
- סריקת אבטחת אתרים
- זיהוי פגיעויות ידועות

#### Enum4linux
```bash
enum4linux 192.168.1.100
```
- חקירת Windows/Samba
- חילוץ משתמשים, shares

## 🔐 Anonymity Surfing

לחיפוי זהות בעת סריקה.

### תפריט אנונימיות

בחר `[a]` בתפריט הראשי:

```
[#] 📜 Anonimity Surfing Menu

[1] - Anonimity Surfing status
[2] - Anonimity Surfing start
[3] - Anonimity Surfing stop

[#] 📜 Network Manager Menu

[4] - ifconfig -a
[5] - ip a

[x] - Exit / Quit / Close
```

### שימוש

```bash
[a] → [2]  # Start anonsurf
# ...בצע סריקות...
[a] → [3]  # Stop anonsurf
```

## 📊 דוחות

### מבנה דוח

כל הדוחות נוצרים בפורמט Markdown:

```markdown
---
AnLoMinus Diablo PenTest Report ClientWebsite
#### Date: Mon Oct 28 22:37:00 IST 2025

---

# 📜 Menu

[a] - Anonymity Surfing
[1] - Planning and Scoping
[2] - Reconnaissance & Vulnerability Assessment
[3] - Gaining Access & Maintaining Access
[4] - Covering tracks
[5] - Analysis & Reporting

---

# [1] - Planning and Scoping
### Planning Log 192.168.1.100:

---

# [2] - Reconnaissance & Vulnerability Assessment
### masscan Scan Log 192.168.1.100:
[scan output]

### nmap Scan Log 192.168.1.100:
[scan output]
```

### עיבוד דוחות

#### המרה ל-PDF
```bash
# עם pandoc
pandoc ClientWebsite-Diablo-Log.md -o ClientWebsite-Report.pdf

# או GitHub Flavored Markdown
# העלה ל-GitHub וצפה
```

#### עיבוד נוסף
```bash
# צירוף דוחות
cat *-Diablo-Log.md > Combined-Report.md

# חיפוש מידע רגיש
grep -i "password\|secret\|key" *-Diablo-Log.md
```

## 💡 טיפים מתקדמים

### עבודה עם מטרות מרובות

```bash
# תיקייה ייעודית לכל פרויקט
mkdir -p ~/pentest-reports
cd ~/pentest-reports

# הפעל Diablo
./Diablo
# [p] → define project → perform scans
```

### אוטומציה חלקית

```bash
#!/bin/bash
# quick-scan.sh

echo "Target IP?"
read TARGET

# Edit Diablo script temporarily
# Or use expect for automation
```

### אינטגרציה עם כלים אחרים

#### Burp Suite
```bash
# Export targets from Diablo report
grep -E "^http://\|^https://" ClientWebsite-Diablo-Log.md > targets.txt

# Import to Burp
```

#### Metasploit
```bash
# Find vulnerabilities
grep -i "vulnerability\|CVE" ClientWebsite-Diablo-Log.md
```

### סקריפטים מותאמים

#### סריקה קלה
```bash
# light-scan.sh
echo "Target?"
read TARGET
echo "Running light scan on $TARGET..."
nmap -sV -p 80,443,22,21 $TARGET
dig $TARGET all
```

#### סריקה עמוקה
```bash
# deep-scan.sh
# הפעל את כל הבדיקות ב-Diablo
# תהליך ארוך אבל מקיף
```

## ⚠️ מומלץ לזכור

### לפני סריקה
- ✅ קבל הרשאה מפורשת
- ✅ ודא שהמטרה שייכת לך/לקוח
- ✅ הגדר שעוני timeout
- ✅ בדוק תצורת Firewall

### במהלך סריקה
- ⏱️ תיזמם נכון - חלק מהסריקות ארוכות
- 📊 שמור פלט ביניים
- ⚠️ היזהר משימוש במשאבים

### אחרי סריקה
- 📝 סקור את הדוח
- 🔒 החסר מידע רגיש
- 📤 שתף רק עם מי שצריך
- 🗑️ הסר דוחות ישנים

## 🆘 פתרון בעיות

### סריקות לא פועלות
```bash
# בדוק כלים מותקנים
which nmap dig masscan

# בדוק הרשאות
sudo nmap -sV target

# בדוק רשת
ping target
```

### דוח גדול מדי
```bash
# סריקות בסיסיות בלבד
# סנן output
nmap target 2>&1 | grep -v "Nmap scan report"
```

### עדכון כלים
```bash
# Kali Linux
sudo apt update && sudo apt upgrade -y

# macOS
brew update && brew upgrade
```

## 📚 משאבים נוספים

- [Getting Started](./GETTING_STARTED.md)
- [Architecture](./ARCHITECTURE.md)
- [FAQ](./FAQ.md)
- [Best Practices](./BEST_PRACTICES.md)

---

**שימוש באחריות ועשייה קודשת** 🔐

