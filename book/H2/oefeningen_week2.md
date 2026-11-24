# Oefeningen: invoer, uitvoer, testen en booleans

In deze oefening voorspel je eerst de uitvoer en bouw je daarna één Java-programma. Daarin gebruik je `Scanner`, een booleanvergelijking en test- en debugstappen.

## Inhoud

1. [Starten](#starten)
2. [Black box: verwacht de uitvoer](#1-black-box-verwacht-de-uitvoer)
3. [Eindopdracht: haal je het doel?](#2-eindopdracht-haal-je-het-doel)
4. [Uitbreiden](#uitbreiden-extra)
5. [Afronden](#afronden)

## Starten

Je maakt voor deze oefening maar **één Java-bestand en één klasse**: `DoelCheck.java` met de klasse `DoelCheck`.

1. Maak de klasse aan in Eclipse.
2. Plak de startcode uit de eindopdracht in de klasse.
3. Sla het bestand op en klik op **Run**.
4. Typ je invoer in de **Console** en druk op Enter.

## 1. Black box: verwacht de uitvoer

Een spel vraagt hoeveel punten de speler heeft. Het doel is **10 punten of meer**. Het programma print de naam van de speler en of het doel is gehaald.

Vul eerst de verwachte uitkomst in. Schrijf nog geen code.

| Invoer: punten | Verwachte uitkomst: doel gehaald |
|---:|---|
| 7 | |
| 10 | |
| 13 | |

- Wat zijn de invoer en de uitvoer van het programma?
- Waarom is het handig om de verwachte uitvoer vooraf vast te leggen?

Bewaar je tabel. Je gebruikt die bij het testen.

## 2. Eindopdracht: haal je het doel?

Maak de black-boxbeschrijving na in Java. Het programma vraagt om de naam en het aantal punten. Daarna print het of de speler het doel heeft gehaald.

Gebruik deze startcode in `DoelCheck.java`:

```java
import java.util.Scanner;

public class DoelCheck {
    public static void main(String[] args) {
        Scanner invoer = new Scanner(System.in);

        System.out.print("Wat is je naam? ");
        String naam = invoer.nextLine();

        System.out.print("Hoeveel punten heb je? ");
        int punten = invoer.nextInt();

        // Deze vergelijking bevat een fout. Zoek die met de tests.
        boolean doelGehaald = punten > 10;

        System.out.println(naam + ": doel gehaald = " + doelGehaald);
    }
}
```

### Bouw, test en verbeter

1. Voorspel wat het programma print bij 7, 10 en 13 punten.
2. Voer de drie tests uit. Vergelijk de werkelijke uitkomst met je tabel uit opdracht 1.
3. Voeg tijdelijk gelabelde debugregels toe om `punten` en `doelGehaald` te printen. Bijvoorbeeld:

   ```java
   System.out.println("DEBUG punten: " + punten);
   System.out.println("DEBUG doelGehaald: " + doelGehaald);
   ```

4. Gebruik de uitvoer om de fout te vinden. Het doel is gehaald bij **10 of meer** punten.
5. Pas de vergelijking aan en voer alle drie de tests opnieuw uit.

### Denk na

- Welke `Scanner`-methode leest een hele regel tekst? Welke leest een geheel getal?
- Welke operator controleert of punten **10 of meer** zijn?
- Wat is het verschil tussen `=` en `==`?
- Waarom was de test met 10 punten belangrijk?

## Uitbreiden

Laat de speler zelf kiezen hoeveel punten nodig zijn om het doel te halen. Breid je bestaande programma uit; maak **geen nieuwe klasse of bestand**.

1. Vraag na de naam en score ook hoeveel punten nodig zijn voor het doel.
2. Sla dat getal op in een variabele, bijvoorbeeld `doel`. Welke type hoort bij deze variabele?
3. Test je programma met deze gevallen:

| Naam | Punten | Doel | Verwachte uitkomst |
|---|---:|---:|---|
| Tugba | 8 | 10 | `false` |
| Sam | 10 | 10 | `true` |
| Noor | 13 | 12 | `true` |
| Oli | 10 | 12 | `false` |

Klopt het? Zo niet, kijk wat er mis is aan de hand van de debugregels.

## Afronden

- Sla `DoelCheck.java` op.
- Controleer dat de tests voor 7, 10 en 13 punten kloppen.
- Als je de uitbreiding hebt gemaakt, controleer dan ook alle drie de extra testgevallen.
- Lever het `.java`-bestand in op itslearning.
