# 1. SOLID nedir?
- ***SOLID*** yazılım prensipleri; geliştirilen yazılımın esnek, yeniden kullanılabilir, sürdürülebilir ve anlaşılır olmasını sağlayan, kod tekrarını önleyen prensipler bütünüdür.
## S - Single Responsibility Principle
- " ***Tek Sorumluluk*** " anlamına gelen bu prensipte amaç; geliştirilen projede bir güncelleme veya değişiklik yapılması istendiğinde, yalnızca ilgili metoda giderek istenilen değişikliğin yapılmasının sağlanmasıdır.
-  Bir fonksiyona birden fazla iş verip onu birçok işten sorumlu tutmak yerine, her bir iş için ayrı bir metot oluşturmalı ve ilerleyen zamanlarda bir değişiklik yapılacağında da kolaylıkla ilgili metoda giderek gerekli değişiklikleri yapabilmeliyiz.
## O - Open/Closed Principle
- Türkçe karşılığı " ***Açık/Kapalı*** " olan prensip, projede geliştirilen nesnelerin geliştirilmeye açık ama değişime kapalı olmaları gerektiğini ifade eder.
- Bir nesne davranışını değiştirmeden yeni özellikler kazanabiliyor olmalıdır. 
- Bu prensip, ***sürdürülebilir*** ve ***tekrar kullanılabilir*** yapıda koda yazmanın temelini oluşturur.
## L - Liskov Substitution Principle
- " ***Yerine Geçme*** " olarak çevirdiğimiz prensibe göre; miras alarak türemiş olan class’ların önce miras aldıkları nesnenin tüm özelliklerini kullanması, daha sonra da kendi özelliklerini barındırması gerekir.
- Eğer oluşturduğumuz class, miras aldığı nesnenin ‘tüm’ özelliklerini kullanmayacaksa ortaya gereksiz kod blokları çıkar ve bu da bir geliştiricinin isteyeceği en son şeydir.
- Çünkü bir geliştirici her daim ***Clean Code*** yazmaya çalışır.
## I - Interface Segregation Principle
- “ ***Arayüz Ayırımı*** ” prensibinde; bir interface’e gerekenden fazla sorumluluk eklemek yerine, daha özelleştirilmiş birden fazla interface oluşturulmalıdır.
- Nesneler, ihtiyacı olmayan özellik veya metotlar içeren interface’leri miras almaya zorlanmamalıdır.
##### NOT: ‘Interface Segregation’ prensibi interface’ler ile ilgilenirken, ‘Single Responsibility’ prensibi class’lar ile ilgilenmektedir.
## D - Dependency Inversion Principle
- Türkçe karşılığı “Bağımlılığın Ters Çevrilmesi” olan bu prensibe göre; alt sınıflarda yapılan değişiklikler üst sınıfları etkilememelidir yani sınıflar arası bağımlılıklar olabildiğince az olmalıdır ve özellikle üst seviye sınıflar, alt seviye sınıflara bağımlı olmamalıdır.
- Burada yüksek seviye sınıf ile düşük seviye sınıf arasında bir soyutlama katmanı oluşturarak her iki sınıfı da soyut kavramlar üzerinden yönetmeliyiz.

# 2. Singleton Design Pattern
-  Singleton (Tek Nesne) Design Pattern, hazırladığımız sınıftan sadece bir örneğinin oluşturulmasını sağlar. 
- Bu sayede nesnenin kopyalanmasını yada yeni bir tane oluşturulmasını engeller ve nesneye ihtiyaç duyulduğunda o nesnenin daha önceden oluşturulan örneği çağırır.
### Ne zaman kullanırız?
- Veritabanı bağlantılarında, port bağlantılarında, yada dosya işlemleri gibi tek bir nesneye ihtiyaç duyduğumuz zamanlarda kullanırız.

### Örnek: Java Singleton Sınıf Sözdizimi
``` 
class SingletonExample {

   private static SingletonExample singleObject;
                                              
   private SingletonExample() {
   }

   public static SingletonExample getInstance() {
   }
}
```
#### Veritabanı bağlantılarında kullanılabilir demiştik. Örnek verecek olursak: 
```
class Database {
   private static Database dbObject;

   private Database() {      
   }

   public static Database getInstance() {

      if(dbObject == null) {
         dbObject = new Database();
      }

       return dbObject;
   }

   public void getConnection() {
       System.out.println("Veritabanına bağlısınız.");
   }
}

class Main {
   public static void main(String[] args) {
      Database db1;

      db1= Database.getInstance();
      
      db1.getConnection();
   }
}

```
# 3. Springde application properties nedir? Ne işe yarar?
- Spring Boot varsayılan olarak yapılandırma ayarlarını src/main/resourcesdizini altındaki application.properties dosyasında tutar.
- Properties dosyaları kolay okunabilirlik ve yazım açısından oldukça kolay bir formattadır. 
