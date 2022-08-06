# JVM nedir, ne işe yarar?
- Java Virtual Machine (JVM), java bytecode unun yürütülebileceği çalışma zamanı ortamı sağlayan bir belirtimdir. 
Adından da anlaşılacağı gibi, JVM “sanal” bir makine veya işlemci görevi görür. Java'nın platform bağımsızlığı, çoğunlukla Java Sanal Makinesi'nden (JVM) oluşur.

- JVM aşağıdaki işlemleri gerçekleştirir:
1. Kodu yükler
2. Kodu doğrular
3. Kodu yürütür
- Çoğu durumda diğer programlama dilleri, derleyici belirli bir işletim sistemi için kod üretir. Ancak Java derleyicisi yalnızca Java Sanal Makinesi için bytecode u üretir. Bir Java programını çalıştırdığınızda, JVM işlemi içinde bir iş parçacığı olarak çalışır. Sınıf dosyalarınızı yüklemek, kodu doğrulamak, yorumlamak ve yürütmek JVM'nin sorumluluğundadır. Java gibi bir komut verdiğinizde, JVM o sınıf için sınıf tanımını yükler ve o sınıfın ana yöntemini çağırır.
