---
id: 377
title: Mutlaka bilmeniz gereken 7 Javascript İpucu
date: 2020-12-29T16:33:16+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-12-29-yedi-javascript-ipucu
categories:
  - Javascript
  - Yazılım
---
Javascript gerçekten çok güçlü bir programlama dil, özellikle de web ortamında. Son beş yıl içerisinde çokça yol katetti. Artık yazmak yeni özellikleriyle yazmak çok daha basit ve pratik. Bu makale de Javascript&#8217;in yedi muhteşem ipucunu keşfeteceğiz.

## 1. Dizeyi sayıya çevirmek {#h-1-dizeyi-say-ya-evirmek}

Javascript&#8217;in tekli operatörü sayesinde bir dizeyi basit bir şekilde sayıya çevirebilirsiniz. Çevirmek için dize başına + girmeniz yeterli. Fakat unutmayın bu işlem sadece Dize içerisinde barınan sayılar için geçerlidir. (Örnekte olduğu gibi)

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>dize = "123";
console.log(+dize);
// 123 

dize_2 = "Yakışıklıyım"
console.log(+dize_2);
// NaN</code></pre>
</div>

## 2. Sayıyı dizeye çevirmek {#h-2-say-y-dizeye-evirmek}

İsterseniz sayıyı dizeye de çevirebilirsiniz. Sayı ile boş bir dizeyle toplamanız yeterli.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var artikObirDize = 5 + "";
console.log(artikObirDize);
// 5
console.log(typeof artikObirDize);
// string</code></pre>
</div>

## 3.Benzersiz değerlere ayıklamak {#h-3-benzersiz-de-erlere-ay-klamak}

Aynı değerlerin bulunduğu bir dizi&#8217;yi ayıklayıp benzersiz değerlere sahip bir dizi oluşturabiliriz. Bunuda **Set** ve **Spread** operatörü ile yapıyoruz.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var cekmecem = [50,60,40,10,90,60,90,40,60,50];
var ihtiyacimOlanlar = [...New Set(cekmecem)];

console.log(ihtiyacimOlanlar);
// [50, 60, 40, 10, 90]</code></pre>
</div>

## 4. Çok boyutlu dizeleri düzleştirmek {#h-4-ok-boyutlu-dizeleri-d-zle-tirmek}

**Concat() metodunu** ve **spread** operatörünü kullanmamız yeterli.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var sayilar = [1,2, [3,4], [5,6], 7, 8];
var duzeltilmisSayilar = [].concat(...sayilar);

console.log(duzeltilmisSayilar);
// [1, 2, 3, 4, 5, 6, 7, 8]</code></pre>
</div>

## 5. Tümünü değiştir {#h-5-t-m-n-de-i-tir}

Hepimiz _dize.replace_ fonksiyonunun işlevini biliyoruz fakat sadece ilk bulduğunu değiştirdiğini de biliyoruz. Neyse, düzenli ifadeler sayesinde dilersek tüm eşleşen verileri değiştirebiliriz.Dilerseniz örneğe bir göz atalım.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var ornek = "çörek çörek";

console.log(ornek.replace("çör", "k"));
// kek çörek
console.log(ornek.replace(/çör/g, "k"));
// kek kek</code></pre>
</div>

## 6. Koşullara kısa devre uygulamak {#h-6-ko-ullara-k-sa-devre-uygulamak}

İlk önce aşağıda bulunan durumu inceleyelim.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>if(hi){
sayHi();
}</code></pre>
</div>

  
Evet hiç bir hata yok fakat fazlalık var. Bu fazlalığı ise **&&** mantık operatörüyle kaldırabiliriz. Aynen şöyle;

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>hi && sayHi();</code></pre>
</div>

  
Bu sizin çok daha kısa kodlar yazmanıza yardımcı olacaktır.

## 7. Uzunluğunu kurcalayarak dizeye mutasyon geçirtmek {#h-7-uzunlu-unu-kurcalayarak-dizeye-mutasyon-ge-irtmek}

Javascript&#8217;te dizenin length değerini dilediğimiz gibi düzenleyebiliriz. Bunu da avantajlı bir şekilde kullanabiliriz. Dilersek dizeyi kısaltabiliriz, dilersek dizeyi boşaltabiliriz.  
Eğer dizeyi kısaltmak istersek;

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var sayilar = [1,2,3,4,5,6,7,8]
console.log(sayilar.length);
// 8
sayilar.length = 5;
consolel.log(sayilar.length);
// 5
console.log(sayilar);
// [1,2,3,4,5]</code></pre>
</div>

  
Peki boşaltmak istiyorsak;

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-js" data-file="ornekler.js" data-lang="JavaScript"><code>var sayilar = [1,2,3,4,5,6,7,8]
console.log(sayilar.length);
// 8
sayilar.length = 0;
console.log(sayilar.length);
// 0
console.log(sayilar);
// []</code></pre>
</div>

## Sonuç {#h-sonu}

Gördüğünüz gibi, çok fazla kod yazmadan birçok görevi yaptık. Bu ipuçlarını kullanmak, kodunuzun daha temiz ve bakımı kolay olmasını sağlayacaktır.  
Bu makaleyi okuduğunuz için teşekkür ederim, umarım faydalı bulmuşsunuzdur. Eğer öyleyse, bu blogu takip ederek daha fazla benzer içerik elde edin.

<p class="has-small-font-size">
  *kaynak(lar): <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax">Spread</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND">&&</a>
</p>
