---
id: 377
title: Mutlaka bilmeniz gereken 7 Javascript İpucu
date: 2020-12-29T16:33:16 03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-12-29-yedi-javascript-ipucu
categories:
  - Javascript
  - Yazılım
tags:
  - Javascript
---

Javascript gerçekten çok güçlü bir programlama dil, özellikle de web ortamında. Son beş yıl içerisinde çokça yol katetti. Artık yazmak yeni özellikleriyle yazmak çok daha basit ve pratik. Bu makale de Javascript’in yedi muhteşem ipucunu keşfeteceğiz.

## 1. Dizeyi sayıya çevirmek {#h-1-dizeyi-say-ya-evirmek}

Javascript’in tekli operatörü sayesinde bir dizeyi basit bir şekilde sayıya çevirebilirsiniz. Çevirmek için dize başına   girmeniz yeterli. Fakat unutmayın bu işlem sadece Dize içerisinde barınan sayılar için geçerlidir. (Örnekte olduğu gibi)

{% highlight javascript %}dize = "123";
console.log( dize);
// 123

dize_2 = "Yakışıklıyım"
console.log( dize_2);
// NaN{% endhighlight %}

## 2. Sayıyı dizeye çevirmek {#h-2-say-y-dizeye-evirmek}

İsterseniz sayıyı dizeye de çevirebilirsiniz. Sayı ile boş bir dizeyle toplamanız yeterli.

{% highlight javascript %}var artikObirDize = 5   "";
console.log(artikObirDize);
// 5
console.log(typeof artikObirDize);
// string{% endhighlight %}

## 3.Benzersiz değerlere ayıklamak {#h-3-benzersiz-de-erlere-ay-klamak}

Aynı değerlerin bulunduğu bir dizi’yi ayıklayıp benzersiz değerlere sahip bir dizi oluşturabiliriz. Bunuda **Set** ve **Spread** operatörü ile yapıyoruz.

{% highlight javascript %}var cekmecem = [50,60,40,10,90,60,90,40,60,50];
var ihtiyacimOlanlar = [...New Set(cekmecem)];

console.log(ihtiyacimOlanlar);
// [50, 60, 40, 10, 90]{% endhighlight %}

## 4. Çok boyutlu dizeleri düzleştirmek {#h-4-ok-boyutlu-dizeleri-d-zle-tirmek}

**Concat() metodunu** ve **spread** operatörünü kullanmamız yeterli.

{% highlight javascript %}var sayilar = [1,2, [3,4], [5,6], 7, 8];
var duzeltilmisSayilar = [].concat(...sayilar);

console.log(duzeltilmisSayilar);
// [1, 2, 3, 4, 5, 6, 7, 8]{% endhighlight %}

## 5. Tümünü değiştir {#h-5-t-m-n-de-i-tir}

Hepimiz _dize.replace_ fonksiyonunun işlevini biliyoruz fakat sadece ilk bulduğunu değiştirdiğini de biliyoruz. Neyse, düzenli ifadeler sayesinde dilersek tüm eşleşen verileri değiştirebiliriz.Dilerseniz örneğe bir göz atalım.

{% highlight javascript %}var ornek = "çörek çörek";

console.log(ornek.replace("çör", "k"));
// kek çörek
console.log(ornek.replace(/çör/g, "k"));
// kek kek{% endhighlight %}

## 6. Koşullara kısa devre uygulamak {#h-6-ko-ullara-k-sa-devre-uygulamak}

İlk önce aşağıda bulunan durumu inceleyelim.

{% highlight javascript %}if(hi){
sayHi();
}{% endhighlight %}

Evet hiç bir hata yok fakat fazlalık var. Bu fazlalığı ise **&&** mantık operatörüyle kaldırabiliriz. Aynen şöyle;

{% highlight javascript %}hi && sayHi();{% endhighlight %}

Bu sizin çok daha kısa kodlar yazmanıza yardımcı olacaktır.

## 7. Uzunluğunu kurcalayarak dizeye mutasyon geçirtmek {#h-7-uzunlu-unu-kurcalayarak-dizeye-mutasyon-ge-irtmek}

Javascript’te dizenin length değerini dilediğimiz gibi düzenleyebiliriz. Bunu da avantajlı bir şekilde kullanabiliriz. Dilersek dizeyi kısaltabiliriz, dilersek dizeyi boşaltabiliriz.  
Eğer dizeyi kısaltmak istersek;

{% highlight javascript %}var sayilar = [1,2,3,4,5,6,7,8]
console.log(sayilar.length);
// 8
sayilar.length = 5;
consolel.log(sayilar.length);
// 5
console.log(sayilar);
// [1,2,3,4,5]{% endhighlight %}

Peki boşaltmak istiyorsak;

{% highlight javascript %}var sayilar = [1,2,3,4,5,6,7,8]
console.log(sayilar.length);
// 8
sayilar.length = 0;
console.log(sayilar.length);
// 0
console.log(sayilar);
// []{% endhighlight %}

## Sonuç {#h-sonu}

Gördüğünüz gibi, çok fazla kod yazmadan birçok görevi yaptık. Bu ipuçlarını kullanmak, kodunuzun daha temiz ve bakımı kolay olmasını sağlayacaktır.  
Bu makaleyi okuduğunuz için teşekkür ederim, umarım faydalı bulmuşsunuzdur. Eğer öyleyse, bu blogu takip ederek daha fazla benzer içerik elde edin.

<p class="has-small-font-size">
  *kaynak(lar): <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax">Spread</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND">&&</a>
</p>
