# Mercedes Araba Fiyatları
## Verinin İncelenmesi
Öncelikle veri seti'ne genel bir bakış yapmak için ilk 5 aracın özelliklerini inceledim. Bu veri seti'nde araçların Yıl, Fiyat, Mil, Vergi, Yakıt Tüketimi ve Motor Hacmi özellikleri bulunuyor.

![1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/885ff4ef-d477-4d3b-91cb-1f51f6f4ed63)

Bir de bu veri seti'nin genel bilgilerini inceledim. Bu tabloda araçların özelliklerinin Sayısı, Ortalaması, Standart Sapması ve Minimum-Maksimum değerleri benim için önemli olan değerler.

![2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/46741bb3-0a69-41c1-b9f1-95075a31ffc5)

Ardından araçların fiyatlarının grafik üzerindeki dağılımlarını inceledim. Burada yüksek fiyatlı araçların az miktarda olması ve normal bir dağılımda olmaması veri seti'tinin güvenilirliğini azalttığını düşündüm.

![3](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/21a687f8-675a-4001-b3c8-453b12b4d25b)

Araç fiyatlarının diğer özelliklerle korelasyonunu da inceledim. Burada da gözüktüğü üzere araçların fiyatları konusunda en yüksek etki Mil özelliğine bağlı gözüküyor. Bunu bir de grafik üzerinde inceledim.

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ae98a6f6-d32e-41fb-b285-65d385606f58)
![4](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5daf43fb-2609-4454-bf7c-5b368f612d77)

## Verinin Düzeltilmesi
Öncelikle gözüme ilk batan yüksek fiyatlı araçların anormal dağılımını kaldırdım. En yüksek %1'lik araçları (131 araç) veri seti'nden kaldırdım. Ardından yeni değerleri, grafiği ile birlikte inceledim. Daha normal bir dağılımda grafik elde ettim.

![2-1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/b8abbad0-0131-4028-a0be-367e8a22837d)
![2-2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/88ab8482-3068-4aaa-970d-43cacf4b602d)

Sonrasında araçların yıllara göre fiyat ortalamalarını listeledim ve burada olması gerektiği gibi düşük modelden yüksek modele giderken fiyatların yükseldiğini gördüm. Ancak 1970 yılı araçlar için bu durum bir istisnaydı. O verileri de veri seti'nden kaldırdım.

![2-3](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/fd317b9c-4470-4d3a-a53a-c78ba2aef4f7)
![2-4](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5bdd7d54-733b-4590-88e1-fdceac23519c)

## Modelin Oluşturulması
Öncelikle 12 nöron(derinlik) içeren 5 katmandan oluşan bir model oluşturdum. Modelin regression yaklaşımını ReLU olarak seçtim.

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/97c68e92-e59c-4789-a688-da40a1fc9f24)
![2-5](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ced48924-dbec-47fe-b506-ca1bc4d8bd85)

Ardından modelimi batch_size=250(veri yükleme paket büyüklüğü), epochs=300(veri seti'ni döndürme sayısı) olacak şekilde eğittim.

## Modelin Değerlendirilmesi
Eğitimdeki kayıp verilerin ve veri seti'ndeki kayıp verileri grafik üzerinde inceledim. Olması gerektiği gibi birbirlerine yakın çizgiler ve giderek sıfıra yaklaştığını gördüm.

![3-1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5e00b4e3-a304-4b2d-8623-e202badf22f7)

Ardından veri seti'nden test için ayırdığım verilerle yeni bir tahmin yaptırdım. Yeni tahminlerin gerçek fiyatlarla örtüşmesini gözlemlemek için bir grafik kullandım. Ortadaki yeşil çizgi olması gereken durumu göstermektedir. Oralama hata payını hesapkadığımda +/- 3137 Pound fiyatlarda değişiklik gösterdiğini gördüm.

![3-2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/2a95511e-e7e9-4319-9491-b577f9ff5491)

Ardından son bir kontrol için tekil bir aracın fiyatını tahmin ettirdim. Aracın gerçek fiyatı 65.980 Pound iken, tahmin sonucu olarak 63.644 Poun elde ettim. Bu da yaklaşık olarak 0.035 hata payı yapıyor

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ee5728f2-00f6-4d45-a8e4-10469cfd3148)
![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/613e21fd-8646-4ceb-8341-8442362848b1)
