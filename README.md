# Currency

## 🎓 Günlük Staj Görevi

### 🎯 Konu: Unity'de ScriptableObject Tabanlı Currency (Oyun Parası) Sistemi + UI + Kayıt Sistemi

***

### 🛠️ Görev Amacı

Unity üzerinde **ScriptableObject** kullanarak esnek bir **para sistemi** oluştur.\
Bu sistemi UI’da göster, klavye ile test et, veri kaydet ve oyuna tekrar girişte geri yükle.

***

### 📋 Görev Adımları

#### 1. Para Birimi Tanımı (ScriptableObject)

* `CurrencyItem` adında bir **ScriptableObject** sınıfı oluştur.
* `CurrencyType` adında bir enum oluştur.
* Bu sınıfa aşağıdaki alanları ekle:
  * `CurrencyType`` ``id`
  * `string displayName`
  * `Sprite icon`
  * `int currentAmount`
* Unity editöründe coin, gem vb. en az 2 adet ScriptableObject asset'i oluştur.

***

#### 2. Para Yönetim Sistemi (Currency Manager)

* `CurrencyManager` adında bir sınıf oluştur.
* Tüm `CurrencyItem` 'ları bir `List<CurrencyItem` `>` içinde tut.
* Aşağıdaki metodları yaz:
  * `AddCurrency(CurrencyType`` ``id, int amount)`
  * `SubtractCurrency(CurrencyType  id, int amount)`
  * `GetCurrencyAmount(CurrencyType id)`
  * `SetCurrencyAmount(CurrencyType id, int amount)`
* Negatif miktara düşmeyi engelle, yoksa hata logla.

***

#### 3. UI Entegrasyonu

* Her currency için UI'da bir ikon ve text göster.
* `CurrencyDisplayUI` adında bir script yaz:
  * Bu script `CurrencyType` referansı almalı.
  * Miktar değiştikçe UI otomatik güncellenmeli.

***

#### 4. Klavye Test Tuşları

* `C` tuşuna basıldığında coin +10
* `G` tuşuna basıldığında gem -5
* Bu işlemler `CurrencyManager` üzerinden yapılmalı.
* Değişiklik sonrası miktarlar konsola yazdırılmalı.
* Tüm ekonomi birimi için test etmek üzere bir tuş atanmalı.
* Hangi tuşların hangi türü etkilediği ReadMe bölümünde belirtilmeli.

***

#### 5. Save ve Load Sistemi

* `CurrencySaveData` adında bir veri sınıfı tanımla.
* Oyundan çıkmadan önce currency bilgilerini **JSON** formatında kaydet (`Application.persistentDataPath` kullan).
* Oyuna tekrar girişte bu verileri yükle ve ScriptableObject içeriğine aktar.
* `SaveManager` adında bir sınıf kullanabilirsin.

> ⚠️ ScriptableObject’lar doğrudan kaydedilemez, sadece verileri serialize edip yüklemelisin.

#### Alternatif Kayıt Yöntemi

İsteğe göre JSON yerine PlayerPrefs kullanılabilir.

***

#### 6. UI Görsel Geribildirim

* Para arttığında ikon kısa süreli **yeşil parlamalı**.
* Para azaldığında kısa süreli **kırmızı efekt** gösterilmeli.
* Bunu yapmak için `CanvasGroup`, `Image.color`, `DOTween` ya da Coroutine kullanabilirsin.

***

#### 7. Yapı ve Teslimat

* Projeyi **tek sahnede çalışır** halde bırak.
* `.unitypackage` olarak dışa aktar.
* `README.txt` veya `README.md` dosyasında:
  * Sistemin ne yaptığı kısa şekilde anlatılmalı.
  * Hangi klasörde neyin bulunduğu belirtilmeli.

***
