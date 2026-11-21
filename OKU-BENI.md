# Yırdaş (Android)

Telefondaki müzikleri ve klipleri **kendiliğinden bulan**, **uygulama kapalıyken de çalmaya devam eden**,
Spotify tarzı arayüzlü müzik çalar.

## Özellikler
- **Gündüz / Gece / Otomatik tema:** Ayarlar ekranından (ana sayfada sağ üstteki dişli simgesi) seçilir. Otomatik, telefonun gece/gündüz ayarına uyar. Ana sayfadaki "Gece Modu" anahtarı hızlı geçiş içindir.
- **Yeni logo:** Sade, tamga biçiminde Türk sembolü (vektör: `res/drawable/ic_logo.xml`). Uygulama simgesi de aynı logodur (tema simgesi desteği dahil).
- İlk açılışta izin ister, ardından telefondaki tüm müzikleri ve klipleri otomatik tarar. Yeni dosya eklenince liste kendiliğinden güncellenir.
- Arka planda çalma: bildirim ve kilit ekranı kontrolleriyle (Media3 MediaSession servisi). Uygulamayı kapatsan da çalar.
- Klipler tam ekran "Şimdi çalıyor" sayfasında görüntüyle oynar. Sadece ses olan parçalarda kapak görünür.
- Şarkı sözleri: İnternet varken lrclib.net'ten bulunur, telefona kaydedilir. Zamanlı sözler şarkıyla akar, bir satıra dokununca oraya atlar.
- En çok dinlediklerin: Bir parça yaklaşık 30 saniye dinlenince sayılır. Ana sayfada ve "En çok" sekmesinde görünür.
- Öneriler: İnternet varken en çok dinlediğin sanatçılara göre benzer sanatçılar (Deezer) "Tavsiye Edilen İstasyonlar" olarak çıkar. Dokununca 30 saniyelik önizlemeler çalar.

- **Yapay zekâ asistanı (Asistan sekmesi):** Ruh halini yaz ya da mikrofon simgesiyle söyle ("ruh halim kötü, solgun şarkılar aç", "iyileştirecek oyun havaları aç"). Asistan telefondaki listene ve en çok dinlediklerine bakıp şarkıları seçer, çalar; istersen listende olmayan yeni sanatçılardan öneri de katar. Asistan telefonun içinde, internetsiz ve ücretsiz çalışır; anahtar gerekmez. Dinledikçe hangi ruh halinde hangi parçaları sevdiğini öğrenir. İstersen ayar simgesinden ücretsiz Google Gemini anahtarı (aistudio.google.com/apikey) ekleyip daha akıllı cevap alabilirsin.
- **Listelerin arasında öneriler:** Ana sayfada ve Kitaplık'ta, sıraya ve çalma listesine her 4-5 parçada bir "ÖNERİ" etiketli parça karışır (30 sn önizleme). Yanındaki kalbe basınca parça **Beğenilen** sekmesine kaydedilir. Oradan paylaş simgesiyle listeyi (sanatçı - şarkı + Deezer bağlantısı) alıp sonra indirebilirsin.

## Yenilikler (1.1)

### Dinleme
- **Sözleri düzenleme:** Şimdi çalıyor sayfasında söz bulunamazsa "Sözleri kendin yaz" düğmesi çıkar. Bulunan sözlerin yanındaki kalem simgesiyle ya da üç nokta menüsünden "Sözleri düzenle" ile değiştirebilirsin. Düz metin ya da `[01:23.45]` gibi zaman damgalı (LRC) satırlar yapıştırabilirsin; zaman damgalıysa sözler şarkıyla akar. Sözler parça başına telefona kaydedilir. Boş kaydedersen silinir.
- **Hız ayarı (0,75x - 2x):** Oynatıcıda süre satırının ortasındaki "Hız" düğmesi. Klip ve 10 dakikadan uzun kayıtlarda (konuşma, sohbet, sesli kitap) hız parça başına hatırlanır. Kısa müzik parçaları her parçada 1x'e döner.
- **Kaldığın yerden devam:** Klipler ve 10 dakikadan uzun parçalar kapanınca konumu hatırlar. Tekrar açınca kaldığı yerden başlar, ana sayfada "Kaldığın Yerden" bölümünde görünür. Sona yaklaşınca kayıt silinir.
- **Kırp ve zil sesi yap:** Oynatıcı > üç nokta > "Kırp / zil sesi yap". Aralığı kaydırıcıyla seçer, "Seçili bölümü dinle" ile dener, kaydedince **Zil sesleri** klasörüne yazar. İstersen "Telefon zili yap" ile varsayılan zil yapar (ilk seferde Android "ayarları değiştirme" izni ister). Yeniden kodlama yapmadan keser; MP3, AAC/M4A ve Opus desteklenir. Klipte sesi alınır.

### Keşif
- **Klasöre göre gezinme:** Kitaplık > Klasörler.
- **Sanatçı ve albüm sayfaları:** Kitaplık > Sanatçılar / Albümler, ya da bir parçanın menüsünden "Sanatçı sayfası" / "Albüm sayfası". Sanatçı sayfasında çal, karışık çal, en çok dinlediklerin ve albümler görünür.
- **Benzer parça bulma:** Parça menüsünde ya da oynatıcı üç nokta menüsünde "Benzer parçaları bul". Telefondaki listeden aynı sanatçı, albüm, klasör, benzer hava (hareketli / hüzünlü / sakin), süre ve dinlenme sayısına göre sıralar.
- **Dinleme rozetleri:** Ana sayfada "Rozetlerin". 1 / 10 / 50 / 100 saat, 3 / 7 / 30 gün üst üste, 100 / 1000 dinleme, farklı parça ve sanatçı sayısı, 10 beğeni. Yeni rozet kazanınca üstte kısa bir bildirim çıkar.

### Görünüm
- **Vurgu rengi:** Ayarlar > Vurgu rengi: kırmızı, altın, mavi, yeşil.
- **Gün doğumu / batımına göre tema:** Ayarlar > Gün doğumu / batımı. Yaklaşık konumunla gün doğunca açık, batınca koyu tema olur (konum izni ister, yalnızca bu hesap için kullanılır, telefondan çıkmaz). Konum alınamazsa saat diliminden yaklaşık hesaplar. "Otomatik" seçeneği eskisi gibi telefonun ayarına uyar.
- **Kapak renginden tema:** Oynatıcı arka planı çalan parçanın kapağına göre renklenir. Ayarlar'dan kapatılabilir.

### Paylaşım
- **Şimdi çalanı paylaş:** Oynatıcının sağ üstündeki paylaş simgesi. Kapak, parça adı ve çalan sözlerden şık bir görsel kart oluşturur.
- **Beğeni listesini dışa aktar:** Beğenilen sekmesi > paylaş simgesi: metin olarak paylaş, .txt dosyası ya da .csv (Excel) olarak kaydet.

## APK nasıl alınır

### Yol A: GitHub ile (bilgisayara bir şey kurmadan)
1. github.com'da ücretsiz hesap aç, yeni bir **boş depo** oluştur.
2. Bu klasörün içindekileri (CepCalar klasörünün içi, `.github` klasörü dahil) depoya yükle.
3. Depoda **Actions** sekmesi > **APK derle** > **Run workflow**.
4. İş bitince (yaklaşık 5-8 dk) sayfanın altındaki **cep-calar-apk** dosyasını indir, zip'ten `app-debug.apk` çıkar.
5. APK'yı telefona gönder, aç. "Bilinmeyen kaynaklardan yükle" izni isterse ver.

### Yol B: Android Studio ile
1. Android Studio'yu kur, **Open** ile bu klasörü aç, Gradle eşitlemesini bekle.
2. **Build > Build APK(s)** ile APK'yı al ya da telefonu USB ile bağlayıp **Run**'a bas.

## Notlar
- Ana sayfadaki kurt silüeti ve manzara kodla çizilir (`Theme.kt`, `res/drawable/ic_wolf.xml`), görsel dosyası gerekmez. Karşılama adı Ayarlar > Profil'den değişir.
- Kod henüz gerçek bir derlemeyle denenmedi. Derleme hata verirse hata metnini gönder, düzeltirim.
- Telefon üreticilerinin pil tasarrufu ayarları arka plandaki çalmayı kesebilir. Kesilirse Ayarlar > Pil > Yırdaş için "Kısıtlama yok" seç.
- Telefonda sanatçı bilgisi olmayan dosyalarda, ad "Sanatçı - Şarkı" biçimindeyse sanatçı dosya adından okunur.
- Klipler: Sanatçı bilgisi olan veya Müzik, Klip gibi klasörlerdeki videolar listelenir. Kamera, WhatsApp vb. videolar gizlidir. Kitaplık sekmesindeki anahtarla tüm videoları gösterebilirsin.

## Sesli sohbet (eller serbest)
- Uygulama açılınca asistan seni sesli karşılar. Asistan sekmesindeki ya da ana sayfadaki hoparlör simgesiyle konuşmasını kapatıp açabilirsin.
- Mikrofon simgesine bir kez dokun: Sohbet modu açılır, sürekli dinler. Dediğin şeyi asistan yanıtlar ve parçaları çalar. Müzik çalarken yalnızca "Yırdaş, ..." diye başlayan cümleleri ve dur/devam/sonraki/önceki gibi kısa komutları dinler.
- İnternetsiz çalışması için telefonda Türkçe çevrimdışı konuşma tanıma paketi (Google uygulaması > Ayarlar > Ses > Çevrimdışı konuşma tanıma) ve Türkçe metin okuma sesi yüklü olmalı.
- Sohbet modu açıkken ekran açık kalır, uygulama arka plandayken dinleme durur.
