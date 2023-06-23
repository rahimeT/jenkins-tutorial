# jenkins-tutorial
Uygulamalarımızı, toolları sürekli update ediyoruz. Bu sürekli update işlemleri için sürekli test edilmeli ve deploy edilmeli. Bunu jenkins ile sağlayabiliriz

![Screenshot 2023-06-22 at 13.01.48.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/914992b9-5a64-4008-84c2-9f328f64193c/Screenshot_2023-06-22_at_13.01.48.png)

1. geliştirici kodu repo ya gönderir. bu arada jenkins sunucusu düzenli aralıklarla repoyu kontrol eder. bir commit gerçekleştikten sonra kısa süre sonra jenkins sunucusu kaynak kod deposunda meydana gelen değişiklikleri algılar, jenkins bu değişiklikleri algılar ve yeni bir build hazırlamaya başlar. 
2. build başarısız olursa ekip bilgilendirilir. başarılı olursa jenkins yerleşik test sunucusuna dağıtır
3. testten sonra jenkins geri bildirim oluşturur, ardından geliştiricileri derleme ve test sonuçları hakkında bilgilendirir.

artifacts: işlem yaptıktan sonra çıktıyı saklamak isterseniz ve sonrasında baska bir sunucuda kullanabilirsiniz

Bu işlemlerle vakit kaybetmek istemiyorum, projemi kendi repona çek, oradaki istediğim test işlemlerini yap, ayağa kaldır, sonra deploy et. Bu işlemlerde fail eden bir durum olursa beni notification ile bilgilendir. Belirli aralıklarla github’ı da yokla. Bu yoklamalarda sana emrettiğim işlemleri tekrar et.

Codepipeline, gitlab CI, codestream, 

**Sürekli entegrasyon**, *tek bir projede günlük olarak birden fazla testin gerçekleştirilmesi işlemine denir*. Bunun gerçekleştirilme sebebi genellikle projede (program, uygulama, vb.) birden fazla geliştiricinin çalışmasıdır.

### **Jenkins’i Selenium ile birlikte kullanmalı mı?**

Evet çünkü oldukça faydalı. Bu birliktelik sayesinde programınız herhangi bir şekilde her değişikliğe uğradığında testler anında gerçekleştirilir.

**geliştiricilerin kaynak kodunda yapılan her değişiklik için sürekli olarak bir yapıyı tetikleyebileceği ve test edebileceği bir sistemin var olmasına büyük bir ihtiyaç vardı.**

Kurulum

docker run -d -v jenkins:/var/jenkins-home -p 8080:8080 --restart unless-stopped jenkins/jenkins:lts

[localhost:8080](http://localhost:8080) den bağlan ve  belirlenen jenkins kaynaklarına uygun eklentilerini indir.
