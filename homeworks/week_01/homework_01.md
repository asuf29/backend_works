# JVM nedir, ne işe yarar?
- **Java Virtual Machine (JVM)**, java bytecode unun yürütülebileceği çalışma zamanı ortamı sağlayan bir belirtimdir. 
Adından da anlaşılacağı gibi, JVM “sanal” bir makine veya işlemci görevi görür. Java'nın platform bağımsızlığı, çoğunlukla Java Sanal Makinesi'nden (JVM) oluşur.

- JVM aşağıdaki işlemleri gerçekleştirir:
1. Kodu yükler
2. Kodu doğrular
3. Kodu yürütür
- Çoğu durumda diğer programlama dilleri, derleyici belirli bir işletim sistemi için kod üretir. Ancak Java derleyicisi yalnızca Java Sanal Makinesi için bytecode u üretir. Bir Java programını çalıştırdığınızda, JVM işlemi içinde bir iş parçacığı olarak çalışır. Sınıf dosyalarınızı yüklemek, kodu doğrulamak, yorumlamak ve yürütmek JVM'nin sorumluluğundadır. Java gibi bir komut verdiğinizde, JVM o sınıf için sınıf tanımını yükler ve o sınıfın ana yöntemini çağırır.

![jvm](https://github.com/asuf29/backend_works/blob/main/homeworks/week_01/images/jvm.png)

# JDK nedir, ne işe yarar?
- **Java Development Kit (JDK)**, Java geliştiricilerinin uygulamalarını geliştirme olanağı sağlayan, program yazma ve çalıştırmayı yerine getiren bir yazılımdır.
Hem yorumlayıcı hem de derleyici görevini üstlenmektedir. 
- JDK, JVM ve JRE’yi de bünyesinde bulundurur.

![jdk](https://github.com/asuf29/backend_works/blob/main/homeworks/week_01/images/jdk.png)

# Garbage Collector görevi nedir? Nasıl çalışır?
- **Garbage Collector (GC)**, erişilebilen herhangi bir Java nesnesi tarafından artık başvurulmayan dolu belleği boşaltmayı amaçlayan ve Java sanal makinesinin (JVM'ler) **dinamik bellek yönetim** sisteminin önemli bir parçası olan işlemdir. Tüm Java nesneleri, oluşturulduklarında ihtiyaç duydukları belleği otomatik olarak alır ve nesneye artık ihtiyaç duyulmadığında, Java Çöp Toplama işlemi belleği geri alır. Bu, Çöp Toplayıcı'nın canlı nesneleri ve çöp olarak adlandırılan diğer her şeyi izlediği anlamına gelir.

# .jar formatı nedir?
- **JAR**, genellikle birçok Java sınıfı dosyasını ve ilişkili meta verileri ve kaynakları dağıtım için tek bir dosyada toplamak için kullanılan bir paket dosyası biçimidir.
- JAR dosyaları, Java'ya özgü bildirim dosyası içeren arşiv dosyalarıdır. ZIP biçiminde oluşturulmuştur ve genellikle **.jar** dosya uzantısına sahiptir.

# Java'da .class ve .java formatının farkı nedir?
- **.java** uzantılı dosyalar, programcının Java programlama dilini kullanarak yazdığı kodu saklar.
- **.class** uzantılı dosyalarda ise .java uzantılı dosyaların derlenmesi ile oluşan bytecode’lar yer alır.

# Abstract class nedir, nasıl çalışır, ne işe yarar?
- Ortak özellikleri olan nesneleri modellemek için Java dilinde **abstract(soyut) sınıflar** kullanır.Soyut sınıflar oluşturulurken class ismi yerine **“abstract class”** kelimeleri kullanılır.
- Soyut sınıflar kalıtım özelliğini kullanarak kod tekrarını azaltır.
- Soyut sınıflar kendisinden türeyen sınıflardır.Bu sınıflardan nesne oluşturamayız.
- Soyut sınıfı extend eden sınıf soyut sınıfın tüm soyut metotlarını override etmek zorundadır.
- Extends ederek farklı sınıflarda kullanabiliriz. Her extends ettiğimiz sınıfta, soyut sınıfların özellikleri kullanılarak farklı sonuçlar üretilir.
- Arayüzdeki somut nesneler( new operatörü ile oluşturduğumuz nesneler) oluşturulamaz.
- Basit bir örnek verecek olursak:

```` Java
package com.company;

public abstract class Person {
	
	private String name;
	private String gender;
	
	public Person(String nm, String gen){
		this.name=nm;
		this.gender=gen;
	}
	
	public abstract void work();
	
	@Override
	public String toString(){
		return "Name="+this.name+"::Gender="+this.gender;
	}

	public void changeName(String newName) {
		this.name = newName;
	}	
}
````
