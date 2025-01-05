# Veri-Tabani-Sistemleri-Proje-Gereksinimleri-ve-E-R-Diyagram-
---
## Proje Başlığı: Araç Otopark Otomasyonu
Ekip Üyeleri:
- Onur ERGÜN
- Enes ARGAMA
- Veysel Emre TAY
***
## Araç Otopark Otomasyon Dönem Projesi Gereksinimleri

 
## İşlevsel Gereksinimler 
 
## Kullanıcı Yönetimi: 
Müşteri kayıtlarının yapılması. 
Personel kayıtlarının yapılması ve yönetici-personel ilişkilerinin tanımlanması. 
 
## Otopark Yönetimi: 
Otoparkların tanımlanması (konum, kapasite, durum bilgileri). 
Her otopark için farklı park yerlerinin tanımlanması ve durumlarının güncellenmesi (dolu, boS) 
 
## Araç Yönetimi: 
Müşterilerin araçlarının kaydedilmesi (plaka, marka, model bilgileri). 
Araçların giriş ve çıkış saatlerinin kaydedilmesi. 
Park yeri atamalarının yapılması. 
 
## Yorum Yönetimi: 
Müşterilerin otoparklar hakkında yorum yapabilmesi. 
Otoparklara yapılan yorumların listelenmesi ve yönetilmesi. 
Yorumların puan aralıklarına göre filtrelenmesi. 
 
## Abonelik Yönetimi: 
Müşteriler için abonelik tanımlanması (başlangıç ve bitiş tarihleri, durum bilgisi). 
Aktif ve pasif aboneliklerin görüntülenmesi. 
 
Ödeme Yönetimi: 
Müşterilerin ödemelerinin kaydedilmesi. 
Her ödemenin tutarı, tarihi ve ödeme yapan müşteri/personel bilgilerinin kaydedilmesi.

---
## Varlıklar ve Özellikleri 

## 1. Araç
Açıklama: Müşterilerin otoparkta park ettikleri araç bilgilerini tutar.
Özellikler:
araçID: Her araca özgü benzersiz kimlik numarası.
plakaNo: Aracın benzersiz plaka numarası.
marka: Aracın markası (örneğin, Toyota, BMW).
model: Aracın modeli (örneğin, Corolla, X5).

## 2. Müşteri
Açıklama: Otoparkı kullanan bireylerin bilgilerini tutar.
Özellikler:
müşteriID: Her müşteriye özgü benzersiz kimlik numarası.
ad: Müşterinin adı.
soyad: Müşterinin soyadı.
telNo: Müşterinin telefon numarası.
email: Müşterinin e-posta adresi.

## 3. Otopark
Açıklama: Otopark yerleri ve genel otopark bilgilerini tutar.
Özellikler:
otoparkID: Otoparkın benzersiz kimlik numarası.
parkYeriNo: Her otopark içindeki park yeri numarası.
kapasite: Otoparkın toplam araç kapasitesi.
konum: Otoparkın adres veya konum bilgisi.
durum: Otoparkın doluluk veya boşluk durumu.

## 4. Yorum
Açıklama: Müşterilerin otopark ile ilgili bıraktıkları yorumları tutar.
Özellikler:
yorumID: Yorumun benzersiz kimlik numarası.
yorumMetni: Müşteri tarafından yazılan yorum metni.
puan: Müşterinin otoparka verdiği puan (örneğin, 1-5 arasında).
yorumTarihi: Yorumun yazıldığı tarih.

## 5. Ödeme
Açıklama: Müşterilerin otoparka yaptıkları ödeme bilgilerini tutar.
Özellikler:
ödemeID: Ödemenin benzersiz kimlik numarası.
ödemeTarihi: Ödemenin yapıldığı tarih.
tutar: Yapılan ödeme miktarı.

## 6. Abonelik
Açıklama: Müşterilerin otopark abonelik bilgilerini tutar.
Özellikler:
abonelikID: Aboneliğin benzersiz kimlik numarası.
başlamaTarihi: Aboneliğin başladığı tarih.
bitişTarihi: Aboneliğin sona erdiği tarih.
durum: Aboneliğin aktif olup olmadığı bilgisi.

## 7. Personel
Açıklama: Otoparkta çalışan personelin bilgilerini tutar.
Özellikler:
personelID: Personelin benzersiz kimlik numarası.
ad: Personelin adı.
soyad: Personelin soyadı.
telefon: Personelin telefon numarası.
yöneticiID: Yöneticinin benzersiz kimlik numarası.


## İlişkiler


İlişki Türlerinin Özeti 
: 
1:N İlişkisi: 
 
Personel → Personel (Yönetici-Alt çalışan) 
Müşteri → Yorum 
Müşteri → Araç 
Müşteri → Abonelik 
Müşteri → Ödeme 
Personel → Ödeme 
Otopark → Araç (Park yeri) 
 
N:1 İlişkisi: 
 
Araç → Otopark (Her araç sadece bir park yerinde olabilir, ancak bir park yerinde birden fazla araç olabilir) 
 
N:M İlişkisi: 
Otopark → Yorum (Bu yüzden ayrı bir ilişki tablosu yaptık.) 

## E-R DİYAGRAMI : 
![er](https://github.com/user-attachments/assets/b4020c6b-a753-4835-87ec-6d34f4879ee8)
