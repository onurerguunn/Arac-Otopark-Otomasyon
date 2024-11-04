# Veri-Tabani-Sistemleri-Proje-Gereksinimleri-ve-E-R-Diyagram-
---
## Proje Başlığı: Araç Otopark Otomasyonu
Ekip Üyeleri:
- Onur ERGÜN
- Enes ARGAMA
- Veysel Emre TAY
***
## Araç Otopark Otomasyon Dönem Projesi Gereksinimleri

1. Personel :
- Görevi araçların girişini yapmak, çıkış işlemlerini yönetmek ve tüm bilgileri veri tabanına kaydetmektir.
- Personel, tüm bilgilere erişim yetkisine sahiptir.
- Araç giriş-çıkış saatlerini kaydetme ve otopark doluluk durumunu güncelleme sorumluluğuna sahiptir.

2. Müşteri :
- Müşteri, otoparkta kaldığı süreye göre ödeme yapar.
- Çıkış işlemi sırasında, kalınan süreye göre hesaplanan ödeme miktarını görebilir.
- Giriş ve çıkış tarihleri, aracın bağlı olduğu müşteri bilgisi ile eşleştirilir.

3. Ödeme Sistemi:
- Otopark ücreti kalınan süreye göre otomatik olarak hesaplanır (örneğin, saat başı ücretlendirme).
- Eğer abonelik durumu aktif ise, ödeme ücreti alınmaz.
- Her ödeme işlemine dair kayıtlar veri tabanında saklanır.

---
## Varlıklar ve Özellikleri 

### 1. Personeller
- id: Birincil anahtar (PK), benzersiz personel kimliği.
- isim: Personel adı, zorunlu.
- soyisim: Personel soyadı, zorunlu.
- gorevi: Personelin görevi (örn. "Görevli", "Yönetici").
   
### 2. Müşteriler
- id: Birincil anahtar (PK), benzersiz müşteri kimliği.
- isim: Müşteri adı, zorunlu.
- soyisim: Müşteri soyadı, zorunlu.
- telefon_numarasi: Müşterinin telefon numarası, zorunlu ve benzersiz.

### 3. Araçlar
- id: Birincil anahtar (PK), benzersiz araç kimliği.
- musteri_id: Aracın sahibi olan müşteri (FK, Müşteriler tablosuna bağlı).
- plaka: Araç plakası, benzersiz olmalı ve zorunludur.
- marka: Aracın markası (örneğin, "Toyota").
- model: Aracın modeli (örneğin, "Corolla").
- renk: Aracın rengi.

### 4. Otopark Yerleri
- id: Birincil anahtar (PK), benzersiz otopark yeri kimliği.
- otopark_yeri: Otopark yer numarası, benzersiz ve zorunludur.
- yer_durum: Yer durumu (boş/dolu).

### 5. Ödemneler
- id: Birincil anahtar (PK), benzersiz ödeme kimliği.
- musteri_id: Ödemeyi yapan müşteri (FK, Müşteriler tablosuna bağlı).
- abonelik_durumu: Abonelik varsa işlem için ödeme alınıp alınmayacağını belirler.(Abonelikler tablosuna bağlı) 
- odeme_miktar: Ödeme miktarı, zorunlu.
- giris_tarihi: Ödeme esnasında çıkış tarihi ile giriş tarihi farkında kullanılacak.
- cikis_tarihi: Ödeme esnasında çıkış tarihi ile giriş tarihi farkında kullanılacak.

### 6. Abonelikler
- id: Birincil anahtar (PK), benzersiz abonelik kimliği.
- musteri_id: Abone olan müşteri (FK, Müşteriler tablosuna bağlı).
- abone_bas_tarih: Abonelik başlangıç tarihi.
- abone_bit_tarih: Abonelik bitiş tarihi.
- abonelik_turu: Abonelik türü (örneğin, "Aylık", "Yıllık", "Günlük").
- abone_durumu: Abonelik durumu ("Aktif", "Pasif" gibi).
---

## İlişkiler

#### Müşteriler - Araçlar:
- İlişki Adı: "Sahiptir"
- Bağlantı: 1’den N’e ilişki
- Açıklama: Her müşteri birden fazla araca sahip olabilir, ancak her araç sadece bir müşteriye aittir.
  
#### Müşteriler - Ödemeler:
- İlişki Adı: "Yapmıştır"
- Bağlantı: 1’den N’e ilişki (1’den 1’e ilişki de olabilir)
- Açıklama: Bir müşteri, bir veya birden fazla ödeme yapabilir (farklı tarihlerde park ettiğinde), ancak her ödeme sadece bir müşteriyle ilişkilidir.

#### Müşteriler - Abonelikler:
- İlişki Adı: "Abonedir"
- Bağlantı: 1’den 1’e ilişki.(1’den N’e ilişki de olabilir)
- Açıklama: Bir müşteri bir veya birden fazla abonelik türüne sahip olabilir, ancak her abonelik yalnızca bir müşteriyle ilişkilidir.

#### Araçlar - Otopark Yerleri:
- İlişki Adı: "Park Edilir"
- Bağlantı: 1’den 1’e ilişki.
- Açıklama: Bir araç park edildiğinde bir otopark yerine atanır, ancak bir otopark yeri aynı anda yalnızca bir araçla ilişkilidir.

---
## E-R DİYAGRAMI : 
![E-R-Diagram](https://github.com/user-attachments/assets/21b58e55-dfd0-4688-bca1-101e6eb04c26)
