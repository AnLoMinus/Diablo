> בס״ד

<div align="center">

<h2 align="center"><a href="https://github.com/Anlominus">⚜️ AnLoMinus ⚜️</a></h2>

<img align="center" width="100" src="https://user-images.githubusercontent.com/51442719/172729066-1293d382-4a31-4f03-8c23-ab0ea5f611a0.png">

⫷ [**`HacKingPro`**](https://github.com/Anlominus/HacKingPro) ⫸
<br>
⫷ [**`TryHackMe`**](https://github.com/Anlominus/TryHackMe) | [**`KoTH`**](https://github.com/Anlominus/TryHackMe/tree/main/King%20of%20the%20Hill/KoTH) ⫸
<br>
⫷ [**`Privilege-Escalation`**](https://github.com/Anlominus/Privilege-Escalation)⫸
<br>
⫷ [**`ScanPro`**](https://github.com/Anlominus/ScanPro) | [**`Linfo`**](https://github.com/Anlominus/Linfo) | [**`Diablo`**](https://github.com/Anlominus/Diablo) ⫸
<br>
⫷ [**`Offensive-Security`**](https://github.com/Anlominus/Offensive-Security) | [**`PenTest`**](https://github.com/Anlominus/PenTest) ⫸
<br>
⫷ [**`Goals`**](https://github.com/Anlominus/Goals) | [**`Studies`**](https://github.com/Anlominus/Studies) | [**`HacKing`**](https://github.com/Anlominus/HacKing) | [**`AnyTeam`**](https://github.com/Anlominus/AnyTeam) ⫸

</div>

---

<div align="center">

# [Diablo](https://github.com/Anlominus/Diablo) 🎯

<a href=""><br><img title="Made in ISRAEL" src="https://img.shields.io/badge/MADE%20IN-ISRAEL-blue?style=for-the-badge"></a>

**Diablo ~ Pentesting / Hacking & Reporting Tool**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/Anlominus/Diablo/graphs/commit-activity)
[![GitHub issues](https://img.shields.io/github/issues/Anlominus/Diablo)](https://github.com/Anlominus/Diablo/issues)
[![GitHub stars](https://img.shields.io/github/stars/Anlominus/Diablo)](https://github.com/Anlominus/Diablo/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Anlominus/Diablo)](https://github.com/Anlominus/Diablo/network)

```shell
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo; chmod 777 Diablo; ./Diablo
```

<img width="801" alt="Diablo Preview" src="https://user-images.githubusercontent.com/51442719/170010336-39176f7e-b5dc-4f31-81ca-4b4144e6938c.png">

**🔴 השתמש באחריות - רק בבדיקות מאושרות!**

</div>

---

## 📋 תוכן עניינים

- [📖 אודות](#-אודות)
- [✨ תכונות](#-תכונות)
- [🚀 התקנה מהירה](#-התקנה-מהירה)
- [📚 תיעוד](#-תיעוד)
- [🎯 שימוש](#-שימוש)
- [🤝 תרומה](#-תרומה)
- [🔐 אבטחה](#-אבטחה)
- [📜 Roadmap](#-roadmap)
- [🙏 קרדיטים](#-קרדיטים)

## 📖 אודות

**Diablo** הוא כלי PenTesting ו-Hacking מדויק שמיועד לביצוע בדיקות חדירה מובנות ויצירת דוחות מפורטים בפורמט Markdown.

### 🎯 מטרות
- **אוטומציה** של תהליכי Reconnaissance
- **ארגון** של כלי PenTest רבים בממשק אחד
- **דוחות** אוטומטיים בפורמט Markdown
- **פשטות** בשימוש ובהוראה

---

## ✨ תכונות

### 🎯 תפריט ראשי

- ✅ **[a] - Anonymity Surfing**
  - Anonimity Surfing status/start/stop
  - Network Manager Menu (ifconfig/ip a)
  
- ✅ **[1] - Planning and Scoping**
  - הגדרת Target IP
  - הגדרת שם הפרויקט
  - הגדרת Domain Name
  - יצירת קובץ דוח ראשוני

- ✅ **[2] - Reconnaissance & Vulnerability Assessment**
  - **Network Analysis:** arp, traceroute, ping, masscan
  - **Port Scanning:** nmap (-sV -sC -O -p-)
  - **DNS Enumeration:** dig, nslookup, whois, dnsenum, fierce, dnsrecon
  - **Web Enumeration:** dirb, nikto
  - **OSINT:** enum4linux

- 🔜 **[3] - Gaining Access & Maintaining Access** (בפיתוח)
- 🔜 **[4] - Covering tracks** (בפיתוח)
- 🔜 **[5] - Analysis & Reporting** (בפיתוח)

### 🔧 תכונות טכניות

- ✅ תמיכה במספר מערכות הפעלה (Linux, macOS, Termux)
- ✅ זיהוי אוטומטי של Package Manager
- ✅ מערכת צבעים עשירה ו-UI מעוצב
- ✅ דוחות אוטומטיים בפורמט Markdown
- ✅ מבנה RepoCraft מלא

---

## 🚀 התקנה מהירה

### Linux / macOS
```bash
# הורד והפעל
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo
chmod +x Diablo
./Diablo
```

### Termux (Android)
```bash
wget https://raw.githubusercontent.com/Anlominus/Diablo/main/Diablo
chmod +x Diablo
./Diablo
```

### דרישות
```bash
# Ubuntu/Debian
sudo apt-get install masscan nmap dnsutils whois nikto enum4linux dirb

# macOS
brew install masscan nmap
```

---

## 📚 תיעוד

📖 **תיעוד מלא** זמין ב-[docs/](./docs/INDEX.md)

- [🚀 Getting Started](./docs/GETTING_STARTED.md)
- [🏗️ Architecture](./docs/ARCHITECTURE.md)
- [❓ FAQ](./docs/FAQ.md)

---

## 🎯 שימוש

### דוגמה בסיסית

```bash
./Diablo

# בתפריט:
# [p] → Planning and Scoping
#   1. הזן IP: 192.168.1.1
#   2. הזן שם פרויקט: TestProject
#   3. הזן Domain: example.com

# [2] → Reconnaissance & Vulnerability Assessment
#   כל הסריקות יתבצעו אוטומטית
#   דוח ייווצר: TestProject-Diablo-Log.md
```

### דוגמה לאנונימיות
```bash
# בתפריט בחר [a]
[a] → Anonymity Surfing
[2] → Start anonsurf
```

---

## 🤝 תרומה

תרומות מוערכות מאוד! ראה את [CONTRIBUTING.md](./CONTRIBUTING.md) לפרטים.

### איך לתרום?
1. 🍴 Fork את הפרויקט
2. 🌿 צור branch חדש (`git checkout -b feature/AmazingFeature`)
3. ✅ עשה commit (`git commit -m 'Add AmazingFeature'`)
4. 📤 Push (`git push origin feature/AmazingFeature`)
5. 🔄 פתח Pull Request

---

## 🔐 אבטחה

⚠️ **חשוב: שימוש אתי וחוקי בלבד!**

- 🔴 השתמש **רק** בבדיקות מאושרות
- 🔴 ציית לכל חוק מקומי
- ✅ דווח על פרצות אבטחה: ראה [SECURITY.md](./SECURITY.md)

---

## 📜 Roadmap

### ✅ הושלם
- [x] Planning and Scoping
- [x] Reconnaissance & Vulnerability Assessment
- [x] Anonymity Surfing
- [x] מבנה RepoCraft מלא
- [x] CI/CD ו-workflows
- [x] תיעוד מקיף

### 🔄 בפיתוח
- [ ] Gaining Access & Maintaining Access
- [ ] Covering tracks
- [ ] Analysis & Reporting
- [ ] תיקון תלות ב-HacKingPro
- [ ] ממשק Web UI

> למפת דרכים מפורטת וסעיפים מעשיים לכל פרק, עיין ב-[🌟 המשך Roadmap](./docs/ROADMAP_NEXT_STEPS.md).

---

## 🙏 קרדיטים

### יוצר
- **Moshe Leon Yaakubov (AnLoMinus)** - [GitHub](https://github.com/Anlominus)

### מקורות השראה
- [RapidScan](https://github.com/skavngr/rapidscan)
- [Reconnoitre](https://github.com/codingo/Reconnoitre)
- [OSCP Report Template](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)
- [HacKingPro](https://github.com/Anlominus/HacKingPro)
- [PenTest](https://github.com/Anlominus/PenTest)

### RepoCraft Framework
בנייה על פי [RepoCraft](https://github.com/AnLoMinus/RepoCraft/) framework

---

## 📊 סטטוס הפרויקט

![GitHub Repo stars](https://img.shields.io/github/stars/Anlominus/Diablo?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/Anlominus/Diablo?style=social)

![Repobeats analytics](https://repobeats.axiom.co/api/embed/dd90ce889645a0528ddedbb71d7310ab3ec30393.svg "Repobeats analytics image")

---

## 📄 רישיון

פרויקט זה מפורסם תחת [MIT License](./LICENSE)

---

## 🌐 קישורים

- 🌍 [GitHub Repository](https://github.com/Anlominus/Diablo)
- 🐛 [Report Bugs](https://github.com/Anlominus/Diablo/issues)
- 💡 [Request Features](https://github.com/Anlominus/Diablo/issues)
- 📖 [Documentation](./docs/)
- 🤝 [Contributing](./CONTRIBUTING.md)
- ⚠️ [Purification Grid](https://aistudio.google.com/app/prompts?state=%7B%22ids%22:%5B%221a_XBsk_mXP_0iSBqYimXo7HbavNZ-uJW%22%5D,%22action%22:%22open%22,%22userId%22:%22103930013484441813523%22,%22resourceKeys%22:%7B%7D%7D&usp=sharing
)

---

<div align="center">

**תודה לשימוש ב-Diablo!** 🎯

### ⚠️ אזכור חשוב
**שימוש באחריות בלבד - רק בבדיקות מאושרות!**

---

> בס״ד - מגדל בסייעתא דשמיא

**נוצר עם ❤️ בישראל** 🇮🇱

![Made with Love](https://img.shields.io/badge/Made%20With-Love-red)

</div>

