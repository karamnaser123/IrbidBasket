# دليل تصدير التطبيق على Apple Developer

## ✅ ما تم إنجازه

1. **✅ تم إعداد الأيقونات**
   - تم إنشاء أيقونة 1024x1024 بكسل
   - تم إنشاء جميع الأحجام المطلوبة للـ iOS
   - تم إضافة الأيقونات إلى `ios/Runner/Assets.xcassets/AppIcon.appiconset/`

2. **✅ تم تثبيت التبعيات**
   - تم تحديث `pubspec.yaml`
   - تم تثبيت جميع التبعيات المطلوبة

3. **✅ تم إنشاء الأيقونات**
   - تم تشغيل `dart run flutter_launcher_icons`
   - تم إنشاء جميع أحجام الأيقونات المطلوبة

## 📱 الخطوات التالية للتصدير

### 1. فتح المشروع في Xcode
```bash
# على macOS
open ios/Runner.xcworkspace

# على Windows (إذا كان لديك Xcode مثبت)
# افتح ios/Runner.xcworkspace يدوياً
```

### 2. إعداد Bundle Identifier
- افتح `ios/Runner.xcodeproj`
- اختر `Runner` من القائمة اليسرى
- في تبويب `General`، غيّر `Bundle Identifier` إلى معرف فريد
- مثال: `com.yourcompany.irbidbasket`

### 3. إعداد Team
- في نفس الصفحة، اختر `Team` من قائمة `Signing & Capabilities`
- اختر حساب Apple Developer الخاص بك

### 4. إنشاء Archive
- اختر `Any iOS Device (arm64)` من قائمة الأجهزة
- اذهب إلى `Product > Archive`
- انتظر حتى يكتمل البناء

### 5. رفع التطبيق
- في نافذة `Organizer`، اختر `Distribute App`
- اختر `App Store Connect`
- اتبع الخطوات لإرسال التطبيق

## 🔧 أوامر مفيدة

```bash
# تنظيف البناء
flutter clean

# تثبيت التبعيات
flutter pub get

# إنشاء الأيقونات
dart run flutter_launcher_icons

# فحص حالة Flutter
flutter doctor
```

## 📋 متطلبات Apple Developer

1. **Apple Developer Account** - حساب مطور Apple ($99/سنة)
2. **Xcode** - أحدث إصدار من App Store
3. **Certificates & Provisioning Profiles** - شهادات وملفات التوزيع
4. **App Store Connect** - حساب لإدارة التطبيقات

## ⚠️ ملاحظات مهمة

- تأكد من أن جميع التبعيات متوافقة مع iOS
- اختبر التطبيق على جهاز حقيقي قبل التصدير
- تأكد من أن جميع الأذونات مطلوبة مدرجة في Info.plist
- على Windows، قد تحتاج لاستخدام Xcode على macOS أو استخدام خدمة سحابية

## 🆘 استكشاف الأخطاء

### مشاكل شائعة:
1. **خطأ في التوقيع**: تأكد من صحة الشهادات
2. **خطأ في Bundle ID**: تأكد من أن المعرف فريد
3. **خطأ في الأيقونة**: تأكد من أن الأيقونة 1024x1024 بكسل
4. **خطأ في التبعيات**: تأكد من أن جميع التبعيات متوافقة مع iOS

## 📞 الدعم

إذا واجهت أي مشاكل، يمكنك:
1. مراجعة ملف `IOS_BUILD_README.md` للحصول على تفاصيل أكثر
2. فحص حالة Flutter باستخدام `flutter doctor`
3. التأكد من أن جميع التبعيات محدثة 