# 🌐 الفصل 5: الترجمة والتخصيص

## 🎯 **مقدمة**

هذا الفصل يغطي كيفية تخصيص OpenClaw AI وترجمته إلى لغات متعددة، مع التركيز على الدعم العربي الكامل.

---

## 🌍 **دعم اللغات المختلفة**

### **1. اللغات المدعومة حالياً**
- ✅ **العربية (ar)** - دعم كامل مع RTL
- ✅ **الإنجليزية (en)** - اللغة الأساسية
- ✅ **الفرنسية (fr)** - دعم محدود
- ✅ **الإسبانية (es)** - دعم محدود
- ✅ **الألمانية (de)** - دعم محدود

### **2. إضافة لغة جديدة**
```bash
# إنشاء مجلد اللغة الجديدة
mkdir -p /home/ubuntu/.openclaw/workspace/openclai_interactive_book/langs/ar

# نسخ المحتوى إلى اللغة الجديدة
cp /home/ubuntu/.openclaw/workspace/openclai_interactive_book/README.md /home/ubuntu/.openclaw/workspace/openclai_interactive_book/langs/ar/

# تعديل المحتوى للغة الجديدة
```

### **3. إعداد الدعم متعدد اللغات**
```bash
# تفعيل الدعم متعدد اللغات
export OPENCLAW_LANG=ar

# التحقق من الإعدادات
openclaw config show --lang
```

---

## 🔧 **التخصيص المحلي**

### **1. تغيير اللغة الافتراضية**
```bash
# تغيير اللغة الافتراضية
openclaw config set --key default.language --value ar

# التحقق من الإعدادات
openclaw config get default.language
```

### **2. تخصيص الواجهة**
```bash
# تغيير ش الواجهة
openclaw config set --key interface.theme --value dark

# تغيير الخط
openclaw config set --key interface.font --value "Segoe UI"

# تغيير حجم الخط
openclaw config set --key interface.font-size --value 16
```

### **3. تخصيص الألوان**
```bash
# تغيير ألوان الواجهة
openclaw config set --key interface.colors.primary --value "#FF6B6B"
openclaw config set --key interface.colors.secondary --value "#4ECDC4"
openclaw config set --key interface.colors.background --value "#2C3E50"
```

---

## 🔄 **الترجمة التلقائية**

### **1. تفعيل الترجمة التلقائية**
```bash
# تفعيل الترجمة التلقائية
openclaw config set --key translation.auto --value true

# اختيار محرك الترجمة
openclaw config set --key translation.engine --value google
```

### **2. محركات الترجمة المدعومة**
| المحرك | الدعم | الجودة | السرعة |
|--------|-------|---------|--------|
| Google | كامل | جيدة | سريعة |
| DeepL | كامل | ممتازة | متوسطة |
| Microsoft | محدود | جيدة | سريعة |
| Yandex | محدود | متوسطة | سريعة |

### **3. ترجمة نصوص مخصصة**
```bash
# ترجمة نص مخصص
openclaw translate --from en --to ar --text "Hello, how are you?"

# ترجمة ملف
openclaw translate --from en --to ar --file input.txt

# ترجمة دليل كامل
openclaw translate --from en --to ar --dir ./docs
```

---

## 🎨 **تخصيص التصميم**

### **1. تغيير الشكل الخارجي**
```bash
# تغيير الشكل الخارجي
openclaw config set --key app.theme --value "modern"

# تغيير اللون الرئيسي
openclaw config set --key app.primary-color --value "#FF6B6B"

# تغيير الشفافية
openclaw config set --key app.transparency --value 0.9
```

### **2. تخصيص الأيقونات**
```bash
# تغيير مجموعة الأيقونات
openclaw config set --key app.icon-set --value "outline"

# تغيير حجم الأيقونات
openclaw config set --key app.icon-size --value 24

# تفعيل الأيقونات المتحركة
openclaw config set --key app.animated-icons --value true
```

### **3. تخصيص الصوت**
```bash
# تغيير صوت المساعد
openclaw config set --key voice.engine --value elevenlabs

# تغيير صوت المساعد
openclaw config set --key voice.voice --value "Roger"

# تغيير سرعة الصوت
openclaw config set --key voice.speed --value 1.0

# تغيير نغمة الصوت
openclaw config set --key voice.pitch --value 1.0
```

---

## 📱 **التكامل مع الأجهزة المحمولة**

### **1. تخصيص التطبيق للجوال**
```bash
# تخصيص التطبيق للجوال
openclaw config set --key mobile.responsive --value true

# تغيير حجم الخط للجوال
openclaw config set --key mobile.font-size --value 18

# تفعيل الإيماءات
openclaw config set --key mobile.gestures --value true
```

### **2. تخصيص الإشعارات**
```bash
# تخصيص إشعارات الجوال
openclaw config set --key mobile.notifications --value true

# تغيير صوت الإشعارات
openclaw config set --key mobile.notification-sound --value "default"

# تخصيص تردد الإشعارات
openclaw config set --key mobile.notification-frequency --value "normal"
```

---

## 🔧 **إضافة لغات مخصصة**

### **1. إنشاء ملف اللغة**
```json
{
  "greeting": "مرحباً",
  "goodbye": "وداعاً",
  "help": "مساعدة",
  "settings": "الإعدادات",
  "save": "حفظ",
  "cancel": "إلغاء",
  "loading": "جاري التحميل...",
  "error": "خطأ",
  "success": "نجاح"
}
```

### **2. تسجيل اللغة الجديدة**
```bash
# تسجيل اللغة الجديدة
openclaw lang register --name ar --code ar --rtl true

# تحميل ملف اللغة
openclaw lang load --file ar.json

# التحقق من اللغة المسجلة
openclaw lang list
```

### **3. استخدام اللغة المخصصة**
```bash
# استخدام اللغة المخصصة
openclaw config set --key app.language --value ar

# تحقق من اللغة الحالية
openclaw config get app.language
```

---

## 🔄 **الترجمة التلقائية للملفات**

### **1. ترجمة ملفات Markdown**
```bash
# ترجمة ملف Markdown
openclaw translate-markdown --from en --to ar --file README.md

# ترجمة دليل كامل من Markdown
openclaw translate-markdown --from en --to ar --dir ./docs
```

### **2. ترجمة ملفات JSON**
```bash
# ترجمة ملف JSON
openclaw translate-json --from en --to ar --file config.json

# ترجمة ملفات JSON متعددة
openclaw translate-json --from en --to ar --dir ./config
```

### **3. ترجمة ملفات نصية**
```bash
# ترجمة ملف نصي
openclaw translate-text --from en --to ar --file.txt

# ترجمة ملفات نصية متعددة
openclaw translate-text --from en --to ar --dir ./texts
```

---

## 🎯 **تحسين الأداء**

### **1. تحسين الأداء في اللغات المختلفة**
```bash
# تحسين الأداء للغة العربية
openclaw config set --key performance.arabic --value optimized

# تحسين الأداء للغة الإنجليزية
openclaw config set --key performance.english --value optimized

# تحسين الأداء العام
openclaw config set --key performance.general --value fast
```

### **2. إدارة الذاكرة**
```bash
# تقليل استخدام الذاكرة
openclaw config set --key memory.usage --value low

# تحسين التخزين المؤقت
openclaw config set --key memory.cache --value true

# تنظيف الذاكرة
openclaw memory clean
```

---

## 🛡️ **الأمان والخصوصية**

### **1. حماية البيانات المترجمة**
```bash
# تشفير البيانات المترجمة
openclaw config set --key security.encrypt-translations --value true

# تأمين ملفات الترجمة
openclaw config set --key security.secure-translations --value true

# تنظيف البيانات المؤقتة
openclaw security cleanup
```

### **2. التحكم في الوصول**
```bash
# التحكم في وصول الترجمة
openclaw config set --key access.translation --value users

# تقييد الوصول إلى اللغات
openclaw config set --key access.languages --value "ar,en"

# مراقبة الوصول
openclaw access monitor
```

---

## 📊 **المراقبة والتحليل**

### **1. تتبع استخدام اللغات**
```bash
# تتبع استخدام اللغات
openclaw analytics track --languages

# عرض إحصائيات اللغات
openclaw analytics show --languages

# تصدير التقارير
openclaw analytics export --languages --file report.json
```

### **2. مراقبة الأداء**
```bash
# مراقبة أداء الترجمة
openclaw performance monitor --translation

# عرض تقارير الأداء
openclaw performance report --translation

# تحسين الأداء
openclaw performance optimize --translation
```

---

## 🎮 **تمرين عملي**

### **التمرين 1: تخصيص اللغة**
1. غيّر اللغة الافتراضية إلى العربية
2. قم بتخصيص الواجهة
3. قم بتغيير الألوان

### **التمرين 2: إضافة لغة جديدة**
1. أنشئ ملف لغة جديد
2. سجل اللغة
3. استخدم اللغة المخصصة

### **التمرين 3: ترجمة محتوى**
1. قم بترجمة ملف Markdown
2. قم بترجمة ملف JSON
3. قم بترجمة ملف نصي

---

## 📚 **متابعة الفصل التالي**

في الفصل التالي، سنتعلم عن الميزات المتقدمة في OpenClaw AI.

---

**[↗️ العودة إلى الفهرس](../README.md) | [📚 الفصل السابق: التحديثات والصيانة](../chapter4_updates.md) | [📚 الفصل السابق: الغلاف](../COVER.md) | [📚 الفصل التالي: الميزات المتقدمة](../chapter6_advanced.md) | [📚 الفصل التالي: الأمان والأفضلية](../chapter7_security.md) | [📚 الفصل التالي: الخاتمة](../CONCLUSION.md)**
