# AnimeUz Pro — Render bepul tarifida sinov

## Fayllar
- `bot.py` — asosiy bot kodi.
- `requirements.txt` — Python kutubxonalari.
- `render.yaml` — Render sozlamalari uchun namuna.

## Render sozlash
1. Uch faylni GitHub repozitoriyga yuklang.
2. Render'da **New → Web Service** tanlab, repozitoriyga ulang. `render.yaml` ishlatilsa, sozlamalar avtomatik olinishi mumkin.
3. Environment Variables bo'limida `BOT_TOKEN` va `OWNER_ID` ni kiriting. Tokenni kodga yoki ommaviy GitHub repozitoriyga yozmang.
4. Deploy tugagach, `https://SIZNING-SERVISINGIZ.onrender.com/healthz` manzilini ochib, `{"status":"ok","service":"anime-bot"}` javobini tekshiring.
5. Uptime monitor (masalan, UptimeRobot) yarating: turi **HTTP(s)**, URL — yuqoridagi `/healthz`, interval — 5 daqiqa.

## Muhim cheklovlar
- Render bepul Web Service 15 daqiqa kiruvchi HTTP so'rovi bo'lmasa uxlaydi. Monitor pinglari xizmatni uyg'oq saqlashi mumkin, lekin bu doimiy ishlashga kafolat emas va Render xohlagan vaqtda servisni qayta ishga tushirishi mumkin.
- Bitta xizmat oy bo'yi uyg'oq tursa taxminan 720–744 soat ishlatadi; Render bepul tarifida workspace uchun oyiga 750 soat limiti bor va boshqa xizmatlar ham shu limitdan foydalanishi mumkin.
- **SQLite ma'lumotlar bazasi doimiy saqlanmaydi.** Render qayta ishga tushirganda, deploy qilganda yoki fayl tizimi tiklanganda baza yo'qolishi mumkin. Foydalanuvchi ma'lumotlari, anime katalogi, adminlar va VIP yozuvlari muhim bo'lsa, keyingi bosqichda doimiy tashqi baza va zaxira nusxasini sozlash kerak.
- Telegram bot kodi sintaksis bo'yicha tekshirildi, ammo haqiqiy `BOT_TOKEN` bilan Render'da ishga tushirish va barcha funksiyalarni Telegram ichida sinash hali bajarilmagan.
