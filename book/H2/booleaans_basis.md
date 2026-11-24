# Boolean: waar of onwaar?

Een programma kan een vraag beantwoorden met één van twee waarden: **`true`** of **`false`**. In Java sla je zo’n waarde op in een variabele van het type `boolean`.

```java
boolean isOpen = true;
boolean isGesloten = false;
```

`true` en `false` zijn speciale Java-waarden. Schrijf ze met kleine letters en zonder aanhalingstekens.

## Vergelijken

Een vergelijking is een vraag over waarden. Java rekent de vergelijking uit en geeft `true` of `false` terug.

| Operator | Betekenis | Voorbeeld | Uitkomst |
|---|---|---|---|
| `==` | is gelijk aan | `8 == 8` | `true` |
| `!=` | is niet gelijk aan | `8 != 5` | `true` |
| `<` | is kleiner dan | `5 < 8` | `true` |
| `>` | is groter dan | `5 > 8` | `false` |
| `<=` | is kleiner dan of gelijk aan | `8 <= 8` | `true` |
| `>=` | is groter dan of gelijk aan | `5 >= 8` | `false` |

### Let op: `=` is niet hetzelfde als `==`

- Met `=` geef je een waarde aan een variabele.
- Met `==` vergelijk je twee waarden.

```java
int punten = 8;                 // sla 8 op in punten
boolean heeftAchtPunten = punten == 8; // vergelijk punten met 8
```

De variabele `heeftAchtPunten` krijgt de waarde `true`.

## Een vergelijking opslaan en printen

Stel: in een spel is het doel om minstens 10 punten te halen. De vergelijking `punten >= 10` controleert of dat doel is gehaald.

```java
int punten = 12;
boolean doelGehaald = punten >= 10;

System.out.println("Punten: " + punten);
System.out.println("Doel gehaald: " + doelGehaald);
```

De uitvoer is:

```text
Punten: 12
Doel gehaald: true
```

Verander `punten` in `7` en voer de code opnieuw uit. De vergelijking wordt dan `7 >= 10`, dus `doelGehaald` wordt `false`.

## Invoer vergelijken

Je kunt ook een ingevoerd getal vergelijken. In dit programma voert de gebruiker een score in en controleert Java of die minstens 10 is.

```java
import java.util.Scanner;

public class DoelCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Hoeveel punten heb je? ");
        int punten = scanner.nextInt();

        boolean doelGehaald = punten >= 10;
        System.out.println("Doel gehaald: " + doelGehaald);
    }
}
```

Bij invoer `8` print het programma `false`. Bij invoer `10` print het `true`.

## Zelf proberen

Neem `int punten = 7;`. Voorspel eerst of elke vergelijking `true` of `false` oplevert. Controleer daarna je voorspellingen door ze te printen.

| Vergelijking | Mijn voorspelling |
|---|---|
| `punten >= 6` | |
| `punten == 7` | |
| `punten != 7` | |
| `punten < 6` | |

```java
int punten = 7;

System.out.println(punten >= 6);
System.out.println(punten == 7);
System.out.println(punten != 7);
System.out.println(punten < 6);
```

## Onthoud

- Een `boolean` heeft als waarde `true` of `false`.
- Een vergelijking levert `true` of `false` op.
- `=` kent een waarde toe; `==` vergelijkt waarden.
- In deze les vergelijk je steeds één voorwaarde. Meerdere voorwaarden combineren en keuzes maken met `if` komen later.
