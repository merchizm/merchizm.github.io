---
title: SQLite Nedir? nasıl kullanılır? Nasıl indirilir?
date: 2021-01-10T15:14:29+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2021-01-10-sqlite-nedir-ne-degildir
categories:
  - Veritabanı
tags:
  - sqlite
---
SQLite popüler bir açık kaynaklı veritabanı türüdür. Bu makalede, Sqlite&#8217;ın ne olduğunu ve SQL&#8217;ın nasıl kurulacağını anlatacağım.

## SQLite Nedir? {#h-sqlite-nedir}

SQLite kurulumu ve kullanımı basit olan, c++ ile yazılmış bir **veritabanı** kütüphanesidir. Tercih edilme sebebi dış kaynaklara bağımlı olmaması ve tüm işletim sistemlerinde çalışabilir olmasıdır. Ayrıca bunun üstüne sunucuya ihtiyaç duymaması tercih edilme sebeplerinin başında gelir.

### Sunucu İhtiyacının olmaması? ( Serverless )

Bunu şu şekilde açıklayabiliriz, normalde veritabanlarının çalışması için sunucuya ihtiyaçları vardır. SQLite&#8217;da böyle bir ihtiyaç yoktur. SQLite&#8217;ın entegre edildiği uygulama veya kendisi aracılığı ile direkt bağlanabilirsiniz.

### Ayarsız veritabanı (Zero-Configuration) 

SQLite kurulmaya ihtiyaç duymaz ve öyle bir prosedürü yoktur. Direkt olarak veritabanı oluşturmaya başlayabilirsiniz.

### Kendine yeten (Self-Contained)

Çok az bağımlılığa sahiptir. Bu SQLite&#8217;ı her işletim sisteminde kullanabilmemizi mümkün kılar. Biraz daha açmak gerekirse SQLite harici kütüphane veya arayüz içermez/kullanmaz.

### Transaction ve ACID

Bu kavramlar tek başına bile makale olmaya yeteceğinden olabildiğince kısa açıklayacağım. **Atomic, Consistent, Isolation, Durable** kelimelerinin kısaltılmış hali ACID&#8217;dir. Bu kelimelerin her biri bir özelliği temsil eder. ACID özelliklerini içeren veritabanına Transaksiyonel(**Transactional**) veritabanı denir.

  
<a href="https://www.merich.rocks/2020/11/11/veritabani-nedir/" target="_blank" rel="noreferrer noopener">«SQL nedir? Veritabanı nedir? gibi soruların cevapları için buraya tıklayın»</a>

## SQLite Nasıl indirilir/kurulur? {#h-sqlite-nas-l-indirilir-kurulur}

  1. [Mac&#8217;te SQLite Kurmak](/2021-01-10-sqlite-nedir-ne-degildir#h-1-mac-zerine-sqlite-kurmak)
  2. [Linux&#8217;ta SQLite Kurmak](/2021-01-10-sqlite-nedir-ne-degildir#h-2-linux-zerine-sqlite-kurmak)
  3. [Windows&#8217;ta SQLite Kurmak](/2021-01-10-sqlite-nedir-ne-degildir#h-3-windows-zerine-sqlite-kurmak)

## 1.) Mac üzerine SQLite Kurmak {#h-1-mac-zerine-sqlite-kurmak}

Mac üzerinde kurulum yaparken kullanabileceğimiz iki yol vardır. Birincisi Paket Yöneticisi ile kurmak diğeri ise direkt olarak site üzerinden indirip çalıştırmaktır.

### Direkt indirip çalıştırmak(paket yöneticisi olmadan) {#h-direkt-indirip-al-t-rmak-paket-y-neticisi-olmadan}

SQLite&#8217;ın indirme sayfasına girin. <a href="https://www.sqlite.org/download.html" target="_blank" rel="noreferrer noopener">Buraya tıkla</a>yarak girebilirsiniz.&#8221;Precompiled Binaries for Mac OS X&#8221; Başlığı altındaki bağlantıyla tıklayarak &#8220;sql-tools-osx-blabla.zip&#8221; dosyasını indirin.Dosyaları arşivden çıkarın ve çıktı klasörüne girin.Resimdeki gibi 3 dosya olacaktır. &#8220;sqlite&#8221; adlı dosyaya tıklayıp açın. SQLite çalışmaya başlayacaktır. SQLite&#8217;ı kapatmak için ise _.quit_ yazmanız yeterlidir.

<img loading="lazy" width="1024" height="553" src="assets/uploads/2020/12/Ekran-Resmi-2020-12-23-20.46.16-1024x553.png" alt="SQLite Nedir? Nasıl Kurulur?" class="wp-image-374" /> 

### Paket yöneticisiyle kurmak {#h-paket-y-neticisiyle-kurmak}

Homebrew ile kurmak için terminali açın ve brew install sqlite3 yazın. Kurulum tamamlandıktan sonra sqlite3 yazıp SQLite&#8217;ı çalıştırabilirsiniz.

## 2.) Linux üzerine SQLite Kurmak {#h-2-linux-zerine-sqlite-kurmak}

Linux üzerine SQLite kurmak için terminale bir kaç satır kod yazmak yeterlidir. Linux dağıtımına göre;

### Debian / Ubuntu {#h-debian-ubuntu}

`apt-get install sqlite3`

### CentOS / Fedora / RedHat {#h-centos-fedora-redhat}

`yum install sqlite3`

  
Terminale sqlite3 yazarak SQLite&#8217;ı çalıştırabilirsiniz. SQLite&#8217;ı kapatmak için ise _.quit_ yazmanız yeterlidir.

## 3.) Windows üzerine SQLite Kurmak {#h-3-windows-zerine-sqlite-kurmak}

Windows üzerine SQLite kurmak için SQLite&#8217;ın indirme sayfasına <a href="https://www.sqlite.org/download.html" target="_blank" rel="noreferrer noopener">buradan</a> girin. &#8220;**Precompiled Binaries for Windows**&#8221; Başlığı altından &#8220;sqlite-tools-win32-x86.zip&#8221; adlı dosyayı indirin. Dosyaları zip arşivinden çıkartıp çıktı klasörüne girin. Orada sqlite.exe dosyası olacaktır. Ona tıkladığınızda SQLite&#8217;a erişmiş olacaksınız. SQLite&#8217;ı kapatmak için ise _.quit_ yazmanız yeterlidir.