---
title: Launchpad Hataları nelerdir? Hatalar nasıl çözülür?
date: 2020-11-20T21:35:00+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2020-11-20-macos-launchpad-hatalarini-gidermek
categories:
  - MacOS
---
Launchpad, Apple tarafından geliştirilen işletim sistemlerinde kullanılan uygulama başlatıcısıdır. Mac OS X Lion sürümünde kullanıcılarla buluşmuştur. Launchpad&#8217;i açtığınızda her uygulamayı temsil eden bir ikon mevcuttur. Çalıştırmak istediğiniz uygulamanın ikonuna tıklamanız yeterlidir.

<blockquote class="wp-block-quote">
  <p>
    Not: Bu makaledeki bilgiler, MacOS Catalina (10.15) ile OS X Lion (10.7) arasındaki Mac&#8217;ler için geçerlidir.
  </p>
</blockquote><figure class="wp-block-image size-large">

<img loading="lazy" width="1024" height="638" src="assets/uploads/2020/11/launcpad-merich.rocks_-1024x638.jpg" alt="MacOS Launchpad Hatalarını Gidermek" class="wp-image-346" /> <figcaption>MacOS Launchpad Hatalarını Gidermek</figcaption></figure> 

## Launchpad&#8217;de Hatalar Nelerdir?

Normal şartlarda kaldırdığınız bir uygulamanın ikonu Launchpad üzerinden silinir fakat bazen bu olağan durum gerçekleşmez ve hata oluşur. 

Veyahut AppStore üzerinden yüklediğiniz uygulamayı, Launchpad üzerinden kaldırmaya çalıştığınızda uygulamanın kaldırılmaması da yaygın hatalardan bir tanesidir.

Ayrıca bazen Uygulamalar klasöründen uygulamayı silmenize rağmen Launchpad&#8217;de uygulama ikonunun soru işareti olması veya uygulama ikonunun üzerine soru işareti gelmesi de yaygın hatalardandır.

<blockquote class="wp-block-quote">
  <p>
    Launchpad sorunlarını düzeltmek, sistem verilerini silmeyi içerir. Devam etmeden önce, Time Machine üzerinden yedekleme almayı unutmayın.
  </p>
</blockquote>

## Hatalar nasıl çözülür?

Launchpad hatalarının çoğunu çözmek için, Launchpad&#8217;in veritabanını yeniden oluşturmaya zorlamak oldukça etkili bir çözüm yoludur.

Launchpad&#8217;in <a rel="noreferrer noopener" href="./2020-11-11-veritabani-nedir" target="_blank">veritabanı</a> dosyasını sildiğinizde ve Launchpad&#8217;i yeniden başlatıldığınızda, veritabanı bulunamadığı için kurulu uygulamaları kontrol edip yeni bir veritabanı oluşturur.

Launchpad&#8217;in veritabanını yeniden oluşturmaya zorlama yöntemi, sahip olduğunuz macOS veya OS X sürümüne bağlı olarak biraz değişir.

## Launchpad veritabanı nasıl yeniden oluşturulur?

<div class="schema-how-to wp-block-yoast-how-to-block">
  <p class="schema-how-to-total-time">
    <span class="schema-how-to-duration-time-text">Gerekli süre: </span>3 dakika.
  </p>
  
  <p class="schema-how-to-description">
    OS X Yosemite (10.10) ve üzeri sürümlerde tüm aşamaları uygulamaya özen gösteriniz. OS X Mavericks (10.9) ve önceki sürümlerde ise 1. gerçekleştirip 4. adımdan itibaren işlemleri yapmaya başlayın.
  </p>
  
  <ol class="schema-how-to-steps">
    <li class="schema-how-to-step" id="how-to-step-1605721759313">
      <strong class="schema-how-to-step-name">Launchpad&#8217;den Çıkın</strong> <p class="schema-how-to-step-text">
        Eğer Launchpad açıksa kapatın, farklı bir pencereye veya masaüstüne tıklayın. Eğer kapalıysa diğer adıma geçin.
      </p>
    </li>
    
    <li class="schema-how-to-step" id="how-to-step-1605722123432">
      <strong class="schema-how-to-step-name">Bir Finder Penceresi Açın</strong> <p class="schema-how-to-step-text">
        Bir finder penceresi açıp <strong>Command+Shift+G</strong> (⌘+⇧+G) tuşlarına basın. Sonra açılan penceredeki kutucuğa &#8220;~/Kitaplık/Application Support/Dock/&#8221; yazıp git tuşuna tıklayın.<img alt="" src="assets/uploads/2020/11/Ekran-Resmi-2020-11-18-21.02.44.png" />
      </p>
    </li>
    
    <li class="schema-how-to-step" id="how-to-step-1605722592386">
      <strong class="schema-how-to-step-name">Veritabanlarını silin</strong> <p class="schema-how-to-step-text">
        <br />Dock klasörü, <em>desktoppicture.db</em> adlı bir dosya da dahil olmak üzere birkaç dosya içerir. Sonu .db ile biten dosyaları seçin. Sonra çöp kutusuna sürükleyin.<br /><img alt="" src="assets/uploads/2020/11/Ekran-Resmi-2020-11-18-21.06.21.png" />
      </p>
    </li>
    
    <li class="schema-how-to-step" id="how-to-step-1605722876790">
      <strong class="schema-how-to-step-name">Terminali açın</strong> <p class="schema-how-to-step-text">
        Önbelleği temizlemek için yapmanız gereken Terminal&#8217;i açıp bir kaç satır kod girmek. Terminali açmak için Spotlight&#8217;tan faydalanalım ⌘ + Space(boşluk) tuşuna basalım. Ekranın ortasına gelen kutucuğa Terminal yazıp enter&#8217;a basalım.
      </p>
    </li>
    
    <li class="schema-how-to-step" id="how-to-step-1605723120341">
      <strong class="schema-how-to-step-name">Önbelleği temizleyin</strong> <p class="schema-how-to-step-text">
        Önbelleği temizlemek için açılan ekrana bu kodu kopyalayıp yapıştırın: <br /><code>&lt;em>defaults write com.apple.dock ResetLaunchPad -bool true&lt;/em></code><br />Kodu yapıştırdıktan sonra enter tuşuna basın.
      </p>
    </li>
    
    <li class="schema-how-to-step" id="how-to-step-1605723311293">
      <strong class="schema-how-to-step-name">Son Adım</strong> <p class="schema-how-to-step-text">
        Aynı pencerede şu koduda çalıştırın.<br /><em><code>killall Dock</code></em><br />Bu işlemlerden sonra bilgisayarınızı yeniden başlatın.
      </p>
    </li>
  </ol>
</div>

Yeniden başlatmadan sonra, Gereken veritabanı dosyası ve önbellek oluşmuş olacaktır. Launchpad&#8217;i ilk açışınızda yavaşladığını düşünebilirsiniz, bu durum normaldir zamanla düzelecektir. Launchpad&#8217;i açtığınızda fark edeceğiniz ilk şey hiç bir şeyin sizin ayarladığınız yerde olmamasıdır. Launchpad&#8217;i ihtiyaçlarınıza göre tekrardan yapılandırmayı unutmayın.
