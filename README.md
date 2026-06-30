# Güneş Klima Bakım ve Temizliği - Vitrin Web Sitesi

Bu proje, Alanya geneline hizmet veren **Güneş Klima Bakım ve Temizliği** firması için özel olarak tasarlanmış, arama motoru optimizasyonu (SEO) odaklı, modern ve yüksek performanslı tek sayfalık (showcase) vitrin web sitesidir.

## Proje Özellikleri

- **Frameworksüz (Vanilla):** Sadece HTML5, modern CSS3 ve Vanilla JS kullanılarak sıfır bağımlılıkla geliştirilmiştir. Lighthouse skorunun tüm kategorilerde (Performans, Erişilebilirlik, En İyi Uygulamalar, SEO) 90+ olması garanti edilmiştir.
- **Mobile-First Arayüz:** Akıllı telefonlardan geniş ekran masaüstü monitörlere kadar tam uyumlu (responsive) esnek ızgara ve kutu düzenleri.
- **Gelişmiş Local SEO:** Sayfa içinde Alanya'nın tüm mahallelerini kapsayan anahtar kelimeler, JSON-LD Schema (HVACBusiness) şeması ve coğrafi etiketler.
- **Güvenli Dönüşüm (CTA):** Form doldurma zahmeti olmaksızın, doğrudan telefonla arama (`tel:`) ve pulse animasyonlu sabit yeşil WhatsApp iletişim hattı.
- **Önce/Sonra Galeri Görsel Yükleyici:** Dosya sistemi hazır, resimler bulunmadığında hata göstermeyen akıllı CSS/JS yer tutucu (placeholder) sistemi.

---

## Dosya Yapısı

```
gunes-klima/
├── index.html          # Ana sayfa (SEO meta etiketleri, JSON-LD, bölümler)
├── css/
│   └── style.css       # Tasarım sistemi, mobile-first düzenler, animasyonlar
├── js/
│   └── main.js         # Menü, pürüzsüz kaydırma, vanilla lightbox galerisi
├── img/
│   ├── logo.svg        # Sun ve Snowflake temalı vektörel logo (Header ve Footer)
│   ├── favicon.ico     # Tarayıcı sekme ikonu
│   └── galeri/         # Önce/Sonra görsellerinin yükleneceği alt klasör
│       ├── once-1.webp
│       ├── sonra-1.webp
│       ├── ...
│       └── sonra-6.webp
├── robots.txt          # Arama motoru örümcek talimatları
└── sitemap.xml         # Site haritası
```

---

## Önce/Sonra Görsellerini Ekleme

Web sitesinin galeri bölümü, 6 adet iş örneğini **Önce/Sonra** şeklinde yan yana gösterecek biçimde kodlanmıştır.

1. Çektiğiniz klima temizlik fotoğraflarını **WebP** formatına dönüştürün (hızlı yüklenmesi ve SEO performansı için WebP önerilir).
2. Görselleri aşağıdaki isimlerle adlandırın:
   - 1. İş için: `once-1.webp` ve `sonra-1.webp`
   - 2. İş için: `once-2.webp` ve `sonra-2.webp`
   - 3. İş için: `once-3.webp` ve `sonra-3.webp`
   - 4. İş için: `once-4.webp` ve `sonra-4.webp`
   - 5. İş için: `once-5.webp` ve `sonra-5.webp`
   - 6. İş için: `once-6.webp` ve `sonra-6.webp`
3. Bu resimleri `img/galeri/` klasörünün içine yerleştirin.
4. **Akıllı Yükleme Teknolojisi:** Görselleri klasöre yüklemeden önce web sitesi tarayıcıda açıldığında, kırık resim simgesi görünmez. Bunun yerine sistem otomatik olarak şık bir gri "Görsel buraya gelecek (Dosya yolu)" yer tutucusu (placeholder) gösterir. Resimler klasöre atıldığı anda web sitesi yer tutucuları kapatır ve gerçek görsellerinizi pürüzsüzce ekrana yansıtır.

---

## Dağıtım (Deploy) Kılavuzu

Web sitesi tamamen statik dosyalardan oluştuğu için tamamen **ücretsiz** ve yüksek hızlı küresel sunucularda (CDN) barındırılabilir.

### Seçenek A: Netlify ile Dağıtım (Kolay)
1. [Netlify.com](https://www.netlify.com/) adresine gidin ve ücretsiz üye olun.
2. Panelinize giriş yaptıktan sonra **Sites** sekmesine geçin.
3. Sayfanın altındaki **"Want to deploy a new site without connecting to Git? Drag and drop your site folder here"** alanına `gunes-klima/` klasörünü sürükleyip bırakın.
4. Birkaç saniye içinde siteniz yayına alınacaktır.
5. **Domain Bağlama:** "Domain settings" bölümünden `alanyaklimatemizligi.com` alan adınızı ekleyerek DNS yönlendirmesini yapabilirsiniz. (Netlify ücretsiz SSL sertifikasını otomatik kuracaktır).

### Seçenek B: Cloudflare Pages ile Dağıtım (En Hızlı & SEO Uyumlu)
1. [Cloudflare.com](https://www.cloudflare.com/) hesabınıza giriş yapın.
2. Sol menüden **Workers & Pages** seçeneğine tıklayın.
3. **Create Application** butonuna, ardından **Pages** sekmesine gelin.
4. **Upload assets** seçeneğini seçin.
5. Projenize bir isim verin ve `gunes-klima/` klasörünü zip yapmadan doğrudan sürükleyip yükleyin.
6. **Custom Domains** sekmesinden kendi domaininizi bağlayın. Cloudflare mükemmel önbellekleme (caching) ve güvenlik sunacaktır.

---

## Google Search Console Kurulumu ve İndeksleme

Sitenizi yayına aldıktan sonra Google'da hemen listelenmesi için:

1. [Google Search Console](https://search.google.com/search-console/) adresine gidin.
2. Domain mülk türünü seçerek domaininizi doğrulayın (Cloudflare veya Netlify DNS alanına ekleyeceğiniz bir TXT kaydı ile).
3. Sol menüden **Sitemaps (Site Haritaları)** bölümüne girin.
4. Yeni bir site haritası ekleme alanına `sitemap.xml` yazıp **Gönder** butonuna basın.
5. Google sitenizi tarayacak ve Alanya klima temizliği aramalarında indekslemeye başlayacaktır.
