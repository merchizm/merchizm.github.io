---
id: 272
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

{% highlight html %}lt;main class="icerik"&gt;
&lt;h2&gt;BAŞLIIK LA BUU&lt;/h2&gt;
&lt;p&gt;İnanmazsın bende paragrafım.&lt;/p&gt;
&lt;/main&gt;{% endhighlight %}

## Section Elementi

`<section>` elementi içeriği gruplamak için kullanılır ve bir belgenin veya uygulamanın bir bölümünü temsil eder, sayfa içerisinde bir çok kez kullanabilirsiniz. Section elementi kendi içerisinde <mark>header</mark> ve <mark>footer</mark> elementlerine sahip olabilir.

{% highlight html %}lt;main class="icerik"&gt;

    &lt;section class="gonderi"&gt;
        &lt;h2&gt;İnsanlar niye saçma şarkıları isteksizce ezberler ?&lt;/h2&gt;
        &lt;p&gt; İsviçreli bilim adamları bu konuyu araştırıyor işte&lt;/p&gt;
    &lt;/section&gt;

    &lt;section class="gonderi"&gt;
        &lt;h2&gt;İnsanlar niye soru sorar ?&lt;/h2&gt;
        &lt;p&gt;...&lt;/p&gt;
    &lt;/section&gt;

&lt;/main&gt;{% endhighlight %}

## Header Elementi

`<header>` elementi genellikle bir giriş veya gezinme yardımcıları grubu olan giriş içeriğini temsil eder. Bazı başlık öğelerinin yanı sıra bir logo, bir arama formu, bir yazar adı ve diğer öğeleri de içerebilir.

{% highlight html %}lt;header class="baslik kedi"&gt;
Pati Kulübü&#39;ne hoş geldiniz!
&lt;/header&gt;
&lt;section&gt;
&lt;header class="yazi-baslik"&gt;
Ünlü ankara kedisi Khaalesi ağıza yakışmayacak söylemlerde bulundu !!
&lt;/header&gt;
&lt;p&gt; miyav miyavına miyav miyavvvv dedi. &lt;/p&gt;
&lt;/section&gt;
&lt;section&gt;
&lt;header class="yazi-baslik"&gt;
Altın yeni klibiyle dünyayı salladı !!
&lt;/header&gt;
&lt;p&gt; kulağımda sayısız cevapsız bir miyavlamaa.... &lt;/p&gt;
&lt;/section&gt;{% endhighlight %}

## Footer Elementi

`<footer>` elementi, bir belgenin veya bölümün “altbilgi” bölümünü temsil eder. Birçok web sitesinde, footer elementi iletişim ve telif hakkı bilgileri, kısa bir “hakkında” kısmı, reklam, sosyal medya logoları ve bağlantıları vb. içerir.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-html" data-file="index.html" data-lang="HTML"><code>
&lt;header class="baslik kedi"&gt;
    Pati Kulübü&#39;ne hoş geldiniz!
&lt;/header&gt;
&lt;section&gt;
    &lt;header class="yazi-baslik"&gt;
        Ünlü ankara kedisi Khaalesi ağıza yakışmayacak söylemlerde bulundu !!
    &lt;/header&gt;
    &lt;p&gt; miyav miyavına miyav miyavvvv dedi. &lt;/p&gt;
&lt;/section&gt;
&lt;section&gt;
    &lt;header class="yazi-baslik"&gt;
        Altın yeni klibiyle dünyayı salladı !!
    &lt;/header&gt;
    &lt;p&gt; kulağımda sayısız cevapsız miyavlamaa.... &lt;/p&gt;
&lt;/section&gt;

&lt;footer class="altbilgi"&gt;
&lt;p&gt;Tüm hakları saklıdır 2020. Pati Kulübü tarafından aşkla oluşturulmuştur&lt;/p&gt;
&lt;a href="https://twitter.com/patimatibumkati"&gt;Twitter Hesabımız&lt;/a&gt;
&lt;/footer&gt;{% endhighlight %}

## Aside Elementi

`<aside>` elementi, temel olarak belirli bir bölümle ilgili içeriği içeren bir sayfanın bir bölümünü temsil etmek için kullanılır. Aside elementleri genellikle kenar çubukları(sidebar) olarak kullanılır.

{% highlight html %}lt;header&gt;
&lt;h2&gt; Vazgeçenlerin Radyosu, BLARADYO..&lt;/h2&gt;
&lt;/header&gt;
&lt;main class="icerikler"&gt;
&lt;section class="icerik"&gt;
Bugün bolca Sezen Aksu dinleyeceğiz.
&lt;aside&gt;
&lt;p&gt;&lt;b&gt;ahmet&lt;/b&gt;: ben sezen ablanın vazgeçtim şarkısı istiyorum.&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mustafa&lt;/b&gt;: ağa efkarım birikti sığmaz içime açsana ya..&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mehmet&lt;/b&gt;: 🇹🇷 🇹🇷 🇹🇷&lt;/p&gt;
&lt;/aside&gt;
&lt;/section&gt;
&lt;/main&gt;{% endhighlight %}

## Article Elementi

<article> elementi, içerik bölümleri için kullanılabilir. Blog gönderileri, gazete makaleleri ve kullanıcı yorumları, makale öğesinin bazı olası kullanım durumlarıdır.

{% highlight html %}lt;header&gt;
&lt;h2&gt; Vazgeçenlerin Radyosu, BLARADYO..&lt;/h2&gt;
&lt;/header&gt;
&lt;main class="icerikler"&gt;
&lt;section class="icerik"&gt;
Bugün bolca Sezen Aksu dinleyeceğiz.
&lt;aside&gt;
&lt;p&gt;&lt;b&gt;ahmet&lt;/b&gt;: ben sezen ablanın vazgeçtim şarkısı istiyorum.&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mustafa&lt;/b&gt;: ağa efkarım birikti sığmaz içime açsana ya..&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mehmet&lt;/b&gt;: 🇹🇷 🇹🇷 🇹🇷&lt;/p&gt;
&lt;/aside&gt;
&lt;/section&gt;
&lt;section class="yazilar"&gt;
&lt;article&gt;
&lt;h3&gt; BLA yeni şarkı çıkardı !!&lt;/h3&gt;
&lt;p&gt; çıkardı çıkardı..&lt;/p&gt;
&lt;a href="yazidevami.html"&gt;devamını oku&lt;/a&gt;
&lt;/article&gt;
&lt;/section&gt;
&lt;/main&gt;{% endhighlight %}

## Blockquote Elementi

Blockquote elementi, harici bir kaynaktan (kişi, belge, gazete, vaka çalışması, vb.) alıntılanan içeriği temsil eder. Genellikle, alıntıyı kaynağına atfetmek için cite elementi eşlik eder.

<div class="hcb_wrap">
  <pre class="prism line-numbers lang-html" data-lang="HTML"><code>&lt;blockquote&gt;
    "Her söylediğini bil, her bildiğini söyleme."
&lt;/blockquote&gt;
&lt;cite&gt;- Cladius&lt;/cite&gt;</code></pre>
</div>

## Nav Elementi

`<nav>` elementi, gezinme öğeleri bir belgenin gezinme bölümünü temsil eder. Gezinme öğesi, belirli bir sayfa, uygulama vb. için ana gezinme bağlantılarını içerir.

{% highlight html %}lt;header&gt;
&lt;h2&gt; Vazgeçenlerin Radyosu, BLARADYO..&lt;/h2&gt;
&lt;/header&gt;
&lt;nav id="menu"&gt;
&lt;ul class="menu"&gt;
&lt;li&gt;&lt;a href="anasayfa.html"&gt;Ana Sayfa&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href="radyo.html"&gt;CANLI RADYO DINLE&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href="iletisim.html"&gt;İletişim&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;/nav&gt;
&lt;main class="icerikler"&gt;
&lt;section class="icerik"&gt;
Bugün bolca Sezen Aksu dinleyeceğiz.
&lt;aside&gt;
&lt;p&gt;&lt;b&gt;ahmet&lt;/b&gt;: ben sezen ablanın vazgeçtim şarkısı istiyorum.&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mustafa&lt;/b&gt;: ağa efkarım birikti sığmaz içime açsana ya..&lt;/p&gt;
&lt;p&gt;&lt;b&gt;mehmet&lt;/b&gt;: 🇹🇷 🇹🇷 🇹🇷&lt;/p&gt;
&lt;/aside&gt;
&lt;/section&gt;
&lt;section class="yazilar"&gt;
&lt;article&gt;
&lt;h3&gt; BLA yeni şarkı çıkardı !!&lt;/h3&gt;
&lt;p&gt; çıkardı çıkardı..&lt;/p&gt;
&lt;a href="yazidevami.html"&gt;devamını oku&lt;/a&gt;
&lt;/article&gt;
&lt;/section&gt;
&lt;/main&gt;{% endhighlight %}

bu yazı bu kadardı, bir dahaki yazılarda görüşmek üzere. Bir sorunuz olursa mutlaka yorumlar kısmında belirtin elimden geldiğince destek olmaya çalışacağım.
