# 🔧 الفصل 2: التثبيت خطوة بخطوة

## 🎯 **المتطلبات النظامية**

### **1. التحقق من نظام التشغيل**
قبل البدء، تأكد من أن نظامك متوافق:

#### **لـ Linux:**
```bash
cat /etc/os-release
```

#### **لـ macOS:**
```bash
sw_vers
```

#### **لـ Windows:**
```cmd
systeminfo | findstr /B /C:"OS Name"
```

### **2. التحقق من Node.js**
```bash
node --version
```
**المطلوب:** Node.js 22 أو أحدث

### **3. التحقق من pnpm**
```bash
pnpm --version
```
**المطلوب:** الإصدار 8 أو أحدث

### **4. التحقق من المساحة**
```bash
df -h /home  # Linux
df -h /      # macOS
```
**المطلوب:** 1GB مساحة خالية

---

## 🚀 **طرق التثبيت المختلفة**

### **الطريقة 1: التثبيت التلقائي (موصى به)**

#### **لـ Linux/macOS:**
```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

#### **لـ Windows (PowerShell):**
```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

### **الطريقة 2: التثبيت عبر npm**
```bash
npm install -g openclaw
```

### **الطريقة 3: التثبيت عبر pnpm**
```bash
pnpm install -g openclaw
```

### **الطريقة 4: التثبيت من المصدر**
```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw
npm install
npm run build
npm link
```

---

## 📋 **التهيئة الأولية**

### **1. تشغيل الموجه التفاعلي**
```bash
openclaw onboard --install-daemon
```

### **2. المتطلبات للموجه التفاعلي**
- ✅ **اختيار اللغة:** English/العربية
- ✅ **إعداد المصادقة:** API Keys
- ✅ **إعداد القنوات:** Telegram/WhatsApp/Slack
- ✅ **إعداد الخدمات:** Gateway, Services

### **3. إعداد المصادقة**
```bash
# عرض الإعدادات الحالية
openclaw config show

# تعديل الإعدادات
openclaw config set --key api-key --value YOUR_API_KEY
```

### **4. إعداد القنوات**
```bash
# إعداد Telegram
openclaw telegram setup

# إعداد WhatsApp
openclaw whatsapp setup

# إعداد Slack
openclaw slack setup
```

---

## 🔍 **التحقق من التثبيت**

### **1. التحقق من الإصدار**
```bash
openclaw --version
```
**النتيجة:** يجب أن تعرض الإصدار المثبت

### **2. التحقق من حالة الخدمة**
```bash
openclaw gateway status
```
**النتيجة:** يجب أن تعرض "running"

### **3. فتح لوحة التحكم**
```bash
openclaw dashboard
```
**النتيجة:** يجب أن يفتح المتصفح على http://127.0.0.1:18789/

### **4. إرسال رسالة اختبار**
```bash
openclaw message send --target YOUR_CHAT_ID --message "Hello from OpenClaw"
```

---

## 🛠️ **حلول المشاكل الشائعة**

### **1. مشكلة: Node.js غير مثبت**
```bash
# لـ macOS (باستخدام Homebrew)
brew install node

# لـ Linux (Ubuntu/Debian)
sudo apt update
sudo apt install nodejs npm

# لـ Windows
# قم بتحميل Node.js من الموقع الرسمي
```

### **2. مشكلة: pnpm غير مثبت**
```bash
# لـ Linux/macOS/Windows
curl -fsSL https://get.pnpm.io/install.sh | sh -s -

# أو عبر npm
npm install -g pnpm
```

### **3. مشكلة: الصلاحيات**
```bash
# لـ Linux/macOS
sudo chown -R $USER ~/.openclaw
sudo chmod -R 755 ~/.openclaw

# لـ Windows
# تأكد من تشغيل PowerShell كمسؤول
```

### **4. مشكلة: المنافذ المشغولة**
```bash
# التحقق من المنافذ المشغولة
netstat -tulpn | grep 18789

# تغيير المنفذ الافتراضي
openclaw config set --key gateway.port --value 8080
```

---

## 🎯 **التكوين الأساسي**

### **1. إعداد API Keys**
```bash
# OpenAI API Key
openclaw config set --key openai.api-key --value sk-your-openai-key

# Anthropic API Key
openclaw config set --key anthropic.api-key --value your-anthropic-key

# Google Gemini API Key
openclaw config set --key google.api-key --value your-gemini-key
```

### **2. إعداد القنوات**
```bash
# إعداد Telegram
openclaw telegram setup
# اتبع التعليمات لربط حسابك

# إعداد WhatsApp
openclaw whatsapp setup
# اتبع التعليمات لربح حسابك
```

### **3. إخدمات إضافية**
```bash
# تشغيل Gateway
openclaw gateway --port 18789

# تشغيل Dashboard
openclaw dashboard

# التحقق من حالة Services
openclaw services status
```

---

## 📊 **التوثيق الأولي**

### **1. إنشاء مجلد المستندات**
```bash
mkdir -p ~/openclaw-docs
cd ~/openclaw-docs
```

### **2. حفظ الإعدادات**
```bash
# تصدير الإعدادات
openclaw config export --file settings.json

# حفظ الإعدادات في ملف آمن
cp ~/.openclaw/openclaw.json ~/openclaw-docs/
```

### **3. إنشاء ملفات الملاحظات**
```bash
cat > ~/openclaw-docs/installation-notes.md << 'EOF'
# ملاحظات التثبيت

## تاريخ التثبيت
$(date)

## الإصدار المثبت
$(openclaw --version)

## الإعدادات الأساسية
- المنفذ: 18789
- القنوات: Telegram
- API Keys: OpenAI, Anthropic

## ملاحظات
$(cat notes-here)
EOF
```

---

## 🎮 **تمرين عملي**

### **التمرين 1: التثبيت الكامل**
1. قم بتثبيت OpenClaw AI باستخدام الطريقة التلقائية
2. قم بإعداد API Key
3. قم بإعداد Telegram
4. أرسل رسالة اختبار

### **التمرين 2: إعداد متقدم**
1. قم بتغيير المنفذ الافتراضي
2. قم بإعداد قناة إضافية
3. قم بتكوين إعدادات متقدمة
4. احفظ الإعدادات في ملف

### **التمرين 3: حل المشاكل**
1. قم بإنشاء مشكلة مقصودة
2. حل المشكلة باستخدام الأوامر
3. احتفظ بالحل في ملف الملاحظات

---

## 📚 **متابعة الفصل التالي**

في الفصل التالي، سنتعلم كيفية تشغيل OpenClaw AI والاستخدام اليومي.

---

**[↗️ العودة إلى الفهرس](../README.md) | [📚 الفصل السابق: مقدمة لـ OpenClaw AI](../chapter1_introduction.md) | [📚 الفصل التالي: التشغيل والاستخدام](../chapter3_operation.md)**