---
id: 226
title: PHP Geliştiricileri için GO Dilini öğrenmeye Giriş
date: 2020-10-16T16:00:32+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-10-16-php-gelistiricileri-icin-go-dilini-ogrenmeye-giris
categories:
  - GO
  - PHP
  - Yazılım
tags:
  - go
  - golang
  - php
  - php geliştiricileri için go dilini öğrenmeye giriş
  - php ile go öğrenmek
---
Bir PHP geliştiricisi olarak GO dilini öğrenmeyi çok istiyordum, uzun bir araştırma yaptıktan sonra sizlere, bu iki dilin arasında bağları ve zıtlıkları gösteren bir içerik çıkarmaya çalışacağım.

## **Kurulum Aşaması** {#h-kurulum-a-amas}

GO’nun [resmi web sitesi](https://golang.org)ne girip işletim sisteminize uygun kurulum paketini indirip kolaylıkla kurabilirsiniz.

## **Başlarken** {#h-ba-larken}

Go’da, tüm Go projeleriniz GOPATH adında tek bir dizinde saklanır, varsayılan olarak GOPATH ana klasörünüzde go olarak ayarlanır, yani kendi bilgisayarımdan örnek vermem gerekirse ~/Users/mrocks/go şeklinde, GOPATH içerisinde birkaç klasör var. Src klasörü içerisinde oluşturacağımız projelerin kaynak kodları olacak, pkg içerisinde bağımlılık olarak indirdiğiniz paketlerin kaynak kodları olacaktır.

Ayrıca bazı işlemler için komut satırına komutlar yazmamız gerekecek. Mesela Go Tour programını indirebiliriz, go get golang.org/x/tour/gotour. İndirdikten sonra çalıştırmak için ise run gotour çalıştırın, çalıştırmanız taktirinde web sunucusu çalıştırılacak ve tarayıcınız ona yönlendirilecektir.

Ayrıca, Go dilini öğrenirken işinizi daha da basitleştirmek isterseniz JetBrains GoLand’ı kullanabilirsiniz, üniversite öğrencileri için tamamen ücretsiz.

Eğer proje oluşturmak istiyorsanız, GoLand içerisinden yeni bir proje oluşturduktan sonra main.go adında bir Go dosyası oluşturup, içeriğine

<pre class="wp-block-code"><code>package main

import "fmt"

func main() {
  fmt.Println("Merhaba Dünya, yine mi sen ?")
}</code></pre>

Yazarsanız derlemek için uygulama içerisindeki kısa yolları kullanabilirsiniz.

## **PHP ile arasındaki büyük farklılıklar**

Artık bir proje kurduğunuza göre, farklı GO özelliklerini keşfetmeye başlayabilirsiniz. Fark edeceğiniz ilk şeylerden biri, GO&#8217;da noktalı virgüllerin gerekli olmamasıdır. Bir ifadenin sonu yeni bir satır tarafından algılanır. İşte anlamak için biraz zaman alan bazı farklılıklar:

### Değişkenler 

Go, statik ve güçlü bir şekilde yazılmış bir dildir, bu nedenle her değişkenin kendisine atanmış bir türü vardır. Go dilinde değişken oluştururken size hız ve kolaylık sağlayacak bir yöntem mevcut, değişken oluştururken := kullanmak yeterli olacaktır, yani: `İsim := “Meriç” // string türünde bir değişken tanımladınız.` İçinde herhangi bir veri ayarlamadan bir değişken oluşturmak için veya işlev dışında (kullanılmayan) değişken oluşturmak için şu söz diziminden yararlanmanız gerekir: `var isim tür`

### Paketler vs Alan adları

Go, içeriğini adlandırmak için paket terimini kullanır, kodunuzda controllers adlı bir klasörünüz varsa bu klasördeki her dosya paket denetleyicileri ile başlar. Denetleyicileri başka bir paketten içeri aktarmak için import “proje/controllers” yazmanız da yeterli olacaktır. Denetleyicilerin içerisinde func HelloWorld() isminde bir fonksiyonunuz varsa denetleyicileri çağırabilirsiniz. Denetleyiciler içe aktarıldıktan sonra fonksiyonu çalıştırmak için ise direkt olarak HelloWorld() kullanabilirsiniz. Ayrıca büyük harfle başlamayan herhangi bir şey yalnızca aynı paketten kullanılabilir.

### Dizeler(string) 

Go’da tüm dizeler çift tırnak ile çerçevelenmek zorundadır, tek tırnak yalnızca Unicode kodları içindir. Bildiğiniz gibi PHP’de dizeleri tek tırnakla yazıyoruz, ne yazık ki buna alışmak biraz zaman alabilir.

<pre class="wp-block-code"><code>var isim = "Meriç"
var galp = '♡'</code></pre>

### Struct&#8217;lar ve Sınıflar 

Go’nun PHP’de gibi bir <mark>sınıf sistemi yok</mark>. Bunun yerine, özel veri yapılarını modellemek için struct kullanılır. Şu şekilde struct yazabilirsiniz:

<pre class="wp-block-code"><code>package main

type Bardak struct {
  isim string
  renk string
  doluluk int
}</code></pre>

Ayrıca fonksiyon isminden önce parantez içerisinde bir struct’u kullanan/başvuran bir fonksiyon oluşturabilirsiniz.

<pre class="wp-block-code"><code>func (b Bardak) isimVeRenk() string {
  return b.isim + ": " + b.renk
}</code></pre>

Yada struct’u değişken içerisinde kullanabiliriz, hatta kullanabiliriz. Yöntem yürütme noktalı gösterimi kullanır.

<pre class="wp-block-code"><code>func main() {
  b := Bardak{isim: "Nescafe", renk: "Siyah", doluluk: 0}
  b.isimVeRenk() // Nescafe : Siyah değerini döndürür.
}</code></pre>

Struct örneğini değiştiren bir yöntem oluşturmak için, yöntemin yapıya bir işaretçiye(pointer) başvurması gerekir:

<pre class="wp-block-code"><code>func (b *Bardak) hayda() {
  b.doluluk = 0
}</code></pre>

## Hatalar 

Go&#8217;da, hatalar istisna olarak değerlendirilmez, atma veya yakalama mekanizması yoktur. Bunun yerine hata oluşmuşsa fonksiyondan hatalar döndürülür. Ayrıca Go fonksiyondan birden fazla değer döndürmeyi destekler, yani hata döndürebilecek bir fonksiyon yazarsanız hatanın oluşup oluşmadığını kontrol etmeniz gerekir. Aşağıdaki örnek kod bloğuna bakarak okuduklarınızı pekiştirebilirsiniz.

<pre class="wp-block-code"><code>package main

import "fmt"

func robotKontrolu(isim string) (string, error) {
  if isim == "Meriç" {
    return "", fmt.Errorf("İsmin Meriç olamaz.")
  }

  return name, nil
}

func main() {
  isim, err := robotKontrolu("Bob")
  if err != nil {
    fmt.Println("hani memleket konusuyla girecektin içeri ?")
  }
}</code></pre>

## Son

Bu yazıda anlatacaklarım bu kadar, tabi ki siz farklı kaynakları kullanarak benden daha fazla şey öğrenebilirsiniz fakat umuyorum ki bu sizler için iyi bir başlangıç olacaktır. Go hakkında daha fazla bilgi için [Go Dökümanlarından](https://merich.rocks/url/2fda4a) veya [Go By Example](https://merich.rocks/url/8ffbec) sitesinden yararlanabilirsiniz.