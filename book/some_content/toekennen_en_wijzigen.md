# Waarden toekennen en wijzigen

In Java geef je bij het maken van een variabele eerst het type op. Je kunt meteen een beginwaarde geven:

```java
int getal = 13;
System.out.println(getal);
```

Hier maak je een variabele van het type `int` en geef je die de waarde `13`. In Python kun je met `type()` het type opvragen. In Java staat het type al in de declaratie: hier zie je aan `int` dat `getal` een geheel getal is.

## Een `int`-waarde toekennen

Een variabele van het type `int` kan een geheel getal bevatten:

```java
int getal = 13;
System.out.println(getal);
```

Wil je een kommagetal omzetten naar een geheel getal, dan kun je in Java een **cast** gebruiken:

```java
double kommagetal = 16.8;
int geheelGetal = (int) kommagetal;

System.out.println(geheelGetal); // computer toont: 16, omdat de omzetting van double naar int alles achter de komma afkapt.
```

`(int)` zet de waarde om naar een geheel getal door het deel achter de komma weg te laten. Dit is afkappen, niet afronden.

## Een `double`-waarde toekennen

In Java gebruik je meestal `double` voor kommagetallen:

```java
double kommagetal = 14.6;
System.out.println(kommagetal);
```

Een geheel getal kan ook in een `double`-variabele worden opgeslagen. Java zet het dan automatisch om:

```java
double kommagetal = 15;

System.out.println(kommagetal); // computer toont: 15.0
```

Java heeft ook het type `float` voor kommagetallen, maar in deze module gebruiken we `double` voor kommagetallen.

## Een `String`-waarde toekennen

Je kunt tekst rechtstreeks aan een `String`-variabele toekennen. Gebruik in Java dubbele aanhalingstekens:

```java
String tekst = "Dit is een tekst";
System.out.println(tekst); //computer toont: Dit is een tekst
```

Wil je een getal expliciet omzetten naar tekst, dan kun je `String.valueOf(...)` gebruiken:

```java
String getalAlsTekst = String.valueOf(16.3);
System.out.println(getalAlsTekst);
```

`getalAlsTekst` bevat nu tekst. Java zet de waarde om; de variabele bevat niet langer een getal.

## Een `boolean`-waarde toekennen

Een `boolean`-variabele krijgt de waarde `true` of `false`. In Java schrijf je deze woorden met kleine letters:

```java
boolean doorgaan = true;
System.out.println(doorgaan);
```

Je kunt ook het resultaat van een vergelijking opslaan. De operator `==` controleert of twee waarden gelijk zijn:

```java
boolean gelijkwaardig = 10 == 20;
System.out.println(gelijkwaardig); // false
```

# Waarden wijzigen

Het teken `=` gebruik je om een waarde aan een variabele toe te kennen. Je kunt het lezen als: “de variabele krijgt de waarde”. Het is niet hetzelfde als het wiskundige gelijkteken. Voor een vergelijking gebruik je in Java `==`.

Bekijk wat er gebeurt met `a` en `b`:

```java
int a = 10;
int b = a;

System.out.println("a: " + a + ", b: " + b);

a = 20;

System.out.println("a: " + a + ", b: " + b);
```

De uitvoer is:

```text
a: 10, b: 10
a: 20, b: 10
```

Toen je `b = a` uitvoerde, kreeg `b` de huidige waarde van `a`: `10`. Daarna veranderde alleen `a`. `b` verandert niet mee en houdt de waarde `10`.