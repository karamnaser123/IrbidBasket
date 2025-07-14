# دليل بناء تطبيق iOS للتصدير على Apple Developer

## المتطلبات الأساسية

1. **Xcode** - أحدث إصدار من App Store
2. **Flutter SDK** - مثبت ومحدث
3. **Apple Developer Account** - حساب مطور Apple
4. **Certificates & Provisioning Profiles** - شهادات وملفات التوزيع

## خطوات البناء

### 1. إعداد الأيقونة ✅
```bash
# إنشاء مجلد الأيقونات
mkdir -p assets/icon

# ضع أيقونة التطبيق في assets/icon/app_icon.png (1024x1024 بكسل)
```

### 2. تثبيت التبعيات ✅
```bash
flutter pub get
```

### 3. إنشاء الأيقونات ✅
```bash
dart run flutter_launcher_icons
```

### 4. فتح المشروع في Xcode
```bash
# على macOS
open ios/Runner.xcworkspace

# على Windows (إذا كان لديك Xcode مثبت)
# افتح ios/Runner.xcworkspace يدوياً
```

## خطوات التصدير في Xcode

### 1. إعداد Bundle Identifier
- افتح `ios/Runner.xcodeproj`
- اختر `Runner` من القائمة اليسرى
- في تبويب `General`، غيّر `Bundle Identifier` إلى معرف فريد
- مثال: `com.yourcompany.irbidbasket`

### 2. إعداد Team
- في نفس الصفحة، اختر `Team` من قائمة `Signing & Capabilities`
- اختر حساب Apple Developer الخاص بك

### 3. إنشاء Archive
- اختر `Any iOS Device (arm64)` من قائمة الأجهزة
- اذهب إلى `Product > Archive`
- انتظر حتى يكتمل البناء

### 4. رفع التطبيق
- في نافذة `Organizer`، اختر `Distribute App`
- اختر `App Store Connect`
- اتبع الخطوات لإرسال التطبيق

## أوامر مفيدة للتحضير

```bash
# تنظيف البناء السابق
flutter clean

# تثبيت التبعيات
flutter pub get

# إنشاء الأيقونات
dart run flutter_launcher_icons

# فحص حالة Flutter
flutter doctor
```

## إعدادات مهمة

### تحديث Info.plist
تأكد من تحديث المعلومات التالية في `ios/Runner/Info.plist`:
- `CFBundleDisplayName`: اسم التطبيق المعروض
- `CFBundleShortVersionString`: إصدار التطبيق
- `CFBundleVersion`: رقم البناء

### إضافة الأيقونة
بعد تشغيل `dart run flutter_launcher_icons`، ستتم إضافة الأيقونات تلقائياً إلى:
- `ios/Runner/Assets.xcassets/AppIcon.appiconset/`

## استكشاف الأخطاء

### مشاكل شائعة:
1. **خطأ في التوقيع**: تأكد من صحة الشهادات
2. **خطأ في Bundle ID**: تأكد من أن المعرف فريد
3. **خطأ في الأيقونة**: تأكد من أن الأيقونة 1024x1024 بكسل
4. **خطأ في التبعيات**: تأكد من أن جميع التبعيات متوافقة مع iOS

### ملاحظات مهمة:
- تأكد من أن جميع التبعيات متوافقة مع iOS
- اختبر التطبيق على جهاز حقيقي قبل التصدير
- تأكد من أن جميع الأذونات مطلوبة مدرجة في Info.plist
- على Windows، قد تحتاج لاستخدام Xcode على macOS أو استخدام خدمة سحابية

## الخطوات التالية

1. ✅ تم إنشاء الأيقونات
2. ✅ تم تثبيت التبعيات
3. 🔄 افتح المشروع في Xcode
4. 🔄 قم بإعداد Bundle Identifier و Team
5. 🔄 أنشئ Archive
6. 🔄 ارفع التطبيق على App Store Connect 