# 🚀 الفصل 3: التشغيل والاستخدام

## 🎯 **الأوامر الأساسية**

### **1. الأوامر الأساسية**
```bash
# عرض المساعدة
openclaw --help

# عرض الإصدار
openclaw --version

# فتح لوحة التحكم
openclaw dashboard

# التحقق من حالة Gateway
openclaw gateway status

# تشغيل Gateway في المقدمة
openclaw gateway --port 18789
```

### **2. أوامر الرسائل**
```bash
# إرسال رسالة نصية
openclaw message send --target YOUR_CHAT_ID --message "Hello from OpenClaw"

# إرسال رسالة صوتية
openclaw message send --target YOUR_CHAT_ID --voice "Hello voice message"

# إرسال ملف
openclaw message send --target YOUR_CHAT_ID --file "/path/to/file.txt"
```

### **3. أوامر القنوات**
```bash
# إعداد Telegram
openclaw telegram setup

# إعداد WhatsApp
openclaw whatsapp setup

# إعداد Slack
openclaw slack setup

# عرض حالة القنوات
openclaw channels status
```

---

## 🤖 **العمل مع الوكلاء (Agents)**

### **1. إنشاء وكلاء مخصصين**
```bash
# إنشاء وكل جديد
openclaw agent create --name "MyAssistant" --model "gpt-4"

# عرض الوكلاء المتاحة
openclaw agent list

# تغيير الوكيل الافتراضي
openclaw agent set-default --name "MyAssistant"
```

### **2. التفاعل مع الوكلاء**
```bash
# التحدث مع الوكيل
openclaw agent --message "What is the weather today?"

# التحدث مع وكيل محدد
openclaw agent --agent "MyAssistant" --message "Explain quantum computing"

# عرض تاريخ المحادثات
openclaw agent --history
```

### **3. إعدادات الوكلاء**
```bash
# عرض إعدادات الوكيل
openclaw agent config --name "MyAssistant"

# تعديل إعدادات الوكيل
openclaw agent config --name "MyAssistant" --set temperature=0.8

# حذف وكيل
openclaw agent delete --name "MyAssistant"
```

---

## 🎛️ **إعداد القنوات**

### **1. Telegram**
```bash
# إعداد Telegram
openclaw telegram setup

# عرض إعدادات Telegram
openclaw telegram config

# اختبار الاتصال
openclaw telegram test
```

### **2. WhatsApp**
```bash
# إعداد WhatsApp
openclaw whatsapp setup

# عرض إعدادات WhatsApp
openclaw whatsapp config

# اختبار الاتصال
openclaw whatsapp test
```

### **3. Slack**
```bash
# إعداد Slack
openclaw slack setup

# عرض إعدادات Slack
openclaw slack config

# اختبار الاتصال
openclaw slack test
```

---

## 🧠 **الميزات المتقدمة**

### **1. الذاكرة والسياق**
```bash
# مسح الذاكرة
openclaw memory clear

# عرض استخدام الذاكرة
openclaw memory usage

# تصدير الذاكرة
openclaw memory export --file memory.json

# استيراد الذاكرة
openclaw memory import --file memory.json
```

### **2. المهام المجدولة (Cron)**
```bash
# إنشاء مهمة مجدولة
openclaw cron create --name "DailyReport" --command "openclaw message send --target YOUR_CHAT_ID --message 'Daily report'" --schedule "0 9 * * *"

# عرض المهام المجدولة
openclaw cron list

# تشغيل مهمة يدوياً
openclaw cron run --name "DailyReport"

# حذف مهمة مجدولة
openclaw cron delete --name "DailyReport"
```

### **3. المهارات (Skills)**
```bash
# عرض المهارات المتاحة
openclaw skills list

# تثبيت مهارة جديدة
openclaw skills install --name "weather"

# إزالة مهارة
openclaw skills uninstall --name "weather"

# إعداد مهارة
openclaw skills setup --name "weather"
```

---

## 🛠️ **استكشاف الأخطاء وإصلاحها**

### **1. مشاكل الاتصال**
```bash
# اختبار الاتصال بالإنترنت
openclaw network test

# اختبار اتصال API
openclaw api test

# اختبار اتصال القنوات
openclaw channels test
```

### **2. مشاكل الأداء**
```bash
# عرض استخدام الموارد
openclaw performance stats

# تنظيف الذاكرة
openclaw memory clean

# إعادة تشغيل الخدمات
openclaw services restart
```

### **3. مشاكل الإعدادات**
```bash
# عرض الإعدادات الحالية
openclaw config show

# استعادة الإعدادات الافتراضية
openclaw config reset

# تصدير الإعدادات
openclaw config export --file config.json

# استيراد الإعدادات
openclaw config import --file config.json
```

---

## 🎮 **سيناريوهات الاستخدام**

### **1. المساعد الشخصي اليومي**
```bash
# تسجيل الدخول للتواصل
openclaw agent --message "Good morning! What's my schedule today?"

# طلب معلومات الطقس
openclaw agent --message "What's the weather like today?"

# إعداد تذكير
openclaw agent --message "Remind me to call mom at 6 PM"
```

### **2. مساعدة المطور**
```bash
# طلب مساعدة في الكود
openclaw agent --message "Help me debug this Python code"

# شرح المفاهيم
openclaw agent --message "Explain machine learning concepts"

# توليد كود
openclaw agent --message "Generate a Python script for data analysis"
```

### **3. مساعدة المؤسسات**
```bash
# إعداد تقارير
openclaw agent --message "Generate daily sales report"

# إدارة المهام
openclaw agent --message "Create a task for the team"

# الإجتماعات
openclaw agent --message "Schedule a meeting with the team for tomorrow"
```

---

## 📝 **اختبار المعرفة - الفصل 3**

### **السؤال 1: أي أمر يفتح لوحة التحكم؟**
- أ) `openclaw dashboard`
- ب) `openclaw control`
- ج) `openclaw panel`
- د) `openclaw gui`

### **السؤال 2: أي أمر يرسل رسالة؟**
- أ) `openclaw send message`
- ب) `openclaw message send`
- ج) `openclaw text send`
- د) `openclaw chat send`

### **السؤال 3: أي أmlink يعرض الوكلاء المتاحة؟**
- أ) `openclaw agents list`
- ب) `openclaw agent list`
- ج) `openclaw agents show`
- د) `openclaw agent show`

---

## 💻 **تمرين عملي**

### **التمرين 1: تشغيل الأساسيات**
1. فتح لوحة التحكم
2. إرسال رسالة اختبار
3. التحقق من حالة القنوات

### **التمرين 2: إنشاء وكلاء مخصصين**
1. إنشاء وكل جديد
2. إرسال رسائل للوكيل
3. تغيير إعدادات الوكيل

### **التمرين 3: إعداد القنوات**
1. إعداد Telegram
2. إعداد WhatsApp
3. إعداد Slack

### **التمرين 4: استخدام المهارات**
1. تثبيت مهارة الطقس
2. استخدام مهارة الطقس
3. إزالة مهارة الطقس

### **التمرين 5: إدارة المهام المجدولة**
1. إنشاء مهمة مجدولة
2. تشغيل المهمة يدوياً
3. حذف المهمة

---

## 📚 **متابعة الفصل التالي**

في الفصل التالي، سنتعلم عن التحديثات والصيانة.

---

**[↗️ العودة إلى الفهرس](../README.md) | [📚 الفصل السابق: التثبيت خطوة بخطوة](../chapter2_installation.md) | [📚 الفصل السابق: الغلاف](../COVER.md) | [📚 الفصل التالي: التحديثات والصيانة](../chapter4_updates.md) | [📚 الفصل التالي: الترجمة والتخصيص](../chapter5_translation.md) | [📚 الفصل التالي: الميزات المتقدمة والأتمتة](../chapter6_advanced.md) | [📚 الفصل التالي: الأمان والأفضلية](../chapter7_security.md) | [📚 الفصل التالي: الخاتمة](../CONCLUSION.md)**