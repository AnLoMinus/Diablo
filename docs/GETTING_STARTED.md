> בס״ד

# 🚀 Getting Started with Diablo

ברוכים הבאים ל-Diablo! מדריך זה יעזור לך להתחיל להשתמש בכלי PenTesting המדויק הזה תוך דקות.

## 📋 דרישות מוקדמות

### מערכת הפעלה נתמכת
- **Linux** (Ubuntu, Debian, Kali Linux, etc.)
- **macOS** (10.14+)
- **Termux** (Android)

### כלים נדרשים
```bash
# כלים בסיסיים
- masscan
- nmap
- dig, nslookup
- whois
- nikto
- enum4linux
- dirb
- anonsurf (לפונקציית אנונימיות)

# בחלק מהמערכות
- traceroute
- arp
- ping
```

## 🔧 התקנה מהירה

### Linux / macOS
```bash
# הורד את הקובץ
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo

# הפוך לקובץ הרצה
chmod +x Diablo

# הפעל
./Diablo
```

### Termux (Android)
```bash
# בטרמינל Termux
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo
chmod +x Diablo
./Diablo
```

## 🎯 שימוש בסיסי

### 1️⃣ הפעלה ראשונית
```bash
./Diablo
```

### 2️⃣ תכנון וטווח (Planning and Scoping)
בחר אפשרות `[p]` או `[P]` או הקלד `plan` בתפריט הראשי:
- הזן את כתובת ה-IP של המטרה
- הזן את שם הפרויקט
- הזן את ה-Domain של המטרה

### 3️⃣ הגדרת יעד (Target Setup)
התפריט יכין עבורך קובץ דוח Markdown:
```
${targetNAME}-Diablo-Log.md
```

### 4️⃣ ביצוע סריקות
בחר אפשרות `[2]` לביצוע Reconnaissance:
- Arp Scan
- TraceRoute Scan
- Ping Scan
- Nmap Scan
- Dig Scan
- Nslookup Scan
- WhoIs Scan
- Dirb Scan
- ועוד...

## 📊 דוגמאות שימוש

### דוגמה בסיסית
```bash
# הפעלת הכלי
./Diablo

# בתפריט:
# [p] → Planning and Scoping
# 1. הזן IP: 192.168.1.1
# 2. הזן שם פרויקט: TestProject
# 3. הזן Domain: example.com

# [2] → Reconnaissance & Vulnerability Assessment
# כל הסריקות יתבצעו וייכתבו ל-TestProject-Diablo-Log.md
```

## 🔐 אנונימיות

אם יש לך anonsurf מותקן, תוכל להשתמש בתכונות אנונימיות:
```bash
# בתפריט בחר [a]
[a] → Anonymity Surfing

# תפריט משני:
# [1] - Anonimity Surfing status
# [2] - Anonimity Surfing start
# [3] - Anonimity Surfing stop
```

## 📝 יצירת דוחות

לאחר כל סריקה, דוח מפורט נוצר בפורמט Markdown:
```markdown
# AnLoMinus Diablo PenTest Report TestProject
#### Date: [תאריך]

---

# [1] - Planning and Scoping
### Planning Log 192.168.1.1:

---

# [2] - Reconnaissance & Vulnerability Assessment
### masscan Scan Log 192.168.1.1:
### enum4linux Scan Log 192.168.1.1:
### nikto Scan Log 192.168.1.1:
### Arp Scan Log 192.168.1.1:
### ... ועוד
```

## ⚠️ שימוש אתי

**חשוב מאוד:**
- השתמש ב-Diablo רק בהרשאה מפורשת
- עבוד רק על מטרות שבבעלותך או שקיבלת הרשאה לבדוק
- שמור על כללי האתיקה והחוק המקומי

## 🆘 בעיות נפוצות

### בעיה: "command not found: masscan"
**פתרון:**
```bash
# Ubuntu/Debian
sudo apt-get install masscan

# macOS
brew install masscan

# Kali Linux (בדרך כלל מותקן מראש)
sudo apt-get update && sudo apt-get install masscan
```

### בעיה: "Permission denied"
**פתרון:**
```bash
chmod +x Diablo
```

### בעיה: תלות ב-HacKingPro
**פתרון:**
הכלי מנסה לטעון קובץ מ-HacKingPro. אם אין, ודא שהתיקייה הנכונה נמצאת בנתיב היחסי.

## 📚 המשך הלאה

עכשיו כשהכל עובד, תוכל לחקור:
- [📖 Usage Guide](./USAGE.md) - מדריך שימוש מתקדם
- [⭐ Features](./FEATURES.md) - כל התכונות
- [🔐 Best Practices](./BEST_PRACTICES.md) - שיטות עבודה מומלצות

---

**הערות:** אם נתקלת בבעיות, אנא דווח ב-[Issues](https://github.com/Anlominus/Diablo/issues)

