# shop_app

Flutter ile geliştirilmiş basit bir ayakkabı alışveriş uygulaması.

Bu proje, ürün listeleme, ürün detay görüntüleme ve sepet yönetimi akışını tek bir uygulamada birleştirmek için oluşturuldu. Durum yönetimi için `provider` kullanıldı; ürünler, detay sayfası ve sepet ekranı bu yapı üzerinden birbirine bağlandı.

## Proje Nasıl Kuruldu?

1. Flutter projesi oluşturuldu ve temel klasör yapısı hazırlandı.
2. Uygulama genelinde durum yönetimi için `CartProvider` tanımlandı.
3. Ana ekran, alt gezinme çubuğu ile iki bölüm halinde kurgulandı: ürün listesi ve sepet.
4. Ürün verileri `global_variables.dart` içinde sabit bir liste olarak tutuldu.
5. Ürün kartları, detay ekranı ve sepet ekranı ayrı widget/sayfalar olarak ayrıştırıldı.
6. Tasarımda `Lato` yazı tipi ve açık sarı ağırlıklı bir tema kullanıldı.
7. Görseller ve fontlar `assets/` klasörü üzerinden projeye dahil edildi.

## Özellikler

- Ürünleri kart yapısında listeleme
- Ekran genişliğine göre liste veya grid görünümü
- Ürün detay sayfasında beden seçimi
- Sepete ürün ekleme ve sepetten silme
- Bottom navigation ile ana sayfa ve sepet arasında geçiş
- Asset tabanlı görsel ve font kullanımı

## Kullanılan Teknolojiler

- Flutter
- Dart
- Provider
- Material Design

## Klasör Yapısı

- `lib/main.dart`: Uygulamanın başlangıç noktası ve tema kurulumu
- `lib/pages/`: Ana sayfa, sepet ve ürün detay sayfaları
- `lib/widgets/`: Ürün kartı, ürün listesi ve sepet provider yapısı
- `lib/global_variables.dart`: Ürün verileri
- `assets/images/`: Ürün görselleri
- `assets/fonts/`: Lato yazı tipi dosyaları

## Uygulama Akışı

Uygulama açıldığında `main.dart` içindeki `MultiProvider` ile `CartProvider` tüm ağaçta erişilebilir hale getirilir. Ardından `MaterialApp` çalışır ve `HomePage` açılır. `HomePage`, `IndexedStack` ve `BottomNavigationBar` kullanarak iki ana ekranı yönetir.

Ürün listesindeki her kart, kullanıcıyı `ProductDetailsPage` ekranına götürür. Bu ekranda ürün bilgisi, görseli, fiyatı ve beden seçenekleri gösterilir. Kullanıcı bir beden seçmeden sepete ekleme yaparsa uyarı mesajı görünür. Seçim yapıldığında ürün, `CartProvider` içine eklenir ve sepet ekranında listelenir.

Sepet ekranında ürünler `context.watch<CartProvider>()` ile dinlenir. Böylece ürün ekleme veya silme işlemleri ekranı otomatik olarak günceller.

## Kurulum

```bash
flutter pub get
```

Uygulamayı çalıştırmak için:

```bash
flutter run
```

## Notlar

- Uygulama, eğitim ve demo amaçlı basit bir alışveriş akışı sunar.
- Ürün verileri şu anda sabit listeden geliyor; gerçek bir backend bağlantısı bulunmuyor.
- Arama kutusu ve filtre alanı arayüzde yer alıyor, ancak filtreleme mantığı henüz tamamlanmış değil.
