> בס״ד

# 🤝 מדריך תרומה ל-Diablo

תודה על העניין שלך בתרומה ל-Diablo! מסמך זה מתאר כיצד תוכל לתרום לפרויקט.

## 📋 תוכן עניינים

- [קוד התנהגות](#קוד-התנהגות)
- [איך לתרום?](#איך-לתרום)
- [תהליך פיתוח](#תהליך-פיתוח)
- [הנחיות קוד](#הנחיות-קוד)
- [פתיחת Issues](#פתיחת-issues)
- [יצירת Pull Requests](#יצירת-pull-requests)

## 👥 קוד התנהגות

פרויקט זה מציית ל-[CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md). על ידי השתתפות, אתה מצפה לקוד התנהגות זה.

## 🚀 איך לתרום?

### דרכים לתרום

1. **🐛 דיווח על באגים** - פתח Issues לבעיות שזיהית
2. **💡 הצעת תכונות** - שתף רעיונות לשיפור
3. **📚 שיפור תיעוד** - עזור לנו לשפר את המדריכים
4. **💻 כתיבת קוד** - תיקן באגים או הוסף תכונות
5. **✅ ביקורת קוד** - בדוק Pull Requests של אחרים
6. **🌍 תרגום** - תרגם תיעוד לשפות אחרות

## 🔧 תהליך פיתוח

### 1️⃣ Fork והכנה

```bash
# Fork את הפרויקט ב-GitHub
# Clone המקומי
git clone https://github.com/[YOUR_USERNAME]/Diablo.git
cd Diablo

# הוסף remote של המקור
git remote add upstream https://github.com/Anlominus/Diablo.git
```

### 2️⃣ יצירת Branch

```bash
# צור branch חדש לתכונה/תיקון
git checkout -b feature/your-feature-name
# או
git checkout -b fix/your-bug-fix
```

### 3️⃣ כתיבת קוד

- עקוב אחר [הנחיות הקוד](#הנחיות-קוד)
- בדוק את הקוד שלך
- כתוב בדיקות אם רלוונטי

### 4️⃣ Commit

```bash
# עשה commit עם הודעה ברורה
git add .
git commit -m "feat: add new scanning feature"
# או
git commit -m "fix: resolve syntax error in menu loop"
```

**Conventional Commits:**
- `feat:` - תכונה חדשה
- `fix:` - תיקון באג
- `docs:` - שינוי תיעוד
- `style:` - שינוי פורמט
- `refactor:` - שינוי קוד ללא שינוי פונקציונליות
- `test:` - הוספת בדיקות
- `chore:` - משימות תחזוקה

### 5️⃣ Push ו-Pull Request

```bash
# Push את ה-branch שלך
git push origin feature/your-feature-name

# לאחר מכן פתח Pull Request ב-GitHub
```

## 💻 הנחיות קוד

### סגנון Bash

```bash
# ✅ טוב
function my_function() {
    local var_name="value"
    if [ condition ]; then
        echo "Success"
    fi
}

# ❌ לא טוב
my_function(){
local var=value
if [ condition ]
then
echo Success
fi
}
```

### כללים

1. **השתמש במיקרו מקומי** - `local` ל-variables פנימיים
2. **צבעים עקביים** - שימוש בפונקציית `DiabloColors()`
3. **הודעות ברורות** - הודעות שגיאה בעברית או אנגלית ברורה
4. **הערות קוד** - הסבר לוגיקה מורכבת
5. **זיהוי מערכת** - בדוק package manager נכון

### דוגמה מלאה

```bash
#!/bin/bash
# Name: Feature Name
# Description: What this feature does

###############################################
# Example function with best practices
###############################################
run_example_scan() {
    local target_ip="$1"
    
    # Check if target is provided
    if [ -z "$target_ip" ]; then
        echo "${BRed}[!]${Color_Off} Target IP is required"
        return 1
    fi
    
    echo "${BGreen}[+]${Color_Off} Running scan on $target_ip"
    # ... actual scan command
    
    return 0
}
```

## 🐛 פתיחת Issues

### דיווח על באגים

כאשר מדווחים על באג, כלול:

1. **תיאור** - מה הבעיה?
2. **שחזור** - צעדים לשחזור
3. **התנהגות צפויה** - מה היה אמור לקרות?
4. **התנהגות בפועל** - מה קרה בפועל?
5. **סביבה** - OS, גרסה, כלים מותקנים
6. **צילומי מסך** - אם רלוונטי

השתמש בתבנית [BUG_REPORT.md](.github/ISSUE_TEMPLATE/bug_report.md).

### בקשת תכונות

כאשר מבקשים תכונה:

1. **בעיה** - איזה בעיה זה פותר?
2. **פתרון** - מה אתה מציע?
3. **חלופות** - מה שקלת?
4. **דוגמאות** - דוגמאות מ-tools אחרים?

השתמש בתבנית [FEATURE_REQUEST.md](.github/ISSUE_TEMPLATE/feature_request.md).

## 🔄 יצירת Pull Requests

### הכנה

```bash
# ודא שאתה מעודכן עם main
git checkout main
git pull upstream main

# Merge את השינויים שלך
git checkout feature/your-feature-name
git rebase main  # או merge
```

### תיאור ה-PR

כתוב תיאור ברור הכולל:

1. **מה** - מה השינוי?
2. **למה** - למה זה נחוץ?
3. **איך** - איך זה עובד?
4. **בדיקות** - איך לבדוק?

השתמש בתבנית [PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md).

### ביקורת קוד

- נענה לפידבק במהירות
- ערוך על פי הערות המבקרים
- שאל אם משהו לא ברור

## 📝 שיפור תיעוד

עזרה בתיעוד מוערכת מאוד!

### קבצים רלוונטיים

- `README.md` - מסמך עיקרי
- `docs/` - כל התיעוד
- `CONTRIBUTING.md` - זה
- תגובות בקוד Bash

### טיפים

- השתמש בעברית או אנגלית ברורה
- כלול דוגמאות
- בדוק קישורים
- עקוב אחר פורמט Markdown

## ✅ בדיקות

לפני PR:

```bash
# בדיקת syntax
bash -n Diablo

# בדיקת styles
shellcheck Diablo

# ריץ manual tests
./Diablo
# נסה את התכונה החדשה
```

## 🏆 הכרה

תורמים פעילים יוכרו ב:
- `CONTRIBUTORS.md` (עתידי)
- Release notes
- README (אם רלוונטי)

## ❓ שאלות?

- פתח [Issue](https://github.com/Anlominus/Diablo/issues)
- ודא תבנית Issue מתאימה
- השתמש בתוויות נכונות

---

**תודה על התרומה שלך! יחד נבנה כלי PenTesting מעולה** 🚀

---

> בס״ד - מגדל בסייעתא דשמיא

