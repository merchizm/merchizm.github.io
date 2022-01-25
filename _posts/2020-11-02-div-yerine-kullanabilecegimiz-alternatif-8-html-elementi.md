---
title: div yerine kullanabileceğimiz alternatif 8 HTML Elementi
date: 2020-11-02T14:17:28+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-11-02-div-yerine-kullanabilecegimiz-alternatif-8-html-elementi
categories:
  - HTML
  - Yazılım
tags:
  - div yerine kullanılabilecek elementler
  - div yerine kullanılabilecek etiketler
  - div yerine kullanılabilecek taglar
  - div yerine kullanıllabilecek şeyler
  - dive alternatif elementler
  - html dive alternatif
---
Bir HTML belgesinin nasıl oluştuğunu öğrenmenin ilk aşamalarında bazı geliştiricilerin div çorbası problemi ile karşılaşmaları gayet olasıdır.

Bu olasılığı olabildiğince düşürmek için bugün sizlere <div> yerine kullanabileceğiniz alternatif 8 html etiketi/elementi göstereceğim.

## Main Elementi 

`<main>` tarayıcılarda veya ekran okuyucularında içeriğin bu element içerisinde olduğunu gösterir. Bu, klavye komutlarına erişmenize, mobil tarayıcıları yakınlaştırmanıza ve daha fazlasına yardımcı olabilir. Sayfa başına sadece <mark>bir kez</mark> kullanılmalıdır.

{% highlight html %}
<main class="icerik">
    <h2>BAŞLIIK LA BUU</h2>
    <p>İnanmazsın bende paragrafım.</p>
</main>
{% endhighlight %}

## Section Elementi 

`<section>` elementi içeriği gruplamak için kullanılır ve bir belgenin veya uygulamanın bir bölümünü temsil eder, sayfa içerisinde bir çok kez kullanabilirsiniz. Section elementi kendi içerisinde <mark>header</mark> ve <mark>footer</mark> elementlerine sahip olabilir.

{% highlight html %}
<main class="icerik">

    <section class="gonderi">
        <h2>İnsanlar niye saçma şarkıları isteksizce ezberler ?</h2>
        <p> İsviçreli bilim adamları bu konuyu araştırıyor işte</p>
    </section>

    <section class="gonderi">
        <h2>İnsanlar niye soru sorar ?</h2>
        <p>...</p>
    </section>

</main>
{% endhighlight %}

## Header Elementi 

`<header>` elementi genellikle bir giriş veya gezinme yardımcıları grubu olan giriş içeriğini temsil eder. Bazı başlık öğelerinin yanı sıra bir logo, bir arama formu, bir yazar adı ve diğer öğeleri de içerebilir. 

{% highlight html %}
<header class="baslik kedi">
    Pati Kulübü'ne hoş geldiniz!
</header>
<section>
    <header class="yazi-baslik">
        Ünlü ankara kedisi Khaalesi ağıza yakışmayacak söylemlerde bulundu !!
    </header>
    <p> miyav miyavına miyav miyavvvv dedi. </p>
</section>
<section>
    <header class="yazi-baslik">
        Altın yeni klibiyle dünyayı salladı !!
    </header>
    <p> kulağımda sayısız cevapsız bir miyavlamaa.... </p>
</section>
{% endhighlight %}

## Footer Elementi

`<footer>` elementi, bir belgenin veya bölümün “altbilgi” bölümünü temsil eder. Birçok web sitesinde, footer elementi iletişim ve telif hakkı bilgileri, kısa bir “hakkında” kısmı, reklam, sosyal medya logoları ve bağlantıları vb. içerir.


{% highlight html %}
<header class="baslik kedi">
    Pati Kulübü'ne hoş geldiniz!
</header>
<section>
    <header class="yazi-baslik">
        Ünlü ankara kedisi Khaalesi ağıza yakışmayacak söylemlerde bulundu !!
    </header>
    <p> miyav miyavına miyav miyavvvv dedi. </p>
</section>
<section>
    <header class="yazi-baslik">
        Altın yeni klibiyle dünyayı salladı !!
    </header>
    <p> kulağımda sayısız cevapsız miyavlamaa.... </p>
</section>

<footer class="altbilgi">
    <p>Tüm hakları saklıdır 2020. Pati Kulübü tarafından aşkla oluşturulmuştur</p>
    <a href="https://twitter.com/patimatibumkati">Twitter Hesabımız</a>
</footer>
{% endhighlight %}

## Aside Elementi

`<aside>` elementi, temel olarak belirli bir bölümle ilgili içeriği içeren bir sayfanın bir bölümünü temsil etmek için kullanılır. Aside elementleri genellikle kenar çubukları(sidebar) olarak kullanılır.

{% highlight html %}
<header>
    <h2> Vazgeçenlerin Radyosu, BLARADYO..</h2>
</header>
<main class="icerikler">
    <section class="icerik">
        Bugün bolca Sezen Aksu dinleyeceğiz.
        <aside>
            <p><b>ahmet</b>: ben sezen ablanın vazgeçtim şarkısı istiyorum.</p>
            <p><b>mustafa</b>: ağa efkarım birikti sığmaz içime açsana ya..</p>
            <p><b>mehmet</b>: 🇹🇷 🇹🇷 🇹🇷</p>
        </aside>
    </section>
</main>
{% endhighlight %}

## Article Elementi

<article> elementi, içerik bölümleri için kullanılabilir. Blog gönderileri, gazete makaleleri ve kullanıcı yorumları, makale öğesinin bazı olası kullanım durumlarıdır.

{% highlight html %}
<header>
    <h2> Vazgeçenlerin Radyosu, BLARADYO..</h2>
</header>
<main class="icerikler">
    <section class="icerik">
        Bugün bolca Sezen Aksu dinleyeceğiz.
        <aside>
            <p><b>ahmet</b>: ben sezen ablanın vazgeçtim şarkısı istiyorum.</p>
            <p><b>mustafa</b>: ağa efkarım birikti sığmaz içime açsana ya..</p>
            <p><b>mehmet</b>: 🇹🇷 🇹🇷 🇹🇷</p>
        </aside>
    </section>
    <section class="yazilar">
        <article>
            <h3> BLA yeni şarkı çıkardı !!</h3>
            <p> çıkardı çıkardı..</p>
            <a href="yazidevami.html">devamını oku</a>
        </article>
    </section>
</main>
{% endhighlight %}

## Blockquote Elementi 

Blockquote elementi, harici bir kaynaktan (kişi, belge, gazete, vaka çalışması, vb.) alıntılanan içeriği temsil eder. Genellikle, alıntıyı kaynağına atfetmek için cite elementi eşlik eder.
{% highlight html %}
<blockquote>
    "Her söylediğini bil, her bildiğini söyleme."
</blockquote>
<cite>- Cladius</cite>
{% endhighlight %}

## Nav Elementi 

`<nav>` elementi, gezinme öğeleri bir belgenin gezinme bölümünü temsil eder. Gezinme öğesi, belirli bir sayfa, uygulama vb. için ana gezinme bağlantılarını içerir.
{% highlight html %}
<header>
    <h2> Vazgeçenlerin Radyosu, BLARADYO..</h2>
</header>
<nav id="menu">
    <ul class="menu">
        <li><a href="anasayfa.html">Ana Sayfa</a></li>
        <li><a href="radyo.html">CANLI RADYO DINLE</a></li>
        <li><a href="iletisim.html">İletişim</a></li>
    </ul>
</nav>
<main class="icerikler">
    <section class="icerik">
        Bugün bolca Sezen Aksu dinleyeceğiz.
        <aside>
            <p><b>ahmet</b>: ben sezen ablanın vazgeçtim şarkısı istiyorum.</p>
            <p><b>mustafa</b>: ağa efkarım birikti sığmaz içime açsana ya..</p>
            <p><b>mehmet</b>: 🇹🇷 🇹🇷 🇹🇷</p>
        </aside>
    </section>
    <section class="yazilar">
        <article>
            <h3> BLA yeni şarkı çıkardı !!</h3>
            <p> çıkardı çıkardı..</p>
            <a href="yazidevami.html">devamını oku</a>
        </article>
    </section>
</main>
{% endhighlight %}

bu yazı bu kadardı, bir dahaki yazılarda görüşmek üzere. Bir sorunuz olursa mutlaka yorumlar kısmında belirtin elimden geldiğince destek olmaya çalışacağım.