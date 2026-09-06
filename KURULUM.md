# MİT - APK Kurulum Rehberi

Bu klasördeki dosyalar, uygulamayı **gerçek, tam ekran bir Android uygulaması** (APK)
haline getirmek için hazırlandı. Tarayıcı arayüzü (adres çubuğu, yenile butonu vb.)
**hiç görünmez** — çünkü uygulama internetten bir web sitesi açmıyor, tüm dosyalar
APK'nın içine gömülü.

## Neden burada derlenmiyor?

Bu ortamda (Claude'un çalıştığı sunucu) internet erişimi ve Android derleme araçları
yok. Bu yüzden derleme işini **GitHub'ın kendi sunucuları** (GitHub Actions) ücretsiz
olarak yapıyor. Senin yapman gereken sadece dosyaları GitHub'a yüklemek.

## Adımlar

### 1. GitHub'a yükle
- GitHub'da yeni bir repo oluştur (veya mevcut "mit" reponu kullan)
- Bu klasördeki TÜM dosyaları o repoya yükle (GitHub web arayüzünden sürükle-bırak
  ile de yapılabilir — "Add file > Upload files")

### 2. Otomatik derlemeyi bekle
- Dosyalar yüklenince GitHub Actions otomatik başlar (repo sayfasında "Actions"
  sekmesinden takip edebilirsin)
- Derleme yaklaşık 3-5 dakika sürer

### 3. APK'yı indir
- Actions sekmesinde tamamlanan çalışmaya tıkla
- En altta "Artifacts" bölümünde **mit-uygulama-apk** dosyasını indir
- İndirilen bir .zip dosyası — içinden **app-debug.apk** çıkacak

### 4. Telefona kur
- app-debug.apk dosyasını telefona aktar (WhatsApp, Drive, kablo — hangisi
  kolaysa)
- Telefonda dosyaya dokun, "Bilinmeyen kaynaklardan kuruluma izin ver" isteğini
  onayla (Android bunu ilk kurulumda soracak)
- Kurulum tamamlanınca "MİT" uygulaması ana ekranında görünecek

## Bu neden "web sitesi gibi" görünmeyecek

- Adres çubuğu, geri/ileri butonu, "Chrome'da aç" gibi hiçbir tarayıcı öğesi
  görünmez — bunlar zaten yalnızca bir web sitesini ziyaret ederken çıkar
- Uygulama, telefonun uygulama listesinde kendi simgesiyle (logo) görünür
- Diğer uygulamalar gibi tam ekran açılır, arka planda internete hiç bağlanmaz
- Tüm verilerin (müşteriler, işler, kalıplar) telefonun kendisinde saklanır

## Not: İmzasız (debug) APK

Bu APK "debug" modunda derleniyor — yani Google Play'e yüklenebilecek resmi bir
imza taşımıyor, ama **telefona kurup normal şekilde kullanmak için hiçbir sorun
yok**. Sadece Android ilk kurulumda "bilinmeyen kaynak" uyarısı gösterecek, bu
normal ve tek seferlik bir onaydır.

İleride Play Store'a yüklemek istersen, o zaman imzalı (release) bir sürüm
gerekir — o farklı bir adım, istediğinde ayrıca hazırlarız.
