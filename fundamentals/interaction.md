# Kullanıcı ile Etkileşim

Tarayıcı üzerinde kullanıcı ile etkileşimde bulunabileceğimiz 3 fonksiyon bulunmaktadır. Bunlar; alert, prompt ve confirm fonksiyonlarıdır.

### Alert
Ekranda mesaj kutusu gösterir. Kullanıcı "OK" butonuna basmadan sonraki koda geçmez.
```js
alert("Merhaba");
```
!["alert"](/img/alert.png);

Açılan mesaj penceresine "modal window" denir. Yani sayfayı kullanan kişi sayfayla etkileşime geçemez, sayfayı kullanamaz, sadece açılan mesaj penceresi ile etkileşime geçebilir.

### Prompt
Kullanıcıdan bilgi istemek için kullanılan fonksiyondur. 2 argümana ihtiyaç duyar.
```js
let name = prompt("İsminiz","isim girilmedi");
```
!["prompt"](/img/prompt.png)
Burada ilk argüman kullanıcıyı bilgilendirmek amacıyla yazılan başlıktır. İkinci argüman ise input alanı içerisinde varsayılan olarak yazılan değerdir. Kullanıcı herhangi bir şey yazmandan "OK" butonuna tıklarsa name değişkenine input alanına yazılan varsayılan değer (*"isim girilmedi"*) atanır.
ESC ya da Cancel butonu tıklanırsa name değişkenine null değeri atanır.

### Confirm
Kullanıcıya soru sorar. Sonucu true ya da false olarak döndürür.
```js
let isStudent = confirm("Öğrenci misin?");
alert(isStudent);
```
!["confirm"](/img/confirm.png)