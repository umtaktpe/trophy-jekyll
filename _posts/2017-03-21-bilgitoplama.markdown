---
layout: post
title: "Pasif Bilgi Toplama"
date: 2017-03-21
categories:
  - Network
description: 
image: http://i.hizliresim.com/5g46al.gif
image-sm: http://i.hizliresim.com/5g46al.gif
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

<h4>2.Katman:Veri Bağlantısı Katmanı</h4>
<p>Bu katmanda fiziksel olarak bağlı iki cihaz arasındaki haberleşmeyi sağlayan ve bu bağlantının koparılmasını sağlayan protokoller bulunur.(MAC,ARP,RARP).</p>

<h4>3.Katman:Ağ Katmanı</h4>
<p>Veri paketlerinin farklı bir ağa gönderilmesi gerektiğinde, bu verilere gerekli bilgilerin eklenmesini sağlayan katmandır.Ağ katmanı,sunucular arası yönlendirme dahil olmak üzere,verinin kaynaktan hedefe gönderilmesinden sorumludur.Ancak bu verinin güvenli olarak gönderilip gönderilmediğini denetlemekten sorumlu değildir.(IP,IPv4,IPv6,ICMP).</p>

<h4>4.Katman:Taşıma Katmanı</h4>
<p>Bu katmanda bulunan protokoller sayesinde biz paketleri gönderip alabiliriz.Bu protokoller TCP ve UDP’dir.TCP protokolü 3’lü el sıkışma mantığı ile çalışır.</p>

<figure>
  <img src="http://i.hizliresim.com/r3jz93.jpg"/>
</figure>

<p>Bu protokolde haberleşme isteği karşı tarafa bildirilir ve eğer karşı taraftan da yanıt gelirse haberleşme başlar.Bunun amacı haberleşmenin daha güvenli olmasını sağlamaktır.UDP protokolünde ise paket karşı tarafa gönderilir ama cevap beklenmez.Bu sayede TCP’ye göre daha hızlı haberleşme sağlar fakat daha güvensizdir.</p>

<h4>5.Katman:Oturum Katmanı</h4>
<p>Oturum katmanı, cihazlar arasındaki bağlantıları kontrol eder.Uzak veya yerel sunuculara bağlantı kurar, bağlantıları yönetir ve koparır.(PAP,HTTP,HTPPS,SSH,Telnet).</p>

<h4>6.Katman:Sunum Katmanı</h4>
<p>Sunum katmanı, gönderilen verilerin karşı tarafın anlayabileceği biçime çevirdiği katmandır.Bu sayede farklı programlar birbirlerine ait verileri kullanabilir.(HTML,CSS,XML,JSON).</p>

<h4>7.Katman:Uygulama Katmanı</h4>
<p>Uygulama katmanı, uygulamaların son kullanıcıya ulaştığı katmandır.Burada kullanıcılar programla etkileşim haline girebilir.(HTTP,FTP,SMTP,DNS).</p>

<h3>Genel Kavramlar</h3>

<p><h4>MAC Adresi:</h4>Kullanılan donanımlara verilen adrestir.MAC adresi fiziksel bir adrestir ve ağ donanımlarının tanımlanmasını sağlar.MAC adresi unique(eşsiz)’dir.Bir MAC adresi 6 oktetten oluşur.İlk 3 oktet üreticiyi, son 3 oktet ise donanımı işaret eder.</p>

<p><h4>ARP:</h4>Bu protokol IP adresinden MAC adresini bulmayı sağlar.</p>

<p><h4>RARP:</h4>Bu protokol ise ARP’ın tersi olarak MAC adresinden IP adresine ulaşmayı sağlar.</p>

<p><h4>DNS(Domain Name System):</h4>nternet ağını oluşturan her birim bir IP adresine sahiptir.Kullanıcaların kolay hatırlaması için bu IP’lere bir www.example.com şeklinde bir domain atanabilir.DNS sunucuları da bu IP adreslerine karşılık gelen domainleri saklar.DNS’in birden fazla kayıt türü vardır.Bunlar:</p>

<ul>
	<li><h5>A kaydı:</h5>Domainlerin IP adreslerini tutar.</li>
	<li><h5>mx kaydı:</h5>DNS sunucuları bir veya birden fazla alan adından sorumludur.Bu alan adından sorumlu maillerin kayıtları burada tutulur.</li>
	<li><h5>cname kaydı:</h5>Alan adlarının tutulduğu yer.</li>
	<li><h5>ns kaydı:</h5>Alan adına ait authoritative DNS sunucusunun kaydının tutulduğu türdür.</li>
	<li><h5>txt kaydı:</h5>Opsiyonel olarak bilgi tutulmak istendiğinde kullanılan kayıtlar.</li>
</ul>

<p><h4>IP(Internet Protocol):</h4>Bu protokol her bir bilgisayarın eşsiz bir adresi olsun diye ortaya çıkmış bir protokoldür.İki versiyonu vardır.IPv4(32 bit) ve IPv6(128 bit).</p>

<p><h4>DHCP(Dynamic Host Control Protocol):</h4>Bilgisayara IP, Gateway, DNS, Proxy vermeye yarayan protokoldür.</p>