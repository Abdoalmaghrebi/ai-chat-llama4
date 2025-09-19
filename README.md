# تطبيق دردشة الذكاء الاصطناعي - AI Chat Application

تطبيق ويب متجاوب للدردشة مع الذكاء الاصطناعي مدعوم بنموذج Llama-4 Scout على منصة Baseten.

## 🚀 الميزات

- **واجهة دردشة عصرية**: تصميم جذاب ومتجاوب باللغة العربية
- **ذكاء اصطناعي متقدم**: مدعوم بنموذج Llama-4 Scout من Meta
- **استجابة متدفقة**: عرض الردود كلمة بكلمة في الوقت الفعلي
- **وضع مظلم**: تبديل سلس بين الوضع الفاتح والمظلم
- **تصميم متجاوب**: يعمل بشكل مثالي على جميع الأجهزة
- **واجهة عربية**: دعم كامل للغة العربية مع اتجاه النص من اليمين لليسار

## 🛠️ التقنيات المستخدمة

### الواجهة الأمامية
- **React 18** - مكتبة JavaScript للواجهات
- **Tailwind CSS** - إطار عمل CSS للتصميم
- **Shadcn/UI** - مكونات واجهة المستخدم
- **Lucide React** - أيقونات عصرية
- **Vite** - أداة البناء والتطوير

### الواجهة الخلفية
- **Flask** - إطار عمل Python للويب
- **OpenAI SDK** - للتفاعل مع نموذج Llama-4
- **Flask-CORS** - دعم CORS للتطبيقات
- **Server-Sent Events** - للاستجابة المتدفقة

## 🚀 التشغيل المحلي

### متطلبات النظام
- Python 3.8+
- Node.js 18+ و pnpm (للتطوير فقط)

### خطوات التشغيل

1. **استنساخ المستودع**
```bash
git clone https://github.com/your-username/ai-chat-app.git
cd ai-chat-app
```

2. **إعداد البيئة الافتراضية**
```bash
python -m venv venv
source venv/bin/activate  # في Windows: venv\Scripts\activate
```

3. **تثبيت المتطلبات**
```bash
pip install -r requirements.txt
```

4. **تشغيل التطبيق**
```bash
python src/main.py
```

5. **فتح التطبيق**
افتح المتصفح وانتقل إلى: `http://localhost:5001`

## ⚙️ التكوين

### مفتاح API
يجب تحديث مفتاح API في ملف `src/routes/chat.py`:

```python
client = OpenAI(
    api_key='YOUR_API_KEY_HERE',
    base_url='https://inference.baseten.co/v1',
)
```

**ملاحظة**: في بيئة الإنتاج، يُنصح بشدة بتخزين مفتاح API في متغيرات البيئة:

```python
import os
client = OpenAI(
    api_key=os.getenv('BASETEN_API_KEY'),
    base_url='https://inference.baseten.co/v1',
)
```

## 📁 هيكل المشروع

```
ai-chat-backend/
├── src/
│   ├── routes/
│   │   ├── chat.py          # API endpoints للدردشة
│   │   └── user.py          # API endpoints للمستخدمين
│   ├── models/
│   │   └── user.py          # نماذج قاعدة البيانات
│   ├── static/              # ملفات الواجهة الأمامية المبنية
│   ├── database/
│   │   └── app.db          # قاعدة بيانات SQLite
│   └── main.py             # نقطة دخول التطبيق
├── venv/                   # البيئة الافتراضية
├── requirements.txt        # متطلبات Python
└── README.md              # هذا الملف
```

## 🌐 النشر

### نشر على Heroku
1. إنشاء ملف `Procfile`:
```
web: python src/main.py
```

2. تحديث المنفذ في `main.py`:
```python
port = int(os.environ.get('PORT', 5001))
app.run(host='0.0.0.0', port=port)
```

### نشر على Railway/Render
1. ربط المستودع بالمنصة
2. تحديد أمر البدء: `python src/main.py`
3. إضافة متغير البيئة `BASETEN_API_KEY`

## 🔒 الأمان

- **مفتاح API**: يجب تخزينه في متغيرات البيئة وليس في الكود
- **CORS**: مُفعل للسماح بالطلبات من الواجهة الأمامية
- **معالجة الأخطاء**: معالجة شاملة للأخطاء والاستثناءات

## 🤝 المساهمة

1. Fork المشروع
2. إنشاء فرع للميزة الجديدة (`git checkout -b feature/amazing-feature`)
3. Commit التغييرات (`git commit -m 'Add amazing feature'`)
4. Push إلى الفرع (`git push origin feature/amazing-feature`)
5. فتح Pull Request

## 📄 الترخيص

هذا المشروع مرخص تحت رخصة MIT - راجع ملف [LICENSE](LICENSE) للتفاصيل.

## 🙏 شكر وتقدير

- [Meta](https://ai.meta.com/) لتطوير نموذج Llama-4
- [Baseten](https://baseten.co/) لتوفير منصة الاستضافة
- [React](https://reactjs.org/) و [Flask](https://flask.palletsprojects.com/) للأدوات الممتازة
- جميع المساهمين في هذا المشروع

---

صُنع بـ ❤️ للمجتمع العربي

