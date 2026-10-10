ماكزوني - نظام إدارة المخزون والمبيعات
=========================================

الملفات:
  index.html       التطبيق كامل
  manifest.json    إعدادات الـ PWA
  sw.js            الـ Service Worker
  icon-192.png / icon-512.png   أيقونات التطبيق
  firestore.rules  قواعد الأمان (لازم تعدّل الـ UID)
  firebase.json    إعدادات النشر على Firebase Hosting

خطوات التشغيل (مرة واحدة):
  1) Firebase Console > Authentication > Sign-in method > فعّل Email/Password
  2) Authentication > Users > Add user (إيميلك + باسورد) ثم انسخ الـ User UID
  3) افتح firestore.rules وبدّل PUT_YOUR_UID_HERE بالـ UID
     (لو عندك موظفين أضف UID كل واحد داخل القائمة بفاصلة)
  4) انشر القواعد:   Firestore Database > Rules > الصق المحتوى > Publish
     أو من الطرفية:  firebase deploy --only firestore:rules
  5) ارفع التطبيق:   firebase deploy --only hosting
     (أو أي استضافة ملفات ثابتة، بشرط HTTPS)
  6) افتح الرابط، سجّل دخول، وابدأ بإضافة الأصناف

ملاحظات:
  - تأكد أن apiKey في firebaseConfig داخل index.html منسوخ كامل من إعدادات المشروع.
  - من Authentication > Settings يفضّل إيقاف تسجيل المستخدمين الجدد إن لم تحتجه.
  - البيع والمشتريات يحتاجان اتصالاً بالإنترنت (Transactions).
