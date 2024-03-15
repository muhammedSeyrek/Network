# Adresler

Çok kısa bir süre önce öğrendiğiniz gibi, bir ağdaki mesajları bölümlere ayırmanız gerekir. Ancak bu bölümlere ayrılmış mesajlar düzgün bir şekilde ele alınmadıkları takdirde hiçbir yere gitmez. Bu konu, ağ adreslerine genel bir bakış sunar. Ayrıca ağ trafiğini 'görüntülemenize' yardımcı olacak Wireshark aracını kullanma şansına sahip olacaksınız.

Ağ ve veri bağlantı katmanları, verilerin kaynak cihazdan hedef cihaza iletilmesinden sorumludur. Şekilde gösterildiği gibi, her iki katmandaki protokoller bir kaynak ve hedef adres içerir, ancak adreslerinin farklı amaçları vardır:

- **Ağ katmanı kaynağı ve hedef adresleri**  - IP paketini orijinal kaynaktan aynı ağda veya uzak ağda olabilecek nihai hedefe teslim etmekten sorumludur.
- **Veri bağlantısı katmanı kaynağı ve hedef adresleri** - Veri bağlantısı çerçevesini bir ağ arabirim kartından (NIC) aynı ağdaki başka bir NIC'ye teslim etmekten sorumludur.

## 3.Katman Mantıksal Adres

IP adresi, şekilde gösterildiği gibi IP paketini orijinal kaynaktan nihai hedefe iletmek için kullanılan ağ katmanı veya Katman 3'tür.

IP paketi iki IP adresi içerir:

- **Kaynak IP adresi**  - Paketin orijinal kaynağı olan gönderen cihazın IP adresi.
- **Hedef IP adresi**   - Paketin son hedefi olan alıcı cihazın IP adresi.

IP adresleri orijinal kaynak IP adresini ve son hedef IP adresini gösterir. Kaynak ve hedef aynı IP ağında veya farklı IP ağlarında olsun, bu doğrudur.

IP adresi iki bölümden oluşur:

- **Ağ bölümü (IPv4) veya Önek (IPv6)**   - IP adresinin üye olduğu ağı gösteren adresin en soldaki kısmı. Aynı ağdaki tüm cihazlar, adresin aynı ağ bölümüne sahip olacaktır.
- **Ana bilgisayar bölümü (IPv4) veya Arabirim Kimliği (IPv6)**   - Adresin ağdaki belirli bir aygıtı tanımlayan kalan kısmı. Bu bölüm ağdaki her cihaz veya arabirim için benzersizdir.

**Not**: Ana bilgisayar bölümünden bir IP adresinin ağ bölümünü tanımlamak için alt ağ maskesi (IPv4) veya önek uzunluğu (IPv6) kullanılır.


Aynı Ağdaki## Aygıtlar

Bu örnekte, aynı IP ağındaki bir FTP sunucusuyla iletişim kuran PC1 istemci bilgisayarımız bulunmaktadır.

- **Source IPv4 address** - The IPv4 address of the sending device, the client computer PC1: 192.168.1.110.
- **Destination IPv4 address** - The IPv4 address of the receiving device, FTP server: 192.168.1.9.

Hem kaynak IPv4 adresinin hem de hedef IPv4 adresinin ağ bölümünün aynı ağda olduğuna dikkat edin. Kaynak IPv4 adresinin ağ kısmının ve hedef IPv4 adresinin ağ kısmının aynı olduğuna ve dolayısıyla kaynak ve hedef aynı ağda olduğuna dikkat edin.

## Veri Bağlantısı Katmanı Adreslerinin Rolü: Aynı IP Ağı

IP paketinin göndereni ve alıcısı aynı ağ üzerinde olduğunda, veri bağlantısı çerçevesi doğrudan alıcı cihaza gönderilir. Ethernet ağında, veri bağlantı adresleri şekilde gösterildiği gibi Ethernet Ortam Erişim Kontrolü (MAC) adresleri olarak bilinir.

MAC adresleri fiziksel olarak Ethernet NIC üzerine yerleştirilmiştir.

- **Kaynak MAC adresi**   - Bu, veri bağlantı çerçevesini kapsüllenmiş IP paketiyle gönderen cihazın veri bağlantı adresi veya Ethernet MAC adresidir. PC1'in Ethernet NIC'inin MAC adresi, onaltılık gösterimde yazılmış AA-AA-AA-AA-AA-AA'dır.
- **Destination MAC address** - When the receiving device is on the same network as the sending device, this is the data link address of the receiving device. In this example, the destination MAC address is the MAC address of the FTP server: CC-CC-CC-CC-CC-CC, onaltılık gösterimde yazılmıştır.

Kapsüllenmiş IP paketine sahip çerçeve şimdi doğrudan PC1'den FTP sunucusuna iletilebilir.

Uzak Ağdaki## Aygıtlar

Fakat bir cihaz uzak ağdaki başka bir cihaz ile iletişim halindeyken ağ katmanı adresi ve veri bağlantısı katmanı adresinin rolü nedir? Bu örnekte istemci bilgisayar olan PC1, farklı bir IP ağında bulunan Web Sunucusu adındaki sunucu ile iletişime geçiyor.

Ağ Katmanı Adreslerinin## Rolü

Paketin göndereni alıcıdan farklı bir ağda olduğunda, kaynak ve hedef IP adresleri farklı ağlardaki hostları temsil edecektir. Bu, hedef hostun IP adresinin ağ bölümü tarafından gösterilecektir.

- **Source IPv4 address** - The IPv4 address of the sending device, the client computer PC1: 192.168.1.110.
- **Destination IPv4 address** - The IPv4 address of the receiving device, the server, Web Server: 172.16.1.99.

Kaynak IPv4 adresinin ve hedef IPv4 adresinin ağ bölümünün farklı ağlarda olduğuna dikkat edin.


## Veri Bağlantısı Katmanı Adreslerinin Rolü: Farklı IP Ağları

IP paketinin alıcısı ve göndereni farklı ağlarda olduğunda, host gönderenin ağı üzerinde doğrudan ulaşılabilir olmadığı için Ethernet veri bağlantısı çerçevesi doğrudan hedef hosta gönderilemez. Ethernet çerçevesi, yönlendirici veya varsayılan ağ geçidi olarak bilinen başka bir cihaza gönderilmelidir. Örneğimizde varsayılan ağ geçidi R1'dir. R1, PC1 ile aynı ağda bulunan bir Ethernet veri bağlantısı adresine sahiptir. Bu, PC1'in yönlendiriciye doğrudan ulaşmasını sağlar.

- **Kaynak MAC adresi**   - Gönderen cihazın Ethernet MAC adresi, PC1. PC1'in Ethernet arayüzünün MAC adresi AA-AA-AA-AA-AA-AA.
- **Hedef MAC adresi**   - Alıcı cihaz, hedef IP adresi, gönderen cihazdan farklı bir ağda olduğunda, gönderen cihaz varsayılan ağ geçidinin veya yönlendiricinin Ethernet MAC adresini kullanır. Bu örnekte, hedef MAC adresi, R1 Ethernet arabiriminin 11-11-11-11-11-11 MAC adresidir. Şekilde gösterildiği gibi PC1 ile aynı ağa bağlı olan arabirimdir.

Kapsüllenmiş IP paketine sahip Ethernet çerçevesi şimdi R1'e iletilebilir. R1 paketi hedef Web Sunucusu'na iletir. Bu, hedef R1'e bağlı bir ağdaysa R1'in paketi başka yönlendiriciye veya doğrudan Web Sunucusu'na ilettiği anlamına gelebilir.

Varsayılan ağ geçidinin IP adresinin yerel ağdaki her hostta yapılandırılması önemlidir. Uzak ağlardaki bir hedefe giden tüm paketler varsayılan ağ geçidine gönderilir. Ethernet MAC adresleri ve varsayılan ağ geçidi diğer modüllerde daha ayrıntılı olarak anlatılmıştır.


## Veri Bağlantısı Adresleri

Katman 2 fiziksel adresinin veri bağlantısı farklı bir role sahiptir. Veri bağlantısı adresinin amacı, veri bağlantısı çerçevesini bir ağ arayüzünden aynı ağ üzerindeki başka bir ağ arayüzüne iletmektir.

Bir IP paketinin kablolu veya kablosuz bir ağ üzerinden gönderilmeden önce, veri bağlantısı çerçevesinde kapsüllenmesi gerekir, böylece fiziksel ortam üzerinden iletilebilir.

IP paketi ana bilgisayardan yönlendiriciye, yönlendiriciden yönlendiriciye ve son olarak yönlendiriciden ana bilgisayara giderken, IP paketinin yeni bir veri bağlantısı çerçevesinde kapsüllenir. Her veri bağlantısı çerçevesi, çerçeveyi gönderen NIC kartının kaynak veri bağlantı adresini ve çerçeveyi alan NIC kartının hedef veri bağlantı adresini içerir.

Katman 2, veri bağlantısı protokolü yalnızca paketi NIC'den NIC'e aynı ağ üzerinde teslim etmek için kullanılır. Yönlendirici, bir NIC'de alındığı sırada Katman 2 bilgilerini kaldırır ve çıkış NIC'sini son hedefe doğru yönlendirmeden önce yeni veri bağlantısı bilgilerini ekler.

IP paketi, aşağıdaki veri bağlantısı bilgilerini içeren bir veri bağlantısı çerçevesinde kapsüllenir:

- **Kaynak veri bağlantı adresi** - Veri bağlantı çerçevesini gönderen NIC'nin fiziksel adresi.
- **Hedef veri bağlantısı adresi**- Veri bağlantı çerçevesini alan NIC'nin fiziksel adresi. Bu adres, bir sonraki atlama yönlendiricisi veya son hedef aygıtın adresidir.


