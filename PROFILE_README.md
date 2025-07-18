# صفحة الملف الشخصي - Profile Page

## الميزات المضافة

### 1. صفحة الملف الشخصي (Profile Page)
- **الموقع**: `lib/profile_page.dart`
- **الوصف**: صفحة جميلة وخفيفة لعرض معلومات المستخدم
- **الميزات**:
  - عرض اسم المستخدم مع إمكانية التعديل
  - عرض البريد الإلكتروني
  - عرض رقم الهاتف
  - عرض رقم QR Code
  - عرض حالة الحساب (نشط/غير نشط)
  - زر لتغيير كلمة المرور
  - زر لتسجيل الخروج
  - زر تحديث لإعادة تحميل البيانات

### 2. صفحة تغيير كلمة المرور (Change Password Page)
- **الموقع**: `lib/change_password_page.dart`
- **الوصف**: صفحة لتغيير كلمة المرور
- **الميزات**:
  - حقل كلمة المرور الحالية
  - حقل كلمة المرور الجديدة
  - حقل تأكيد كلمة المرور الجديدة
  - التحقق من صحة البيانات
  - رسائل خطأ واضحة

### 3. نموذج المستخدم (User Model)
- **الموقع**: `lib/models/user.dart`
- **الوصف**: نموذج لتخزين بيانات المستخدم
- **الحقول الأساسية**:
  - `id`: معرف المستخدم
  - `name`: اسم المستخدم
  - `email`: البريد الإلكتروني
  - `phone`: رقم الهاتف
  - `active`: حالة الحساب (نشط/غير نشط)
- **الحقول الإضافية**:
  - `qrcodeNumber`: رقم QR Code
  - `emailVerifiedAt`: تاريخ تأكيد البريد الإلكتروني
  - `lastLoginAt`: آخر تسجيل دخول
  - `createdAt`: تاريخ إنشاء الحساب
  - `updatedAt`: تاريخ آخر تحديث

### 4. خدمة المستخدم (User Service)
- **الموقع**: `lib/services/user_service.dart`
- **الوصف**: خدمة للتعامل مع API المستخدم
- **الوظائف**:
  - `getUserProfile()`: جلب بيانات المستخدم
  - `updateUserName()`: تحديث اسم المستخدم
  - `changePassword()`: تغيير كلمة المرور

## كيفية الاستخدام

### الوصول إلى صفحة الملف الشخصي
1. من صفحة QR Code، اضغط على أيقونة الشخص في الشريط العلوي
2. ستنتقل إلى صفحة الملف الشخصي

### تغيير الاسم
1. في صفحة الملف الشخصي، اضغط على أيقونة التعديل بجانب الاسم
2. أدخل الاسم الجديد
3. اضغط "حفظ" أو "إلغاء"

### تغيير كلمة المرور
1. في صفحة الملف الشخصي، اضغط على زر "تغيير كلمة المرور"
2. أدخل كلمة المرور الحالية
3. أدخل كلمة المرور الجديدة
4. أكد كلمة المرور الجديدة
5. اضغط "تغيير كلمة المرور"

## API Endpoints

### جلب بيانات المستخدم
```
GET /api/user
Headers: Authorization: Bearer {token}
Response: {
  "id": 7,
  "name": "test",
  "email": "partner@test.com",
  "phone": "12341234",
  "qrcode_number": "G4RRGOWBNF",
  "active": 1,
  ...
}
```

### تحديث اسم المستخدم
```
POST /api/update-profile
Headers: Authorization: Bearer {token}
Body: {"name": "الاسم الجديد"}
Response: {
  "message": "Profile updated successfully",
  "status": "success"
}
```

### تغيير كلمة المرور
```
POST /api/update-password
Headers: Authorization: Bearer {token}
Body: {
  "old_password": "كلمة المرور القديمة",
  "new_password": "كلمة المرور الجديدة"
}
Response: {
  "message": "Password updated successfully",
  "status": "success"
}
```

## التصميم

### الألوان المستخدمة
- **الخلفية**: تدرج من الأسود إلى الأزرق الداكن
- **اللون الرئيسي**: `#e94560` (أحمر غامق)
- **النصوص**: أبيض وأبيض شفاف

### الميزات التصميمية
- تصميم عصري وخفيف
- تأثيرات بصرية جميلة
- أزرار واضحة وسهلة الاستخدام
- رسائل خطأ واضحة
- مؤشرات تحميل

## الأمان
- استخدام Bearer Token للمصادقة
- التحقق من صحة البيانات المدخلة
- معالجة الأخطاء بشكل آمن
- رسائل خطأ واضحة للمستخدم r