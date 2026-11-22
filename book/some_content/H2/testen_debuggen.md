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

## Zelf proberen: gemiddelde in Magister

Je wilt het gemiddelde berekenen van drie cijfers. Het programma leest de cijfers in, berekent het gemiddelde en print het. Er zit een logische fout in de berekening.

```java
import java.util.Scanner;

public class Gemiddelde {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Cijfer 1: ");
        double cijfer1 = scanner.nextDouble();

        System.out.print("Cijfer 2: ");
        double cijfer2 = scanner.nextDouble();

        System.out.print("Cijfer 3: ");
        double cijfer3 = scanner.nextDouble();
        

        double totaal = cijfer1 + cijfer2 + cijfer2;
        double gemiddelde = totaal / 2;

        System.out.println("Gemiddelde: " + gemiddelde);
    }
}
```

Eén test kan soms toevallig de verwachte uitvoer geven, ook als er fouten in het programma zitten. Probeer het programma daarom met **beide** invoercombinaties:

| Test | Cijfer 1 | Cijfer 2 | Cijfer 3 | Verwacht gemiddelde |
|---|---:|---:|---:|---:|
| 1 | 6 | 2 | 7 | 5.0 |
| 2 | 6 | 8 | 10 | 8.0 |

1. Voer test 1 uit. Komt de uitvoer overeen met het verwachte gemiddelde?
2. Voer test 2 uit. Komt de uitvoer nu ook overeen?
3. Voeg vóór de uitvoerregel debug-prints toe voor `cijfer1`, `cijfer2`, `cijfer3`, `totaal` en `gemiddelde`.
4. Voer test 2 nog eens uit. Zijn de cijfers goed ingelezen? Klopt de som? Klopt het gemiddelde?
5. Zoek de fouten in de code en herstel ze
6. Test opnieuw met invoer van test 2. Klopt het nu? Zo nee, probeer het opnieuw. 
7. Klopt het nog voor de invoer van test 1? Zo ja, verwijder dan de tijdelijke debug-prints.


## Onthoud

- Test met invoer waarbij het probleem zichtbaar wordt.
- Vergelijk wat je verwacht met wat er werkelijk gebeurt.
- Een geslaagde test bewijst niet dat een programma altijd goed werkt, test dus met meerdere invoer.
- Print tijdelijk de waarden die je wilt controleren.
- Verander de code pas als je een aanwijzing hebt gevonden.
- Test na je aanpassing opnieuw en haal tijdelijke debug-uitvoer weg.