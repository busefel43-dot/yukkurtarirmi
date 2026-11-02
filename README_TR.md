# YükKurtarırMı? — Android kaynak proje

- Uygulama adı: `YükKurtarırMı?`
- Android Application ID: `com.yukkurtarirmi.app`
- AdMob App ID ve Banner / Geçiş / Ödüllü reklam kimlikleri projeye eklendi.

## Kurulum ve Android oluşturma
Node.js LTS, npm ve Android Studio gerekir. Proje klasöründe:
```bash
npm install
npm run build
npx cap add android
npm run configure:android
npx cap sync android
npx cap open android
```
Android Studio Gradle senkronizasyonundan sonra fiziksel Android cihazda test edin.

## Reklamlar
İlk açılışta Google demo reklam birimleri kullanılır. `www/admob.js` içindeki `APP_AD_MODE` değerini testler tamamlanmadan `production` yapmayın. Uygulamada banner, başarılı sefer kaydı sonrası sınırlı sıklıkta geçiş reklamı ve kullanıcı talebiyle açılan ödüllü video akışı bulunur. Ödüllü videonun uygulama içi karşılığı henüz tanımlanmamıştır.

## Güncelleme
`www/` içindeki web dosyalarını değiştirdikten sonra:
```bash
npm run build
npx cap sync android
```

## Yayın
Android Studio > Build > Generate Signed Bundle / APK > Android App Bundle ile imzalı AAB oluşturun. Önce Play Console dahili test kanalında deneyin. Bu ZIP imzalı AAB değildir.

Daha fazla bilgi: `CONFIG_GEREKSINIMLERI_TR.md`.
