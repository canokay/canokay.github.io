# İlk Xamarin Deneyimim Nasıldı?

Her zaman Mobile Developerlıkla uğraşmak istedim. Windows işletim sistemi kullanıyorum. 

Windowsta da iOS geliştirmek imkansız (yani ben öyle sanıyordum). 

Daha sonra bitirme projemi hem Android hem iOS olan bir uygulama aldım. 
Ne yapacağımı bilmiyordum. Yani Android'i Android Studioda halledebilirdim ama iOS için illaki mac gerek.
GDG 2018 İzmir Event'ine gittim ve orada Angular kullanarak Ionicde tasarlayarak tek kodda Hem Android Hem iOS App yapılabileceğini öğrendim.

Bunu çok yakın arkadaşım <a href="https://github.com/TheAvenqer"> Barış'a </a> (Yazılım Mühendisliği Öğrencisi) anlattım ve "Bana angular kaynağı bulabilir misin?" diye sordum. O da "Sen C# ile ilgilen miyor musun? Git Xamarini araştır." dedi.

ve yeni macera başladı= XAMARIN

Buraya kadar her şey iyi güzel. Ama sorunlar burada başlıyor.

Bir hafta boyunca Xamarinin Açık Akademideki videolarını izledim. Temel olarak her şeyi öğrendim. Zaten C# ile yıllarca deneyimim olduğundan çok kolay geldi.

İşte o hafta sonu Xamarini Visual Studioma kurmaya başladım.

Videoları dizüstü Ubuntu bilgisayarımdan izliyordum "Şimdi nasıl bir dilmiş diye öğreneyim hafta sonu ana bilgisayarıma yüklerim daha sonrada bir sürü Cross Platform App yaparım" diyeerk izlemiştim.

Kuramadım. Evet kuramadım. Çünkü ana masaüstü bilgisayarımın işlemcisi: AMD FX 8320. Android Emulator sadece ama sadece Intel'i destekliyor. (Yani AMD yi de destekliyormuş belli bir sürümünden sonra ama benim işlemciyi desteklemiyor orası kesin)
Uzun lafın kısası sırf işlemcimin AMD oluşu yüzünden bir haftalık XAMARIN eğitimi boşa gitti. Halbuki deftere elle yazarak notlar bile almıştım.

Eeee o zaman bu repostory ne?: https://github.com/canokay/XamarinFirstApp 

## İkinci kısım:

Xamarini kuramadıktan sonra Android'e başladım. Ubuntuya Android Studioyu kurdum. Sonra programı kapattım. Tekrar açmak için Lauchera gittim. Fakat o da ne? Android Studio yok.

Hemen bir googlelamayla Terminal'e bash kodları ile açıldığını öğrendim.

Fakat gene olmadı. Yani Terminalde doğru dizilimi yazıyorum, doğru dosyayı başlat diyorum fakat nafile. Olmuyor. Bir türlü başlatılamıyor.

Hal böyle olunca ubuntuyu silip Windows 10 yükledim ve sorunsuz bir şekilde Android Studioyu kurup başlattım.

 (bu arada Laptop'um sadece HTML CSS kodları yazmak için aldım. Yani işlemcisi güçlü değil).
 
 İşlemcisi güçlü değil ama bilin bakalım markası ne? INTEL
 
 Evet Intel. Ama Intel Pentium. Ama sonuçta intel.
 
 Aklıma dahiyane bir fikir geldi. Bu pentium işlemcili laptop'a Xamarin kurayım dedim. 
 
 Tabi ki de Intel işlemci olduğu için sorunsuz kuruldu. 
 
 Hemen her programcının yaptığı gibi Merhaba Dünya kodunu yazdım
 
 
 ### XamarinFirstApp/XamarinFirstApp/XamarinFirstApp/MainPage.xaml
 
 ``` xaml
 <Label Text="Merhaba Xamairin!!!" 
           VerticalOptions="Center" 
           HorizontalOptions="Center" />
 ```
 
 Emülatörde çalıştırayım dedim. Zaten Mac olmadığından iOS'i eledik. Android Emülatörde çalıştırayım dedim fakat baaaammm. 
 
 Evet işlemcimiz INTEL. Ama INTEL PENTIUM. Bu yüzden emülatör çalışmadı. Yani işlemci yanacak diye korktum :)
 
 Kısacası çok kısa bir deneyimim oldu. İleride Intel işlemcili iyi bir bilgisayarım olursa tekrar geri dönebilirim Xamarin'e. Ama bu laptopta Visual Studioya bile girilmiyor, Visual Studioya girilen bilgisayarda da Xamarin yazılamıyor.
 
 Xamarin durumu bu.
 
 Bir sonraki yazıda görüşmek üzere...
