ÜÇGENKOD V5 — Gerçek SaaS / Cloudflare

Bu paket bilgisayarsız kurulum için klasörsüz hazırlanmıştır. GitHub'a yalnızca 4 kök dosya yüklenir:
- worker.js
- wrangler.jsonc
- package.json
- README.md

Cloudflare Workers > Create application > Import a repository yoluyla GitHub deposunu bağlayın. Deploy komutu varsayılan npx wrangler deploy olarak kalabilir. Wrangler 4.68+ D1 ve R2 bindinglerini otomatik provision eder.

V5 özellikleri:
- Kayıt / giriş / HttpOnly oturum çerezi
- Her kullanıcıya ayrı işletme ve kalıcı slug
- D1 üzerinde kategori/ürün/ayarlar/veri
- R2 üzerinde logo ve ürün görselleri
- Kalıcı /m/isletme-slug menü adresi
- Kalıcı QR SVG
- Çok cihazlı panel senkronizasyonu
- Menü görüntülenme istatistiği
- Tema paletleri

Not: Ödeme/abonelik sağlayıcısı henüz bağlanmamıştır. Veritabanında plan alanı hazırlanmıştır.
