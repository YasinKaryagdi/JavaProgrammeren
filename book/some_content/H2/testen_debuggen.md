# Testen en debuggen in Java

## Wat is debuggen?

Een **bug** is een fout in een programma. Bij **debuggen** zoek je uit waar de fout ontstaat en pas je de code aan.

- Bij een **syntaxfout** kan Java de code niet goed lezen. Het programma start niet en Eclipse geeft een foutmelding.
- Bij een **logische fout** start het programma wel, maar gebeurt er iets anders dan je verwacht.

Een handige eerste stap is steeds dezelfde invoer opnieuw gebruiken. Vergelijk daarna de **verwachte uitvoer** met wat het programma echt laat zien.

## Print-debuggen

Soms weet je nog niet welke regel de fout veroorzaakt. Dan kun je tijdelijk extra `System.out.println`-regels toevoegen. Daarmee laat je waarden uit je programma op het scherm zien.

```java
System.out.println("[DEBUG] naam = " + naam);
```

Zet een herkenbaar label, zoals `[DEBUG]`, voor de waarde. Zo zie je dat deze regel alleen bedoeld is om te onderzoeken wat er gebeurt.

### Stappenplan

1. Voer het programma uit met een invoer die het probleem laat zien.
2. Noteer wat je verwacht en wat er werkelijk gebeurt.
3. Bedenk welke waarden je wilt controleren.
4. Zet daar tijdelijk debug-prints bij.
5. Voer het programma opnieuw uit en bekijk de waarden.
6. Pas de oorzaak aan en test opnieuw.
7. Verwijder de tijdelijke debug-prints als je klaar bent.

## Voorbeeld: de verkeerde begroeting

Het programma vraagt om een naam en een lievelingsdier. Daarna begroet het de gebruiker.

**Invoer**

```text
Naam: Noor
Lievelingsdier: otter
```

**Verwachte uitvoer**

```text
Hallo Noor!
```

**Werkelijke uitvoer**

```text
Hallo otter!
```

Het programma start, maar de uitvoer klopt niet. Dat wijst op een logische fout.

### De code

```java
import java.util.Scanner;

public class Begroeting {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Naam: ");
        String naam = scanner.nextLine();

        System.out.print("Lievelingsdier: ");
        String dier = scanner.nextLine();

        System.out.println("Hallo " + dier + "!");
    }
}
```

### Onderzoek met debug-prints

We willen weten of de invoer goed in de variabelen terechtkomt. Voeg deze twee regels vlak vóór de bestaande begroetingsregel toe:

```java
System.out.println("[DEBUG] naam = " + naam);
System.out.println("[DEBUG] dier = " + dier);
```

De gewone begroetingsregel blijft er direct onder staan. Met de invoer Noor en otter verschijnt dan:

```text
[DEBUG] naam = Noor
[DEBUG] dier = otter
Hallo otter!
```

De waarden zijn goed opgeslagen. De fout zit in de oorspronkelijke begroetingsregel: daar wordt `dier` gebruikt, terwijl de begroeting `naam` moet gebruiken.

Vervang die regel door:

```java
System.out.println("Hallo " + naam + "!");
```

Voer het programma opnieuw uit met dezelfde invoer. Klopt de begroeting nu? Haal daarna de twee regels met `[DEBUG]` weg. Die waren alleen tijdelijk nodig om de fout te vinden.

## Zelf proberen: favoriete hobby

Dit programma vraagt om een naam en een hobby. De tweede uitvoerregel is niet goed.

```java
import java.util.Scanner;

public class Hobby {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Naam: ");
        String naam = scanner.nextLine();

        System.out.print("Hobby: ");
        String hobby = scanner.nextLine();

        System.out.println("Hallo " + naam + "!");
        System.out.println("Je hobby is " + naam + ".");
    }
}
```

Gebruik als invoer:

```text
Naam: Mila
Hobby: volleybal
```

1. Wat is de verwachte uitvoer van de tweede regel?
2. Voeg na het inlezen van de invoer en vóór de gewone uitvoerregels een debug-print toe voor `naam` en een voor `hobby`.
3. Voer het programma uit. Wat vertellen de debug-prints je?
4. Welke regel moet je aanpassen? Test je aanpassing met dezelfde invoer.
5. Verwijder daarna de tijdelijke debug-prints.

## Onthoud

- Test met invoer waarbij het probleem zichtbaar wordt.
- Vergelijk wat je verwacht met wat er werkelijk gebeurt.
- Print tijdelijk de waarden die je wilt controleren.
- Verander de code pas als je een aanwijzing hebt gevonden.
- Test na je aanpassing opnieuw en haal tijdelijke debug-uitvoer weg.