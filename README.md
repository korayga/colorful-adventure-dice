RENKLİ MACERA KÜPÜ
🧊 Renkli Macera Küpü, HTML5 Canvas kullanılarak geliştirilen bir 2D platform oyunudur. Oyuncu bir zar şeklinde küpü kontrol eder ve renk eşleşmelerini kullanarak duvarlara yapışır, tuzaklardan kaçar ve hedefe ulaşmaya çalışır.

## 🎮 Nasıl Oynanır?

1.  **Oyunu Başlatma:**
    *   Bu repository'yi klonlayın veya ZIP olarak indirin.
    *   `index.html` dosyasını modern bir web tarayıcısında (Chrome, Firefox, Edge vb.) açın.
    *   Başlangıç ekranında **ENTER** tuşuna basarak oyuna başlayın.

2.  **Kontroller:**
    *   **A / Sol Yön Tuşu (Klavye):** Sola Hareket
    *   **D / Sağ Yön Tuşu (Klavye):** Sağa Hareket
    *   **W (Duvarda Yapışırken):** Yukarı Kayma 
    *   **S (Duvarda Yapışırken):** Aşağı Kayma
              |--> daha akıcı kayma mekaniği için yukarı için w+a/ w+d aşağı için s+a / s+d kullanın
    *   **Space (Boşluk):** Zıplama / Duvardan Zıplama
    *   **Sol Ok Tuşu (Klavye):** Küpün yüzeylerini sola doğru döndür
    *   **Sağ Ok Tuşu (Klavye):** Küpün yüzeylerini sağa doğru döndür
    *   **Shift:** Yapışmayı Bırak / Duvardan İtilme

3.  **Oyunun Amacı:**
    *   Küpü kontrol ederek engelleri aşın.
    *   Küpün alt yüzey rengini, üzerinde durduğunuz renk yamalarıyla değiştirebilirsiniz.
    *   Küpün yan yüzeylerinden birinin rengi, temas ettiğiniz renkli duvarla eşleşiyorsa o duvara yapışabilirsiniz.
    *   Tuzaklara değmeden bölüm sonundaki bitiş çizgisine ulaşın.
  

## ✨ Özellikler

*   **Dinamik Küp Kontrolü:** Küpün her bir yüzeyi farklı bir renge sahip olabilir ve bu renkler ok tuşlarıyla döndürülebilir.
*   **Yapışma Mekaniği:** Küp, yüzey rengiyle eşleşen renkli platformlara yapışabilir ve bu duvarlarda hareket edebilir.
*   **Platform Çeşitliliği:** Farklı renklerde yapışılabilir platformlar, normal zeminler ve renk değiştirici yamalar.
*   **Engeller:** Hareketli tuzaklar ve sabit tuzaklar.
*   **Kontrol Noktaları (Checkpoint):** Oyuncunun ilerlemesini kaydeder.
*   **Seviye Tasarımı:** `oyunHaritasi` dizisi ile kolayca düzenlenebilir ve genişletilebilir bir harita yapısı.
*   **Ses Efektleri ve Müzik:** Zıplama, ölüm, kayma, kazanma sesleri ve arka plan müziği.
*   **Kamera Takibi:** Oyuncuyu takip eden yumuşak bir kamera hareketi.
*   **Kazanma Ekranı:** Oyunu bitirdiğinizde konfeti efektli bir tebrik ekranı.

## 🗺️ Harita (Seviye) Yapısı

Oyunun seviyesi `index.html` dosyasındaki `oyunHaritasi` adlı 2D JavaScript dizisi içinde tanımlanmıştır. Her bir sayı farklı bir oyun elemanını temsil eder:

*   `0`: Boş alan
*   `1`: Normal zemin platformu (VARSAYILAN_YAN_RENK)
*   `2` `3` `4` `5`: Renkli yapışılabilir platformlar (renkler `kutucukRenkleri` objesinden gelir)
*   `6` `7` `8` `9`: Üzerine gelindiğinde küpün alt yüzey rengini değiştiren renk yamaları (altındaki platform normal zemindir)
*   `81`: TÜRK Bayrağı 
*   `90` `91` `92` `93` `94`: Tuzaklar (altındaki platform ilgili renkte zemindir, dikenler üsttedir)
*   `99`: Kontrol Noktası (Checkpoint, altına zemin ekler)
*   `100`: Yatay hareket eden canavar tuzağı
*   `101`: Dikey hareket eden canavar tuzağı
*   `777`: Bitiş çizgisi alanı (altına zemin ekler)

Yeni seviyeler oluşturmak veya mevcut seviyeyi düzenlemek için bu diziyi değiştirebilir veya ekleme çıkarma yapabilirsiniz.

## 🖼️ Varlıklar (Assets)

Oyun için kullanılan tüm resim ve ses dosyaları `assets/` klasöründe bulunmaktadır:

*   `assets/jump.mp3`: Zıplama sesi
*   `assets/die.mp3`: Ölüm/yeniden başlama sesi
*   `assets/slide.mp3`: Duvarda kayma sesi
*   `assets/arkaplanMuzik.mp3`: Arka plan müziği
*   `assets/win.mp3`: Kazanma sesi
*   `assets/tuzak.png`: Dikenli tuzak resmi
*   `assets/checkpoint.png`: Kontrol noktası resmi
*   `assets/monster.png`: Hareketli tuzak resmi
*   `assets/finish.png`: Bitiş çizgisi resmi
*   `assets/bayrak.png`: TÜRK Bayrağı resmi
*   `assets/Background_2.png`: Arka plan resmi

## 🛠️ Kurulum ve Çalıştırma

Bu proje saf HTML, CSS ve JavaScript ile yazılmıştır. Ek bir derleme veya bağımlılık kurulumu gerektirmez.

1.  Projeyi klonlayın:
    ```bash
    git clone https://github.com/korayga/korayga.github.io.git
    ```
2.  Proje klasörüne gidin:
    ```bash
    cd korayga.github.io/JSOYUN
    ```
3.  `index.html` dosyasını bir web tarayıcısında açın.

## 🧪 Test Senaryosu
Oyuna girişte Enter tuşuna basılır.

Oyuncu sol ve sağa hareket eder, zıplar, duvara yapışır ve kayar.

Zar yönleri döndürülerek renk eşleşmesi sağlanır.

Tuzaklara değildiğinde kontrol noktasına geri dönülür.

Bitişe ulaşıldığında konfeti kutlaması oynar ve oyun kazanılır.

## 📁 Kullanılan Teknolojiler
HTML5 Canvas 

JavaScript 

CSS

Ses Efektleri: HTML Audio API

Yayın: GitHub Pages


👥 Geliştirici
Koray G.
🔗https://github.com/korayga


