Ekleme Sıralaması, Bilgisayar Bilimlerinde kullanılan bir sıralama algoritmasıdır. Ekleme sıralamanın zaman karmaşıklığı durumları şunlardır:

En İyi Vaka Karmaşıklığı O(n)

En Kötü Durum Karmaşıklığı O(n2)

Ortalama Vaka Karmaşıklığı O(n2)

Peki, bunlar arasındaki fark nedir?

Best Case karmaşıklığı, öğeler zaten sıralandığında ortaya çıkar. Bu durumda, algoritma n elemanı n kez kontrol eder. Dolayısıyla algoritma O(n) ile çalışır, bu da lineer zaman anlamına gelir.

En Kötü Durum karmaşıklığı, öğeler ihtiyacımız olanın tam tersi olduğunda ortaya çıkar. (Örn: alçalmamız gerekiyor ama yükseliyor veya yükselmemiz gerekiyor ama azalıyor). Bu durumda, algoritma her öğeyi (kendisi hariç) karşılaştırmak için her öğeyi kontrol eder. Böylece, algoritma O(n^2) çalışır,

Ortalama Vaka karmaşıklığı, öğeler karıştırıldığında meydana gelir. (ancak öğeler tam olarak azalan veya artan değildir).

Ekleme Sıralama algoritmasının nasıl çalıştığını kontrol edelim.

İlk olarak, algoritma ilk öğenin sıralandığını varsayar. Ardından, karşılaştırmak için ikinci öğeyi alır. Birinci ve ikinci elemanlar) algoritma ile karşılaştırılır. Eğer birincisi ikincisinden büyükse ikincinin sağ tarafına gelir. Ve tüm öğeler sıralanana kadar gider.

İşte başlıyoruz.

Örnek 1:

Artan düzende kontrol edin: [22,27,16,2,18,6]

Öncelikle karmaşıklığı kontrol edelim:

Sipariş edilmedi, bu yüzden en iyi durum değil. İhtiyacımız olanın tam tersi değil, bu yüzden en kötü durum değil. Yani ortalama bir durum. O zaman zaman karmaşıklığı o(n^2) olur.

Nasıl çalıştığını görelim. [22,27,16,2,18,6]:

i=0 22,27,16,2,18,6 --> 22 kaydedilir ve 27 ilk elemanla karşılaştırmaya başlar. 27, birinciden büyüktür.

i=1 22,27,16,2,18,6 --> 27 saklandı ve 16 tanesi saklananlarla karşılaştırmaya başladı. 16 saklananlardan daha küçüktür. Yani, 16 başlangıca gidecek.

i=2 16,22,27,2,18,6 --> 16 kaydedildi ve 2 tanesi saklananlarla karşılaştırmaya başladı. 2 saklananlardan daha küçüktür. Yani, 2 başlangıca gidecek.

i=3 2,16,22,27,18,6 --> 2 kaydedildi ve 18 tanesi saklananlarla karşılaştırmaya başladı. 18, 16 ile 22 arasında gidecek.

i=4 2,16,18,22,27,6 --> 18 kaydedildi ve 6 tanesi saklananlarla karşılaştırmaya başladı. 6, 2 ile 16 arasında gidecek.

i=5 2,6,16,18,22,27 --> 6 saklandı ve elemanlar ekleme algoritması ile artan şekilde sıralandı.

Örnek 2: [7,3,5,8,2,9,4,15,6]

i=0 7,3,5,8,2,9,4,15,6 --> 7 kaydedilir ve 3 bir tanesini kaydetmeye başlar. Yani 3, birinciden daha küçüktür. 3 başlangıcına gidecek.

i=1 3,7,5,8,2,9,4,15,6 --> 3 saklandı ve 5 tanesi saklananlarla karşılaştırmaya başladı. Yani, 5, 7 ile 3 arasında gidecek.

i=2 3,5,7,8,2,9,4,15,6 --> 5 kaydedildi ve 8 tanesi saklananlarla karşılaştırmaya başladı. Yani, 8 aynı indekste kalacak.

i=3 3,5,7,8,2,9,4,15,6 --> 8 kaydedildi ve 2 tanesi saklananlarla karşılaştırmaya başladı. 2 başlangıcına gidecek.

i=4 2,3,5,7,8,9,4,15,6 --> 2 kaydedildi ve 9 tanesi saklananlarla karşılaştırmaya başladı. 9 aynı endekste kalacak.

i=5 2,3,5,7,8,9,4,15,6 --> 9 kaydedildi ve 4 tanesi saklananlarla karşılaştırmaya başladı. 4, 3 ile 5 arasında gidecek.

i=6 2,3,4,5,7,8,9,15,6 --> 4 kaydedildi ve 15 tanesi saklananlarla karşılaştırmaya başladı. 15 aynı indekste kalacaktır.

i=7 2,3,4,5,7,8,9,15,6 --> 15 kaydedildi ve 6 tanesi saklananlarla karşılaştırmaya başladı. 6, 5 ile 7 arasında gidecek.

i=8 2,3,4,5,6,7,8,9,15 --> 6 saklandı ve elemanlar ekleme algoritması ile artan şekilde sıralandı.