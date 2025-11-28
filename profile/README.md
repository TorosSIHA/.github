# TOROS SİHA – Savaşan İHA 2025 Projesi

Bu depo, TEKNOFEST 2025 Savaşan İHA Yarışması kapsamında geliştirilen TOROS SİHA insansız hava aracı yazılım ve yer istasyonu altyapısını içerir. Projede sabit kanatlı İHA’mız için otonom kalkış, uçuş, kilitlenme, kamikaze görevi ve otonom iniş görevleri ile yarışma sunucusu entegrasyonu hedeflenmektedir.

## 🎯 **Projenin Amacı**

Savaşan İHA yarışmasının hedefi; İHA’ların hava–hava ve hava–yer muharebe senaryolarında yüksek otonomi ile görev icra edebilmesini sağlamak, bu süreçte görüntü işleme, karar verme, planlama ve otonom uçuş kabiliyetlerini geliştirmektir.

**TOROS SİHA projesinde:**

Havadaki diğer İHA’lara görüntü tabanlı otonom kilitlenme

Yarışma alanındaki QR kod tabanlı yer hedefine otonom kamikaze kilitlenmesi

Yarışma sunucusuna anlık telemetri, kilitlenme ve kamikaze verisi gönderimi

Hava savunma sistemi (HSS) bölgelerinden kaçınma için akıllı görev planlama ve kaçınma algoritmaları

Kullanıcı dostu bir Yer Kontrol İstasyonu (YKI) arayüzü

geliştirilmektedir.

### 🧩 **Görevler ve Yetenekler**

Bu proje, yarışmanın iki ana görevini destekleyecek şekilde tasarlanmıştır:

**Savaşan İHA Görevi**

Otonom kalkış / otonom uçuş / otonom kilitlenme (hava aracı) / otonom iniş

Rakip İHA’nın görüntüde belirli bir dikdörtgen içinde en az 4 saniye tutulmasıyla kilitlenme/vuruş tespiti

Hedefin görüntüde en az %5’lik alanı kaplamasını takip eden görüntü işleme algoritmaları

Kilitlenme anında hem yarışma sunucusuna paket gönderimi hem de video kaydı

**Kamikaze İHA Görevi**

Otonom kalkış / otonom uçuş / yer hedefine otonom kilitlenme (QR kod) / otonom iniş

Yarışma alanındaki sabit QR hedefinin tespit edilmesi ve içeriğindeki metnin sunucuya iletilmesi

Hedefe dalış sırasında irtifa ve sınır kurallarına uyum, kamikaze sürecinin video ile belgelenmesi

Bunlara ek olarak sistem, yarışma sunucusu üzerinden sağlanan hava savunma sistemi ve sinyal karıştırma bölgeleri bilgilerini alıp bu bölgelerden kaçınarak uçuş rotasını dinamik olarak güncelleyebilmek üzere tasarlanmıştır.

**Yarışma Sunucusu ile Haberleşme**

Yarışma sırasında tüm takımlar, telemetri gönderimi ve diğer takımların konum bilgilerini alabilmek için yarışma sunucusu ile JSON tabanlı HTTP API üzerinden haberleşmek zorundadır.

Sunucu tarafında kullanılan temel uç noktalar:

*POST /api/giris*

Amaç: Takım kullanıcı adı ve şifresi ile oturum açmak

Doğru girişte takım numarası döner; hatalı girişte 400 kodu

*GET /api/sunucusaati*

Amaç: Sunucu saatini almak ve uçuş bilgisayarının saatini bu saate göre kalibre etmek

*POST /api/telemetri_gonder*

Amaç: İHA enlem, boylam, irtifa, dikilme, yönelme, yatış, hız, batarya, otonom bayrağı ve kilitlenme durumunu içeren telemetriyi saniyede 1–5 Hz arası sunucuya göndermek

Cevapta: Sunucu saati + diğer takımların konumları ve zaman farkı bilgileri gelir

*POST /api/kilitlenme_bilgisi*

Amaç: Başarılı kilitlenme sonrası, kilitlenme bitiş zamanı ve otonom/manuel kilitlenme bilgisini sunucuya iletmek

*POST /api/kamikaze_bilgisi*

Amaç: Kamikaze görevi bitiminde, kamikaze başlangıç/bitiş zamanları ve okunan QR metnini sunucuya bildirmek

*GET /api/qr_koordinati*

Amaç: Kamikaze görevi için kullanılacak QR hedefinin enlem/boylam bilgilerini almak

*GET /api/hss_koordinatlari*

Amaç: Hava Savunma Sistemi (HSS) koordinatları ve yarıçaplarını almak; aktif HSS bölgelerinden kaçınmak için kullanılır

Bu uç noktalar için örnek JSON gövdeleri ve cevaplar, yarışma Haberleşme Dökümanında verilmiştir; projedeki onboard/comm veya benzer modül bu formatı birebir uygulamalıdır.

## TOROS SİHA Takımı

Üniversite: Akdeniz Üniversitesi

Danışman: Dr.Ögr.Yalçın Albayrak

Takım Kaptanı: İbrahim Buğra Tekinli

Yazılım Kaptanı: Tayfun Akay Çınar

Mekanik Kaptanı: Khaled Balali
