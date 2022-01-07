---
id: 419
title: "MAC OS'ta PHPRedis ve Redis kurulumu"
date: 2022-01-07T15:30:21+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2022-01-07-macos-redis-kurulumu
categories:
  - Genel
  - MacOS
---
Aslında gayet basit, ihtiyacımız olanlar homebrew ve pecl'i kurduğunuz dizin. Eğer PHP'yi HomeBrew ile kurduysanız, pecl dizini büyük ihtimalle şöyle olacaktır :

<pre> /usr/local/opt/php\@[php versiyonunuz]/bin/pecl </pre>

pecl'in varlığını teyit ettikten sonra başlayabiliriz, sırasıyla şu komutları çalıştıracağız:

{% highlight bash %}
/usr/local/opt/php\@8.1/bin/pecl install igbinary
/usr/local/opt/php\@8.1/bin/pecl install redis
{% endhighlight %}

Bu şekilde PHPRedis'i kurmuş olduk.

Bu kurulum sürecinden sonra PHP servisinizi yeniden başlatmayı unutmayın. Ben hem PHP servisini hem de httpd'yi yeniden başlatıyorum.

___

Şimdi de redisi kuralım, bunun için de Terminale sadece `brew install redis` yazmamız yeterli.

kurulum sonrası çıkan paragrafı okuyun, dilerseniz servisin sürekli arkaplanda çalıştırabilir veya `/usr/local/opt/redis/bin/redis-server /usr/local/etc/redis.conf`  komudunu kullanarak ihtiyaç duyduğunuz anlarda çalıştırabilirsiniz.

Redis için şifreyi de `/usr/local/etc/redis.conf` üzerinden ayarlayabilirsiniz.
