

Start.java      – 26 linija
Calculator.java – 188 linija :contentReference[oaicite:0]{index=0}:contentReference[oaicite:1]{index=1}
Ukupno (LOC)    – 214 linija

STATICKA ANALIZA

Start.java – 6  – Promenljiva `Expression` ne prati Java naming convention (trebalo bi `expression`).
Start.java – 7  – Nepotrebna promenljiva `active`; umesto toga može se koristiti `while (true)` sa `break`.
Start.java – 13 – Poređenje stringova putem `.equals()` ne obuhvata varijacije poput "Exit"; razmotriti `.equalsIgnoreCase()`.
Start.java – 22 – `catch (Exception e)` je previše generički; bolje hvatanje konkretnih izuzetaka (npr. `NumberFormatException`).

Calculator.java

 Calculator.java – 2   – Globalno polje `static float finalResult` može izazvati stanja “baka-in muka”; bolje koristiti lokalne varijable.
Calculator.java – 5   – Metoda `ToString()` ima veliko “T” i krši Java naming convention (trebalo bi `toString()`). :contentReference[oaicite:2]{index=2}:contentReference[oaicite:3]{index=3}
Calculator.java – 14  – Nema provere da li je `expression` prazan pre poziva `expression.charAt(0)`, što vodi u `StringIndexOutOfBoundsException`. :contentReference[oaicite:4]{index=4}:contentReference[oaicite:5]{index=5}
Calculator.java – 28  – `catch (Exception exc)` u parsiranju hvata sve izuzetke; bolje hvatati samo `NumberFormatException`. :contentReference[oaicite:6]{index=6}:contentReference[oaicite:7]{index=7}
Calculator.java – 67  – Višestruka rekurzija u `Calculate()` otežava čitljivost i održavanje; razmotriti iterativno rešenje ili refaktorisanje. :contentReference[oaicite:8]{index=8}:contentReference[oaicite:9]{index=9}
