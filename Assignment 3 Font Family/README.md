## <a name="3"></a> Araştırma Projesi 3

- Font family dosyası nasıl oluşturulup kullanıyoruz?
- Neden belirttiğiniz şekilde kullanımı tercih ediyoruz?

### Font Family Files

Font family, stil (fontStyle) ve ağırlık (fontWeight) özellikleriyle birlikte bir yazı tipi dosyası kümesidir. Android'de, bir XML kaynağı olarak yeni bir font family oluşturabiliriz. 
Bu sayede aslında her bir stile ve ağırlığa ayrı kaynaklar olarak başvurmak yerine tek bir kaynak üzerinden erişebiliriz. Bunu yaptığımızda ise sistem, kullanmaya çalıştığımız metin 
stiline göre otomatik olarak doğru yazı tipini ağırlık ve stil değerlerine göre seçebilir.

Font family dosyası oluşturmak için ilk olarak res klasörü altında “font” adlı yeni bir klasör oluşturmalıyız.
Res klasörü üzerinde sağ tuş -> new ->  Android resource directory dedikten sonra Resource type ‘ı font olarak seçip klasörümüzü oluşturuyoruz.

![ss1 1](https://user-images.githubusercontent.com/61115571/165630474-3647cec5-453f-4540-bdfe-de668d9441b5.jpg)

Ardından kullanmak istediğimiz font değerlerini indirdikten sonra direkt olarak sürükle-bırak veya kopyala-yapıştır yöntemleri ile font klasörümüze ekliyoruz.
Şimdi de font family dosyamızı oluşturmalıyız. 

Font klasörü üzerinde sağ tuş -> new -> Font resource file dedikten sonra dosyamıza isim veriyoruz. Genelde indirdiğimiz font adını veririz. 
Ardından bu xml dosyamız içerisine her yazı tipi için <font> etiketi içerisine stil, ağırlık ve font özelliklerini ekliyoruz.
  
  
![ss7](https://user-images.githubusercontent.com/61115571/165630793-d0f01dfc-4e6f-494e-93c2-0e8dc01d35bf.jpg)
  
![ss1 2](https://user-images.githubusercontent.com/61115571/165630893-2a805571-4a19-4cfb-819c-073836fba72e.jpg)
  
Daha iyi açıklamak gerekirse, örneğin siz istok web adında bir font kullanmak istiyoruz. Ama bu fontun yeri geldiğinde bold yeri geldiğinde italic veya regular 
halini kullanmak istiyoruz. Bunun için bold, italic ve regular olan fontları indiriyoruz. Ardından oluşturduğumuz font resource dosyası içerisinde her bir yazı tipi 
 için (regular, italic, bold) <font> etiketi içerisine stil, ağırlık ve font özelliklerini ekliyoruz.
  
Aslında artık bu dosyayı kullanmaya hazırız. Fakat bu işlemleri gerçekleştirdiğimizde aşağıdaki görselde görüldüğü gibi bir uyarı alacağız. 
Dosyamızı andorid namsespace’i (xlmns:andorid) ile oluşturduğumuzda API seviyesi 26 ve üzeri cihazlarda çalışacaktır. 
  
<img width="610" alt="Ekran Alıntısı" src="https://user-images.githubusercontent.com/61115571/165631357-d00075c4-ec80-419d-b099-8d83a4827d5e.PNG">
  
Bunu düzeltmek için uyarı önerisinde tıklayarak kaynağı geçersiz kılmayı (override resource in font v-26) seçebiliriz. Bunu yaptığımızda iki adet istokweb.xml dosyası
oluşacaktır. Bir tanesi API seviyesi 26 ve üzeri için diğeri ise API seviyesi 26’nın altı için. 

Oluşan dosyalarda v26 olan dosyada herhangi bir değişiklik yapmıyoruz. Diğer dosyamıza ise app namespace’i ekliyoruz. Bunu yaptığımız zaman aslında yazı tipini API 
seviyesi 26'nın altına ayarlayabilen destek kitaplığından(support library) yararlanmış oluyoruz.
  

<img width="916" alt="ss12345" src="https://user-images.githubusercontent.com/61115571/165631571-58afef1b-59c9-4c7f-ae20-7ae5d088c222.png">
  
 Artık kullanım için hazırız. Aşağıdaki görsellerde olduğu gibi istediğimiz görünüm için oluşturduğumuz font dosyamızı kullanabiliriz.

<img width="577" alt="a" src="https://user-images.githubusercontent.com/61115571/165632096-94c33a81-bf9b-4571-88f6-ad86ea038823.png">
  
<img width="577" alt="b" src="https://user-images.githubusercontent.com/61115571/165632097-016cc218-fec0-4426-8620-78ce6b7d4f36.png">
  
<img width="568" alt="c" src="https://user-images.githubusercontent.com/61115571/165632337-856b3f70-a24c-42dd-9e14-223c03b71486.png">
  
  
  Ek olarak aşağıdaki görselden hangi font stilinin hangi ağırlığa sahip olduğunu da görebilirsiniz.
  
  ![fontWeights](https://user-images.githubusercontent.com/61115571/165632519-14c50fe5-45d6-4246-b525-355d4f15def1.jpg)

  




