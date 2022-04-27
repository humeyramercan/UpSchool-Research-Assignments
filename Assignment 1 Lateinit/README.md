
## <a name="1"></a> Araştırma Projesi 1

- Lateinit neden kullanıyoruz?
- Lateinit kullanımından bahseder misiniz?
- Lateinit için bir örnek kullanım gösterir misiniz ?

### Lateinit

Kotlin'de, tanımlama işleminden sonra başlatılan değişkenler için lateinit anahtar sözcüğü kullanılır veya bir başka deyişle geç başlatılan değişkene lateinit değişkeni denir.

Lateinit anahtar sözcüğü, değişkenin kullanılmadan önce başlatılacağından emin olduğumuzdakullanılır. Bir lateinit değişkenini kullanmadan önce başlatmazsak “lateinit property has not been
initialized” hatası alırız. 

lateinit değişkenini kullanmadan önce isInitialized() yöntemi yardımıyla başlatılıp başlatılmadığını kontrol edebiliriz. Bu yöntem, lateinit özelliği başlatılmışsa true değerini
döndürür, aksi takdirde false döndürür.

Örneğin uygulamamızda en yüksek skoru tutacağımız bir SharedPreferences yapısı kullanacağız. Bu yapıyı ana fonksiyonumuzun dışında lateinit olarak tanımlayarak aslında “şu an değer atamasam da
sonrasında kesin olarak bu değişkeni tanımlayacağım” diyoruz. Ardından da onCreate() altında oluşturduğumuz sharedPreferences’ımızı başlatabiliyoruz.

Veya haritalar ile ilgili bir uygulama yapacağız. Bunun için de locationManager ve locationListener yapılarına ihtiyacımız var. Bu yapıları lateinit olarak tanımlayıp sonrasında onMapReady() altında bu
yapıları nerede kullanacaksak orada başlatabilir ve kullanabiliriz.

Örnek kullanımlar için aşağıdaki görselleri inceleyebilirsiniz.

![ss2](https://user-images.githubusercontent.com/61115571/165557484-f1a9e517-1e0e-4af2-aa9d-94cec5dd04da.jpg)

![ss3](https://user-images.githubusercontent.com/61115571/165557655-acc0e0ca-3a99-4eab-8ea5-c7c59c4ee957.jpg)


![ss4](https://user-images.githubusercontent.com/61115571/165557667-5134bb77-f371-4935-ae1b-b6c3087851b9.jpg)
