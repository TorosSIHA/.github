# TOROS SİHA – Savaşan İHA 2025 Projesi

Bu depo, TEKNOFEST 2025 Savaşan İHA Yarışması kapsamında geliştirilen TOROS SİHA insansız hava aracı yazılımını ve yer istasyonu altyapısını içerir. Projenin hedefi, sabit kanatlı İHA’mızın tamamen otonom şekilde kalkış yapabilmesi, havada rakip İHA’lara kilitlenebilmesi, yer hedefi üzerindeki QR koduna kamikaze dalışı gerçekleştirebilmesi ve güvenli şekilde otonom iniş yapabilmesidir. Tüm bu görevler sırasında yarışma sunucusu ile gerekli temel veri alışverişi de sağlanır.

## 🎯 Projenin Amacı

Savaşan İHA yarışması; hava–hava ve hava–yer muharebe senaryolarını kontrollü bir ortamda simüle ederek, yüksek otonomiye sahip İHA’lar geliştirilmesini hedefler. Bu kapsamda TOROS SİHA projesi, görüntü işleme, hedefe kilitlenme, görev planlama, otonom uçuş ve yer istasyonu arayüzü gibi bileşenlerin tamamını uçtan uca tek bir sistemde birleştirmeyi amaçlar.

Proje kapsamında havadaki diğer İHA’lara görüntü tabanlı otonom kilitlenme, yarışma alanındaki sabit QR hedefe kamikaze kilitlenmesi, hava savunma sistemi (HSS) bölgelerinden kaçınma ve yarışma sunucusu ile haberleşme yetenekleri geliştirilmektedir. Tüm bu süreçler, operatörün durumu net şekilde takip edebileceği kullanıcı dostu bir Yer Kontrol İstasyonu (YKI) arayüzü üzerinden yönetilir.

## 🧩 Görevler ve Yetenekler

### Savaşan İHA Görevi

Savaşan görevinde İHA, burnuna sabitlenmiş bir kameradan aldığı görüntü ile rakip İHA’ları tespit eder ve belirli bir dikdörtgen alan içerisinde belirli bir süre boyunca tutarak “kilitlenme/vuruş” gerçekleşmesini sağlar. Bu sırada İHA; otonom kalkış, rota takibi ve otonom iniş görevlerini de yerine getirir.

Görüntü işleme modülü, rakip hava aracının görüntüde yeterli alan kaplamasını takip eder ve kilitlenmenin geçerli sayılması için gerekli süre ve alan koşullarını gözetir. Geçerli bir kilitlenme gerçekleştiğinde bu olay hem uçuş kaydına hem de yarışma sunucusuna raporlanır; eş zamanlı video kaydıyla hakem değerlendirmesi desteklenir.

### Kamikaze İHA Görevi

Kamikaze görevinde İHA, otonom kalkış ve seyir sonrasında yarışma alanındaki sabit QR hedefinin bulunduğu koordinasyona gider. Hedefe yaklaşırken kamera görüntüsü üzerinden QR kodu tespit eder, içeriğini okur ve dalış sürecini video ile kaydeder. QR içeriği ve dalış zamanı, görev tamamlandıktan sonra yarışma sunucusuna bildirilir.

Bu görevde amaç, uçuş zarfı (irtifa ve sınır kuralları) içinde kalırken doğru zamanda dalışa girip QR kodunu güvenilir şekilde okuyabilecek bir yaklaşma profili oluşturmaktır. Kamikaze dalışı sonrasında güvenli bir otonom inişle görev sonlandırılır.

### Hava Savunma Sistemi (HSS) ve Görev Planlama

Yarışma senaryosunda belirli zamanlarda aktifleştirilen HSS ve sinyal karıştırma bölgeleri, sanal “uçuşa yasaklı” alanlar oluşturur. TOROS SİHA yazılımında, bu bölgelerin koordinatlarını yarışma sunucusundan alıp güncel uçuş planına entegre eden ve İHA’nın bu alanlara girmesini engelleyen kaçınma algoritmaları tasarlanmaktadır. Böylece İHA hem Savaşan hem Kamikaze görevlerini bu kısıtlar altında yerine getirebilecek şekilde rota güncellemesi yapar.

## 🌐 Yarışma Sunucusu ile Haberleşme

TOROS SİHA, TEKNOFEST Savaşan İHA Haberleşme Dokümanı ile uyumlu, hafif bir HTTP tabanlı haberleşme katmanı içerir. Bu katmanın temel işi, uçuşun durumunu yarışma sunucusuna bildirmek ve senaryoya ait kritik bilgileri almaktır.

## 👥 TOROS SİHA Takımı

- **Üniversite:** Akdeniz Üniversitesi  
- **Danışman:** Dr. Öğr. Üyesi Yalçın Albayrak  
- **Takım Kaptanı:** İbrahim Buğra Tekinli  
- **Yazılım Kaptanı:** Tayfun Akay Çınar  
- **Mekanik Kaptanı:** Khaled Balali  
