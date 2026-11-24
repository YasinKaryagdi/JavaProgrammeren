# Oefening: Variabelen en printopdrachten in Java

Je oefent met `println`, variabelen en het combineren van tekst en waarden. Eerst bekijk je een voorbeeld, daarna maak je zelf een gepersonaliseerd uitvoer in de Console. `printf` is een extra uitdaging.

## Inhoud

1. [Starten](#starten)
2. [Voorspel de uitvoer](#1-voorspel-de-uitvoer)
3. [Voer het programma uit](#2-voer-het-programma-uit)
4. [Bekijk de code](#3-bekijk-de-code)
5. [Pas de code aan](#4-pas-de-code-aan)
6. [Maak je eigen uitvoer](#5-maak-je-eigen-uitvoer)
7. [Uitdaging: gebruik printf](#6-uitdaging-gebruik-printf)
8. [Afronden en inleveren](#afronden-en-inleveren)

## Starten

Maak in Eclipse een Java-klasse met de naam `PrintOefening`. De bestandsnaam wordt dan `PrintOefening.java`.

1. Plak de code hieronder in de klasse.
2. Sla het bestand op.
3. Voer het programma nog niet uit. Begin eerst bij **Voorspel de uitvoer**.

De klasse en de `main`-methode staan al in de code. Je hoeft die niet zelf te maken.

```java
public class PrintOefening {
    public static void main(String[] args) {

        String voornaam = "Vwo";
        String achternaam = "Leerling";
        int leeftijd = 13;

        System.out.println("Hallo wereld");
        System.out.println("Hallo " + voornaam + " " + achternaam); // <- de begroetingsregel
        System.out.println("Leeftijd: " + leeftijd);

        leeftijd = 18;
        System.out.println("Nieuwe leeftijd: " + leeftijd);
    }
}
```

> **Let op!** Java-opdrachten eindigen meestal op een puntkomma (`;`).

## 1. Voorspel de uitvoer

Lees de code rustig door. Schrijf op wat je denkt dat het programma in de Console toont. Schrijf de regels in de juiste volgorde op.

Denk ook na over deze vragen:

- Welke zin toont deze regel: `System.out.println("Leeftijd: " + leeftijd);`?
- Wat toont de laatste `println`-regel? Welke waarde heeft leeftijd tijdens deze regel?
- Hoeveel regels tekst verschijnen er in de Console?

## 2. Voer het programma uit

1. Klik op **Run**.
2. Bekijk de uitvoer in de **Console**.
3. Vergelijk de uitvoer met je voorspelling.

Noteer het verschil tussen je voorspelling en de uitvoer.

## 3. Bekijk de code

Beantwoord de vragen. Je kunt hiervoor de code en de uitvoer bekijken.

1. Welke variabelen staan in het programma en welk type heeft elke variabele?
2. Welke regel geeft `leeftijd` een nieuwe waarde?
3. Wat wordt met `+` samengevoegd in de begroetingsregel? Wat is de functie van `" "`?

## 4. Pas de code aan

**Voer na iedere aanpassing het programma uit. Controleer steeds of de uitvoer klopt met wat je verwacht.**

1. Verander de tekst `Hallo wereld` in:

   ```text
   Ik leer programmeren!
   ```

2. Verander de waarde in de toekenning `leeftijd = 18;` bijvoorbeeld naar `leeftijd = -21;`.

3. Verander de regel `System.out.println("Hallo " + voornaam + " " + achternaam);`, toon eerst je achternaam, en pas daarna je voornaam. 

## 5. Maak je eigen uitvoer

Maak onderaan in de `main`-methode een klein profiel met je eigen gegevens.

1. Maak een tekst variabele met de naam `naam`.
2. Maak een geheel getal variabele met de naam `profielLeeftijd`.
3. Maak een tekst variabele met de naam `hobby`.
4. Geef de variabelen passende waarden.
5. Print met `println` een zin waarin je naam, leeftijd en hobby staan.

Je uitvoer kan er bijvoorbeeld zo uitzien:

```text
Ik ben Noor Bakker, 16 jaar oud en mijn hobby is tekenen.
```

Maar het mag ook uitgebreider! 

**Gebruik voor dit profiel ten minste de nieuwe variabelen `naam`, `profielLeeftijd` en `hobby`.**

## 6. Uitdaging: gebruik printf (optioneel opdracht)

`System.out.printf()` is een andere manier om uitvoer op te maken. In de tekst zet je invulcodes op de plekken waar waarden moeten komen:

- `%s` voor tekst
- `%d` voor een geheel getal
- `%f` voor kommagetallen
- `%n` voor een nieuwe regel

De waarden van de variabelen na de tekst komen op volgorde op de plekken van de invulcodes. Bekijk dit voorbeeld:

```java
System.out.printf("Hallo %s!%n Je bent %d jaar!!", voornaam, leeftijd);
```

Hier vervangt Java `%s` door de waarde van `voornaam`, begint `%n` een nieuwe regel en vervangt Java `%d` door de waarde van `leeftijd`.

**Uitdaging:** print je zin uit de eindopdracht ook met `printf`. Gebruik de juiste invulcode voor tekst en voor het gehele getal.

Tip: de invulcodes en variabelen moeten in dezelfde volgorde staan.

## Afronden en inleveren

1. Sla `PrintOefening.java` op.
2. Voer het programma nog één keer uit.
3. Controleer of je eigen zin zichtbaar is in de Console.
4. Lever het `.java`-bestand in via de opdracht in Itslearning.
