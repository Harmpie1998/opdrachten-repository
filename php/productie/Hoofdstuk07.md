# Hoofdstuk 7 Beslissingen

## 7.1 Wat ga je leren ?

In dit hoofdstuk worden: 
- if else constructies verder verdiept
- booleaanse expressies (php code die een true of een false opleveren)

    - ==  precies gelijk aan
    - <   kleiner dan
    - <=  kleiner dan of gelijk
    - &gt;   groter dan
    - &gt;=  groter dan of gelijk aan
    - <>  ongelijk aan

- and en or in booleaanse expressies

    - && and
    - || or

- nesten van if else constructies

- shorthand notatie if else


## 7.2 Wanneer en waar wordt het gebruikt?
~~~php
    //Tussen de ronde haakjes
    if () {

        //deze code wordt uitgevoerd als dat wat tussen () true oplevert

    }
    else {

        //deze code wordt uitgevoerd als dat niet zo is (=false)
    }
~~~
- Hoe?

## 7.3 Voorbeeld 1 met strings
~~~php

      $naam = "Sander";

    //true or false?

    echo "<hr>";    
    if ($naam == "sander") {
        echo "$naam == 'sander' is waar(true)";
    } 
    else {
        echo "$naam == 'sander' is niet waar(false)";        
    } 

    echo "<hr>";    
    if (strtolower($naam) == "sander") {
        echo strtolower($naam)." == 'sander' is waar(true)";
    } 
    else {
        echo "$naam == 'sander' is niet waar(false)";        
    } 

    echo "<hr>";    
    if ($naam <> "sander") {
        echo "$naam <> 'sander' is waar(true)";
    } 
    else {
        echo "$naam <> 'sander' is niet waar(false)";        
    } 

~~~

## 7.4 Voorbeeld 2 met getallen
~~~php

    $leeftijd = 28;

    //true or false?
    echo "<hr>";    
    if ($leeftijd > 28) {
        echo "$leeftijd > 28 is waar(true)";
    } 
    else {
        echo "$leeftijd > 28 is niet waar(false)";        
    } 
    echo "<hr>";    
    if ($leeftijd >= 28) {
        echo "$leeftijd >= 28 is waar(true)";
    } 
    else {
        echo "$leeftijd >= 28 is niet waar(false)";        
    } 
    echo "<hr>";    
    if ($leeftijd < 28) {
        echo "$leeftijd < 28 is waar(true)";
    } 
    else {
        echo "$leeftijd < 28 is niet waar(false)";        
    } 
    echo "<hr>";    
    if ($leeftijd <= 28) {
        echo "$leeftijd <= 28 is waar(true)";
    } 
    else {
        echo "$leeftijd <= 28 is niet waar(false)";        
    } 

~~~

## 7.5 Voorbeelden met and (&&) en or (||)

&& (and) en || (or) worden gebruikt om meerdere voorwaarden te kunnen combineren

Voorbeelden van een combinatievragen (voorwaarden) zijn:

1. Is de leeftijd lager dan 18 __of__ is de leeftijd hoger dan 65?
2. Is de leeftijd lager dan 18 __en__ is de woonplaats Den Bosch?
3. Is de leeftijd lager dan 18 __of__ is de woonplaats Den Bosch?
4. Is de leeftijd hoger dan 18 __en__ lager dan 65?

Vertaling naar php-code:
~~~php

 $leeftijd = 17;
    $plaats = "Vught";

    echo "leeftijd is $leeftijd en plaats is $plaats";
    // voorbeeld 1 van hierboven
    echo "<hr>";    
    if ($leeftijd <18 || $leeftijd >65) {
        echo "<br>Je bent of jong of heel oud";
    } 
    else {
        echo "<br>Je bent een volwassen persoon";        
    } 

    //voorbeeld 2 van hierboven
    if ($leeftijd <18 && $plaats == "Den Bosch") {
        echo "<br>Je bent een jonge Bosschenaar";
    } 
    else {
        echo "<br>Je bent oud of je komt niet uit Den Bosch";        
    } 

    //voorbeeld 3 van hierboven
    if ($leeftijd <18 || $plaats == "Den Bosch") {
        echo "<br>Je bent een jong persoon of je woont in Den Bosch";
    } 
    else {
        echo "<br>Je bent niet jong en je bent geen Bosschenaar";        
    }

~~~
## 7.6 Nesten van if else constructies

Het komt vaak voor dat binnen een if-else constructie weer een if-else constructie nodig is. Voorbeeld...

~~~php
    //leeftijd if
    if ($leeftijd > 25) {
        //ook een plaats voorwaardelijkheid nodig
        if ($plaats == "Den Bosch") {
            $korting = "99%";
        } //else is niet verplicht 
        
    }
    else {
        //nesten kan in de if mmar ook in de else
        if($leeftijd<45) {
            $korting= "33%";
        }
        else {
            $korting = "40%";
        }
    
    }
~~~

__Let op__: Zorg ervoor bij nesten dat je inspringt zoals hierboven, zodat je code leestbaar blijft. Vergeet ook geen commentaar te schrijven

## 7.7 Opdracht 70

Bestudeer, probeer zelf de code in bovenstaand voorbeeld 1.

Declareer en initialiseer de variabele $mop met de waarde: 
"Waarom gaan Belgen in Engeland nooit in een dubbeldekker boven zitten? Daar zit geen chauffeur."

Test met een if-else constructie de volgende beweringen:
1. De lengte van de mop is langer dan 100 karakters. (Tip: strlen()) 
2. Het woord beneden komt voor in de mop. (Tip: strpos())
3. De eerste 6 karakters van de mop is "Waarom"
4. De laatste 10 karakters is gelijk aan "chauffeur."
5. Er meer dan 1 keer het woord "in" wordt gebruikt.

### Visuele weergave 70

De mop:
__Waarom gaan Belgen in Engeland nooit in een dubbeldekker boven zitten? Daar zit geen chauffeur.__

- Heeft (g-/)een lengte van meer dan 100 tekens
- Het woord beneden komt wel/niet voor in de mop.
- De eerste 6 karakters van de mop is niet/wel waarom.
- De laatste 10 is wel/niet gelijk aan chauffeur.
- In de mop komt het woord in wel/niet meer dan 1 keer voor.

### Beoordelingscriteria 70
1. Geldige html code; content wordt alleen geprint in de body
2. Sla het bestand op opdracht70.php in de map Hoofdstuk7
3. Zowel de if code als de else code print de bevestiging/ontkenning van de bewering    

## 7.8 Opdracht 71

### Opdrachtomschrijving 71

Maak een php-script dat ervoor zorgt dat bij een gekozen verzekeringstype (wa, casco of allrisk via een get-parameter) welke schade(/-oorzaak) wel of niet wordt gedekt. Ga uit van de volgende afbeelding.

![opdracht71](https://github.com/ictacademiekw1c/opdrachten-repository/blob/master/php/images/opdracht71.png?raw=true)

### Beoordelingscriteria 71
1. Sla je script op opdracht71.php en upload het als rar in je portfolio
2. Je php-script toont een volledige en geldige html pagina
3. Je maakt gebruik van een get-parameter met als default waarde "allrisk"
4. Je toont alleen de schades die gedekt zijn voor het verzekeringstype
5. Je maakt gebruik van een if else statement.

## 7.9 Opdracht 72

### Opdrachtomschrijving 72

Maak een php-script dat ervoor zorgt dat uitgaande van 2 get-parameters:
1. Aantal personen op 1 pas
2. Bezoeknummer 1,2,3,4,5

Het juiste kortingspercentage wordt geprint. Ga uit van de standaardwaarde voor aantal personen 1, en voor bezoeknummer ook 1.
 
Ga uit van de volgende afbeelding.

![opdracht72](https://github.com/ictacademiekw1c/opdrachten-repository/blob/master/php/images/opdracht72.png?raw=true)

### Beoordelingscriteria 72
1. Sla je script op opdracht72.php en upload het als rar in je portfolio
2. Je php-script toont een volledige en geldige html pagina
3. Je maakt gebruik van 2 get-parameters
4. De namen van de variabelen zijn geldig en zinvol
5. Je hebt in een if-else statement de && (and) of || (or) operator gebruikt.
6. Je test je script op alle mogelijke combinaties van de get-parameters   
