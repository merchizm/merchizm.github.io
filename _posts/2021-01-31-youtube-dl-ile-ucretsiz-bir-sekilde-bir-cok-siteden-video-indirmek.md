---
id: 405
title: youtube-dl ile ücretsiz bir şekilde bir çok siteden video indirmek
date: 2021-01-31T16:21:06+03:00
author: Meriç Enes Kayalar
layout: post
permalink: /2021-01-31-youtube-dl-ile-ucretsiz-bir-sekilde-bir-cok-siteden-video-indirmek
categories:
  - Genel
  - MacOS
tags:
  - youtube-dl
---
Başlıkta da belirttiğim gibi popüler birçok siteyi destekleyen ve desteklenen sitelerdeki videoları indirmenize avantaj sağlayan bir uygulama. Gizli veya grup içi videoları indirmek için hesabınızı kullanabiliyorsunuz. Yani hesabınıza giriş yapıyorsunuz. 

Ayrıca uygulama tamamen terminal üzerinden kullanılıyor. MacOS&#8217;ta <a href="https://formulae.brew.sh/formula/youtube-dl" target="_blank" rel="noreferrer noopener">Homebrew</a> ile çok basit bir şekilde kurulumunu yapabilirsiniz. Windows&#8217;ta kurmak için ise <a href="https://github.com/ytdl-org/youtube-dl/releases/latest" target="_blank" rel="noreferrer noopener nofollow">githubdan</a> indirip, aynı klasörde açtığınız command prompt ile çalıştırabilirsiniz. Her klasörden erişip çalışmak için ise path&#8217;e eklemeniz gerekiyor. <a href="https://www.howtogeek.com/118594/how-to-edit-your-system-path-for-easy-command-line-access/" target="_blank" rel="noreferrer noopener nofollow">Tıklayarak</a> bunun için yazılmış makaleye gidebilirsiniz.

kullanımı ise gayet basit:

<pre class="wp-block-preformatted">youtube-dl <a href="https://www.youtube.com/watch?v=EL-D9LrFJd4">https://www.youtube.com/watch?v=EL-D9LrFJd4</a></pre>

tabi ki diğer parametrelere `--help` yazarak erişebilir ve tam olarak nasıl kullanacağınızı öğrenebilirsiniz.

İçeriğin kalite seçeneklerini görmek için `-F` parametresini kullanın. Büyük bir f olmasına dikkat edin. Karşınıza gelen liste sayesinde format kodlarının karşısındaki kalite değerlerini göreceksiniz. Bu sefer format koduyla beraber küçük f ile şu şekilde bir kullanım sergileyin.

**NOT:** _Bağlantıyı tek tırnak içerisine &#8216;bu şekilde&#8217; almayı unutmayın._

<pre class="wp-block-preformatted">youtube-dl -F 'https://www.youtube.com/watch?v=EL-D9LrFJd4'
-- çıktı olarak kalite değerlerinin bulunduğu listeyi aldım.
youtube-dl -f 137 'https://www.youtube.com/watch?v=EL-D9LrFJd4'
-- indirme başladı.</pre>

<img loading="lazy" src="https://i.hizliresim.com/Dil4Zh.png" alt="" width="670" height="426" />

Unutmayın ki indirme terminalin veya command prompt&#8217;un çalıştığı dizinde gerçekleşecektir. MacOS&#8217;ta terminalin bulunduğu dizini açmak için `open .` komutu girmeniz gerekirken, Windows&#8217;ta `explorer .` komutu girmelisiniz.

Tabi bu uygulamanın avantajları nedeniyle arayüzü gönüllü bir kişi tarafından tasarlanmış. Onu indirip kullanmak isterseniz <a href="https://github.com/MrS0m30n3/youtube-dl-gui" target="_blank" rel="noreferrer noopener nofollow">buraya tıklayıp github </a>sayfasına gidebilirsiniz.

Umarım bu yazı yararlı olmuştur. Sık sık kullandığım bu aracı sizlere bu şekilde önermek istedim.