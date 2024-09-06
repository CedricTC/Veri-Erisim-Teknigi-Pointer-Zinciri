# 1. Giriş
Bu rapor, veritabanı sistemlerinde kullanılan pointer zinciri veri erişim tekniğini tanımlamaktadır. Pointer zinciri, veri erişimini optimize etmek ve ilgili tablolar arasındaki veri ilişkilerini etkili bir şekilde yönetmek için kullanılan bir yöntemdir. 

Veritabanları genellikle karmaşık veri yapıları içeren sistemlerdir ve verilerin verimli bir şekilde yönetimi ve erişimi hayati öneme sahiptir. Pointer zinciri veri erişim tekniği, farklı tablolardaki veriler arasında ilişkiler kurarak veri erişimini kolaylaştırır ve sorgu işlemlerini optimize eder.


# 2. Veritabanında Pointer Zinciri 
Pointer zinciri, bellekteki veriye erişmek için birbirine bağlı pointer'ların (göstericiler) kullanıldığı bir programlama terimidir. Bu, pointer'ların birbirine bağlandığı ve dolaylı olarak verilere erişim sağladığı bir veri yapısıdır.
Örneğin, bir restorana gittiğinizi ve garsondan sipariş verdiğinizi hayal edin. Garson, siparişinizi kaydetmek ve mutfağa iletmek için bir pointer zinciri kullanabilir. Bu pointer, sipariş ve müşteri bilgilerini temsil eder ve mutfak bölümüne gönderilir. Şef, bu pointer'ı kullanarak siparişi hazırlar. Sipariş hazırlandığında, pointer sonraki adıma yönlendirilir, örneğin servis bölümüne gönderilir ve garson doğru siparişi zinciri takip ederek alır ve müşteriye servis eder.
Yukarıdaki örnekte gösterildiği gibi, bir dizi içindeki elemanlara pointer zinciri kullanarak erişebilirsiniz. İlk pointer, dizinin ilk elemanını işaret eder ve sonraki pointer'lar diğer elemanlara erişmek için kullanılır. Bu şekilde, zincirleme pointer'lar dizi içindeki verilere erişmek için kullanılır.

Bir pointer başka bir pointer'ı işaret ettiğinde ve bu pointer da başka bir pointer'ı işaret ettiğinde zincir oluşur. Bu teknik, verilerin fiziksel depolama konumlarına bakılmaksızın verilere erişimi mümkün kılar. Veritabanındaki veriler fiziksel olarak farklı bloklara dağıtılabilir, ancak pointer zinciri bu bloklara erişimi basitleştirir.


![Deneme](image/deneme.png)



## Avantajları:
- **Esneklik:** Veriler arasındaki ilişkileri esnek bir şekilde temsil eder.
- **Veri Bağlantılarını İzleme:** İlgili verilere erişmek için pointer'ların izlenmesini sağlar.
- **Bellek Verimliliği:** Gerçek veri yerine pointer kullanarak bellek kullanımını optimize eder.

## Dezavantajları:
- **Hatalara Duyarlılık:** Yanlış pointer kullanımı veya zincirin yanlış izlenmesi hatalara yol açabilir.
- **Karmaşıklık:** Karmaşık veri yapıları veya ilişkiler olduğunda kod karmaşıklığını artırabilir.
- **Bellek Sorunları:** Yanlış pointer kullanımı veya hatalı referanslar bellek hatalarına neden olabilir.

Örneğin, bir e-ticaret platformunun veritabanında iki tablo olduğunu varsayalım: "Ürünler" ve "Siparişler."

### "Ürünler" Tablosu:
| Ürün ID | Ürün Adı   | Fiyat  |
|---------|------------|--------|
| 1       | Telefon    | 1000   |
| 2       | Bilgisayar | 2000   |
| 3       | Televizyon | 1500   |

### "Siparişler" Tablosu:
| Sipariş ID | Müşteri ID | Ürün ID |
|------------|------------|---------|
| 101        | 1          | 2       |
| 102        | 2          | 1       |
| 103        | 1          | 3       |

Bu senaryoda, "Siparişler" tablosu, "Ürünler" tablosunu işaret eden bir pointer içerir.

Sipariş ID'si 101 olan bir siparişin ürün bilgilerine erişmek istediğinizi varsayalım.
"Siparişler" tablosunda Sipariş ID'si 101 olan satıra gidin ve ilgili "Ürün ID" alanını kontrol edin. Bu alan, "Ürünler" tablosundaki ilgili ürüne işaret eden bir değeri içermelidir.Pointer'ı takip ederek, ilgili ürünün bilgilerine erişebilirsiniz. Bu durumda, Ürün ID'si 2 olan ürünü, yani "Bilgisayar"ı elde edersiniz.



