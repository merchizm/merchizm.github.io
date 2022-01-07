---
id: 419
title: "MacOS&#8217;a Tesseract ve Ek Dil Kurulumu"
date: 2021-01-31T16:45:48+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2021-01-31-tesseract-kurulumu-macos
categories:
  - Genel
  - MacOS
tags:
  - MacOS
---

Bu yazıda Tesseract&#8217;ı bir Mac&#8217;te nasıl kullanabileceğinizi anlatacağım. Ayrıca istediğiniz farklı bir dili nasıl kurabileceğinizi de göstereceğim.

Şimdi Tesseract&#8217;ı kurmak için bilgisayarımızda Homebrew paket yöneticisinin olması gerekiyor. Kurmak için Terminali açıp alttaki kodu kopyala/yapıştır yapmanız yeterli.

{% highlight bash %}/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"{% endhighlight %}

Homebrew&#8217;i kurduktan sonra Tesseract&#8217;ı kurmak için yine Terminale `brew install tesseract` yazmanız yeterli. Kurulum sonrası Tesseract&#8217;ın hangi dizine kurulduğunu öğrenmek için ise `brew info tesseract` yazmanız yeterli. Karşınızda bir çıktı gelecek ve o çıktı içerisinde şuna benzer bir satır olmalı:

<pre class="wp-block-code">/usr/local/Cellar/tesseract/4.1.1 (66 files, 47.5MB) *</pre>

Finder&#8217;i açıp klasöre git yaptığınızda _bin_ dizini içerisinde Tesseract&#8217;ı **bulabilirsiniz**.

## Türkçe veya farklı bir dili kurmak {#h-t-rk-e-veya-farkl-bir-dili-kurmak}

İngilizce dışında dil kurmak içinse Tesseract&#8217;ın tessdata reposuna girip oradan dilediğiniz dilin dosyasını indirin.

Dil paketini 4.1.1 sürümünde kurmak içinse yine Finder&#8217;i açıp klasöre git yapıp `/usr/local/Cellar/tesseract/4.1.1/share` klasörüne dosyayı atmanız takdirinde sıkıntısız bir şekilde dili kullanabileceksiniz. (Makalenin yazıldığı tarihte mevcut güncel sürüm)

Farklı bir sürüm kullanıyorsanız `/usr/local/Cellar/tesseract/` klasörüne gidip kurulu olan sürümün içerisindeki `share` klasörü içerisine indirdiğiniz dosyayı atın.
