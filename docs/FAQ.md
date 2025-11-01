> בס״ד

# ❓ שאלות נפוצות (FAQ)

## 🤔 שאלות כלליות

### מה זה Diablo?
Diablo הוא כלי PenTesting ו-Hacking מדויק שמיועד לביצוע בדיקות חדירה מסודרות ויצירת דוחות מפורטים בפורמט Markdown.

### מי יכול להשתמש ב-Diablo?
כל אחד, אבל חשוב לזכור:
- ✅ השתמש רק על מטרות שרשת לצאת
- ✅ ציית לכל חוק מקומי
- ❌ אל תבצע התקפות בלתי חוקיות

### האם Diablo חינמי?
כן! Diablo הוא פרויקט Open Source תחת רישיון MIT.

## 🔧 שאלות טכניות

### באילו מערכות הפעלה Diablo עובד?
- Linux (Ubuntu, Debian, Kali Linux)
- macOS (10.14+)
- Termux (Android)

### אילו כלים נדרשים?
```bash
masscan, nmap, dig, nslookup, whois, nikto, enum4linux, dirb, anonsurf
```

### איך מתקינים את כל כלי התלויות?
**Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install masscan nmap dnsutils whois nikto enum4linux dirb
```

**macOS:**
```bash
brew install masscan nmap
# יתר הכלים בדרך כלל מותקנים מראש
```

**Kali Linux:**
```bash
sudo apt-get update && sudo apt-get install -y masscan nmap dnsutils nikto dirb
```

### למה צריך תלות ב-HacKingPro?
קטע הקוד הבא:
```bash
. ../HacKingPro/HacKingPro-Parts/Main/HacKingPro-Planning
```
מנסה לטעון פונקציות מתוך פרויקט HacKingPro שקשור. אם אין לך את HacKingPro, תוכל להסיר או להחליף את השורה הזו.

## 🐛 פתרון בעיות

### "Permission denied"
```bash
chmod +x Diablo
./Diablo
```

### "command not found: masscan"
התקן את masscan:
```bash
# Ubuntu/Debian
sudo apt-get install masscan

# macOS
brew install masscan
```

### הסריקות לא רצות
וודא שהכתובת IP שלך נכונה ושהרשת זמינה:
```bash
ping [your-target-ip]
```

### הדוח לא נוצר
וודא שיש הרשאות כתיבה בתיקייה הנוכחית:
```bash
ls -la
mkdir -p reports
```

## 📊 שאלות על דוחות

### איפה נשמרים הדוחות?
בתיקייה שבה הפעלת את Diablo:
```
[Project-Name]-Diablo-Log.md
```

### מה הפורמט של הדוחות?
Markdown - ניתן לצפות בכל עורך טקסט או ב-GitHub.

### איך מייצאים לדוחות אחרים?
Diablo יוצר Markdown. תוכל להמיר ל-PDF, HTML וכדומה באמצעות כלים כמו:
- pandoc
- Markdown-to-PDF
- GitHub Pages

## 🔐 שאלות אבטחה

### האם Diablo אוסף נתונים?
לא. הכלי פועל באופן מקומי ולא שולח נתונים החוצה.

### האם אנונימי לי שישתמשו ב-Diablo לבדיקות שלי?
אם מישהו משתמש בכלי הזה לבדיקת הרשת שלך בלי הרשאה, זה בלתי חוקי. זה לא עובדה שמקורה ב-Diablo עצמו.

### איך משתמשים באנונימיות?
אם יש לך anonsurf:
```bash
./Diablo
# בחר [a] → Anonymity Surfing
# [2] - Anonimity Surfing start
```

## 🚀 תכונות

### מה זה "Planning and Scoping"?
זה שלב ההתחלה שבו מוגדרים מטרות הבדיקה, IP, שם פרויקט, domain וכו'.

### מה זה "Reconnaissance & Vulnerability Assessment"?
סריקות נרחבות לאיסוף מידע וזיהוי פגיעויות:
- חילוץ DNS
- סריקת פורטים
- סריקת שירותי Web
- חקירת רשת

### מתי יתווספו תכונות 3, 4, 5?
גישת Gaining Access, Covering tracks ו-Analysis & Reporting מוגדרות כעת כמקומות-מצייצים (placeholders) והן מתוכננות להתפתח בחליפות עתידיות.

## 🤝 תרומה

### איך תורמים?
ראה את [CONTRIBUTING.md](../CONTRIBUTING.md) לפרטים מלאים.

### איך מדווחים על באג?
פתח Issue חדש ב-GitHub עם תגיף "bug".

### איך מבקשים תכונה?
פתח Issue חדש עם תגיף "enhancement".

## 📞 קישורים והפניות

- GitHub: https://github.com/Anlominus/Diablo
- Issues: https://github.com/Anlominus/Diablo/issues
- Discussions: https://github.com/Anlominus/Diablo/discussions

---

**שאלות נוספות?** פתח Issue ב-GitHub!

