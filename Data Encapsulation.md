## Mesajları Bölümleme

OSI referans modelini ve TCP/IP protokol modelini bilmek, bir ağ üzerinden hareket eden verilerin nasıl kapsüllendiğini öğrendiğinizde kullanışlı olacaktır. Bu süreç, posta sistemi aracılığıyla gönderilen fiziksel bir mektup kadar basit değildir.

Teorik olarak, bir video veya bir çok büyük eki olan bir e-posta mesajı gibi tek bir iletişim, bir ağ üzerinden bir kaynaktan bir hedefe devasa, kesintisiz bir bit akışı olarak gönderilebilir. Ancak bu durum, aynı iletişim kanallarını veya bağlantılarını kullanması gereken diğer aygıtlar için sorun yaratacaktır. Bu büyük veri akışları önemli gecikmelere neden olacaktı. Ayrıca, birbirine bağlı ağ altyapısında herhangi bir bağlantı iletim sırasında başarısız olursa, mesajın tamamı kaybolur ve tam olarak yeniden iletilmesi gerekir.

Daha iyi bir yaklaşım, veriyi ağ üzerinden göndermek için daha küçük ve daha yönetilebilir parçalara bölmektir. Bölümleme (segmentasyon), bir veri akışını ağ üzerinden iletimler için daha küçük birimlere bölme işlemidir. Veri ağları TCP/IP protokol paketini kullandığından, verileri tek tek IP paketlerine gönderdiğinden, bölümlendirme gereklidir. Her paket, ayrı ayrı kartpostal dizisi olarak uzun bir mektup göndermeye benzer şekilde ayrı ayrı gönderilir. Aynı hedef için segmentleri içeren paketler, farklı yollar üzerinden gönderilebilir.

İletilerin bölümlenerek gönderilmesinin iki temel faydası vardır:

- **Hızı artırır** - Büyük bir veri akışı paketlere ayrıldığından, bir iletişim linki olmadan ağ üzerinden büyük miktarda veri gönderilebilir. Bu, ağda çoğullama adı verilen birçok farklı konuşmanın araya girmesini sağlar.
- **Verimliliği artırır** - Ağdaki bir başarısızlık veya ağ tıkanıklığı nedeniyle tek bir segment hedefine ulaşamazsa, tüm veri akışını yeniden göndermek yerine yalnızca o segmentin yeniden iletilmesi gerekir.

## Sıralama

Mesajları bir ağ üzerinden iletmek için segmentasyon ve çoğullama kullanmanın zorluğu, sürece eklenen karmaşıklık düzeyidir. 100 sayfalık bir mektup göndermeniz gerektiğini, ancak her zarfın yalnızca bir sayfa alabileceğini düşünün. Bu nedenle 100 zarf gerekli olacaktır ve her zarfın ayrı ayrı ele alınması gerekecektir. 100 farklı zarf içindeki 100 sayfalık mektubun bozuk (kullanım dışı) olması mümkündür. Sonuç olarak, zarftaki bilgilerin alıcının sayfaları doğru sırayla yeniden bir araya getirebilmesini sağlamak için bir sıra numarası içermesi gerekir.

Ağ iletişiminde, mesajın her bir bölümünün doğru hedefe ulaşmasını ve şekilde gösterildiği gibi orijinal mesajın içeriğine yeniden birleştirilmesini sağlamak için benzer bir süreçten geçmesi gerekir. TCP, tek tek segmentleri sıralamaktan sorumludur.


## Protokol Veri Birimleri

Uygulama verileri, ağ ortamından iletilmek üzere protokol yığınından geçirildikçe, her düzeyde çeşitli protokol bilgileri eklenir. Bu işlem, kapsülleme olarak bilinir.

**Not**: UDP PDU, datagram olarak adlandırılsa da, IP paketleri de bazen IP datagramları olarak adlandırılır .

Veri parçasının herhangi bir katmanda aldığı biçim, protokol veri birimi (PDU) olarak adlandırılır. Kapsülleme sırasında, birbirini takip eden her katman, kullanılan protokole göre yukarıdaki katmandan aldığı PDU'yu kapsüller. PDU, işlemin her aşamasında yeni işlevlerini yansıtmak için farklı bir ad alır. PDU'lar için evrensel bir adlandırma kuralı olmamasına rağmen, bu derste PDU'lar TCP/IP paketinin protokollerine göre adlandırılmıştır. Her veri biçimi için PDU'lar şekilde gösterilmiştir.


