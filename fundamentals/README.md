# Veri Tipleri

## Number Veri Tipi

Number veri tipi integer ve floating point verilerle birlikte Infinity ve NaN gibi özel sayısal değerleri de tutabilir.

- Infinity matematiksel sonsuzluğu ifade eder.

```js
alert(1 / 0); //Infinity
```

- NaN hesaplamada hata olduğunu gösterir. Hatalı veya tanımsız matematiksel hesaplamaları gösterir.

```js
alert("Text" / 2); //NaN (Not a Number)
```

NaN yapışkandır. NaN üzerine yapılacak herhangi bir işlem yine NaN çıktısı verir.

```js
alert("Text" / 2 + 5); //NaN
```

Yukarıdaki kodda ilk olarak metin ve sayı bölme işlemine alınır ve sonuç NaN olarak döner. NaN ile 5 sayısı toplama işlemine alındığında sonuç yine NaN olarak döner.

## String Veri Tipi

String ifadeleri çift tırnak(" "), tek tırnak(' ') ya da backticks (` `) içerisine yazılabilir. Tek tırnak ile çift tırnak arasında bir fark yoktur.
Backticks genişletilmiş işlevsellik olarak kullanılır.

```js
let name = "Semih";
alert(`Merhaba ${name}`); //Merhaba Semih
```

- JavaScript'te char diye bir veri tipi yoktur.

### Null

"null" değeri diğer veri tiplerine ait olmayan boş değer içeren bir tür anlamına gelir.

- null -> hiçbir şey (nothing)
- empty -> boş
- value unknown -> bilinmeyen değer

**Diğer dillerde olduğu gibi null veri tipi var olmayan bir nesneye başvuru veya boş işaretçi anlamına gelmez.**

### Undefined Value

Null veri türünde olduğu gibi ayrı bir anlamı vardır. "Değer atanmamış" anlamına gelir. Bir değişken bildirilmiş ancak değer atanmamışsa değeri _undefined_ olur.

```js
let age;
console.log(age); //undefined
```

- Teknik olarak bir değişkene açık bir şekilde _undefined_ atamak mümkündür.

```js
let age = 30;
age = undefined;
console.log(age); //undefined
```

Normalde bir değişkene "boş" veya "bilinmeyen" bir değer atamak için _null_ kullanılır. Değer atanmamış değişkenler için varsayılan başlangıç değeri olarak ise _undefined_ ayrılır.

#### type of

Değişkenlerin veri türünü döndürür. 2 tür kullanımı vardır.
1-Operatör olarak

```js
let x = 12;
typeof x; //number
```

2-Fonksiyon olarak

```js
let x = 12;
typeof(x); //number
```

**Dikkat:**

```js
typeof null; //object
```

Yukarıdaki kod çıktısının object olarak dönmesi JavaScript dilinin ilk günlerinden gelen ve uyumluluk için saklanan typeof davranışında resmi olarak saklanan bir hatadır. Null kesinlikle bir object değil kendisine ait bir türü olan özel bir değerdir.
