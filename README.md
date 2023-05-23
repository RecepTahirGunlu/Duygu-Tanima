# Duygu-Tanima
Çalışmamız Fer2013 veriseti ile elde ettiğimiz yüz verilerini kullanarak derin öğrenme methodları ile sınıflandırmayı amaçlamaktadır.
Fer2013 verisetini kaggle platformu kullanılarak elde edilmiştir. Veriseti 7 sınıftan oluşmaktadır.
<ul>
  <li>Angry</li>
  <li>Disgust</li>
  <li>Fear</li>
  <li>Happy</li>
  <li>Neutral</li>
  <li>Sad</li>
  <li>Surprise</li>
</ul> 

Verisetinden elde ettiğimiz yüz görüntülerini kendi derin öğrenme modelimizi oluşturarak yüksek bir başarı ile sınıflandırmayı amaçlamaktayız.
<hr>
<H2>Kullanılması Planlanan Algoritmalar</h2>
Problemin çözümü için oluşturduğumuz algoritmamız Veri Ön İşleme, Filtreleme, Derin Öğrenme Modelinin Oluşturulması, Sonuçların Alınması ve Değerlendirilmesi olmak üzere 4 aşamadan
oluşmaktadır.
<br><br>

<h3>Veri Ön İşleme Aşaması</h3>
Projemizin ilk aşamasında verilerimizi derin öğrenme ile sınıflandırma için uygun hale getirme amacıyla train test ve validation olarak 3 klasor halinde parçalara ayırdık. Daha sonrasında eksik olan verilerimizi diğer sınıflar ile denk hale getirmek için disgust sınıfına veri çoğaltma(data augmentation) işlemi uyguladık. Bu işlem ile sınıflandırma sırasında karşımıza çıkabilecek sorunların önüne geçmeyi amaçlamaktayız. 
<br><br>

Train, test ve validation için ayrı ayrı uyguladığımız veri çoğaltma işlemi ile disgust sınıfında bulunan görüntülerin sayısını 9 katına çıkarttık, bu sayede görüntü sayısını diğer sınıfların görüntü sayısına yaklaştırmış olduk. 
<br><br>
Veri çoğaltma işlemi için kullandığımız yöntemler:
<ul>
  <li>Sağ-Sol Öteleme</li>
  <li>Ters Döndürme</li>
  <li>Parlaklık</li>
  <li>Yaklaştırma</li>
</ul> 
Bu yöntemler `from keras.preprocessing.image import ImageDataGenerator` classı kullanılarak yapılmıştır.
<br><br>

<h3>Görüntülerin Filtrelenmesi</h3>
Verisetinden elde ettiğimiz görüntülere filtre uyguladığımız aşamadır. Kullandığımız filtreler ve kullanım amaçları aşağıda verilmiştir.
<ul>
  <li>Yumuşatma (Smoothing) Filtresi: Yüzdeki kırışıklıkları, lekeleri veya diğer küçük detayları gidermek için kullanılmıştır.</li>
  <li>Kontrast Artırma Filtresi: Yüzdeki kontrastı artırarak ayrıntıları daha belirgin hale getirmesi amaçlanmıştır.</li>
  <li>Işıklandırma Düzeltme Filtresi: Yüzdeki ışıklandırma dengesizliklerini gidermek ve yüzün daha doğal görünmesini sağlamak için kullanılmıştır.</li>
</ul> 
Kullanılan filtreler verisetinde bulunan bütün görüntülere uygulanmıştır.
<br>
![filter](https://github.com/RecepTahirGunlu/Duygu-Tanima/assets/94441940/c9805701-ab86-45b2-9211-5bdb771de80b)



<br><br>
Projemizin şuanda 2. aşamasını tamamlamış bulunmaktayız ve derin öğrenme modelimizi oluşturmak için çalışmalar yapmaktayız.
