# استخدم صورة Node.js الرسمية
FROM node:22.16

# مجلد العمل داخل الحاوية
WORKDIR /app

# نسخ ملفات الباكيج لتثبيت الاعتمادات
COPY package*.json ./

# تثبيت الاعتمادات
RUN npm install

# نسخ جميع ملفات البوت
COPY . .

# إعداد المتغيرات البيئة (يمكن تعديلها لاحقًا من Render)
ENV NODE_ENV=production
ENV AMAZON_TRACKING_ID=lamhaauto-20
ENV EMAIL=lamha1store@gmail.com
ENV IBAN=532000010006086106335
ENV ENABLE_PUBLISHING=true

# أمر تشغيل البوت
CMD ["node", "index.js"]
