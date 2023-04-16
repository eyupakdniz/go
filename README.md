# go

Go (ya da Golang), Google tarafından geliştirilen bir programlama dilidir ve özellikle ağ uygulamaları ve web hizmetleri için tasarlanmıştır. Go, C dilinden etkilenerek tasarlanmış ve modern bir dil olarak düşük seviye programlama ve yüksek seviye programlama arasında bir denge sağlamayı amaçlamaktadır.

Go'nun birçok avantajı vardır ve bu nedenle birçok geliştirici tarafından tercih edilir. Bazı nedenleri şunlardır:

- Hızlı: Go, C++ veya Java gibi dillere kıyasla daha hızlı bir derleme sürecine sahiptir. Ayrıca, Go'nun hafif olması nedeniyle, uygulamalar daha hızlı çalışır ve daha az bellek tüketir.

- Paralel işleme desteği: Go, paralel işleme ve eşzamanlılık konusunda özel olarak tasarlanmıştır. Bu nedenle, Go ile çok sayıda işlemi aynı anda çalıştırmak kolaydır ve performans açısından daha iyi sonuçlar elde edilir.

- Kolay sözdizimi: Go, temiz ve basit bir sözdizimine sahiptir. Bu nedenle, özellikle yeni başlayanlar için kolay öğrenilebilir bir dildir.

- Bellek yönetimi: Go, bellek yönetimi konusunda otomatik bir araç sunar. Bu nedenle, bellekle ilgili sorunlarla karşılaşma olasılığı daha azdır.

- Güçlü standart kütüphane: Go'nun güçlü bir standart kütüphanesi vardır. Bu kütüphane, web uygulamaları, veritabanı işlemleri, ağ programlama, dosya işlemleri ve daha birçok konuda işinizi kolaylaştırır.

- Statik tip kontrolü: Go, statik tip kontrolüne sahiptir. Bu nedenle, kodunuzun daha az hata içermesi ve daha güvenli olması muhtemeldir.

Bu nedenlerden dolayı, Go genellikle ağ uygulamaları, web hizmetleri, veri işleme uygulamaları ve arka uç sistemleri için tercih edilir.


`var`<br>
- function içinde ve dışında tanımlanabilir
- tanımlandığı yerde ilk değeri vermek zorunda değiliz

`:=`<br>
- function içinde tanımlanır
- tanımlandığı yerde değer verilmeli


### Değişken Tanımlama
  `var s1 string = "metin"`<br>
  `var s2 = "metin2"`<br>
  `i1 := 2`<br><br>

### Çoklu Değişken Tanımlama
`var a, b, c int`<br>
`var a, b, c, d int = 1, 2, 3, 4`<br><br>
 
 
### İsim Tanımlama Kuralları
- _ veya harf ile başlamalı, sayı ile başlayamaz
- Variable adıda a-z,A-Z,0-9 ve _ kullanılabilir
- Küçük büyük harfe duyarlıdır.
- Variable adının boyutunun limiti yoktur
- Bir variable boşluk içeremez
- Go keyword'ü kullanılamaz<br><br>

`const`
- const ile sabit değer tanımalanabilir
- const ifade tanımlandığı yerde başlangıç değeri verilmeli
- Büyük harf ile isimlendirilir
- const function içinde veya dışında tanımlanabilir
- () içinde alt alta birden çok tanımlanabilir


### Static type
- Bir variable hep aynı type'a sahiptir.
- Üç tür static type vardır : bool, numeric, string

#### boolean
- bool şeklinde kullanılır
- true, false alır ve defaultu false'dır

#### Number
- signed veya unsigned şeklinde vardır

##### Signed Integers
- int şeklinde belirtilir
- Pozitif veya negatif olabilir

  * int => 2^32 ile -2^32 veya 2^64 ile -2^64 
  * int8 => 2^8 ile -2^8
  * int16 => 2^16 ile -2^16
  * int32 => 2^32 ile -2^32
  * int64 => 2^64 ile -2^64

##### Unsigned Integers
- uint şeklinde belirtilir
- sadece pozitif olabilir

  * uint => 2^32 ile 0 veya 2^64 ile 0 
  * uint8 => 2^8 ile 0
  * uint16 => 2^16 ile 0
  * uint32 => 2^32 ile 0
  * uint64 => 2^64 ile 0

##### Float
- Pozitif veya negatif noktalı sayılardır 

  * float32 => -3.4e+38 to 3.4e+38.
  * float64 => -1.7e+308 to +1.7e+308.

#### String
- "" arasına yazılır.
- Metin ifadeleri yazarken kullanılır.


### Array
- Bir variable içinde birden fazla variable tanımlamak için kullanırız
- var veya := şeklinde tanımalanabilir
- Dizi uzunluğu baştan belirtildiği 
- Index 0 dan başlar
- Dizinin bir noktası değiştirildiğinide orjinal dizi değişir
- len() methodu ile dizinin uzunluğuna ulaşılabilir

`var arr1 = [3]int{1,2,3}`<br>
`arr2 := [5]int{4,5,6,7,8}`<br><br>

- Array başlangıçta boyutu tanımlanmadan tanımlanabilir.<br>
`var arr1 = [...]int{1,2,3}`<br>
`arr2 := [...]int{4,5,6,7,8}`<br><br>

- Sadece belirli indexlere eleman atayarak array oluşturulabilir<br>
`arr1 := [5]int{1:10,2:40} //sadece 1. ve 2. indexlere eleman tanımlanır diğerleri default olarak 0 dır`<br><br>

Slices
- Arraya benzer.
- Bir dizinin alt kümesini oluşturmak için kullanırız.
- Dinamik olarak boyutlandırılabilir.
- Bir kaç şekilde tanımlanabilir.
  * []datatype{values}<br>
  `myslice := []int{}`<br><br>
  * diziden slice oluşturma<br>
  `var myarray = [length]datatype{values}`<br>
  `myslice := myarray[start:end]`<br><br>

  * make() ile<br>
  `slice_name := make([]type, length, capacity)`<br>
  `myslice1 := make([]int, 5, 10)`<br><br>

- Dizi uzunluğu len() veya cap() ile öğrenilebilir

#### `append()`
- Arrayin sonuna yeni eleman veya yeni dizi eklemek için kullanılır
- Bu şekilde dizi uzunluğu değiştirilmiş olur<br>

`slice_name = append(slice_name, element1, element2, ...)`<br>
`slice3 = append(array1, array2...)`<br><br>

#### `copy()`<br>
- Dizi büyükse ve yalnızca birkaç öğeye ihtiyacınız varsa, bu öğeleri copy() işlevini kullanarak kopyalamak daha iyidir.
- İki parametresi vardır, ikincisi array uzunluğunu döner.<br>

`copy(dest, src)`<br><br>


#### Arithmetic Operators<br>
`+` ->  Ekleme<br>
`-` ->  Çıkarma<br>
`*` ->  Çarpma<br>
`/` ->	Bölme<br>
`%` ->  Mod alma<br>
`++` ->	Arttırma<br>
`--` ->	Azaltma<br>

#### Assignment Operators<br>
`=`   ->   x = 5	<br>
`+=`   ->   x = x + 3	<br>
`-=`   ->   x = x - 3	<br>
`*=`   ->   x = x * 3	<br>
`/=`   ->   x = x / 3	<br>
`%=`   ->   x = x % 3	<br>
`&=`   ->   x = x & 3	<br>
`|=`   ->   x = x | 3	<br>
`^=`   ->   x = x ^ 3	<br>
`>>=`   ->   x = x >> 3	<br>
`<<=`   ->   x = x << 3<br><br>

#### Comparison Operators<br>
`==`   ->   Equal to			            	<br>
`!=`   ->   Not equal			            	<br>
`>`    ->   Greater than			        	<br>
`<`    ->   Less than			           	<br>
`>=`   ->   Greater than or equal to		<br>
`<=`   ->   Less than or equal to		 <br><br>


#### Logical Operators<br>
`&&`   ->   Logical and		<br>
`||`   ->   Logical or<br>
`!`    ->   Logical not<br><br>


#### Bitwise Operators<br>
`&`    ->   AND	<br>
`|`    ->   OR		<br>
`^`    ->   XOR	<br>
`<<`   ->   Zero fill left shift	<br>
`>>`   ->   Signed right shift<br><br>


### Loops
- Go'da sadece for ile döngü yapılır<br>
- Birkaç şekilde döngü tanımlanabilir.<br><br>
  - 1. yol<br>
  `for i:=0; i < 5; i++ {}`<br><br>
  
  - 2. yol<br>
  `i := 1`<br>
	`for i < 10{`<br>
			` fmt.Println(i)`<br>
			` i++`<br>
      ` }`<br><br>
    
#### Sonsuz döngü<br>
   `i := 1`<br>
	`for{`<br>
			` fmt.Println(i)`<br>
			` i++`<br>
      ` }`<br><br>
      
-Nested for'lar yazılabilir<br>
`for i:=0; i < 5; i++ {`<br>
    ` for j:=0; j < 5; j++ {`<br>
     `  fmt.Println(i,j)`<br>
    ` }`<br>
  ` }`<br><br>

#### continue 
- O bloktan çıkmamızı sağlar.

#### break 
- O bloğu kırar.




























