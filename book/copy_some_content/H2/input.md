# Invoer via de console

Tot nu toe gaf je zelf waarden aan variabelen in je code. Met **invoer** (ook wel bekend als **input**) kan een gebruiker tijdens het uitvoeren van een programma informatie typen. Het programma kan die invoer opslaan in variabelen en later gebruiken.

In deze les gebruik je Java’s `Scanner` om invoer uit de console te lezen.

## Een compleet voorbeeld

Maak in Eclipse een klasse met de naam `InputVoorbeeld`. De bestandsnaam moet `InputVoorbeeld.java` zijn. Vervang de inhoud van de klasse door deze code:

```java
import java.util.Scanner;

public class InputVoorbeeld {
    public static void main(String[] args) {
        Scanner invoer = new Scanner(System.in);

        System.out.print("Wat is je volledige naam? ");
        String naam = invoer.nextLine();

        System.out.print("Hoe oud ben je? ");
        int leeftijd = invoer.nextInt();

        System.out.println("Hallo " + naam + ". Je bent " + leeftijd + " jaar oud.");
    }
}
```

Klik op **Run**. Klik daarna in de Eclipse-**Console**, typ je antwoord en druk op Enter. Het programma wacht na elke vraag op invoer, dit komt door de methoden ...., want ....

Voorbeeld van de interactie:

```text
Wat is je volledige naam? Grote Geelstaart
Hoe oud ben je? 16
Hallo Grote Geelstaart. Je bent 16 jaar oud.
```

## Wat gebeurt er in de code?

- `import java.util.Scanner;` maakt de klasse `Scanner` beschikbaar.
- `Scanner invoer = new Scanner(System.in);` maakt een Scanner die invoer uit de console leest.
- `System.out.print(...)` toont een vraag. Anders dan `println` begint `print` niet meteen een nieuwe regel.
- `invoer.nextLine()` leest een hele regel tekst en levert een `String` op.
- `invoer.nextInt()` leest een geheel getal en levert een `int` op.
- De antwoorden worden opgeslagen in de variabelen `naam` en `leeftijd`.

### Scanner leest invoer op verschillende manieren

De **methode** bepaalt welk type waarde je uit de invoer leest:

| Scanner-methode | Leest | Type resultaat |
|---|---|---|
| `nextLine()` | Een hele regel tekst | `String` |
| `nextInt()` | Een geheel getal | `int` |
| `nextDouble()` | Een kommagetal | `double` |

Je hoeft dus niet te zeggen dat alle invoer in Java automatisch tekst is. `nextLine()` leest tekst; met `nextInt()` of `nextDouble()` leest `Scanner` een getal van dat type.

> **Let op:** voer bij `nextInt()` een geheel getal in, zoals `16`. Als je tekst invoert, kan Java de invoer niet als `int` lezen en ontstaat er een fout.

## Opdrachten

Werk steeds in `InputVoorbeeld.java`. Voer het programma na elke aanpassing opnieuw uit.

1. Verander de eerste vraag in `Wat is je voornaam?`.
2. Verander de begroeting zodat de computer ook zegt dat hij blij is dat je er bent.
3. Verander de vraag over leeftijd in een vraag over je favoriete getal. Pas de naam van de variabele aan zodat die duidelijk beschrijft wat erin staat.
4. Test het programma met verschillende invoer, bijvoorbeeld met een naam met twee woorden en met verschillende leeftijden.

### Zelf proberen

Maak daarna een programma dat de gebruiker vraagt naar een favoriete sport en hoeveel jaar diegene die sport al doet. Print beide antwoorden in één nette zin.

Gebruik `nextLine()` voor de sport en `nextInt()` voor het aantal jaren. De twee Scanner-methoden leveren verschillende typen waarden op.

## Onthouden

1. Maak één Scanner met `new Scanner(System.in);`, deze herbruik je telkens.
2. Stel een vraag met `System.out.print(...)`.
3. Lees het antwoord met de Scanner-methode die past bij het soort invoer.
4. Sla het antwoord op in een variabele van het juiste type.

In [het volgende onderdeel](blackbox.md) bekijken we programma’s als black box: welke invoer gaat erin en welke uitvoer komt eruit?

> Deze codevoorbeelden gebruiken losse Java-klassen. De bestandsnaam moet overeenkomen met de naam achter `public class`.