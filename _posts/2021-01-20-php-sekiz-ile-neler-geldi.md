---
id: 382
title: PHP 8 ile gelen yeni özellikler ve fonksiyonlar
date: 2021-01-20T08:58:51+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2021-01-20-php-sekiz-ile-neler-geldi
categories:
  - PHP
  - Yazılım
---

PHP ilk çıktığında şu an olduğu kadar mükemmel değildi. Geçen Yıllar ve kitlesi PHP&#8217;yi bu hale getirdi. Artık yeni bir major versiyonumuz var. Hadi gelin yeniliklere beraber göz gezdirelim.  
Ayrıca şunu belirtmeliyim ki sürüm güncellemesi yapmadan önce değişikliklerin listesine bakmanız yararınıza olacaktır. Buna [bu bağlantı](https://www.php.net/manual/tr/migration80.php)dan ulaşabilirsiniz.

## Named Arguments (Adlandırılmış Argümanlar)

PHP 8 ile gelen sanırım en güzel özellik bu olabilir. Normal&#8217;de bir fonksiyonu kullanırken doldurmak istediğimiz bir argümanın sırası gelene kadar uğraşmamız gerekiyordu. Bu yeni gelen özellikle birlikte buna gerek kalmıyor. Argümanın ismini kullanarak direkt olarak o argümanı kullanabiliyorsunuz. Örnekle göstermek gerekirse;

{% highlight php %}
// önceden pozisyonel argümanları kullanıyorduk ve 
// istediğimiz argümanı kullanmak için birazcık uğraşmamız gerekiyordu.
array_fill(0, 100, 50);

// fakat artık istediğimiz argümanı doldurabiliriz.
array_fill(start_index: 0, num: 100, value: 50);
// veya bu şekilde kullanabiliriz.
array_fill(value: 50, num: 100, start_index: 0);
{% endhighlight %}

## Attributes {#h-attributes}

PHPDoc yorum satırları yerine PHP Söz dizimi ile yapılandırılmış metadata kullanılabiliyor. Yani şu şekilde;

{% highlight php %}

# eskiden

class AboutPage extends AbstractController {
/\*\*
_ @Route("/about")
_/
public function page() {}
}

# şimdi ise

class AboutPage extends AbstractController { #[Route(&#39;/about&#39;)]
public function page() {}
}
{% endhighlight %}

## Construct&#8217;ta değişken tanımlamak (Constructor property promotion)

Biliyorsunuz ki önceden bir sınıf içerisinde değişken oluşturduktan sonra this->değişken = veri şeklinde verileri atıyorduk. Artık böyle bir şeye ihtiyacımız yok! Hemen örnekle göstereyim.

{% highlight php %}

# eskiden

class Point {
public float $x;
public float $y;
public float $z;

    public function __construct(
        float $x = 0.0,
        float $y = 0.0,
        float $z = 0.0,
    ) {
        $this-&gt;x = $x;
        $this-&gt;y = $y;
        $this-&gt;z = $z;
    }

}

# şimdi ise

class Point {
public function \_\_construct(
public float $x = 0.0,
public float $y = 0.0,
public float $z = 0.0,
) {}
}
{% endhighlight %}

Gördüğünüz gibi inanılmaz pratikleşti.

## Union types (Birleşim türleri)

Artık değişken türlerinin kombinasyonu için PHPDoc açıklamaları yerine çalışma zamanında doğrulanan union types tanımlamaları kullanılabiliyor.

{% highlight php %}

# eskiden

class Number {
/\*_ @var int|float _/
private $number;

/\*\*

- @param float|int $number
   */
  public function __construct($number) {
  $this-&gt;number = $number;
  }
  }

new Number(&#39;NaN&#39;); // Ok

# şimdi ise

class Number {
public function \_\_construct(
private int|float $number
) {}
}

new Number(&#39;NaN&#39;); // TypeError
{% endhighlight %}

## Match expression (Eşleşme İfadesi)

Eşleşen veriye göre veri döndüren switch benzeri bir ifade geldi. Verinin durumuna göre veri döndürdüğü için belki dil değiştirme benzeri sistemlerde kullanılabilir. Kesinlikle işlevsel olduğunu düşünüyorum.

{% highlight php %}
$yaş = 23;

$result = match (true) {
$yaş &gt;= 65 =&gt; &#39;yaşlı&#39;,
$yaş &gt;= 25 =&gt; &#39;yetişkin&#39;,
$yaş &gt;= 18 =&gt; &#39;genç&#39;,
default =&gt; &#39;çocuk&#39;,
};
{% endhighlight %}

## Nullsafe Operatörü

Bu operatörle birlikte büyük bir dertten kurtulacaksınız. Aslında isminde gizli işlevi. Eğer varsa kullan gibi veya eğer varsa ilerle fakat çok daha pratik bir şekilde, hemen kodu inceleyelim:

{% highlight php %}

# eskiden

$country = null;

if ($session !== null) {
$user = $session-&gt;user;

if ($user !== null) {
$address = $user-&gt;getAddress();

    if ($address !== null) {
      $country = $address-&gt;country;
    }

}
}

# şimdi ise

$country = $session?-&gt;user?-&gt;getAddress()?-&gt;country;
{% endhighlight %}

Gördüğünüz gibi muhteşem !

## Dize içinde, Dize sonu, Dize Başı Fonksiyonları

Fonksiyonların isminden de anlayacağımız üzere dize üzerinde yapabileceğimiz bir kaç özellik sunuyor. Dize içinde bir iğne ararken strpos kullanmak zorunda kalmayacağız. Yani şundan kurtuluyoruz:

{% highlight php %}

# eskiden

if(strpos(&#39;Kek yapmak için gereken tek şey ilham !&#39;, &#39;ilham&#39;) !== false):

# şimdi ise

if(str_contains(&#39;Kek yapmak için gereken tek şey ilham !&#39;,&#39;ilham&#39;)):
{% endhighlight %}

Ayrıca diğer fonksiyonlarda şöyle;

{% highlight php %}
str_starts_with(&#39;Liberta&#39;, &#39;Lib&#39;) // true döndürür.
str_ends_with(&#39;Liberta&#39;, &#39;a&#39;) // true döndürür.
{% endhighlight %}

## JIT yada Just in Time Compiler (Son Dakika Derleyicisi)

Bu sanırım en büyük yenilik sayılabilir. Bu yenilikle birlikte PHP Run time bir dil olmaktan çıkıyor. Peki Runtime neydi? çalıştığı anda yorumlanan bir dile Run Time dil denir. JIT ile birlikte makine diline derlenerek yorumlanmaya başlıyor.  
Bu ise performansı etkiliyor ve geliştiriyor fakat OPCache üzerinden aktif etmeliyiz. Yoksa büyük ihtimalle hız ve performansta artış göremeyebiliriz.

## Sonuç

Benim gözüme çarpan yenilikler bunlar. Açıkcası daha bir çok yenilik var ve bunun için RFC PHP&#8217;yi takip etmenizi öneririm. Ayrıca tek satır fonksiyon konusunda ümitliyim. Umarım gelir 🙂
