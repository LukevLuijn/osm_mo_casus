
# Software Requirements Specification

| **Vak**       | OSM - Modeling                                                    |
| :-----------: | :---------------------------------------------------------------: |
| **Opdracht**  | Toets - Casus                                                     |
| **Docent**    | Bram Knippenberg                                                  |
| **Auteurs**   | Elviana Cornelissen <br> Luke van Luijn                           |
| **E-Mail**    | EH.cornelissen1@student.han.nl <br> LWH.vanluijn@student.han.nl   |
| **Datum**     | 19-03-2021                                                        |
| **Versie**    | 0.1                                                               |

# Inhoudsopgaven
> TODO https://ecotrust-canada.github.io/markdown-toc/


## Introductie

### Algemene beschrijving

<details>
    <summary> Beschrijving </summary>

> Provide a short description of the software being specified and its purpose, including relevant benefits, objectives, and goals. If a separate description of the product scope is available (e.g. in the PvA), refer to it rather than duplicating its contents here.
</details>

Deze software is bedoeld zodat klanten gebruik kunnen maken van de RedCars deelauto service.
Gebruikers kunnen een deelauto reserveren via een website, waarmee zij auto's kunnen lenen voor een bepaalde tijd.
Zonder daarvoor naar het autoverhuurbedrijf RentIt te gaan.

### Gebruikers, klassen en karakteristieken

<details>
    <summary> Beschrijving </summary>    

> Identify the various user classes (actors) that you anticipate will use this product. User classes may be differentiated based on the  subset of product functions used. Describe the pertinent characteristics of each user class. Certain requirements may pertain only to certain user classes.

</details>

Er zijn meerdere actoren die gebruik maken van dit systeem. Hieronder staan de verschillende actoren beschreven.

1. De klant, de klant maakt gebruik van het systeem door middel van registreren en het huren van auto's. 
   Er kan niet vanuit worden gegaan dat de klant voldoende kennis heeft van het systeem, 
   of dat de klant zich zal houden aan alle opgestelde regels van RedCars.

2. De medewerker, de medewerker kan gebruik maken van dezelfde functionaliteiten als een klant. 
   Een medewerker heeft verder nog de mogelijkheid tot het beheer van de beide de klantgegevens en de auto gegevens. 
   Er kan vanuit worden gegaan dat een medewerker voldoende techische kennis heeft van het systeem voor het beheren van de verschillende functionaliteiten.

### Ontwikkelomgeving

<details>
    <summary> Beschrijving </summary>

> Describe the environment in which the software will operate, including the hardware platform, operating system and versions, and any other software component.
</details>

> **TODO dit nog even navragen/bespreken met Bram.**

De applicatie kan onderverdeeld worden in vier onderdelen, de verschillende auto's, de parkeerpalen, de gebruikersinterface en het onderliggende systeem.

- De onderdelen verwerkt in de verschillende auto's zal draaien op een **|| microcontroller ||**.
- De onderdelen verwerkt in de parkeerpalen zal draaien op een  **|| microcontroller ||**.
- De gebruikersinterface zal worden weergegeven aan de klant door middel van een web-browser.
- Het onderliggende systeem zal ontwikkeld worden voor windows 10 en Ubuntu Focal Fossa (20.04).

### Ontwerp- en implementatie beperkingen

<details>
    <summary> Beschrijving </summary>    

> Describe any items or issues that will limit the options available to the developers. These might include: hardware (e.g. specific mobile platforms), specific technologies, tools, and databases to be used; interfaces to other applications; programming language required; or communications protocols
</details>

De programeertaal C++ is nodig voor dit project. Er zal gebruik gemaakt worden van UML om alle ontwerpen te visualiseren.
Er moet een database aanwezig zijn waarin klantinformatie en autoinformatie in word opgeslagen. Daarbij kan de software alleen kosten berekenen
en zal hierbij gebruik maken van externe bedrijven/services om de betaling te voltooien.

### Product functionaliteiten

<details>
    <summary> Beschrijving </summary>    

> Summarize the major functions the product must perform or must let the user perform. Details will be provided in Section 3, so only a high level summary is needed here. In most cases, this section will primarily contain a use case diagram and brief use case descriptions
</details>

![use case diagram RedCars](https://github.com/LukevLuijn/osm_mo_casus/blob/main/diagrams/export/use_case/use_case_diagram.svg?raw=true "Usecase Diagram")
![<<CRUD>>](https://github.com/LukevLuijn/osm_mo_casus/blob/main/diagrams/export/use_case/use_case_crud.svg?raw=true "<<CRUD>>")

#### Use case beschrijvingen

|index|Naam|Beschrijving|
|-----|----|------------|
|**UC_01**|Account Registeren      |Een gebruiker kan een account registeren. Het registeren van een acount kan door middel van het invoeren van de naam, adres en woonplaats van de klant. Vervolgens moet de klant zijn of haar email adres en bankrekeningnummer invoeren. Tot slot moet de klant de voorwaardes acepteren waaronder het toestemming verlenen tot het automatisch afschrijven van de gemaakte kosten.|
|**UC_02**|Opsturen Gebruikerspas  |Wanneer een gebruiker de registratie heeft voltooid zal er een gebruikerspas naar het opgegeven adres worden gestuurd, deze pas is gelinkt aan de account van de desbetreffende gebruiker.|
|**UC_03**|Auto Reserveren         |Een RedCars member kan een auto reserveren. Het reserveren van een auto kan via het weportaal. De member zal moeten aangeven welke van de beschikbare auto's hij of zij zou willen reserveren. Vervolgens zal de start en eind datum aangegeven moeten worden. En tot slot moet de member een abonement kiezen (UC_0X : abonnement aflsluiten)|
|**UC_04**|Abonnement Afsluiten    |Een RedCars member kan een abonnement afsluiten voor het reserveren van een auto. Er zijn vijf verschillende abonnementen: <br> 1. **Per uur**, met deze keuze zullen de kosten per uur berekend worden. <br> 2. **Per dag**, met deze keuze zullen de kosten per dag berekend worden.<br> 3. **Per weekend**, met deze keuzen kun je een auto huren voor een weekend.<br>4. **Per week**, met deze keuze zullen de kosten per week brekend worden.<br>5. **KM Vrij**, Met deze keuzen wordt er een intieel bedrag betaald en kan de gebruiker de auto onbeperkt gebruiken.|
|**UC_05**|Beheren Klant Gegevens  |Een RedCars medewerker kan de gegevens van de klanten beheren, dit houdt in dat de medewerker klanten kan aanmaken en verwijderen. En ook de gegevens van de klant kan bekijken en verwijderen.|
|**UC_06**|Inactief stellen klant  |Een RedCars medewerker kan de geregistreerde account van een klant op inactief stellen, dit is bijvoorbeeld een gevolg van achterstallige betalingen.|
|**UC_07**|Beheren Auto Gegevens   |Een RedCars medewerker kan de gegevens van de auto's beheren. Het beheren van de autogegevens houdt in dat de data per auto bekeken, veranderd en verwijderd kan worden. Tevens kan een medewerker nieuwe auto's aanmaken. |
|**UC_08**|Auto Inchecken          |Een RedCars member kan met zijn of haar gebruikerspas een auto Inchecken als deze gereserveerd is door de account van de gebruikerspas.|
|**UC_09**|Auto Openen             |Een RedCars member kan met zijn of haar gebruikerspas een auto openen als deze auto ingechecked is door de account van de gebruikerspas.|
|**UC_10**|Auto Sluiten            |Een RedCars member kan met zijn of haar gebruikerspas een auto afsluiten als deze auto ingechecked is door de account van de gebruikerspas.|
|**UC_11**|Auto Starten            |Een RedCars member kan met zijn of haar gebruikerspas een auto starten als deze auto ingechecked is door de account van de gebruikerspas.|
|**UC_12**|Auto Uitchecken         |Een RedCars member kan met zijn of haar gebruikerspas een auto als deze auto ingechecked is door de account van de gebruikerspas.|
|**UC_13**|Afschrijven Kosten      |Het systeem zal wanneer er een auto uitgechecked is de kosten berekenen van het gebruik en deze kosten vervolgens afschrijven van het aan de gebruikerspas gekoppelde bankrekeningnummer.|
|**UC_14**|Afschrijven Boete       |Het systeem zal wanneer er een auto uitgechecked is de boetekosten berekenen van het gebruik en deze kosten vervolgens afschrijvenvan het aan de gebruikerspas gekoppelde bankrekeningnummer.|

## Domein model

<details>
    <summary> Beschrijving </summary>    

> Provide a diagram showing important real-situation conceptual classes in the application domain. Do NOT include software classes. Describe each of the conceptual classes in a glossary.
</details>

## Use-case beschrijvingen
<details>
    <summary> Beschrijving </summary>    

> In this section, each use-case is described in detail, optionally accompanied by a system sequence diagram (SSD) and operation contracts. Make sure that the use case descriptions are consistent with the domain model and the use case diagram from Section 1.5
</details>

<details>
    <summary> use case template </summary>    

### Use case x
> Don’t really say “Use case 1.” State the use-case name instead.
#### Fully-dressed use case beschrijving
> Provide a fully-dressed use-case description in the format you know from the OOAD course
#### System Sequence Diagram (optioneel)
> In case the use-case entails complex scenarios, you may decide to create a system sequence diagram showing events generated by external actors, the order of events and inter-system events. All systems are treated as a black box
#### Operation Contracts (optioneel)
> If the use case contains complex manipulations of domain objects, you may decide to specify operation contracts for all system operations included in the use case/ SSD.
</details>

## Andere functionele requirements
<details>
    <summary> Beschrijving </summary>    

> Use this section to describe functional requirements that cannot be expressed in the shape of use cases, for instance because they do not concern goal-oriented interactions of an actor with the system.

|Code|Beschrijving|
|----|------------|
|FR_1| een beschrijving|

</details>

## Niet-functionele requirements
<details>
    <summary> Beschrijving </summary>    

> Describe non-functional requirements in this section. Please refer to existing software quality models like ISO_IEC_IEEE_25010 or FURPS+.

### Usability
|Code|Beschrijving|
|----|------------|
|NFR_1| een beschrijving|

### Reliability
|Code|Beschrijving|
|----|------------|
|NFR_2| een beschrijving|

etc..

</details>


> TODO iets over furps en niet func reqs
>
> Reliability niet gebruikt.
>
> Performance niet gebruikt.


### Usability

|Index     |Beschrijving|
|----------|------------|
|**NFR_01**|De klant moet kunnen inzien waar de parkeerlocatie is van de auto's per stad.|
|**NFR_02**|De klant moet kunnen inzien of een bepaalde auto beschikbaar is voor verhuur.|
|**NFR_03**|De auto moet lichtsignalen vertonen tot dat er uitgeschekt is door de gebruiker.|
|**NFR_04**|De paal moet lichtsignalen vertonen tot dat er uitgeschekt is door de gebruiker.|
|**NFR_05**|Als de klant een betalings achterstand heeft mag hij/zij geen auto reserveren.|
|**NFR_06**|Als de klant een betalings achterstand heeft mag hij/zij geen auto inchecken.|
|**NFR_07**|Een klant mag niet op meerdere locaties tegelijkertijd ingechecked zijn.|

### Performance

|Index     |Beschrijving|
|----------|------------|
|**NFR_08**|Het reserverings systeem moet een X aantal bezoekers tegelijk aankunnen zonder preformance verlies.|

### Supportablity

|Index     |Beschrijving|
|----------|------------|
|**NFR_08**|De abonnementen moeten makkelijk uitbreidbaar zijn. << verder uitschrijven.|
|**NFR_09**|De auto types moeten makkelijk uitbreidbaar zijn. << verder uitschrijven.|




