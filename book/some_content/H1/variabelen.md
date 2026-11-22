# Variabelen

## Wat is een variabele?

Stel: je wilt de computer een som laten uitrekenen. Je kunt zeggen: “Neem het getal 4 en tel daar het getal 3 bij op.” Dat zijn twee verschillende getallen. In een programma kun je ze allebei een eigen naam geven:

```java
int getal = 4;
int anderGetal = 3;
int som = getal + anderGetal;

System.out.println(som);
```

De computer toont `7`.

Een **variabele** is een naam waarmee je in je programma naar een waarde verwijst. In Java geef je bij het maken van een variabele ook aan welk **type** waarde erin hoort. In het voorbeeld is `int` het type en zijn `getal` en `anderGetal` de namen van de variabelen.

Je kunt een variabele vergelijken met een **gelabeld doosje**:

- Het **label** is de naam van de variabele, bijvoorbeeld `leeftijd`.
- Het **type** geeft aan wat voor waarde erin mag, bijvoorbeeld `int`.
- De **waarde** is wat er op dat moment in staat, bijvoorbeeld `16`.

Je kunt **de waarde van een variabele** veranderen naar een andere waarde van hetzelfde type. Ik zou bijv. de waarde van `leeftijd` kunnen veranderen:

```java
int leeftijd = 16;
leeftijd = 19;          // Dit mag: 19 is ook een int.
// leeftijd = "zeventien"; // Dit geeft een fout: tekst past niet bij het type int.
```
De vergelijking is niet helemaal precies, maar helpt om het idee van naam, type en waarde te begrijpen.

> Let op: De codevoorbeelden op deze pagina zijn losse fragmenten. In een Java-programma plaats je ze binnen de `main`-methode.

## Veelgebruikte typen in Java

Een type bepaalt wat voor soort waarde een variabele kan bevatten. Veelgebruikte typen zijn:

- **`int`**: een geheel getal, bijvoorbeeld `4` of `-12`
- **`double`**: een kommagetal, bijvoorbeeld `3.14` of `-14.553`. In Java schrijf je een **punt**, geen komma.
- **`char`**: één karakter, bijvoorbeeld `'A'`; gebruik enkele aanhalingstekens.
- **`String`**: tekst, bijvoorbeeld `"Hallo!"`; gebruik dubbele aanhalingstekens.
- **`boolean`**: `true` of `false`

**Let op:** `String` begint met een hoofdletter. Java maakt onderscheid tussen hoofdletters en kleine letters: `String` en `string` zijn niet hetzelfde. Dat geldt ook voor variabelen: `anderGetal` en `andergetal` zijn **verschillende** namen.

## Regels en afspraken voor namen

De naam van een variabele is een **identifier**: de naam waarmee Java een variabele herkent. Java heeft regels voor identifiers. Programmeurs gebruiken daarnaast afspraken om code leesbaar te houden.

### Regels van Java

- Een naam mag niet met een cijfer beginnen.
- Een naam mag geen spaties of tekens zoals `@` bevatten.
- Een gereserveerd woord, zoals `class` of `int`, mag niet als variabelenaam worden gebruikt.
- Namen zijn hoofdlettergevoelig: `naam` en `Naam` zijn verschillende namen.

Java laat technisch ook namen met een underscore (`_`) of dollarteken (`$`) toe. Gebruik `$` liever niet. 

### Gebruikelijke afspraken

- Begin een variabelenaam met een kleine letter.
- Gebruik een beschrijvende naam, zoals `leeftijd` of `straatnaam`.
- Bestaat de naam uit meerdere woorden? Gebruik dan **camelCase**: schrijf de woorden aan elkaar en geef ieder volgend woord een hoofdletter, bijvoorbeeld `aantalLeerlingen` of `kleinsteGetal`.

Afspraken maken code duidelijker, maar zijn niet altijd hetzelfde als regels die Java afdwingt. Zo is `Classificatie` technisch een geldige naam, maar `classificatie` past beter bij de gebruikelijke schrijfwijze voor variabelen.

## Oefening: variabelenamen

```{exercise}
:label: java-variable-names

Bekijk de namen hieronder.

1. Welke namen zijn volgens de Java-regels **ongeldig** en geven dus een fout?
2. Welke namen zijn wel geldig, maar worden volgens de gebruikelijke Java-afspraken **afgeraden** als variabelenaam?
3. Leg bij je keuzes kort uit waarom.

1. `classificatie`
2. `Classificatie`
3. `cl@ssificatie`
4. `class1f1cat1e`
5. `1classificatie`
6. `_classificatie`
7. `class`
8. `Class`
9. `PI`
```

Als je de opgave hebt gemaakt, kun je de uitwerking hieronder bekijken.

```{solution}
:label: java-variable-names-solution
:class: dropdown

Namen die Java niet accepteert

- **3. `cl@ssificatie`** — `@` mag niet in deze naam voorkomen.
- **5. `1classificatie`** — een naam mag niet met een cijfer beginnen.
- **7. `class`** — `class` is een gereserveerd woord in Java.

Namen die geldig zijn, maar als variabelenaam worden afgeraden

- **2. `Classificatie`** — geldig, maar variabelen beginnen volgens de afspraak met een kleine letter. 
- **4. `class1f1cat1e`** — geldig, maar moeilijk te lezen. Gebruik een duidelijke naam zoals `classificatie`.
- **6. `_classificatie`** — geldig, maar een underscore aan het begin is niet de gebruikelijke schrijfwijze. 
- **8. `Class`** — geldig, maar een hoofdletter aan het begin past niet bij de afspraak voor variabelen.

Geldige en bruikbare namen

- **1. `classificatie`** — geldig en geschreven volgens de gebruikelijke afspraak voor variabelen.
- **9. `PI`** — geldig. Hoofdletters worden vaak gebruikt voor constanten, maar de naam `PI` alleen maakt de variabele niet constant. Daarvoor gebruik je `final`, bijvoorbeeld `final double PI = 3.14159;`. Let op: Met `final` kan de variabele niet opnieuw een waarde krijgen.
```
