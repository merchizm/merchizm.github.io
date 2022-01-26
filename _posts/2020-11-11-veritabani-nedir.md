---
title: Veritabanı Nedir? SQL Nedir? Neden Veritabanı?
date: 2020-11-11T18:11:38+03:00
author: Meriç Enes Kayalar
description: "Bildiğiniz üzere veri bulunduğumuz çağda çok büyük bir öneme sahip, bu bağlamda veritabanları da aynı değeri kazanıyor. Peki Veritabanı Nedir?"
layout: post
permalink: /veritabani-nedir-sql-nedir-neden-veritabani
categories:
  - Veritabanı
---
Bildiğiniz üzere veri bulunduğumuz çağda çok büyük bir öneme sahip, bu bağlamda veritabanları da aynı değeri kazanıyor. Eğer bir yazılımcıysanız veya olmayı düşünüyorsanız günlük hayatınız içerisinde sıkça bu veritabanı terimini duymuşsunuzdur. Peki veritabanı nedir? Bu konuya geçmeden önce veri nedir ona bakalım.

## Veri nedir?

Temel tanımıyla veri ham (işlenmemiş) gerçek enformasyon parçacığına verilen addır. Bilgisayar bilimleri açısından veri ise hesaplama ya da manipülasyon amacı ile kullanılan bir gerçeği belirtir. Bu iki tanımı harmanlayıp şöyle bir sonuç elde edebiliriz;

Veri işlenmemiş, hesaplama ya da manipülasyon amacı ile kullanılan enformasyon parçacığına verilen addır.

  
Fark ettiğiniz üzere cümle başında direkt olarak işlenmemiş yani ham yazdım ve vurguladım. Yani verilerin her zaman saf ve ham kalması verinin doğru enformasyona ulaşmasının en kısa yoludur.

## Neden Veritabanına ihtiyacımız var?

Eğer veriye sahipseniz ve bunları bir yerde saklamak istiyorsanız güvenli bir seçeneğe ihtiyacınız olacaktır. Bu veriler herhangi bir şey olabilir. Örnek vermek gerekirse; bir şirketiniz var, çalışanların bilgilerini saklamak istiyorsunuz aynı zamanda siz bir çevre dostusunuz. Böyle bir durumda çalışanınızın yaşını, ismi, soy ismi ve iş tecrübelerini saklayabilirsiniz ki bu dosya olarak saklamaktan daha güvenli olmakla beraber daha erişilebilir olacaktır.

## Veritabanı

### Veritabanı Tarihçesi 

Aslında biraz geçmişe gidip, çokta uzun tutmadan sizlere veritabanının evrimi üzerinden veritabanını anlatmak istiyorum. Bildiğiniz üzere şu an sahip olduğumuz teknoloji ile elimizde 1 TB&#8217;lik veriyi 2.5 inçlik bir kutuya sığdırabiliyoruz. Fakat geçmişte durum böyle değildi.<figure class="wp-block-image size-large">

<img loading="lazy" width="1000" height="954" src="assets/uploads/2020/11/4137.jpg.png" alt="" class="wp-image-335" /> - 1956 IBM Markasına ait 5 mb bellek.

Görselde o kadar insanın ittirdiği donanım IBM&#8217;nin geliştirmiş olduğu 5 MB&#8217;lik bir bellek. Aslında bakarsanız bu görsel çok fazla şeyi açıklıyor. Elde teknoloji yokken veri depolamak için ve o veriyi aktarmak için insanlar resimde gördüğümüz gibi büyük donanımları ülke ülke gezdiriyordu. Resimdeki donanım uçağa götürülmek üzere yükleniyor.  
Tarihte biraz daha ilerlediğimizde ilk veritabanı CODASYL (Conference/Committee on Data Systems Languages) 1960&#8217;lı yılların başında ortaya çıkıyor. Ayrıca bu alanda rekabette artınca haliyle teknoloji çok daha hızlı gelişiyor ve günümüzdeki halini alıyor.

### Veritabanı Nedir? 

<img loading="lazy" src="assets/uploads/2020/11/database.png" alt="" class="wp-image-336" width="479" height="539" /> - Büyük ihtimalle veritabanı dendiğinde bu görsel aklınıza geliyordur. 

Veritabanı, depolanan yapılandırılmış bilgi veya veriden oluşan düzenli koleksiyona verilen addır. Veritabanları genellikle bir veritabanı yönetim sistemi (DBMS) ile kontrol edilir.

  
Veritabanı içeriği sizin koyduğunuz kurallara ve modellemelere göre şekillenir. Böylece veriyi kolayca erişilebilir, yönetilebilir, değiştirilebilir, güncellenebilir ve kontrol edilebilir hale getirirsiniz. Çoğu veritabanında veri yazma ve sorgulama için yapılandırılmış sorgu dili (SQL) kullanılır.

  
Veritabanının yapısından bahsetmek gerekirse, en temel birimi tablolardır. Tablolar, Şemalar içerisinde tutulur. Tablolar bilgilerin tutulduğu nesnelerdir. Tabloların içeriğini ise satır ve sütunlardan meydana gelen bilgiler veya veriler oluşturur.

#### Örnekle Veritabanı Anlatımı

Şimdi şöyle düşünelim. Bir araba kiralama şirketiniz var ve şirketinizdeki müşterileri veritabanına kaydetmek istiyorsunuz. Bunu nasıl yapabiliriz? Lütfen acele etmeyin.

  
Eğer düşündüyseniz devam edelim. Öncelikle şemayı en genel süzgeç olarak kabul edebiliriz. Biz araba kiralama şirketimiz için veritabanı oluşturacağız. Yani şemanın ismini &#8220;araba\_kiralama&#8221; yapabiliriz. Müşterileri saklamak içinse &#8220;araba\_kiralama&#8221; şemasının içerisine &#8220;musteriler&#8221; tablosunu oluşturabiliriz. Müşterilerimizinse şu verilerini alacağız;

  * İsim
  * Soy isim
  * E-Posta
  * Telefon Numarası

Yani bu veriler tablomuzdaki sütunlarımız olacak, şimdiye kadar yaptıklarımızı şöyle bir görselle özetleyebiliriz.<figure class="wp-block-image size-large is-resized">

<img loading="lazy" src="assets/uploads/2020/11/Ekran-Resmi-2020-11-13-10.29.35.png" alt="SQL, Veritabanı nedir ?" class="wp-image-337" width="577" height="516" />

### Yapılandırılmış Sorgu Dili (SQL) Nedir? 

SQL; veriyi sorgulamak, tanımlamak, değiştirmek ve aynı zamanda erişim kontrolü sağlamak üzere kullanılan programlama dilidir. Neredeyse tüm ilişkisel veritabanları SQL dilini kullanır. SQL dili ilk olarak 1970&#8217;li yıllarda Oracle&#8217;ın büyük katkıları ile IBM&#8217;de geliştirilmiştir. Daha sonra da SQL ANSI standardı uygulanmış. IBM, Oracle ve Microsoft gibi şirketlerde SQL pek çok uzantının temelini atmıştır. SQL günümüzde oldukça yaygın bir şekilde kullanılsa da yeni programlama dilleri geliştirilmeye başlandı.

### Veritabanı Türleri

Veritabanları özelliklerine göre birbirlerinden ayrılırlar.

  * **İlişkisel veritabanları**

Genellikle birden fazla tablo bulunur. Bu tablolar birbirleriyle belirli alanlara göre ilişkilendirilir. Birden çok tablonun mantıksal bir ilişki içerisinde tutulduğu veritabanlarına “**İlişkisel Veritabanı**” denir.

  * **Nesne odaklı veritabanları**

Veriler tıpkı nesne odaklı programlamada olduğu gibi nesneler biçiminde temsil edilir. Yani veriler nesneler biçiminde veritabanında tutuluyorsa o veritabanına “**Nesne odaklı veritabanı**” denir.

  * **Paylaşımlı**(**Dağıtılmış) veritabanları**

Bu veritabanı farklı yerlerde bulunan iki veya daha fazla dosyadan oluşur. Bu dosyalar birden çok fiziksel lokasyonda veya aynı fiziksel konumda farklı bilgisayarlarda depolanır. Bu türe “**Paylaşımlı**(**Dağıtılmış) veritabanları**” denir.

  * **Veri ambarları**

Veriler için merkezi bir depo olan veri ambarı, hızlı sorgulama ve analiz için özel olarak tasarlanmış bir veritabanı türüdür.

  * **NoSQL (ilişkisel olmayan) veritabanları**

İlişkisel olmayan, esnek yapılı, büyük verili ve çok sayıda aktif kullanıcılı sistemlerde yüksek performans ve yönetim kolaylığı sunan veritabanına “**NoSQL veritabanı**” denir.

  * ****Çizge (Graph)** veritabanları**

Kısa ve öz tanımlamak gerekirse, çizge kuramını kullanan NoSQL veritabanıdır. Diğer veritabanlarından oldukça farklıdır.<figure class="wp-block-image size-large is-resized">

<img loading="lazy" src="assets/uploads/2020/11/cizge-veritabani.png" alt="SQL, Veritabanı nedir ?" class="wp-image-338" width="345" height="324" />

  * **OLTP veritabanları**

Birden fazla kullanıcı tarafından gerçekleştirilen çok sayıda işlem için tasarlanmış hızlı ve analitik bir veritabanıdır.



<p class="has-normal-font-size">
  <strong>Kaynakça:</strong><br /><a href="https://en.wikipedia.org/wiki/Database#Design_and_modeling">https://en.wikipedia.org/wiki/Database</a><br /><a href="https://tr.wikipedia.org/wiki/Veri">https://tr.wikipedia.org/wiki/Veri</a><br /><a href="https://www.oracle.com/database/what-is-database.html">https://www.oracle.com/database/what-is-database.html</a><br /><a href="https://www.guru99.com/introduction-to-database-sql.html">https://www.guru99.com/introduction-to-database-sql.html</a><br /><a href="https://medium.com/omarelgabrys-blog/database-introduction-part-1-4844fada1fb0">https://medium.com/omarelgabrys-blog/database-introduction-part-1-4844fada1fb0</a><br /><a href="http://blog.inetmar.com/414-2/">http://blog.inetmar.com/414-2/</a>
</p>
