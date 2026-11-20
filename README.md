# NMEA0183 Haberleşme Simülatörü

STM32 mikrodenetleyicisiyle UART üzerinden NMEA0183 seyir mesajları alışverişi yapmayı hedefleyen C++ ve Qt tabanlı masaüstü uygulaması.

## Projenin amacı

Uygulama, RMC ve GGA türünde NMEA0183 mesajları oluşturacak ve ilerleyen aşamalarda bu mesajları STM32’ye gönderecektir. STM32’den gelen yanıtlar da masaüstü uygulamasında görüntülenecektir.

## Mevcut durum: Faz 1

Bu sürümde Qt Widgets kullanılarak temel arayüz hazırlandı. Ekranda seri bağlantı ayarları, RMC ve GGA sekmeleri, mesaj önizleme alanı ve iletişim günlüğü bulunuyor.

Şu an bu bölümler arayüz taslağıdır. Seri porta bağlanma, mesaj oluşturma, checksum hesaplama ve mesaj gönderip alma işlevleri henüz eklenmemiştir. STM32 firmware’i de henüz geliştirilmemiştir.

## Kullanılan teknolojiler

- C++
- Qt 6 Widgets
- CMake

## Proje dosyaları

```text
.
├── .gitattributes
├── .gitignore
├── CMakeLists.txt
├── README.md
├── main.cpp
├── mainwindow.cpp
├── mainwindow.h
└── mainwindow.ui
```

- `main.cpp`: Uygulamayı başlatır.
- `mainwindow.h` ve `mainwindow.cpp`: Ana pencere sınıfını ve arayüz davranışını tanımlar.
- `mainwindow.ui`: Qt Creator’da görsel olarak hazırlanan arayüzü içerir.
- `CMakeLists.txt`: Projenin derleme ayarlarını tanımlar.

## Derleme ve çalıştırma

1. Projeyi Qt Creator’da `CMakeLists.txt` dosyasından açın.
2. Kurulu Qt 6 masaüstü kitini seçin.
3. Projeyi derleyip çalıştırın.

## Geliştirme planı

1. Qt Widgets arayüzü — tamamlandı
2. Seri portları listeleme ve bağlantı ayarları
3. RMC/GGA mesajları oluşturma ve checksum hesaplama
4. UART üzerinden mesaj gönderme ve alma
5. STM32 HAL ile UART alımı, NMEA doğrulaması ve yanıt gönderme
6. Masaüstü uygulaması ile STM32 arasında çift yönlü iletişim
7. Donanım üzerinde doğrulama ve proje dokümantasyonu

STM32 firmware’i masaüstü uygulamasından ayrı bir proje olarak geliştirilecektir. Kart pinleri ve UART birimi, donanım bağlantısı doğrulanmadan belirlenmeyecektir.
