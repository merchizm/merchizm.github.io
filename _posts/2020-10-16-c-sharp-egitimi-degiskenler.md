---
id: 260
title: 'C# Eğitimi : Değişkenlerin Tanımı ve Kullanımı'
date: 2020-10-16T21:48:02+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-10-16-c-sharp-egitimi-degiskenler
categories: ['C#', Yazılım]
tags: [ c sharp değişkenler, 'c#' ,'c# değişkenler' ,'c# değişkenler detaylı anlatım' ,'c# eğitimi' ,yazılım geliştirme]
---
 

Herkese merhaba arkadaşlar, bu gün C# eğitiminin ilki olan değişkenler konusunu işleyeceğiz. Değişkenler, hafızada veri tipine ve boyutuna göre yer kaplayan yapılardır. Uygulamamızda atanan 2 değeri türüne göre toplayabilir,birleştirebilir veya çıkarabilir,bölebilirsiniz. Program içerisinde istediğiniz yerde değişkeni tanımlayıp, istediğiniz yerde ise değiştirebilirsiniz.

Öncelikle değişken tanımlarken uymamız gereken bir kaç kural var, sırasıyla değinelim ;

  * Değişken tanımlarken boşluk kullanılmaz. Gerekli durumlarda boşluk kullanmak yerine alt çizgi (_) ile kelimeler birleştirilebilir.
  * Değişken tanımlarken Türkçe ve özel harfler kullanılmaz. (Örn: ö,ü,ğ,?,!,@)
  * Değişken tanımlarken ilk karakter her zaman harf olmalıdır, sayı ile başlayan bir değişken tanımlanamaz.

<blockquote class="wp-block-quote">
  <p>
    <em><strong>Dip Not:&nbsp;</strong>Değişken tanımlarken&nbsp;büyük-küçük harf kullanımına dikkat ediniz. Değişken isimleri büyük-küçük harf duyarlıdır.Yani deli ile DELI aynı değişken sayılmaz.</em>
  </p>
</blockquote>

### C#: **Değişken Türleri** {#h-c-de-i-ken-t-rleri}

Değişkenler barındırdıkları veriyle göre türden türe değişir. İçinde sayı barındıran bir değişken double,int,short,long türünde olabilirken true veya false değerini döndüren&nbsp;checkbox kontrolünün verisi ise bool türündeki bir değişken tarafından barındırılır.<figure class="wp-block-table">

<table>
  <tr>
    <td>
      <strong>Değişken</strong>
    </td>
    
    <td>
      <strong>Boyut</strong>
    </td>
    
    <td>
      <strong>Değer</strong>
    </td>
  </tr>
  
  <tr>
    <td>
      Bool
    </td>
    
    <td>
      1 Byte
    </td>
    
    <td>
      True yada false
    </td>
  </tr>
  
  <tr>
    <td>
      Byte
    </td>
    
    <td>
      1 Byte
    </td>
    
    <td>
      Minimum 0, Maximum 255
    </td>
  </tr>
  
  <tr>
    <td>
      Char
    </td>
    
    <td>
      2 Byte
    </td>
    
    <td>
      Unicode tek karakter
    </td>
  </tr>
  
  <tr>
    <td>
      Decimal
    </td>
    
    <td>
      12 Byte
    </td>
    
    <td>
      &nbsp;Minimum “-7.9 x 1028”, Maximum “+7.9 x 1028”
    </td>
  </tr>
  
  <tr>
    <td>
      Double
    </td>
    
    <td>
      8 Byte
    </td>
    
    <td>
      &nbsp;Minumum “±5.0 × 10−324”, Maximum ±1.7 × 10308
    </td>
  </tr>
  
  <tr>
    <td>
      Int
    </td>
    
    <td>
      4 Byte
    </td>
    
    <td>
      &nbsp;Minimum “-2,147,483,648”, Maximum “2.147.483.647”
    </td>
  </tr>
  
  <tr>
    <td>
      Short
    </td>
    
    <td>
      2 Byte
    </td>
    
    <td>
      &nbsp;Minimum “-32.768”, Maximum “32.767”
    </td>
  </tr>
  
  <tr>
    <td>
      long
    </td>
    
    <td>
      8 Byte
    </td>
    
    <td>
      &nbsp;Minimum “-9,223,372,036,854,775,808”,&nbsp; Maximum “9,223,372,036,854,775,807”
    </td>
  </tr>
  
  <tr>
    <td>
      float
    </td>
    
    <td>
      4 Byte
    </td>
    
    <td>
      &nbsp;Minimum “-3.4 × 10<sup>38&nbsp;</sup>“, Maximum “+3.4 × 10<sup>38&nbsp;“</sup>
    </td>
  </tr>
  
  <tr>
    <td>
      string
    </td>
    
    <td>
      –
    </td>
    
    <td>
      &nbsp;Maximum 2,147,483,647 Unicode Karakter tutar
    </td>
  </tr>
</table><figcaption>

_**Dip Not:**&nbsp;Int16, Int32, Int64 tipleri .NET veri tipleridir ve C# karşılıkları short, int, long veri tipleridir._</figcaption></figure> 

Yukarıdaki tabloda veri tiplerini, veri tiplerinin RAM’de kapladığı alanı ve alabileceği maximum/minimum değerleri görmekteyiz.

### **Değişken Tanımlama** {#h-de-i-ken-tan-mlama}

Değişkeni tanımlar iken dikkat etmemiz gereken unsurlar vardır. Veri tipini belirledikten sonra değişkene vereceğimiz ismi belirliyoruz. Örnek olarak kullanıcının yaşını tutmak istiyoruz. Short veri tipi hem az yer kaplayıp hemde bizim isteyeceğimiz aralıkta bir kapasitesi var. Şimdi aşağıdan nasıl değişken oluşturmanız gerektiğine bakabilirsiniz.

`<Veri Tipi> <Değişken ismi>;`

Değişkeni sadece oluşturmak için yukarıdaki komut yeterli birden fazla aynı türde değişken oluşturmak için ise,

`<Veri Tipi> <Değişken Adı>, <Değişken Adı 2>, <Değişken Adı 3>;`

Yapmanız gerekmektedir. İsterseniz veriyi oluştururken aynı anda ona veri atayabilirsiniz ama birden fazla oluşturulmuş değişkenlere veri atamak için tek tek yazmanız gerekir. Aşağıdan değişkeni hem oluşturup hemde nasıl veri ataya bileceğinize bakabilirsiniz.

`<Veri Tipi> <Değişken ismi> = <İçerik>;`

Tabi ki her şeyin kuralları olduğu gibi değişken ismi koyarken de bir takım kurallara uymamız gerekmektedir. Değişken ismi sayı ile veya farklı bir karakter ile başlayamaz ayrıca[ C# anahtar sözcükleri](https://merich.rocks/url/3ce661) değişken ismi olarak kullanılamaz.  Anahtar sözcüklerine bakmak için[ tıkla](https://merich.rocks/url/3ce661)yınız. Aşağıda nasıl değişken oluşturulduğuna bakabilirsiniz.

{% highlight c-sharp %}
string Isimsoyisim = "İsim Soyisim";
string dogumtarihi = "1991.11.11";
short yas = "11";
double kilo = 60.40;
double boy = 1.78;
bool iookul = false;
bool lise = true;
{% endhighlight %}


Ayrıca değişkenler oluşturulduğu yere göre farklı alanlarda kullanılabilir veya kullanımı kısıtlanabilir. Her yerde kullanabildiğimiz değişkenlere ise Global Değişken deriz.<figure class="wp-block-image size-large is-style-default">

<img loading="lazy" width="725" height="382" src="assets/uploads/2020/11/Screenshot_2-1.png" alt="" class="wp-image-302" /> 

### **Değişkene Değer Atama** {#h-de-i-kene-de-er-atama}

Tanımlanmış bir değişkenin değerini değiştirmek için sadece değişken ismi ve değer ataması yapmak için ise eşittir (=) kullanılır.Bir değişkene değer atama değişkeni tanımlarken veya farklı bir satırda yapılabilir.

`<değişken adı> = 5;`&nbsp;Int türüne sahip bir değişkenine böyle değer atarız.&nbsp;`<değişken adı> = "metin 123";`&nbsp;String türüne sahip bir değişkenede bu şekilde değer atarız ama unutmayın değişkenin önceden tanımlanmış olması gerek.

<blockquote class="wp-block-quote">
  <p>
    <strong><em>Dip Not:</em></strong><em>Float ve decimal tipindeki değişkenlere değer atanırken verilen değerden sonra bir son ek kullanılır. Float tipi için f ya da F, decimal tipi için m ya da M kullanılır, bu eklerden önce boşluk bırakılmaz ve&nbsp;ondalık sayılarda ondalık kısmı ayırırken nokta kullanılmalıdır.</em>
  </p>
</blockquote>

Anlamadığınız bölüm olursa yorum kısmına yazmayı unutmayın.