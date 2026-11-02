# YükKurtarırMı? — AdMob entegrasyon ayarları

## Uygulama kimliği
- Paket adı: `com.yukkurtarirmi.app`
- AdMob App ID: `ca-app-pub-3759490841134440~6160247417`

## Gerçek reklam birimleri (hesap sahibinin gönderdiği)
- Banner: `ca-app-pub-3759490841134440/4471761226`
- Geçiş reklamı: `ca-app-pub-3759490841134440/3534084077`
- Ödüllü video: `ca-app-pub-3759490841134440/9456047488`

## Güvenli test ayarı
`www/admob.js` içinde `APP_AD_MODE = 'test'` olarak ayarlanmıştır. Bu nedenle uygulama şimdilik Google'ın resmî demo reklam birimlerini kullanır. Gerçek reklam birimlerine geçişi, testler ve AdMob politika/izin kontrolleri tamamlandıktan sonra aynı dosyada `APP_AD_MODE = 'production'` yaparak gerçekleştirin. Test sırasında gerçek reklamlara tıklamayın.

## Entegrasyon davranışı
- Banner: uygulama ekranının alt tarafında.
- Geçiş reklamı: sefer kaydı başarılı olduktan sonra; en az 5 dakika aralıkla.
- Ödüllü video: kullanıcı kendi isteğiyle butona bastığında. Reklam tamamlanma olayı algılanır; uygulama içi ödülün ne olacağı ayrıca ürün kararı olarak belirlenmelidir. Şu an jeton/puan/PRO hakkı tanımlanmamıştır.
- UMP kullanıcı rızası bilgisi istenir; gerekli form varsa gösterilir. `canRequestAds` false ise reklam isteği gönderilmez.

## Android proje oluşturma
Terminalde proje klasöründe:
```bash
npm install
npm run build
npx cap add android
npm run configure:android
npx cap sync android
npx cap open android
```
Android Studio'da Gradle senkronizasyonu yapıp gerçek cihazda test edin. Android klasörü bir kez oluşturulduktan sonra sonraki web güncellemelerinde `npm run build` ve `npx cap sync android` yeterlidir.

## Önemli
Bu ZIP, reklam çağrıları ve kimlikleri eklenmiş kaynak projedir; burada Android SDK/Gradle çalıştırılmadığı için derlenmiş APK/AAB veya cihazda doğrulanmış reklam gösterimi değildir. Gizlilik politikası, AdMob gizlilik/mesaj ayarları, Play Console Veri Güvenliği ve test cihazı kontrolleri tamamlanmadan üretim reklamlarına geçmeyin.
