# Döngüler (Loops)

Çoğu zaman aynı işi yapan kodları tekrar tekrar yazmak durumunda kalırız. Örneğin bir listeden elemanları sıra ile çağırmak ya da 1'den 100'e kadar sayıları yazdırmak gibi.
Bu durumlarda kullanacağımız döngü yapıları ile aynı kodları defalarca çalıştırabiliriz.

#### "*while*" Döngüsü
```js
while(koşul) {
    //Döngü gövdesi
}
```
```js
let sayi = 0;
while(sayi<10) {
    console.log(sayi);
    sayi++;
}
```
Döngünün gövdesinde bulunan kodun koşula bağlı olarak her çalışmasına tekrar (iteration) denir. Eğer `sayi++;` gibi bir kod yazmasaydık döngü sonsuza kadar çalışabilirdi. Böyle durumda tarayıcı uzun süre bu kodun çalışmasını engeller.
Döngüde koşul olarak sadece karşılaştırma değil bir ifade ya da değişken de yazılabilir. 
```js
let i = 10;
while(i) {
    console.log(i);
    i--;
}
```
Her tekrarda i değeri bir azalacaktır ve 0 olduğunda döngünün koşul yapısı false olacak ve döngü sonlandırılacaktır.

*Tek satır gövde varsa { } kullanımına gerek kalmaz.

```js
let i=3;
while(i) alert(i--);
```
Yukarıdaki kod önce i değerini mesaj kutusunda gösterip daha sonra bir azaltarak döngüyü tekrarlıyor.

#### "*do...while*" Döngüsü

Önce döngü gövdesi çalıştırılır. Sonra koşul kontrolü yapılır. Eğer doğruysa döngü tekrar çalıştırılır.

```js
do{
    //döngü gövdes
} while(koşul);
```

```js
let i = 0;
do {
    console.log(i);
    i++;
} while(i<10);
```
Bu şekilde döngü kullanılmasının amacı en azından döngü gövdesi bir kez çalıştırılması ve kodun ne yaptığının görülmek istenmesidir. Bunun yerine genellikle *while* döngüsü kullanılır.

#### "*for*" Döngüsü

En fazla kullanılan döngü yapısıdır.
```js
for(i=0; i<100; i++) {
    console.log(i);
}
```

Burada oluşturulan *"i"* değişkeni **satır arası değişken** olarak geçer ve sadece döngü gövdesinde kullanılır.

*For döngüsünde bazı bölümler pas geçilebilir.

- **Başlangıç bölümü daha önce tanımlandıysa pas geçilebilir.**
```js
let i = 0;
for(; i<10; i++) {
    alert(i);
}
```

- **Artırma bilgisi gövdede kullanılıyorsa pas geçilebilir.**
```js
let i = 0;
for(; i<10;) {
    alert(i++);
}
```
Yukarıdaki kod yapısı *while* döngüsü ile aynı yapıda oldu.

- *Tüm alanlar pas geçilirse sonsuz döngü olur.*

```js
for(;;) {
    //sonsuz döngü
}
```

## Döngüyü Kırma

```js
let toplam = 0;
while(true) {
    let deger = +prompt("Bir sayı giriniz:",'');
    if(!deger) break;
    toplam += deger;
}
alert(toplam);
```
Yukarıdaki kod parçasında kullanıcıdan bir değer girilmesi isteniyor. Kullanıcı herhangi bir değer girmezse if koşul yapısı true olduğu için çalışacak ve break komutuyla döngüden çıkalacaktır. Koşul sağlanır ve break komutu çalışırsa program döngüden sonraki ilk satırla devam eder.

Bir diğer döngü kırma aracı *"continue"* yapısıdır. Burada döngü *break* yapısında olduğu gibi tamamen kırılmaz. Sadece o tekrar pas geçilir ve bir sonraki tekrar ile devam edilir. 

```js
const number = [];
for(let i=0; i<10; i++) {
    if(i%2==0) continue;
    number.push(i);
}
alert(number);
```
Yukarıdaki kodun çıktısı şu şekildedir.
![](/img/loops.png)

Yukarıdaki kodun şu şekilde de yazılabilir. 

```js
const number = [];
for (let i = 0; i < 10; i++) {
  if (i % 2 == 1) {
    number.push(i);
  }
}
alert(number);
```

**"if" yerine "?" kullanılıyorsa *continue/break* kullanılmaz.**
```js
(i > 5) ? alert(i) : continue; // `continue` burada kullanılamaz!!!
```

####break/continue için etiket tanımlanması

```js
for(let i=0; i<10; i++) {
    for(let j=0; j<10; j++) {
        if(j%3==0) continue;
        console.log("i --- j " + i + " " + j)
    }
}
```

Yukarıdaki kod çalıştığında ilk döngü 10 kez çalışacak ve her çalıştığında içerisindeki döngü 3 sayısının katlarında döngüyü kıracak şekilde çalışmaya devam edecektir. Kod çıktısı; 

i --- j 0 1
i --- j 0 2
i --- j 0 4
i --- j 0 5
i --- j 0 7
i --- j 0 8
....
....
....
şeklinde devam edecektir.

Kodu j değişkeninin 3'e bölümünden kalan 2 olduğunda dışarıdaki döngüyü kırmak (break) istediğimizde ise iç döngüden dışarıdaki döngüye ulaşmak için etiket kullanmamız gerekecektir.

```js
topLoop: for(let i=0; i<10; i++) {
    for(let j=0; j<10; j++) {
        if(j%3==2) break topLoop;
        console.log("i --- j " + i + " " + j)
    }
}
```

Etiketler "**goto**" anlamına gelmez. Kodun herhangi bir yerine atlamak mümkün değildir. break/continue sadece döngü içerisinde kullanıldığı için etiketler döngünün başına yazılmalıdır.

