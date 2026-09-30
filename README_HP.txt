NANG STUDIO — HTML + VERCEL AUTO PAYMENT

1. Upload folder ini ke GitHub dari HP lalu import repository ke Vercel.
2. Di Vercel > Settings > Environment Variables isi:
MIDTRANS_SERVER_KEY = Server Key Midtrans
MIDTRANS_ENV = sandbox
KEY_SECRET = secret random panjang
OWNER_TOKEN = token rahasia owner

Untuk jualan asli, ubah MIDTRANS_ENV menjadi production.

3. Di dashboard Midtrans, set Payment Notification URL:
https://DOMAIN-KAMU.vercel.app/api/webhook

4. Buka website /, masukkan Roblox UserId dan paket.
5. Setelah transaksi QRIS berstatus settlement, halaman pembayaran mengambil status otomatis dan membuat key.

Catatan:
- QRIS otomatis membutuhkan payment gateway; template ini memakai Midtrans.
- Server Key dan KEY_SECRET hanya berada di Vercel, bukan HTML.
- Key diikat ke order + UserId + paket + expiry.
- /owner memakai OWNER_TOKEN.

Dokumentasi Midtrans:
https://docs.midtrans.com/docs/introduction-qris-payment
https://docs.midtrans.com/docs/https-notification-webhooks
