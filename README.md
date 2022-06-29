###@activities True
###@explicitHints true

## introduction@fullscreen
בפרויקט זה נכין  קוד לסמניית קסם שעוקבת אחרי הקריאה שלנו
[הנחיות בנייה](https://drive.google.com/file/d/1deYuFE6IoH5on1HUNhE0uOUUhGmyahkX/view?usp=sharing)
## Step 1 @fullscreen
הכינו שלושה משתנים:
משתנה  כוח מגנטי, משתנה ניקוד קריאה ומשתנה סיכום
השתמשו ב ``||variables: set magnetic force  ||``  ןהגדירו ערך ראשוני ל-0

```blocks
let magnetic_force = 0
let reading = 0
let total = 0

```
## Step 2
אפסו את המצפן
השתמשו ב: ``||input:calibrateCompass()||``

דוגמה
```blocks
input.calibrateCompass()

```
##step 3
מתחת לאתחול המצפן הוסיפו לבנה שמגדירה ערך כוח מגנטי לפי המצפן 
ובערך אבסולטי של חוזק המגנט
השתמשו ב:
``||Math:abs()||``

##~tutorialhint
רמז
```blocks
magnetic_force = Math.abs(input.magneticForce(Dimension.Strength))
```
## Step 4 
חברו הכל יחד
```blocks

let magnetic_force = 0
let reading = 0
let total = 0
input.calibrateCompass()
magnetic_force = Math.abs(input.magneticForce(Dimension.Strength))

```
## Step 5
הסמנייה שלנו תבדוק כמה זמן אנחנו קוראים לשם כך נשתמש בלולאת חזור תמיד
הכניסו לתוך לולאת החזור 
הכניסו  לבנת  "הראה מספר" 
השתמשו ב``||basic: showNumber()||`` והזינו ערך משתנה total
``||variable: total||`` 

##Step 6
נשתמש בשלושה תנאים כדי לבדוק האם הסמניה סגורה או פתוחה
התנאי הראשון בודק האם יש מגנט בסביבה
לשם כך צרו משתנה נוסף קראו לו "מגנט כאן" 
אם החוזק שלו גדול מ-100 סימן שיש משיכה או דחיה והסמניה סגורה
השתמשו בלבנת 
``||variables: set ||``  השתמשו ב ןהגדירו את הערך לתנאי 
``||logic: magnetic_force > 100||``
העזרו ברמז
```blocks
basic.showNumber(total)
magnet = magnetic_force > 100	
```
## step 7
בשלב הבא הקוד יבדוק האם הסמניה פתוחה[מצב קריאה]
ואם כן, כמה זמן היא פתוחה נשתמש הפעם בלבנת תנאים
``||logic: if true then  else||``

## Step 8
כתבו זאת בעצמכם:
כאשר נלחץ על כפתור  
 יופיע פרצוף עצוב והודעה "נא לקרוא" 
אחרת
משתנה נקוד + 1
   חצי שנייה השהייה
ותמונת "לב" 
העזרו ברמז
```blocks
if (input.buttonIsPressed(Button.A)) {
        basic.showIcon(IconNames.Sad)
        basic.showString("read")
    } else {
        reading += 1
        basic.pause(500)
        basic.showIcon(IconNames.Heart)
} 
```
## Step 9
התנאי האחרון מופיע בדיוק מתחת לתנאי הקודם
כאן הוסיפו לבנת ``||logic:if  true >  then||`` 
שבודקת האם סכום הנקודות גדול מ-600
זה אמור להראות כך
```blocks
if (reading  > 600) {
       
}
```
## Step 10
אם עברו יותר מ-5 דקות אז נוספת נקודה לסכום הכולל
השתמשו בלבנות המשתנה המתאים 
למשל: ``||variable:change ||``
עכשיו צריך גם לאפס את מדד הקריאה
הגדירו את משתנה הקריאה ל-0
```blocks
if (reading  > 600) {
        total += 1
        reading = 0
}
```
 @boardname@ הסתכלו בסימולציה  ובדקו מה קורה למשתנים בלחיצה על  כפתור A
## Step 14

 @boardname@ לחצו `|download|` כדי להעביר את הקוד ללוח המיקרו:ביט




> Open this page at [https://shelibenm.github.io/tutorial_reading-tag/](https://shelibenm.github.io/tutorial_reading-tag/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://makecode.microbit.org/](https://makecode.microbit.org/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/shelibenm/tutorial_reading-tag** and import

## Edit this project ![Build status badge](https://github.com/shelibenm/tutorial_reading-tag/workflows/MakeCode/badge.svg)

To edit this repository in MakeCode.

* open [https://makecode.microbit.org/](https://makecode.microbit.org/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/shelibenm/tutorial_reading-tag** and click import

## Blocks preview

This image shows the blocks code from the last commit in master.
This image may take a few minutes to refresh.

![A rendered view of the blocks](https://github.com/shelibenm/tutorial_reading-tag/raw/master/.github/makecode/blocks.png)

#### Metadata (used for search, rendering)

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
