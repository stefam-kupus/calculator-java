# Softverska analiza – Assignment

##  LOC (Lines of Code)

Broj linija koda po fajlovima:

```
Start.java           – 26
Calculator.java      – 188
------------------------------
Ukupno (LOC)         – 214
```

---

##  Staticka analiza koda (Code Review)

> Alat: Checkstyle (opciono) i rucna analiza

### Start.java

```
Start.java – 6  – Promenljiva `Expression` ne koristi Java konvenciju imenovanja (trebalo bi `expression`).
Start.java – 7  – Nepotrebna promenljiva `active`; moze se koristiti `while (true)` sa `break` unutar bloka.
Start.java – 13 – Poredjenje stringova putem `.equals()` ne obuhvata varijacije (npr. "Exit"); razmotriti `.equalsIgnoreCase()`.
Start.java – 22 – `catch (Exception e)` je previse genericki; hajde da hvatamo specificne izuzetke.
```

### Calculator.java

```
Calculator.java – 2   – Globalno polje `static float finalResult` vodi ka nepredvidivom stanju; bolji bi bio lokalni rezultat.
Calculator.java – 5   – Ugnjezdena klasa `Operations` koristi metodu `ToString()` velikim slovom, krsi Java naming convention (trebalo bi `toString()`).
Calculator.java – 13  – Nema provera da li je `expression` prazan pre `charAt(0)`; moze doci do `StringIndexOutOfBoundsException`.
Calculator.java – 28  – Parsiranje `Float.parseFloat()` hvata `Exception` presiroko; bolje hvatati specificne `NumberFormatException`.
Calculator.java – 45  – Metoda `Calculate()` je veoma rekurzivna i radi dupliranje logike za svaku operaciju; tesko odrzavanje.
Calculator.java – 67  – Magic number `3.14` (u Utils, ako postoji) treba definisati kao konstantu (`static final`).
Calculator.java – 105 – Koriscenje `List<String>` za operacije je neefikasno; moze se koristiti `List<Character>` ili enum.
```

