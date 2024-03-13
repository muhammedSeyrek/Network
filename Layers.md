**Uygulama Katmanı**

Ad Sistemi

- **DNS** - Etki Alan Adı Sistemi. Cisco.com gibi alan adlarını IP adreslerine çevirir.

Host Yapılandırma

- **DHCPv4** - IPv4 için Dinamik Ana Bilgisayar Yapılandırma Protokolü. DHCPv4 sunucusu, başlangıçta DHCPv4 istemcilerine IPv4 adresleme bilgilerini dinamik olarak atar ve artık ihtiyaç duyulmadığında adreslerin yeniden kullanılmasına izin verir.
- **DHCPv6** - IPv6 için Dinamik Ana Bilgisayar Yapılandırma Protokolü. DHCPv6, DHCPv4'e benzer. DHCPv6 sunucusu, başlangıçta DHCPv6 istemcilerine IPv6 adresleme bilgilerini dinamik olarak atar.
- **SLAAC** - Durumsuz Adres Otomatik Yapılandırma. Bir aygıtın DHCPv6 sunucusu kullanmadan IPv6 adresleme bilgilerini almasını sağlayan bir yöntem.

E-posta

- **SMTP** - Basit Posta Aktarım Protokolü. İstemcilerin bir posta sunucusuna e-posta göndermesini sağlar ve sunucuların diğer sunuculara e-posta göndermesini sağlar.
- **POP3** - Postane Protokolü sürüm 3. İstemcilerin bir posta sunucusundan e-posta almasını ve e-postayı istemcinin yerel posta uygulamasına indirmesini sağlar.
- **IMAP** - İnternet Mesaj Erişim Protokolü. İstemcilerin, bir posta sunucusunda depolanan e-postalara erişebilmesinin yanı sıra sunucuda e-postaları da korumasını sağlar.

Dosya Transferi

- **FTP** - Dosya Aktarım Protokolü. Bir hosttaki kullanıcının başka bir hosttaki dosyalara ağ üzerinden erişmesini veya aktarıp almasını sağlayan kuralları belirler. FTP güvenilirdir, bağlantı odaklı ve onaylı bir dosya dağıtım protokolüdür.
- **SFTP** - SSH Dosya Aktarım Protokolü. Secure Shell (SSH) protokolünün bir uzantısı olarak SFTP, dosya aktarımının şifrelendiği güvenli bir dosya aktarım oturumu oluşturmak için kullanılabilir. SSH, genellikle bir cihazın komut satırına erişmek için kullanılan güvenli uzaktan oturum açma yöntemidir.
- **TFTP** - Önemsiz Dosya Aktarım Protokolü. En iyi çaba gerektiren, onaylı olmayan dosya teslimi ile basit, bağlantısız bir dosya aktarım protokolü. FTP'den daha az ek yük kullanır.

Web ve Web Hizmeti.

- **HTTP** - Köprü Metin Transfer Protokolü World Wide Web'de metin, grafik görüntü, ses, video ve diğer multimedya dosyalarını alıp vermek için bir dizi kural.
- **HTTPS** - HTTP Güvenli. World Wide Web üzerinden değiştirilen verileri şifreleyen güvenli bir HTTP formu.
- **REST** - Temsili Durum Transferi. Web uygulamaları oluşturmak için uygulama programlama arayüzlerini (API'ler) ve HTTP isteklerini kullanan bir web hizmeti.


**Taşıma katmanı**

Bağlantı Odaklı

- **TCP** - İletim Kontrol Protokolü. Ayrı ana bilgisayarlarda çalışan süreçler arasında güvenilir iletişimi sağlar ve başarılı teslimatı doğrulayan güvenilir, onaylı iletimler sağlar.

Bağlantısız

- **UDP** - Kullanıcı Datagram Protokolü. Bir hostta çalışan bir işlemin, başka bir hostta çalışan bir işleme paket göndermesini sağlar. Ancak, UDP başarılı datagram iletimini doğrulamaz.


**İnternet Katmanı**

İnternet Protokolü

- **IPv4** - İnternet Protokolü sürüm 4. Taşıma katmanından ileti kesimlerini alır, iletileri paketler ve ağ üzerinden uçtan uca teslim etmek için paketleri adresler. IPv4, 32 bit adres kullanır.
- **IPv6** - IP sürüm 6. IPv4'e benzerdir ancak 128-bit adres kullanır.
- **NAT** - Ağ Adres Çevirisi. Özel bir ağdaki IPv4 adreslerini, genel olarak benzersiz genel IPv4 adreslerine çevirir.

Mesajlaşma

- **ICMPv4** - IPv4 için İnternet Kontrol Mesajı Protokolü. Paket dağıtımındaki hatalar hakkında bir hedef hosttan kaynak hosta geri bildirim sağlar.
- **ICMPv6** - IPv6 için ICMP. ICMPv4 ile benzer işlevsellik sağlar, ancak IPv6 paketleri için kullanılır.
- **ICMPv6 ND** - ICMPv6 Komşu Keşfi. Adres çözümlemesi ve yinelenen adres algılaması için kullanılan dört protokol iletisi içerir.

Yönlendirme Protokolleri

- **OSPF** - Açık Önce En Kısa Yol Alanlara dayalı hiyerarşik bir tasarım kullanan bağlantı durumu yönlendirme protokolü. OSPF açık standart bir iç yönlendirme protokolüdür.
- **EIGRP** - Gelişmiş İç Ağ Geçidi Yönlendirme Protokolü. Bant genişliği, gecikme, yük ve güvenilirliğe dayalı kompozit metrik kullanan, Cisco tescilli bir yönlendirme protokolü.
- **BGP** - Sınır Geçidi Protokolü. Internet Servis Sağlayıcıları (ISS) arasında kullanılan açık standart dış ağ geçidi yönlendirme protokolü. BGP aynı zamanda ISS'ler ile büyük özel müşterileri arasında yönlendirme bilgileri alışverişinde bulunmak için yaygın olarak kullanılmaktadır.


**Ağ Erişim Katmanı**

Adres Çözümleme

- **ARP** - Adres Çözümleme Protokolü. IPv4 adresi ile donanım adresi arasında dinamik adres eşlemesi sağlar.

Veri Bağlantısı Protokolleri

- **Ethernet** - Ağ erişim katmanının kablolama ve sinyalizasyon standartlarını tanımlar.
- **WLAN** - Kablosuz Yerel Alan Ağı. 2,4 GHz ve 5 GHz radyo frekanslarında kablosuz sinyal verme kurallarını tanımlar.

