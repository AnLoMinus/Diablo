> בס״ד

# 🏗️ Architecture

מסמך זה מתאר את הארכיטקטורה הכללית של Diablo ואת החלטות התכנון.

## 📐 סקירה כללית

Diablo הוא כלי PenTesting מבוסס Bash שמארגן תהליכי בדיקות חדירה בצורה מובנית ומפיקה דוחות מפורטים בפורמט Markdown.

## 🗂️ מבנה הקוד

```
Diablo/
├── Diablo                    # סקריפט ראשי
├── README.md                 # מסמך עיקרי
├── CONTRIBUTING.md           # מדריך תרומה
├── SECURITY.md               # מדיניות אבטחה
├── CODE_OF_CONDUCT.md        # קוד התנהגות
├── .github/                  # הגדרות GitHub
│   ├── ISSUE_TEMPLATE/
│   ├── workflows/
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                     # תיעוד
│   ├── INDEX.md
│   ├── GETTING_STARTED.md
│   └── ARCHITECTURE.md
└── assets/                   # משאבים
```

## 🔄 זרימת עבודה (Workflow)

### 1️⃣ אתחול (Initialization)
```
System Check → Package Manager Detection → Color Setup
```

### 2️⃣ תפריט ראשי (Main Menu)
```
Target Status Display → Menu Options → User Selection
```

### 3️⃣ תהליכי PenTest

#### Planning & Scoping
```
User Input → Target Variables → Report File Setup → File Header Creation
```

#### Reconnaissance
```
Individual Scan Tools → Output Capture → Markdown Report Append
```

## 🧩 רכיבים מרכזיים

### DiabloLogo1()
- תצוגת לוגו ASCII
- עיצוב חזותי

### DiabloColors()
- הגדרת צבעי טרמינל
- תמיכה בריבוי פלטפורמות

### TargetStatus()
- ניהול מצב יעד
- משתני יעד:
  - `targetIP`
  - `targetDns`
  - `targetNAME`
  - `targetEmail`
  - `targetPhone`

### MainMenu()
- לולאת תפריט ראשית
- רישות בקשות משתמש

### AnonMainMenu()
- תפריט אנונימיות
- ניהול anonsurf

## 🔧 כלי סריקה

### Network Analysis
- **arp** - טבלת ARP
- **traceroute** - מסלול IP
- **ping** - בדיקת שירותיות
- **masscan** - סריקת פורטים מהירה

### Port Scanning
- **nmap** - סריקת פורטים מפורטת
  ```
  nmap -sV -sC -O -p- $targetIP
  ```

### DNS Enumeration
- **dig** - בירורי DNS
- **nslookup** - בדיקות DNS
- **whois** - מידע WHOIS
- **dnsenum** - חילוץ תת-דומיינים
- **fierce** - סריקת DNS אגרסיבית
- **dnsrecon** - חקירת DNS מקיפה

### Web Enumeration
- **dirb** - גילוי דירקטוריות
  ```
  dirb http://$targetDNS
  ```
- **nikto** - סריקת אבטחת אתרים

### OSINT
- **enum4linux** - חילוץ מידע Windows/Samba

## 📊 מערכת דוחות

### פורמט דוח
```markdown
---
AnLoMinus Diablo PenTest Report [Project Name]
#### Date: [Timestamp]

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
### Planning Log [Target IP]:

---

# [2] - Reconnaissance & Vulnerability Assessment
### [Scan Type] Scan Log [Target]:
[Scan Output]
```

## 🔐 מודל אבטחה

### הרשאות מערכת
- אין צורך בהרשאות root ברוב המקרים
- סריקות מסוימות עשויות לדרוש הרשאות מיוחדות

### ניהול נתונים רגישים
- לא נשמרים credentials
- נתונים רגישים רק בקובץ דוח מקומי

## 🚀 הרחבה עתידית

### תכונות מתוכננות
- [ ] Gaining Access & Maintaining Access
- [ ] Covering tracks
- [ ] Analysis & Reporting
- [ ] ממשק Web UI
- [ ] API לבדיקות אוטומטיות
- [ ] תמיכה ב-Containers

## 📝 Best Practices

### כתיבת קוד
- שימוש בצבעים עקביים
- הודעות שגיאה ברורות
- עיצוב ASCII מעוצב

### ביצועים
- סריקות מקבילות (עתידי)
- ניהול זיכרון יעיל
- הגבלת משאבי רשת

---

**מומלץ לקרוא:** [Security Model](./SECURITY_MODEL.md)

