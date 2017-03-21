---
layout: post
title: "Pasif Bilgi Toplama"
date: 2017-03-21
categories:
  - Network
description: 
image: 
image-sm:
---

<h3>Pasif Bilgi Toplama</h3>

<p>Pasif bilgi toplama işlemleri, hedef hakkında kayıtlara düşmeden bilgi toplama işlemlerdir.Bu işlemleri çeşitli kali tool'larıyla yapmak mümkündür.Aşağıda bunlardan bazılarını anlatmaya çalışacağım.</p>

<h4>IP Adresinin Tespiti </h4>

<p>Öncelikli amacımız hedefin IP adresini tespit etmektir.Bunun için ping atarak veya nslookup aracını kullanarak tespit yapabiliriz.</p>

<ul>
	<li>ping google.com.tr</li>
	<li>nslookup</li>
	<li>nslookup server değiştirerek ip adresi bulma:</li>
		<ul>
        	<li>server 8.8.8.8</li>
        	<li>www.google.com.tr</li>
		</ul>

	<figure>
  		<img src="http://i.hizliresim.com/Npk8jN.png"/>
	</figure>

	<li>Whois:</li>

	<figure>
  		<img src="http://i.hizliresim.com/nRE9ng.png"/>
	</figure>
<ul>

<h4>DNS Analizi</h4>

<ul>
	<li>A kaydı:</li>
	<p>dig www.linux.org.tr</p>
	
	<figure>
  		<img src="http://i.hizliresim.com/4P0Qgq.png"/>
	</figure>

	<li>NS kaydı:</li>
	<p>dig www.linux.org.tr NS</p>

	<figure>
  		<img src="http://i.hizliresim.com/bryp4m.png"/>
	</figure>

	<li>SOA kaydı:</li>
	<p>dig www.linux.org.tr SOA</p>
	<figure>
  		<img src="http://i.hizliresim.com/9QGA9Z.png"/>
	</figure>

	<li>Tüm DNS bilgileri:</li>
	<figure>
  		<img src="http://i.hizliresim.com/ojEp2X.png"/>
	</figure>

</ul>

<h4>Subdomain Tespiti</h4>
<p>Veri paketlerinin farklı bir ağa gönderilmesi gerektiğinde, bu verilere gerekli bilgilerin eklenmesini sağlayan katmandır.Ağ katmanı,sunucular arası yönlendirme dahil olmak üzere,verinin kaynaktan hedefe gönderilmesinden sorumludur.Ancak bu verinin güvenli olarak gönderilip gönderilmediğini denetlemekten sorumlu değildir.(IP,IPv4,IPv6,ICMP).</p>

<ul>
	<li>Fierce :</li>
	<p>fierce -dns ankara.edu.tr</p>
	<figure>
  		<img src="http://i.hizliresim.com/vbZV6v.png"/>
	
	</figure>
	
	<li>Theharvester:</li>
	<p>theharvester -d ankara.edu.tr -b all</p>
	<figure>
  		<img src="http://i.hizliresim.com/Eg3N2A.png"/>
	</figure>
	
	<li>Dnsmap:</li>
	<p>dnsmap ankara.edu.tr</p>
	<figure>
  		<img src="http://i.hizliresim.com/4P0QWG.png"/>
	</figure>
</ul>

<h4>Virtualhost Tespiti</h4>
<ul>
	<li>bing.com arama motorundan IP:x.y.z.a şeklinde arama yaptığımızda virtualhost'lara ulaşabiliriz.</li>
	<li>dig -x ankara.edu.tr</li>
	<figure>
  		<img src="http://i.hizliresim.com/5gYXzz.png"/>
	</figure>
</ul>

<h4>E-mail Tespiti</h4>
<p>Tespit için yine theharvester tool’unu kullanabiliriz.</p>
<figure>
  		<img src="http://i.hizliresim.com/1LNB3B.png"/>
	</figure>

<h4>Shodan kullanımı:</h4>

<ul>
	<li>Port Taraması</li>
		<ul>
			<li>Port taraması örneği || port:22,80,445</li>
		</ul>
	<li>Server Taraması</li>
		<ul>
			<li>Server taraması örneği || server:webcam</li>
		</ul>
	<li>İşletim Sistemi Taraması</li>
		<ul>
			<li>İşletim Sistemine göre tarama örneği || os:"linux"</li>
		</ul>
	<li>Ülkeye Göre Tarama</li>
		<ul>
			<li>Ülkeye göre tarama örneği || country:TR</li>
		</ul>
</ul>

<h4>Google Dork ile arama</h4>

<ul>
	<li>site:*.ankara.edu.tr --> subdomain listeler</li>
	<li>inurl:login site:*.ankara.edu.tr</li>
</ul>

<h4>Cloudflare:</h4>

<p>Siteleri koruyan bir firewall servisidir.Sitenin bilgilerini gizler.(ip,ddos savunma, vb.)</p>

<ul>
	<li>Atlatma yolları</li>
		<ul>
			<li>Ağ haritasını çıkararak </li>
			<li>Subdomainlerinin ip adreslerine bakarak</li>
			<li>Mail serverin ip adresine bakarak</li>
			<li>Bazı otomatize araçlar ve scriptler sayesinde</li>
		</ul>
</ul>

<h4>Lokasyon Tespiti:</h4>

<p>ipinfo.io, ip2location.com, whois.domaintools.com (IP adresini aratarak)</p>

<h4>İndirelebilir Dosyaların Keşifi</h4>

<ul>
	<li>google</li>
		<ul><li>filetype:pdf ankara.edu.tr</li></ul>
	<li>FOCA =windowsta çalışan ve hedefe ait bütün dosyaları tarayan içindeki user,pass,keywordleri çıkaran tool.</li>
</ul>

<h4>Reverse whois:</h4>

<p>IP adresi veriyoruz. Bu IP adresine ait bilgilere ulaşıyoruz.</p>

<ul>
	<li>whois.com (sansürlü, güncel)</li>
	<li>viewdns.info (sansürsüz, eski)</li>
</ul>

<h4>Alexa analizi:</h4>

<ul><li>www.alexa.com : Domain'ler hakkında istatiksel bilgiler tutan bir servis.</li></ul>

<h4>İş ilanları analizi:</h4>

<ul><li>Bazen araştırılan hedef, kendisi hakkında donanım/yazılım bilgilerini iş ilanlarında paylaşmış olabilir.</li></ul>

<h4>Archive.org analizi:</h4>
<ul><li>archive.org : İnternet sitelerinin eski belgelerinin yer alıyor olabileceği bir servis. Bağımsız ve kar amacı gütmüyor.</li></ul>

<h4>Sosyal medya hesaplarının analizi:</h4>
<ul><li>Facebook'da paylaşığı fotoğraf bir çok bilgi verebilir. Örnek: Bilgisayarın ekran görüntüsü atmış olabilir. Kritik bir bilgi elde edebiliriz. (veriden veri üretme) (fotoğraftan parmak izi çıkartan adam örneği)</li></ul>

<h4>Kaynak kod ve geliştirici firma analizi:</h4>

<ul><li>Bir websitesinin kaynak kodları incelenerek bilgi elde edilebilir.</li></ul>

<h4>Çalışanların geliştirici siteleri analizi:</h4>

<ul><li>Hedef kurumdaki çalışanların github hesaplarından bilgi elde edilebilir.</li></ul>

<h4>Pastebin üzerinden bilgi toplama:</h4>

<ul>
	<li>www.pastebin.com:</li>
	<ul>
		<li>Dump'ların vs. paylaşıldığı bir site.</li>
	</ul>
</ul>