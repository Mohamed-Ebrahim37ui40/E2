Ethmar PWA – تعليمات التشغيل والتثبيت
=====================================
الملفات المطلوبة (ارفعها بنفس الهيكل):
  index.html
  sw.js
  manifest.webmanifest
  icons/
    icon-192.png
    icon-512.png
    maskable-512.png
    apple-touch-icon.png
    favicon-32.png

مهم جداً: يجب أن يكون مجلد icons موجوداً ويحتوي على الأيقونات داخله.
لا ترفع الأيقونات في المجلد الجذر بدون مجلد icons.

1) الاستضافة (مرة واحدة – مطلوب https)
   - GitHub Pages: أنشئ مستودعًا، ارفع محتويات المجلد (وليس المجلد نفسه)،
     أي ارفع index.html و sw.js و manifest.webmanifest ومجلد icons معاً في جذر المستودع.
     ثم Settings > Pages > Deploy from a branch > main / root.
     الرابط يكون مثل: https://USERNAME.github.io/REPO/
   - أو أي استضافة https (Netlify / Cloudflare Pages / سيرفرك).
   - للتجربة على جهازك: python -m http.server 8000  ثم افتح http://localhost:8000

2) التثبيت (بعد فتح الرابط مرة واحدة بالإنترنت)
   - Android / Chrome / Edge / Windows / Linux / ChromeOS:
     زر 📲 في أعلى التطبيق، أو أيقونة التثبيت في شريط العنوان (شكل شاشة مع سهم).
     إذا لم تظهر: انتظر 30 ثانية + انقر في الصفحة، أو من قائمة المتصفح (⋮) → تثبيت التطبيق / Install this site as an app.
   - iPhone / iPad (Safari): زر المشاركة ثم "إضافة إلى الشاشة الرئيسية".
   - Mac: Chrome/Edge: أيقونة التثبيت في شريط العنوان. Safari 17+: ملف > إضافة إلى Dock.

3) العمل بدون إنترنت
   بعد أول فتح يتم حفظ كل شيء على الجهاز، وكل الأدوات (بما فيها تصدير واستيراد Excel) تعمل أوفلاين.
   بياناتك تُحفظ على الجهاز، فخذ نسخة احتياطية من زر 💾 بشكل دوري.

4) التحديث
   عند رفع نسخة جديدة غيّر رقم النسخة داخل sw.js (const V = 'ethmar-v2') ثم ارفع الملفات.
   سيظهر تنبيه "تم تحديث التطبيق" ويكفي إعادة فتح التطبيق.

ملاحظة: فتح index.html مباشرة من الجهاز (file://) يعمل كتطبيق عادي لكن لا يمكن تثبيته ولا يعمل كـ PWA.

إصلاحات هذه النسخة:
- تحويل الأيقونات إلى PNG حقيقي (كانت JPEG بأسماء PNG).
- تحسين جودة الأيقونات.
- إضافة prefer_related_applications: false.
- تحديث رقم الـ Service Worker.
