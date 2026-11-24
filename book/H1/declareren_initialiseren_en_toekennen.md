# Declareren, initialiseren en toekennen

Op de vorige pagina heb je gezien dat een variabele een **gelabelde doosje** is waarin een programma een waarde van een bepaald type bijhoudt.

Bij het werken met variabelen gebruiken we drie begrippen:

- **Declareren:** een variabele maken door het type en de naam op te geven.
- **Initialiseren:** de variabele voor het eerst een waarde geven.
- **Toekennen:** een waarde aan de variabele geven. De eerste toekenning is de initialisatie. Met een latere toekenning kun je de waarde wijzigen.

We gebruiken in deze uitleg steeds dezelfde vier variabelen: `leeftijd`, `toetsCijfer`, `naam` en `isLeerling`.

> De codevoorbeelden horen binnen de `main`-methode. Voer de voorbeelden onder **Declareren**, **Initialiseren** en **Toekennen** in die volgorde uit. Zo bestaan de variabelen al wanneer je ze een waarde geeft.

## Declareren

Bij het **declareren** geef je het type en de naam van een variabele op. Je sluit de opdracht af met een puntkomma (`;`).

```java
int leeftijd;
double toetsCijfer;
String naam;
boolean isLeerling;
```

Deze variabelen zijn nu gedeclareerd. We hebben ze een naam en een type gegeven. We hebben een plekje vrijgemaakt in onze computer om er waardes in op te slaan. Maar deze waardes zit er nog niet in! De variabelen hebben namelijk nog geen beginwaarde gekregen. **Een variabele die je declareert moet eerst een waarde krijgen voordat je die variabele kunt gebruiken**. Er zit namelijk na het declareren "nog niets in". Dit resulteert in een foutmelding wanneer je ze probeert te gebruiken, bijvoorbeeld tijdens een printopdracht, probeer maar:

Wat gebeurt er wanneer je de variabele gelijk gebruikt nadat je het declareert?
```java
// Verwijder deze regels code na het testen
int cijfer;
System.out.println(cijfer); // Wat gebeurt er als je deze code runt?
```

## Initialiseren

**Initialiseren** betekent dat je een variabele voor het eerst een waarde geeft. Daarvoor gebruik je het teken `=`. Lees dit als: “de variabele krijgt de waarde”.

De variabelen zijn hierboven al gedeclareerd. Daarom schrijf je het type niet opnieuw.


```java
leeftijd = 16;
System.out.println(leeftijd); // computer toont: 16

toetsCijfer = 6.6;
System.out.println(toetsCijfer); // computer toont: 6.6

naam = "Hyperion Lyceum";
System.out.println(naam); // computer toont: Hyperion Lyceum

isLeerling = true;
System.out.println(isLeerling); // computer toont: true
```
Wat gebeurt er als je een variabele probeert te initialiseren zonder deze te declareren?

```java
// Verwijder deze code na het testen
getal = 13;
```

### Declareren en initialiseren op één regel

Je kunt een variabele ook meteen bij het declareren een beginwaarde geven. 

```java
// Je zou al je huidige code kunnen vervangen met dit stukje code
int leeftijd = 16;
double toetsCijfer = 6.6;
String naam = "Hyperion Lyceum";
boolean isLeerling = true;
```

Dit is een **alternatief** voor het apart declareren en initialiseren hierboven. Je mag zelf kiezen welke je gebruikt, maar bedenk even dat het niet altijd handig is om gelijk te initialiseren!

## Toekennen

**Toekennen** betekent dat je een waarde aan een variabele geeft. Dat doe je ook bij het initialiseren. Als de variabele al een waarde heeft, kun je met een nieuwe toekenning die waarde wijzigen.

Je gebruikt opnieuw `=`, maar schrijft het type niet opnieuw. De variabele bestaat namelijk al.


```java
leeftijd = 20;
System.out.println(leeftijd); // toonde 16, toont nu: 20

toetsCijfer = 9.0;
System.out.println(toetsCijfer); // toonde 6.6, toont nu: 9.0, dus net als jouw cijfer ;)

naam = "De kleine Johannes";
System.out.println(naam); // toonde Hyperion Lyceum, toont nu: De kleine Johannes

isLeerling = false;
System.out.println(isLeerling); // toonde true, toont nu: false
```

Een nieuwe waarde moet passen bij het type van de variabele. Je kunt bijvoorbeeld geen tekst aan `leeftijd` toekennen, want `leeftijd` heeft het type `int`.

> **Let op:** `=` is een toekenning, geen vergelijking. Om te controleren of twee waarden gelijk zijn, gebruik je in Java `==`. Bij tekst vergelijken werkt dit anders; dat behandelen we later.

## Eindprogramma
Als je nog eens alles achter elkaar wilt bekijken kan je kijken naar dit fragment, als het goed is heb je dit nu zelf staan:
```java
// Declareren (naam geven, type aangeven, maakt ruimte in computer)
int leeftijd;
double toetsCijfer;
String naam;
boolean isLeerling;

// Initialiseren (want eerste keer dat we een waarde toekennen)
leeftijd = 16;
System.out.println(leeftijd); // computer toont: 16

toetsCijfer = 6.6;
System.out.println(toetsCijfer); // computer toont: 6.6

naam = "Hyperion Lyceum";
System.out.println(naam); // computer toont: Hyperion Lyceum

isLeerling = true;
System.out.println(isLeerling); // computer toont: true

// Toekennen (waarde wijzigen)
leeftijd = 20;
System.out.println(leeftijd); // toonde 16, toont nu: 20

toetsCijfer = 9.0;
System.out.println(toetsCijfer); // toonde 6.6, toont nu: 9.0, dus net als jouw cijfer ;)

naam = "De kleine Johannes";
System.out.println(naam); // toonde Hyperion Lyceum, toont nu: De kleine Johannes

isLeerling = false;
System.out.println(isLeerling); // toonde true, toont nu: false
```

## Kort samengevat

| Begrip | Wat doe je? | Voorbeeld |
| --- | --- | --- |
| Declareren | Het type en de naam opgeven. | `int leeftijd;` |
| Initialiseren | Voor het eerst een waarde geven. | `leeftijd = 16;` |
| Opnieuw toekennen | Een nieuwe waarde geven. | `leeftijd = 20;` |

Met `int leeftijd = 16;` declareer en initialiseer je de variabele op een regel.
