# Oefening: Variabelen en printopdrachten in Java

In deze oefening leer je tekst op het scherm te tonen en variabelen in uitvoer te gebruiken. Je werkt in één Java-programma en voert dat uit in de console.

## Inhoud

1. [Starten](#starten)
2. [De println-opdracht](#1-de-println-opdracht)
3. [Variabelen en concatenatie](#2-variabelen-en-concatenatie)
4. [Getallen in uitvoer](#3-getallen-in-uitvoer)
5. [Uitvoer opmaken met printf](#4-uitvoer-opmaken-met-printf)
6. [Eindopdracht](#5-eindopdracht-maak-je-eigen-uitvoer)
7. [Afronden en inleveren](#afronden-en-inleveren)

## Starten

Maak in Eclipse een Java-klasse met de naam `PrintOefening`. De bestandsnaam wordt dan `PrintOefening.java`.

1. Plak de code hieronder in de klasse.
2. Sla het bestand op.
3. Klik op **Run** om het programma uit te voeren.
4. Bekijk de uitvoer in de **Console**.
5. Pas bij elke opdracht de code aan en voer het programma opnieuw uit.

De opdrachten staan samen in één programma. Je hoeft de klasse en de `main`-methode niet zelf opnieuw te schrijven.

```java
public class PrintOefening {
    public static void main(String[] args) {

        // 1. De println-opdracht
        System.out.println("Hallo wereld");

        // 2. Variabelen en concatenatie
        String voornaam = "Vwo";
        String achternaam = "Leerling";

        // OPDRACHT: print hier een begroeting met voornaam en achternaam.

        int leeftijdVoorbeeld = 16;

        // OPDRACHT: print hier een zin met leeftijdVoorbeeld.

        // 3. Getallen in uitvoer
        double cijfer = 7.5;
        System.out.println("Mijn cijfer is: " + cijfer);

        String cijferAlsTekst = String._(cijfer); // <- Welke methode moet je hier gebruiken?
        System.out.println("Het cijfer als tekst is: " + cijferAlsTekst);

        String straatnaam = "Dorpsstraat";
        int huisnummer = 12;

        // OPDRACHT: print hier het adres met straatnaam en huisnummer.

        // 4. Uitvoer opmaken met printf
        String stad = "Utrecht";
        System.out.printf("Ik woon in de stad %s.%n", stad);

        // OPDRACHT: print hier je voornaam met printf.

        // 5. Eindopdracht
        // OPDRACHT: maak hieronder de variabelen naam, leeftijd en hobby.
        // Bijvoorbeeld: String naam = "...";
        // Bijvoorbeeld: int leeftijd = ...;
        // Bijvoorbeeld: String hobby = "...";

        // OPDRACHT: print met printf een zin met naam, leeftijd en hobby.

    }
}
```

> Java is hoofdlettergevoelig. Let op hoofdletters in namen zoals `String` en `System.out.println`. Java-opdrachten eindigen meestal op een puntkomma (`;`).

## 1. De println-opdracht

Met `System.out.println()` laat je de computer iets in de console tonen. Tekst zet je tussen dubbele aanhalingstekens.

**Opdracht:** verander de tekst `Hallo wereld` in:

```text
Ik leer programmeren!
```

Voer het programma uit en controleer de uitvoer.

## 2. Variabelen en concatenatie

Een variabele bewaart een waarde. In Java vermeld je bij het maken van een variabele welk type waarde erin staat. `String` is voor tekst en `int` is voor een geheel getal.

Met `+` kun je tekst aan elkaar plakken. Dit heet **concatenatie**. Java voegt zelf geen spaties toe.

**Opdrachten:**

1. Gebruik de variabelen `voornaam` en `achternaam` om deze uitvoer te maken:

   ```text
   Hallo Vwo Leerling
   ```

2. Gebruik `leeftijdVoorbeeld` in een zin, bijvoorbeeld: `Ik ben 16 jaar oud.`
3. Verander de waarden van de variabelen en voer het programma opnieuw uit.

## 3. Getallen in uitvoer

In Java kun je een getal met tekst combineren als een deel van de uitdrukking al tekst is:

```java
System.out.println("Mijn cijfer is: " + cijfer);
```

Java zet het getal dan automatisch om naar tekst voor de uitvoer. Je hoeft hier dus niet eerst een conversie uit te voeren. Met `String.valueOf(...)` kun je een getal wel expliciet omzetten naar een `String`, bijvoorbeeld als je de tekst later verder wilt gebruiken.

**Opdrachten:**

1. Verander de waarde van `cijfer` en bekijk de uitvoer.
2. Gebruik `straatnaam` en `huisnummer` om een adres te printen.
3. Zorg zelf voor de spatie tussen de straatnaam en het huisnummer.

## 4. Uitvoer opmaken met printf

Java heeft geen f-strings. Met `printf` kun je wel waarden op vaste plekken in een tekst zetten. Je gebruikt daarvoor een aanduiding in de tekst:

- `%s` voor tekst (`String`)
- `%d` voor een geheel getal (`int`)
- `%f` voor een kommagetal (`double`)
- `%.1f` voor een kommagetal met één cijfer achter de komma
- `%n` voor een nieuwe regel

Voorbeeld:

```java
String stad = "Utrecht";
System.out.printf("Ik woon in de stad %s.%n", stad);
```

De eerste `%s` wordt vervangen door de waarde van `stad`.

**Opdracht:** gebruik `printf` om je voornaam in een zin te tonen. Gebruik de variabele `voornaam`.

## 5. Eindopdracht: maak je eigen uitvoer

Maak in het laatste deel van het programma drie variabelen:

- `naam` met het type `String`
- `leeftijd` met het type `int`
- `hobby` met het type `String`

Gebruik `printf` om een nette zin te tonen waarin alle drie de waarden voorkomen. Je zin kan er bijvoorbeeld zo uitzien:

```text
Ik ben Noor, 16 jaar oud en mijn hobby is tekenen.
```

Controleer of je de juiste aanduidingen gebruikt: `%s` voor tekst en `%d` voor een geheel getal.

## Afronden en inleveren

1. Sla `PrintOefening.java` op.
2. Voer het programma nog één keer uit en controleer of je eindopdracht zichtbaar is in de Console.
3. Lever het `.java`-bestand in via de opdracht in Itslearning.