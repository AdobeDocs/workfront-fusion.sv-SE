---
title: verktyg
description: Avsnittet  [!DNL Adobe Workfront Fusion Tools] innehåller flera användbara moduler som kan förbättra ditt scenario.
author: Becky
feature: Workfront Fusion
exl-id: d9425f5b-4f4a-42da-9aca-1c1783be5fa7
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2000'
ht-degree: 0%

---

# [!UICONTROL Tools]

Avsnittet [!DNL Adobe Workfront Fusion Tools] innehåller flera användbara moduler som kan förbättra ditt scenario.

[!UICONTROL Tools] moduler är tillgängliga i listan över program eller från [!UICONTROL Tools] ikonen ![Verktygsikonen](/help/workfront-fusion/references/apps-and-modules/assets/tools-icon-small.png) längst ned på skärmen.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens</td> 
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Workfront Fusion-licens krävs inte</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront package: Your organization must purchase Adobe Workfront Fusion.</li><li>Ultimate Workfront-paket: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## [!UICONTROL Tools] och deras fält

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Aggregatorer](#aggregators)
* [Transformers](#transformers)

### Utlösare

#### [!UICONTROL Basic trigger]

Med den här modulen kan du skapa en anpassad utlösare och definiera dess indatapaket.

Du kan använda den här modulen för kontakter eller andra listor som är schemalagda att skickas till en angiven e-postadress (till exempel [!UICONTROL Email] >[!UICONTROL Send an Email] eller [!DNL Gmail] >[!UICONTROL Send an Email] moduler), eller som en enkel påminnelse som utlöses när du vill.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bundle]</td> 
   <td> <p>Skapa anpassade paket genom att lägga till arrayobjekt. För varje objekt som du vill lägga till i paketet klickar du på <b>Lägg till objekt</b> och anger objektets namn och värde.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Get Multiple Variables]](#get-multiple-variables)
* [[!UICONTROL Get Variable]](#get-variable)
* [[!UICONTROL Increment function]](#increment-function)
* [[!UICONTROL Set Multiple Variables]](#set-multiple-variables)
* [[!UICONTROL Set Variable]](#set-variable)
* [[!UICONTROL Sleep]](#sleep)

#### [!UICONTROL Get Multiple Variables]

Den här modulen hämtar värden som tidigare har skapats av modulen [!UICONTROL Set Variable] eller [!UICONTROL Set Multiple Variables].

Den här modulen kan läsa variabler som har angetts var som helst i scenariot, även om variabeln har angetts i en annan väg än där modulen [!UICONTROL Get Multiple Variables] finns. Det enda kravet är att modulen [!UICONTROL Tools] > [!UICONTROL Set Variable] eller [!UICONTROL Tools] > [!UICONTROL Set Multiple Variable] körs före modulen [!UICONTROL Tools] > [!UICONTROL Get Multiple Variables]. Mer information om i vilken ordning moduler körs finns i [Lägg till en routermodul och konfigurera vägar](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Variables]</td>
        <td>För varje variabel som du vill att modulen ska hämta klickar du på <b>Lägg till objekt</b> och anger namnet på variabeln.</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

**Exempel:** Följande är möjliga användningar av modulerna [!UICONTROL Set]/[!UICONTROL Get (multiple) variable(s)]:

* Om du vill lagra ett beräknat värde för senare användning, även i en annan väg. Detta är användbart när värdet används i flera moduler och formeln för att beräkna värdet är alltför komplex.
* Felsöka en formel. Om en formel som används i en modul inte verkar ge rätt resultat kopierar du formeln och klistrar in den i en [!UICONTROL Set Variable]-modul som du infogar före den relevanta modulen. Koppla från modulerna efter modulen [!UICONTROL Set Variable] och kör scenariot. Verifiera utdata från modulen [!UICONTROL Set Variable], justera eller förenkla formeln, kör scenariot igen och fortsätt göra det tills problemet har lösts.

>[!ENDSHADEBOX]


#### [!UICONTROL Get Variable]

Den här modulen hämtar ett värde som tidigare har skapats av modulen [!UICONTROL Set Variable] eller [!UICONTROL Set Multiple Variables].

Den här modulen kan läsa variabler som har angetts var som helst i scenariot, även om variabeln har angetts i en annan väg än där modulen [!UICONTROL Get Variable] finns. Det enda kravet är att modulen [!UICONTROL Tools] > [!UICONTROL Set Variable] eller [!UICONTROL Tools] > [!UICONTROL Set Multiple Variables] körs före modulen [!UICONTROL Tools] > [!UICONTROL Get Variable]. Mer information om i vilken ordning moduler körs finns i [Lägg till en routermodul och konfigurera vägar](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable name]</td> 
   <td> <p>Mappa namnet på variabeln som du vill att modulen ska hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Increment function]

Den här modulen returnerar ett värde som ökas med 1 efter varje cykel eller varje scenario som körs.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reset a value]</td> 
   <td> <p>Välj när du vill att modulen ska återställa värdet. Det är när du vill att värdet ska börja om vid det första värdet.</p> 
    <ul> 
     <li>[!UICONTROL After one cycle]</li> 
     <li>[!UICONTROL After one scenario run]</li> 
     <li>[!UICONTROL Never]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:**

Den här modulen kan användas för att implementera en tilldelning av uppgifter, leads, e-postmeddelanden och så vidare till användare i en grupp. Algoritmen väljer tilldelningar från en grupp i någon rationell ordning, som vanligtvis går uppifrån och ned i en lista. När algoritmen når slutet av listan ger den sedan nästa tilldelning till användaren högst upp i listan och fortsätter att göra tilldelningar nedåt i listan.

Följande scenario skickar ett e-postmeddelande till den första mottagaren efter varje ojämnt numrerad körning av ett scenario och till den andra mottagaren efter varje jämn körning av ett scenario.

![Exempel på e-post](/help/workfront-fusion/references/apps-and-modules/assets/example-email.png)

Så här skapar du det här scenariot:

1. Ange att fältet **[!UICONTROL Reset a value]** för modulen ska vara Aldrig.
1. Ange flöde för udda värden. Ange filtret för den här vägen med den modulus-matematiska funktionen som är lika med `1`:

   ![Udda siffror](/help/workfront-fusion/references/apps-and-modules/assets/odd.png)

**Obs!**: Glöm inte att ändra operatorn [!UICONTROL Equal to] från standardoperatorn [!UICONTROL Text] till operatorn [!UICONTROL Numeric].

1. Ange vägen för jämna värden med den modulus-matematiska funktionen som är lika med `0`:

Ökningsfunktionen lägger till en varje gång scenariot körs. Filtren kontrollerar ökningen och agerar utifrån dess värde och ser till att e-postmeddelandena distribueras jämnt.

>[!ENDSHADEBOX]

#### [!UICONTROL Set Multiple Variables]

Den här modulen skapar variabler som kan mappas av andra moduler i flödet. Variabeln kan också mappas till modulerna [!UICONTROL Get Variable] eller [!UICONTROL Get Multiple Variables] för alla vägar i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variables]</td> 
   <td>För varje variabel som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger variabelns namn och värde.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>Ange hur länge du vill att variablerna ska förbli giltiga (behåll samma värde).</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>: Variabeln är giltig för en cykel. Detta är användbart när flera webbhooks tas emot i ett scenario, eftersom fler webbhooks skapar fler cykler. </li> 
     <li><strong>[!UICONTROL One execution]</strong>: Variabeln är giltig för körning av ett scenario. En körning kan innehålla en eller flera cykler.</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Set Variable]

Den här modulen skapar en variabel som kan mappas av andra moduler i flödet. Variabeln kan också mappas till modulerna [!UICONTROL Get Variable] eller [!UICONTROL Get Multiple Variables] för alla vägar i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variable name] </td> 
   <td>Ange variabelnamnet. Det här namnet visas när variabeln mappas i andra moduler. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>Ange hur länge du vill att variablerna ska förbli giltiga (behåll samma värde).</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>: Variabeln är giltig för en cykel. Användbart när flera webbhooks i en enda scenariokörning tas emot (fler webbhooks = fler cykler). </li> 
     <li><strong>[!UICONTROL One execution]</strong>: Variabeln är giltig för körning av ett scenario. En körning kan innehålla en eller flera cykler.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable value] </td> 
   <td>Ange eller mappa värdet för variabeln. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Sleep]

Med den här modulen kan du fördröja scenarioflödet i upp till 300 sekunder (5 minuter).

Den här funktionen kan vara användbar om du till exempel vill sänka belastningen på tjänstservern [!DNL target] eller imitera det mänskliga beteendet när du skickar SMS eller e-post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Delay]</p> </td> 
   <td> <p>Ange i hur många sekunder scenariot ska pausas.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!TIP]
>
>Om du vill pausa flödet under längre perioder rekommenderar vi att du delar upp ditt scenario i två scenarier:
>
>* Det första scenariot skulle innehålla delen före pausen.
>* Det andra scenariot skulle innehålla delen efter det.
>
>Det första scenariot skulle resultera i att all nödvändig information lagras i ett datalager tillsammans med den aktuella tidsstämpeln. Det andra scenariot skulle regelbundet kontrollera datalagret för poster med en tidsstämpel som är äldre än den avsedda fördröjningen, hämta posterna, slutföra bearbetningen av data och ta bort posterna från datalagret.
>
><!--For more information on data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]]().-->
>
>Mer information om specifika datalagermoduler finns i [[!UICONTROL Data store] moduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md).

### Aggregatorer

* [[!UICONTROL Numeric aggregator]](#numeric-aggregator)
* [[!UICONTROL Table aggregator]](#table-aggregator)
* [[!UICONTROL Text aggregator]](#text-aggregator)

#### [!UICONTROL Numeric aggregator]

I den här modulen kan du hämta numeriska värden, sedan använda någon av de valda funktionerna (SUM, AVG, COUNT, MAX, MIN) och returnera resultatet i ett paket.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Markera modulen som du vill samla in fält från.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Aggregate function]</p> </td> 
   <td> <p>Välj den funktion som du vill använda för att samla värdena.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Definiera ett uttryck som du vill gruppera aggregerade utdata med. Det här uttrycket kan innehålla ett eller flera mappade objekt. De aggregerade data delas sedan upp i grupper med hjälp av det här uttryckets värde. Varje grupp skickar som ett separat paket med en nyckel (det utvärderade uttrycket) och ett värde (det aggregerade värdet). Du kan använda nyckeln som ett filter i efterföljande moduler.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Aktivera det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Value]</p> </td> 
   <td> <p>Ange eller mappa värdet som du vill aggregera.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Table aggregator]

Den här modulen sammanfogar värden från de valda fälten i mottagna paket till ett enda paket med en angiven kolumn- och radavgränsare (som gör att du kan skapa en tabell).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Markera modulen som du vill samla in fält från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Aggregated fields]</td> 
   <td> <p> Markera de fält i modulen som är markerad ovan som innehåller värden som du vill sammanfoga i ett paket.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Column separator]</p> </td> 
   <td> <p>Välj eller ange den typ av avgränsare som ska separera fältvärdeskolumnerna i det resulterande paketet. Om du väljer [!UICONTROL Other] anger du tecknet som du vill använda för att avgränsa värden till avgränsningsfältet.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>Välj eller ange den typ av avgränsare som ska separera fältvärdesraderna i det resulterande paketet. Om du väljer [!UICONTROL Other] anger du tecknet som du vill använda för att avgränsa värden till avgränsningsfältet.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Definiera ett uttryck som du vill gruppera aggregerade utdata med. Det här uttrycket kan innehålla ett eller flera mappade objekt. De aggregerade data delas sedan upp i grupper med hjälp av det här uttryckets värde. Varje grupp skickar som ett separat paket med en nyckel (det utvärderade uttrycket) och ett värde (det aggregerade värdet). Du kan använda nyckeln som ett filter i efterföljande moduler.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Välj det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Text aggregator]

Den här modulen sammanfogar värden från de valda fälten i mottagna paket till ett enda paket.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>Markera modulen som du vill samla in fält från.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>Välj eller ange den typ av avgränsare som ska separera fältvärdesraderna i det resulterande paketet. Om du väljer [!UICONTROL Other] anger du tecknet som du vill använda för att avgränsa värden till avgränsningsfältet.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>Definiera ett uttryck som innehåller ett eller flera mappade objekt. De aggregerade data separeras under Grupper med samma uttrycksvärde. Varje grupp returnerar som ett separat paket som innehåller en nyckel med det utvärderade uttrycket och den aggregerade texten. På så sätt kan du använda Key (Nyckel) som ett filter i efterföljande moduler.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Välj det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text]</td> 
   <td> <p> Ange eller mappa den text som du vill att modulen ska sammanfoga.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:** Du kan använda textaggregatorn för att infoga fler värden (till exempel kundnamn eller anteckningar) i ett paket och skicka ett e-postmeddelande som innehåller alla värden i e-postmeddelandets brödtext eller e-postmeddelandets ämne.

>[!ENDSHADEBOX]

### Transformers

* [[!UICONTROL Compose a string]](#compose-a-string)
* [[!UICONTROL Convert the encoding of the text]](#convert-the-encoding-of-the-text)
* [[!UICONTROL Switch]](#switch)

#### [!UICONTROL Compose a string]

Konverterar alla värden till en strängdatatyp (text). Detta gör mappningen enklare vid mappning, till exempel binära data.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p>Ange eller mappa data som du vill konvertera till text.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Convert the encoding of the text]

Konverterar den angivna indatatexten (eller binära data) till den valda kodningen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input data]</p> </td> 
   <td> <p>Ange eller mappa innehållet som du vill konvertera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Input data codepage]</td> 
   <td> <p>Välj kodningstyp för indata. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Output data codepage]</p> </td> 
   <td> <p>Välj kodningstyp för måldata (utdata).</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Switch]

Kontrollerar om indatavärdet matchar den angivna listan med värden. Returnerar utdata baserat på resultatet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input]</p> </td> 
   <td> <p>Ange uttrycket som du vill utvärdera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use regular expressions to match]</td> 
   <td> <p>Aktivera det här alternativet om du vill använda reguljära uttryck. Modulen avgör fallen baserat på det reguljära uttrycket, i stället för en exakt matchning.</p> 
    <div> 
     <p>Ett reguljärt uttryck är en teckensekvens där varje tecken antingen är ett metatecken med en speciell innebörd eller ett reguljärt tecken med en litteral betydelse. Dessa tecken och metatecken identifierar ett mönster som kan användas för att söka efter text. Om du t.ex. vill söka efter namn kan du skapa ett reguljärt uttryck som söker efter ett mönster som består av två ord i följd som börjar med versaler. Reguljära uttryck är ett kraftfullt verktyg för att söka efter och ändra text.</p> 
     <p>En diskussion om reguljära uttryck ligger utanför den här artikelns räckvidd. Vi rekommenderar följande resurser:</p> 
     <ul> 
      <li>En fullständig lista över metatecken finns i <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions">Reguljära uttryck</a> i MDN-webbdokument.</li> 
      <li>Om du vill ha en genomgång om hur du skapar reguljära uttryck rekommenderar vi <a href="https://regexone.com/">RegexOne</a>.</li> 
      <li>Om du vill experimentera med reguljära uttryck rekommenderar vi webbplatsen <a href="https://regex101.com/">Reguljära uttryck 101</a>. Markera ECMAScript (JavaScript) FLAVOR i den vänstra panelen.</li> 
     </ul> 
    </div> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cases] </td> 
   <td> För varje fall som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger objektets mönster och utdata. <p>Om indata innehåller ett värde som har angetts för fältet [!UICONTROL Pattern], returneras värdet som har angetts för fältet [!UICONTROL Output].</p> <p>Om indata inte matchar något av de värden som du har angett i ett [!UICONTROL Pattern]-fält händer något av följande:</p> 
    <ul> 
     <li>Värdet från fältet [!UICONTROL Else] returneras</li> 
     <li>Om det inte finns något värde i fältet [!UICONTROL Else] returneras inga utdata.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Else]</p> </td> 
   <td> <p>Ange det värde som returneras när de villkor som angetts i fältet Ärenden inte uppfylls. </p> </td> 
  </tr> 
 </tbody> 
</table>
