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

<h4>4.Katman:Taşıma Katmanı</h4>
<p>Bu katmanda bulunan protokoller sayesinde biz paketleri gönderip alabiliriz.Bu protokoller TCP ve UDP’dir.TCP protokolü 3’lü el sıkışma mantığı ile çalışır.</p>

<figure>
  <img src="http://i.hizliresim.com/r3jz93.jpg"/>
</figure>

<p>Bu protokolde haberleşme isteği karşı tarafa bildirilir ve eğer karşı taraftan da yanıt gelirse haberleşme başlar.Bunun amacı haberleşmenin daha güvenli olmasını sağlamaktır.UDP protokolünde ise paket karşı tarafa gönderilir ama cevap beklenmez.Bu sayede TCP’ye göre daha hızlı haberleşme sağlar fakat daha güvensizdir.</p>

<h4>Subdomain Tespiti</h4>

<p>Tool kullanmadan sadece arama motorlarını kullanarak subdomain tespiti mümkündür.Örneğin, google üzerinde *.pau.edu.tr şeklinde arama yaptığımız zaman subdomainlere ulaşabiliriz.Tabii bunu kali tool’ları kullanarak yapmakta mümkün.</p>

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

<h3>Shodan kullanımı:</h3>

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

