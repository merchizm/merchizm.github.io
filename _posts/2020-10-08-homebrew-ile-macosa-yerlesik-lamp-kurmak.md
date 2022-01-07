---
title: 'Homebrew ile MacOSa Yerleşik (L)AMP Kurmak'
date: 2020-10-08T22:00:28 03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-10-08-homebrew-ile-macosa-yerlesik-lamp-kurmak
categories: [MacOS, Yazılım]
tags: [Hızlı bir şekilde MacOS AMP Kurulumu ,install lamp on MAC ,kurulum ,lamp ,lamp kurulumu ,MacOS PHP MYSQL APACHE Kurulumu ,MacOS üzerine LAMP Kurmak ,MacOS üzerine localhost kurmak]
---
Merhaba, bundan kısa zaman önce böyle bir Türkçe içeriğin olmadığını fark ettim, ki günümüzde insanlar çoğunlukla her şeyin hazırı olan uygulamaları sevmekte fakat benim gibi klasik sevenler için bugün Homebrew ile MacOS’a Yerleşik (L)AMP kuracağız. Bunu da en hızlı ve en kolay şekilde yapacağız.

## (L)AMP Kurmaya Başlamadan Önce {#h-l-amp-kurmaya-ba-lamadan-nce}

Öncelikle Homebrew nedir, geliştiricilere ne gibi katkısı var sizlere bunu anlatmak istiyorum. Homebrew bir paket yönetim uygulaması, sayesinde bilgisayarınızda olmayan fakat kullanmak istediğiniz paketleri rahatlıkla kurabilirsiniz. Mesela Homebrew ile kolaylıkla wget paketini kurabilir ve hemen kullanmaya başlayabilirsiniz.

### Gereklilikler {#h-gereklilikler}

  * MacOS Yüklü bir cihaz 💻 _(Benim sürümüm 1.15.5 Catalina)_
  * HomeBrew 🍺 _(eğer yüklü değilse, hemen _[https://brew.sh/](https://merich.rocks/url/009515)__ buradan adımlara uyarak kolaylıkla yükleyebilirsiniz_)_

### Hazırlık {#h-haz-rl-k}

  1. Kullanıcınızın dizinine yani genel tabiri ile Ev klasörünüze ‘Sites’ adında bir klasör oluşturun, daha sonra bu klasörü php ve html dosyalarımızla dolduracağız. Klasörü oluşturmak için ise Terminali açıp `$ mkdir ~/Sites` yazalım.
  2. Hatta Apache kurulumu sonrasında kurulumdan emin olmak için Sites klasörü içerisine bir de index.html dosyası oluşturalım, onuda terminale şu şekilde yazarak oluşturacağız. `$ echo "Sites klasörü içerisinden Merhabaa!" >~/Sites/index.html` 
  3. Şimdi ise `$ whoami` komutunu yazıp kullanıcı adımızı öğrenelim, ileride işimize yarayacak mutlaka not alın.

## Apache’nin A’sı 🦅 {#h-apache-nin-a-s}

### Kurulum Aşaması {#h-kurulum-a-amas}

  1. Mac içerisinde varolan Apache’yi durduralım ve çalışmamasını sağlayalım.  
    `$ sudo apachectl stop`  
    `$ sudo launchctl unload -w /Systems/Library/LaunchDaemons/org.apache.httpd.plist`  
    her iki komutu da ayrı ayrı girelim.
  2. şimdi [httpd formula](https://merich.rocks/url/8529b0)‘yı Homebrew ile kuralım. Kurmak için Terminale bu kodu yazın: `$ brew install httpd`  
    Ayrıca ortamlarda satabileceğiniz bir bilgi sunayım, httpd ile Apache aynı şeydir.
  3. Şimdi ise Apache ve arkaplan servislerini çalıştıralım.  
    `$ brew services start httpd`  
    `$ sudo apachectl start`
  4. Eğer <http://localhost:8080/> açarsanız karşınıza “**It works!**” sonuçu çıkacaktır.

### Ayarlar {#h-ayarlar}

Fark ettiğiniz üzere şu an Apache bizim Sites klasörümüzü çalıştırmıyor, çalıştırmak için yapmanız gereken ise aşağıdaki adımları takip etmek.

Önce kullandığınız editör uygulamasında `/usr/local/etc/httpd/httpd.conf` dosyasını açın. Ara ve değiştir özelliğini kullanarak aşağıdaki adımları gerçekleştirin.  
`aratacağınız` ➡️ `değiştiri`lecek şeklinde yaptığınızdan emin olun :).

  1. `Listen 8080` ➡️ `Listen 80`  
    _Bu ayar localhost’a direkt olarak erişmemizi sağlayacaktır._
  2. `DocumentRoot "/usr/local/var/www"` ➡️  
    `DocumentRoot "/Users/<em>KULLANICI_ADINIZ</em>/Sites"`
  3. `<Directory "/usr/local/var/www">` ➡️  
    `<Directory "/Users/<em><em>KULLANICI_ADINIZ</em></em>/Sites">`  
    _Bu iki ayar sayesinde Sites klasörü üzerinde çalışacaktır Apache._
  4. _Daha demin düzenlediğimiz kod blogunun hemen içinde şöyle bir ayar olacaktır, onu da şu şekilde değiştirin:_  
    `AllowOverride None` ➡️ `AllowOverride All`
  5. `#LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`️ ➡️  
    `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`
  6. `User _www` ➡️ `User <em>KULLANICI_ADINIZ</em>`
  7. `Group _www` ➡️ `Group staff#ServerName`
  8. `#ServerName www.example.com:8080` ➡️ `ServerName localhost:8`  
    _bazı adımlarda metinin başındaki # silmeyi unutmayın._

veeeee Ta Daaaa, karşınızda mükemmel bir şekilde kurulmuş ve ayarlanmış bir Apache, şimdi değişikliklerin geçerli olması için Apache’yi yeniden başlatmalıyız. Şu komutu kullanmak kafi sudo `apachectl restart` artık localhost’u açtığınızda karşınıza Sites klasör içeriği gelecek.

## PHP’nin P’si 🐘 {#h-php-nin-p-si}

### Kurulum {#h-kurulum}

  1. Şimdi HomeBrew ile [php formula](https://merich.rocks/url/3fe46d)‘yı kurmak için terminale şu komutunu girelim `$ brew install php`
  2. PHP kurulumu bittikten sonra PHP servislerini açmak için `$ brew services start php` komutunu girelim.

### Ayarlar {#h-ayarlar-1}

Önce kullandığınız editör uygulamasında `/usr/local/etc/httpd/httpd.conf` dosyasını açın. Ara ve değiştir özelliğini kullanarak aşağıdaki adımları gerçekleştirin.  
`aratacağınız` ➡️ `değiştiri`lecek şeklinde yaptığınızdan emin olun :).

  1. Öncelikle son modülün hemen ardında php modülünü eklemekle işimize başlayalım _(ki büyük ihtimal mod_rewrite.so’dur)_  
    `LoadModule php7_module /usr/local/opt/php/lib/httpd/modules/libphp7.so`
  2. `DirectoryIndex index.html` ➡️ `DirectoryIndex index.html index.php`
  3. Hemen DirectoryIndex alanı ile htaccess/htpasswd “IfModule” alanı arasına şu kod bloğunu yerleştirin:  
    `<FilesMatch \.php$><br>SetHandler application/x-httpd-php<br></FilesMatch>`
  4. Apache servisinizi bu komutla `$ sudo apachectl restart` yeniden başlatın.  
    

Ahha! php’nin en son sürümünü de kurduk ve ayarlamalarını yaptık. Şimdi php’nin kurulduğundan emin olmak için Sites klasörümüze gidip info.php isminde dosya oluşturalım ve editörümüzde içerisine `<?php phpinfo();` kodunu yazıp kaydedelim. _http://localhost/info.php_‘i açtığınızda phpinfo komutunun çıktısını göreceksiniz.

## MySql’in M’si 🐬 {#h-mysql-in-m-si}

### Kurulum {#h-kurulum-1}

  1. Homebrew ile [mysql formula](https://merich.rocks/url/cb1ad7) paketini kuralım, bunun için terminale `$ brew install mysql` yazalım.
  2. MySql’i çalıştıralım.  
    `$ brew services start mysql`

### Ayarlar {#h-ayarlar-2}

  * MySql’i ayarlamak için terminale `$ mysql_secure_installation` yazalım.

  1. Şimdi tam olarak belirttiğim gibi ayarlarınızı yapın.  
    “Would you like to setup VALIDATE PASSWORD component?”: _n_  
    “password for root”: _mysql\_için\_şifreniz_  
    “Remove anonymous users?”: _y_  
    “Disallow root login remotely?”: _y_  
    “Remove test database and access to it?”: _y_  
    “Reload privilege tables now?”: _y_

Yeyy! Tebrikler MySql kurup başarılı bir şekilde ayarladık. Homebrew ile servisleri istediğiniz gibi kapatabilir|açabilir|yeniden başlatabilirsiniz, `$ brew services start|stop|restart mysql`. Eğer mysql bağlantınızı sınamak isterseniz W3Schools’un hazırladığı [bu makale](https://merich.rocks/url/d5c3eb) ile sınayabilirsiniz.

## Peki ya şimdi ? {#h-peki-ya-imdi}

#### -Sites klasörü içerisinde ayar dosyalarının bağlantılarını oluşturmak {#h-sites-klas-r-i-erisinde-ayar-dosyalar-n-n-ba-lant-lar-n-olu-turmak}

Bu noktada, Sites dizininizin içinde (L)AMP yığınınızın farklı yapılandırma dosyalarına ve klasörlerine bağlantılar oluşturmanızı öneririm.

  1. Sites klasörü içerisinde etc adında bir klasör oluşturalım ve bu klasör içerisine ayar dosyalarının bağlantılarını oluşturalım.  
    `$ mkdir /Users/<em>KULLANICI_ADINIZ</em>/Sites/etc`
  2. Apache  
    `$ ln -s /usr/local/etc/httpd /Users/<em><em>KULLANICI_ADINIZ</em></em>/Sites/etc/httpd`
  3. MySQL  
    `$ ln -s /usr/local/etc/my.cnf /Users/<em><em><em>KULLANICI_ADINIZ</em></em></em>/Sites/etc/my.cnf`
  4. PHP  
    `$ ln -s /usr/local/etc/php/7.2 /Users/<em><em><em>KULLANICI_ADINIZ</em></em></em>/Sites/etc/php72`

işte bu kadar. Artık yeni projelerinizi ve websitelerinizi burada deneyimleyebilirsiniz, hemde uygulama açmak zorunda kalmadan şappadanak, bir sonraki makalede görüşmek üzere.



<p style="font-size:12px">
  bu makale yazar tarafından tercüme edilmiştir. Kaynak:<a href="https://medium.com/@JanFaessler/setup-local-lamp-stack-on-mac-with-homebrew-47eb8d6d53ea">https://medium.com/@JanFaessler/setup-local-lamp-stack-on-mac-with-homebrew-47eb8d6d53ea</a>
</p>