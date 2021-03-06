# Laboration 1, del A

I denna laborationsuppgift är tanken att ni ska lära er att använda koncept som arv, gränssnitt, metod-overloading (överlagring) och metod-overriding (skuggning) tillsammans med Java. Se till att noga läsa igenom instruktionerna och att följa de regler och krav som labbdokumentet föreskriver. Börja med att kolla igenom hela labbdokumentet och se vad som krävs för att få godkänt, samt med att ladda ner de filer som behövs.

I första deluppgiften bekantar vi oss med den givna Java-koden, samt skapar ny kod. Därefter bygger varje deluppgift på den tidigare lösningen. Koden som skrivs och godkänns i denna labb kommer senare att användas i Laboration 2.

### Generella regler för laboration:

* Det är inte tillåtet att dela, kopiera eller använda skriven kod från varandra på något sätt. Det är däremot fullt accepterat, för att inte säga uppmuntrat, att diskutera uppgifter och lösningar sinsemellan.
* För att få godkänt på labben gör ni muntliga redovisningar. Gruppen gör denna tillsammans: alla gruppmedlemmar kommer ställas frågor var och en för sig. För att gruppen ska bli godkänd ska alla gruppmedlemmar kunna svara på frågor. Se med andra ord till att ni hänger med i laborationen, och att era kamrater i gruppen hänger med. Fråga assistenterna om hjälp ifall ni fastnar.

### Krav för godkänt vid redovisning:

* Alla uppgifter ska vara lösta vid redovisningen. Lösningen skall gå att kompilera och köra!
* Alla gruppmedlemmar ska ha deltagit i skrivandet av koden, och känna till hela arbetet
* Alla gruppmedlemmar ska kunna svara på frågor om lösningen.

## Uppgift 1: Grundläggande arv

Börja med att klona repot https://github.com/dit953/laboration-1 och bekanta er med det. För närvarande finns det två Java-filer, *Volvo240.java* och *Saab95.java*. Just nu verkar klasserna ha ganska mycket gemensamt, eftersom båda representerar bilar.

* Skapa en arvshierarki där `Volvo240` och `Saab95` ingår, som eliminerar all kod-duplicering, och som följer Open-Closed Principle. Gör dessa ändringar utan att ändra på klassernas funktionalitet.
  * Bör ni använda implementationsarv (subclassing) eller specifikationsarv (interfaces)? Varför? Kan båda användas? Vilka för- och nackdelar ser ni?
* I originalfilerna är alla metoder och variabler `public`, vilket exponerar allt till användaren. Ändra synligheten på de metoder och variabler som användaren inte behöver se eller känna till. 
  * Vilken synlighet bör ni använda för de olika metoder och variabler som klasserna innehåller? Vilket gränssnitt bör ni exponera?

Se till att alla filer kompilerar och fortsätt till nästa uppgift.

 
## Uppgift 2: Action Interfaces

I denna uppgift fortsätter vi bygga på föregående genom att vi nu också implementerar ett interface kallat `Movable`.

* Skapa en fil *Movable.java*, som deklarerar ett interface med följande metoder:
```java
    void move();
    void turnLeft();
    void turnRight();
```
* Se till att era bilar implementerar interfacet `Movable`, med någon lämplig intern representation av deras riktning och position. Metoden `move()` ska fungera så att beroende på riktning ökas (eller minskas) bilens `x`- eller `y`-koordinat med dess `currentSpeed`.

## Uppgift 3: Dokumentation och testning

Dokumentation och testning är viktigt vid design av program.

* Använd Javadoc för att kommentera samtliga klasser och interfaces. Ni bör ha 100% comment/Javadoc coverage för era filer. Använd funktioner som finns i IntelliJ för att uppnå detta. Det finns mycket information om Javadoc på nätet om ni behöver ta fram det.
* När ni är klara bör ni kunna få ut lämpliga API-dokument för ert program som HTML-filer. Stämmer det API (= "Application Programmer Interface") som Javadoc genererar med vad ni vill exponera?
* Använd JUnit för att skriva tester med 100% coverage för era bilklasser. Även JUnit har mycket information på nätet som ni kan leta upp. Era tester inte behöver testa "allt"; det viktiga är att ni bekantar er med JUnit och förstår hur det fungerar. Ni behöver inte skriva kodkontrakt för era metoder. Det räcker att ni skriver testmetoder som testar metodernas funktionalitet med hjälp av `assert`/`equals` osv. Därefter testar ni så att alla JUnit-tester går igenom med "Run with coverage".

## Uppgift 4: Sanity checks

Bilklassernas metoder har för närvarande inget sätt att kontrollera hur mycket farten kan ökas eller sänkas. Skriv om metoder (och dokumentation) så att:

* `gas()` och `break()` bara accepterar värden i intervallet [0,1],
* `currentSpeed` alltid ligger i intervallet [0,`enginePower`],
* Anrop till `gas()` inte kan resultera i att farten sänks, och
* Anrop till `break()` inte kan resultera i att farten höjs.


### Extra uppgift för mer utmaning:

* Skapa en enkel applikation som använder sig av era bilar.

### För att redovisa:

* Ladda upp ert repo till github (eller annat alternativ som hanterar git-repon).
* "Lämna in" en URL till ert repo här i Canvas.
* Redovisa muntligt för en handledare, senast under laborationspasset, Måndag 4/2 kl 13:15-17:00
