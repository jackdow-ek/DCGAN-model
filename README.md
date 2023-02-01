# DCGAN-model

DCGAN (Deep convolutional generative adversarial networks) – Gözetimsiz öğrenmeyi
hedefleyen ve bunu gan'daki üretici ve ayrımcı yapay sinir ağı model çifti arasındaki
dinamik öğrenme etkileşimi neticesinde başaran, çok katmanlı mimariye ve
konvolüsyonel işlemlere dayalı yapay öğrenme tekniği. Gözetimsiz öğrenme
aşamasındaki anahtar nokta, üretici sinir ağını hedef sınıflandırma işlemi için klasik
şekilde doğrudan eğitmek (hata oranını minimize etmeye çalışmak) yerine, çıktıdaki veri
dağılımının mümkün olduğunca ayrımcı ağ modelini yanıltmaya çalışmasını sağlamaktır.
Bu sayede her epoch'ta, üretici model hatalı dağılım üretmede (ayrımcı modeli
kandırmada) daha başarılı hale gelirken, diğer model bu hataları tespit etmede uzman hale
gelir. bu anlamda ayrımcı model shift-invariant bir cnn'dir. Mimaride, perceptron'lar için
aktivasyon fonksiyonu olarak genelde relu kullanılmakla birlikte, üreticinin çıkış katmanı
için hiperbolik tanjant fonksiyonu kullanılır (negatif değerlerin mapping'i için). Ayrımcı
ağdaki katmanlarda ise giriş negatif değerler aldığında, çıkışta doğrudan sıfır vermek
yerine çok küçük negatif değerlere de izin verebilen (y = max(0, x) yerine, y = 0.01 * x ,
gibi...) ve bir relu varyasyonu olan leaky relu kullanılır. Bu sayede daha dengeli ve hızlı
bir öğrenme aşaması hedeflenir.
