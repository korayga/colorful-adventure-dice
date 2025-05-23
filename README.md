# 🧊 RENKLİ MACERA KÜPÜ
HTML5 Canvas kullanılarak geliştirilen bir 2D platform oyunudur. Bu oyun, dört farklı kenarı farklı renklere boyanabilen bir zar karakterinin, küpün hangi yüzeyiyle temas ediyorsa o yüzeyin rengine göre platformlara yapışabildiği, yapıştığı yüzeylerde yukarı ya da yana kayabildiği, çeşitli tuzaklardan kaçınarak ilerlemeye çalıştığı ve renk uyumu mantığına dayalı benzersiz bir platform macerasıdır.

👉 [🎮 Oyunu Hemen Oyna](https://korayga.github.io/colorful-adventure-dice/)


![Image](https://github.com/user-attachments/assets/d27de5e3-545d-45f6-92e5-96051bf9f1fb)

![Image](https://github.com/user-attachments/assets/f4d878f9-4ab6-4912-8c86-6760df6ce885)

![Image](https://github.com/user-attachments/assets/8f246343-5b8f-4369-945b-5482a831936c)

## 🎲 İlham Kaynağı
Bu proje, "Roll - The Die" adlı oyundan ilham alınarak geliştirilmiştir.
Nir Zaid ve ekibi tarafından, 2022 yılında GMTK Game Jam kapsamında geliştirilen bu yaratıcı bulmaca-platform oyunu, "Roll of the Dice" (Zar Atışı) teması etrafında şekillenmiştir.
👉 [Orijinal Oyunu Görmek ve Oynamak için Tıklayın](https://nir-zaid.itch.io/roll-the-die)

## 🎮 Nasıl Oynanır?
1.  **Oyunu Başlatma:**
    *    https://korayga.github.io/colorful-adventure-dice/ adresinden ya da bu repository'yi klonlayın veya ZIP olarak indirin.
    *   `index.html` dosyasını modern bir web tarayıcısında (Chrome, Firefox, Edge vb.) açın.
    *   Başlangıç ekranında **ENTER** tuşuna basarak oyuna başlayın.

3.  **Kontroller:**
    *   **A / Sol Yön Tuşu (Klavye):** Sola Hareket
    *   **D / Sağ Yön Tuşu (Klavye):** Sağa Hareket
    *   **W (Duvarda Yapışırken):** Yukarı Kayma 
    *   **S (Duvarda Yapışırken):** Aşağı Kayma
             ➤ Daha akıcı kayma için: `W + A` / `W + D` (yukarı), `S + A` / `S + D` (aşağı)
    *   **Space (Boşluk):** Zıplama / Duvardan Zıplama
    *   **Sol Ok Tuşu (Klavye):** Küpün yüzeylerini sola doğru döndür
    *   **Sağ Ok Tuşu (Klavye):** Küpün yüzeylerini sağa doğru döndür
    *   **Shift:** Yapışmayı Bırak / Duvardan İtilme

4.  **Oyunun Amacı:**
    *   Küpü kontrol ederek engelleri aşın.
    *   Küpün alt yüzey rengini, üzerinde durduğunuz renk yamalarıyla değiştirebilirsiniz.
    *   Küpün yan yüzeylerinden birinin rengi, temas ettiğiniz renkli duvarla eşleşiyorsa o duvara yapışabilirsiniz.
    *   Tuzaklara değmeden bölüm sonundaki bitiş çizgisine ulaşın.

## 🎬 Oynanış Videosu:
 📺 [YouTube'da İzle](https://www.youtube.com/watch?v=495S1Q45BaI)

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

![Image](https://github.com/user-attachments/assets/def60fa3-369e-4c17-9c64-9bab8a79ce3e)

![Image](https://github.com/user-attachments/assets/2a202734-a3c7-4b5b-806d-db7c64ba8739)

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

Bu proje saf **HTML**, **CSS** ve **JavaScript** ile geliştirilmiştir. Herhangi bir derleme, bağımlılık veya kurulum gerektirmez.

### 🔄 Çevrimdışı Oynama (Local)

1. Bu repoyu bilgisayarına klonla:
   ```bash
   git clone https://github.com/korayga/colorful-adventure-dice.git

2.  Proje klasörüne gidin:
    ```bash
    cd colorful-adventure-dice
    ```
3.  `index.html` dosyasını bir web tarayıcısında açın.

### 🌐 Çevrimiçi Oynama (Web)
 Projeyi online olarak doğrudan tarayıcınızda oynamak için aşağıdaki bağlantıyı kullanabilirsiniz:
👉 https://korayga.github.io/colorful-adventure-dice/

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


## 👥 Geliştirici
Koray G.
🔗https://github.com/korayga

![Image](https://github.com/user-attachments/assets/db75f65d-e5d8-4ec1-ade0-a32738a66563)


