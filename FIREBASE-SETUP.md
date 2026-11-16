# חיבור מערכת ניהול BARBER PRO ל-Firebase

האתר מוכן בקוד, אבל לא ניתן להתחבר עד שמגדירים פרויקט Firebase ומפעילים את כללי האבטחה.

1. פותחים https://console.firebase.google.com/ ויוצרים פרויקט.
2. מוסיפים Web App ומעתיקים את הערכים הציבוריים של Firebase לקובץ firebase-config.js. אין לשים סיסמאות או מפתחות שירות בקוד.
3. Authentication > Sign-in method > Email/Password > Enable.
4. Authentication > Users > Add user. יוצרים את חשבון בעל העסק, עם אימייל וסיסמה חזקה. אין לשלוח את הסיסמה בצ'אט.
5. מעתיקים את ה-UID של המשתמש (לא את הסיסמה) ומחליפים את REPLACE_WITH_OWNER_UID בקובץ firestore.rules.
6. Firestore Database > Create database, בוחרים אזור ויוצרים מסד נתונים.
7. מדביקים את תוכן firestore.rules בלשונית Rules של Firestore ולוחצים Publish. אין להשאיר את מסד הנתונים במצב בדיקה פתוח.
8. Authentication > Settings > Authorized domains: מוסיפים eva726.github.io אם אינו מופיע.
9. נכנסים ל-admin.html, מתחברים עם אימייל וסיסמה, עורכים ושומרים. בפעם הראשונה, תוכן האתר הקיים ייטען מקובץ site.json; לחיצה על שמירה תיצור את מסמך Firestore הראשון.

אבטחה: אין רישום עצמי; רק מנהל Firebase מוסיף משתמשים. הרשאת כתיבה נקבעת לפי UID בכללי Firestore ולא רק בדפדפן. אין להכניס סיסמאות בקוד GitHub. שימו לב שהגדרת חשבון מנהל נעשית לכל אתר בנפרד.
