
## <a name="4"></a> Araştırma Projesi 4

- Property Animation ile ilgili olarak objectAnimator ile animator arasındaki farkı kısaca açıklayınız

### animator ve objectAnimator Kavramları

Animasyonları, kaynak dosyası şeklinde (xml) veya programmatically dediğimiz yani kotlin kodları sayesinde oluşturabilir ve uygulayabiliriz. Property animation 
oluştururken kullandığımız 3 adet sınıf vardır. Bunlar ValueAnimator, ObjectAnimator ve AnimatorSet sınıflarıdır. Bu bilgilere ek olarak ObjectAnimator aslında ValueAnimator
sınıfından türetilmiş bir alt sınıftır.

ValueAnimator sınıfının kaynak dosyasındaki (xml) karşılığı animator etiketidir. ObjectAnimator sınıfının ise kaynak dosyasındaki karşılığı objectAnimator etiketidir.
Yani bu durumda aslında property animation oluştururken ValueAnimator sınıfı kullanımı ile ObjectAnimator sınıfı kullanımı farkını açıklamak da aslında <animator> 
ile <objectAnimator> etiketleri arasındaki farkı açıklamak ile eş değer olmaktadır.

Eğer ki propertyAnimation oluştururken ValueAnimator sınıfından faydalanıyorsak, addUpdateListener() fonksiyonunu kullanmalıyız. Bu fonksiyonda bulunan listener 
sayesinde animasyonumuzdaki değişken değerler (valueFrom, valuaTo) dinlenir. Ardından animasyon süresi boyunca değişmesini istediğimiz özelliğe bu değerler atanır.

 Aşağıdaki görselde bir textView görünümünün x ve y konumlarını 0 ile -200 değerleri arasında 3 saniye boyunca değiştirilmesi sağlanmıştır. Bu işlem için 0 ile -200 
 arasındaki değerler bir listener ile sürekli olarak dinlenerek, görünümün translationX ve translationY özelliklerine atanmıştır.
  
<img width="550" alt="valueAnimator" src="https://user-images.githubusercontent.com/61115571/165642790-28feb8a1-03b8-4e1c-9714-382dd6500936.png">
  
 Fakat ObjectAnimator sınıfını kullanırken bir listener ayarlayarak, bir görünümün değiştirilmesini istediğimiz özelliklerini manuel olarak güncellememize gerek yoktur. 
 Bu güncelleme işlemini kendisi otomatik olarak yapar. Çünkü ValueAnimator sınıfından farklı olarak başlangıç ve bitiş değerlerinin haricinde bir de hangi özelliğin 
 değişeceği ve bu özelliğin hangi görünüme uygulanacağı bilgilerini de parametre olarak alan değerlerin tiplerini belirlememizi sağlayan fonksiyonlara (ofFloat, ofInt vb.) sahiptir .

  Yukarıdaki işlemin aynısını ObjectAnimator ile yaparsak aşağıdaki görselde olduğu gibi kodlarımızı güncelleriz. Görüldüğü üzere ofFloat() fonksiyonu özellik ve görünüm bilgilerini
  de parametre olarak aldığından dolayı bir listener kullanmaya ihtiyaç kalmamıştır.
  
  <img width="745" alt="objectAnimator" src="https://user-images.githubusercontent.com/61115571/165643360-f6d40219-b365-4960-8477-cc9a75b100a6.png">
  
Animasyonlarımız kaynak kod şeklinde oluşturdupumuzda da yine animator etiketi ile oluşturuluşmuş animasyonlarımız için, animasyonu başlatmadan önce addUpdateListener() 
içerisinde  listener ile başlangıç ve bitiş değerlerini dinleyerek görünümün ilgili özelliğine atamalıyız. Fakat objectAnimator ile oluşturulmuş animasyonlar için bu gerekmiyor. 

  Örnek ugulama için aşağıdaki kodları inceleyebilirsiniz.
  
  #### animator
  
<img width="692" alt="valuanimatorXml" src="https://user-images.githubusercontent.com/61115571/165643846-1b1ed2c5-eec4-466d-bc6e-f0a5124ce977.png">
  
<img width="778" alt="valueAnimatorcode" src="https://user-images.githubusercontent.com/61115571/165643855-6e7a3ee7-271f-42d8-a5b4-f9d7c3af19f7.png">
  
 #### objectAnimator
  
  
<img width="645" alt="objectAnimatorXml" src="https://user-images.githubusercontent.com/61115571/165643922-989f50d0-66fe-49fb-a310-34ffdde5aa47.png">
  
<img width="836" alt="objectAnimatorcode" src="https://user-images.githubusercontent.com/61115571/165643926-30bd0aea-c8f8-48d8-9a9d-4c343a5b281f.png">
