---
title: JSON-moduler
description: Adobe Workfront Fusion JSON-appen innehåller moduler som bearbetar data i JSON-format så att Adobe Workfront Fusion kan arbeta vidare med datainnehållet eller skapa nytt JSON-innehåll.
author: Becky
feature: Workfront Fusion
exl-id: f8b281c5-bb63-4412-98c5-d82f45f8eafc
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 0%

---

# [!UICONTROL JSON] moduler

Appen Adobe Workfront Fusion [!UICONTROL JSON] innehåller moduler för att bearbeta data i JSON-format så att Adobe Workfront Fusion kan arbeta vidare med datainnehållet eller skapa nytt JSON-innehåll.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla Adobe Workfront Workflow-paket och alla Adobe Workfront Automation and Integration-paket</p><p>Workfront Ultimate</p><p>Workfront Prime- och Select-paket med ytterligare köp av Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licenser</td> 
   <td> <p>Standard</p><p>Arbeta eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++



## Att tänka på vid tolkning av JSON

* [Datastruktur](#data-structure)
* [Samling kontra matris](#collection-vs-array)

### Datastruktur

Datastrukturen beskriver hur JSON-data ordnas och möjliggör mappning av enskilda JSON-objekt till andra moduler i ditt scenario. Om du inte anger datastrukturen kan du köra modulen manuellt, och Workfront Fusion bygger strukturen från den tillhandahållna JSON:

1. Lägg till modulen [!UICONTROL Parse JSON] i ett scenario.
1. I fältet **[!UICONTROL JSON String]** anger du den JSON som du vill bygga en datastruktur från.
1. Anslut inte andra moduler till modulen [!UICONTROL Parse JSON] än. Eftersom Workfront Fusion ännu inte känner till JSON-datastrukturen är det ännu inte möjligt att mappa data från modulen [!UICONTROL Parse JSON] till andra moduler i ditt scenario.
1. Kör scenariot manuellt. Detta gör att modulen [!UICONTROL Parse JSON] kan identifiera JSON-strukturen från den JSON som du har angett.
1. Nu kan du ansluta följande moduler. Objekten från JSON-modulen Parse är nu tillgängliga för mappning.

Mer information finns i [Datastrukturer i [!UICONTROL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

### Samling kontra matris

Om JSON-strängfältet innehåller en samling `{ ... }` är utdata ett enda paket som innehåller objekten i samlingen.

>[!BEGINSHADEBOX]

**Exempel:**

```
{
    "name" : "Peter",

    "ID" : 1>}
```


![JSON-samling](/help/workfront-fusion/references/apps-and-modules/assets/json-collection.png)

>[!ENDSHADEBOX]

Om JSON-strängfältet innehåller arrayen `[ ... ]` är utdata en serie paket. varje paket innehåller ett element i arrayen.

>[!BEGINSHADEBOX]

**Exempel:**

```
[
  {
    "name" : "Peter",
    "ID" : 1
  },

  {
    "name" : "Mike",
    "ID" : 2
  }
]
```

![JSON-matris](/help/workfront-fusion/references/apps-and-modules/assets/json-array.png)

>[!ENDSHADEBOX]

## [!UICONTROL JSON]-moduler och deras fält

När du konfigurerar [!DNL JSON]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare JSON-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Konvertera JSON till XML](#convert-json-to-xml)
* [Tolka JSON](#parse-json)
* [Skapa JSON](#create-json)
* [Omforma JSON](#transform-json)

### Aggregatorer

#### [!UICONTROL Aggregate to JSON]

Den här aggregeringsmodulen aggregerar utdata från en tidigare modul till JSON.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module] </td> 
   <td> <p>Markera modulen som matar ut data som du vill aggregera till JSON.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>Välj den datastruktur som du vill använda för att skapa JSON. Datastrukturen avgör vilka andra fält som är tillgängliga i den här modulen. Mer information finns i <a href="#data-structure" class="MCXref xref">Datastruktur</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Indentation]</td> 
   <td> <p> Ange om du vill dra in JSON med hjälp av tabbar, två blanksteg eller fyra blanksteg.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td>Definiera ett uttryck som du vill gruppera aggregerade utdata med. Det här uttrycket kan innehålla ett eller flera mappade objekt. De aggregerade data delas sedan upp i grupper med hjälp av det här uttryckets värde. Varje grupp skickar som ett separat paket med en nyckel (det utvärderade uttrycket) och ett värde (den sammanställda texten). Du kan använda nyckeln som ett filter i efterföljande moduler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Aktivera det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td> 
  </tr> 
 </tbody> 
</table>

### Transformers

* [Konvertera JSON till XML](#convert-json-to-xml)
* [Skapa JSON](#create-json)
* [Tolka JSON](#parse-json)
* [Omforma JSON](#transform-json)

#### [!UICONTROL Convert JSON to XML]

Den här åtgärdsmodulen konverterar en JSON-sträng till XML.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>Ange eller mappa den JSON som du vill konvertera till XML.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create JSON]

Den här åtgärdsmodulen skapar JSON från en datastruktur.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Datastruktur</td> 
   <td> <p>Välj den datastruktur som du vill använda för att skapa JSON. Mer information finns i <a href="#data-structure" class="MCXref xref">Datastruktur</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Indrag</td> 
   <td> <p>Välj det indrag du vill använda för detta JSON.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Parse JSON]

Den här åtgärdsmodulen tolkar en JSON-sträng i en datastruktur, som gör att du kan komma åt data i JSON-strängen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>Välj den datastruktur som du vill använda för att skapa JSON. Mer information finns i <a href="#data-structure" class="MCXref xref">Datastruktur</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>Ange eller mappa den JSON som du vill analysera.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Transform JSON]

Den här åtgärdsmodulen omvandlar ett objekt till en json-sträng.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Indrag</td> 
   <td> <p>Välj det indrag du vill använda för detta JSON.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object]</td> 
   <td> <p>Ange eller mappa objektet som du vill omforma till JSON.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Omvandla dataposter till JSON

>[!BEGINSHADEBOX]

**Exempel:** I följande exempel visas hur du omformar dataposter från [!DNL Google Sheets] till JSON-format:

1. Placera modulen [!DNL Google Sheets] > [!UICONTROL Select rows] i ditt scenario för att hämta data. Konfigurera modulen för att hämta rader från ditt [!DNL Google]-kalkylblad. Ställ in &#x200B;**[!UICONTROL Maximum number of returned rows]** på ett litet tal, men större än ett för testningsändamål (exempel, tre). Kör modulen [!DNL Google Sheets] genom att högerklicka på den och välja **[!UICONTROL Run this module only]**. Kontrollera modulens utdata.

1. Anslut modulen [!UICONTROL Array Aggregator] efter modulen [!DNL Google Sheets]. Välj modulen [!DNL Google Sheets] i fältet **[!UICONTROL Source node]** i modulens konfiguration. Låt de andra fälten vara som de är för tillfället.

1. Anslut [!UICONTROL JSON] > [!UICONTROL Create JSON] efter modulen [!UICONTROL Array Aggregator]. Modulens konfiguration kräver en datastruktur som beskriver JSON-formatet. Klicka på **[!UICONTROL Add]** för att öppna datastrukturinställningarna. Det enklaste sättet att skapa den här datastrukturen är att generera den automatiskt från ett JSON-exempel. Klicka på **[!UICONTROL Generator]** och klistra in JSON-exemplet i fältet **[!UICONTROL Sample data]**:

   **Exempel:**

   ```
   {
   "books": [
   {
   "id": "ID",
   "title": "Title",
   "author": "Author"
   }
   ]
   }
   ```

1. Klicka på **[!UICONTROL Save]**. Fältet [!UICONTROL Specification] i datastrukturen innehåller nu den genererade strukturen.
1. Ändra namnet på datastrukturen till något mer specifikt och klicka på **[!UICONTROL Save]**. Ett fält som motsvarar rotarrayattributet visas som ett mappningsbart fält i JSON-modulens inställningar.

1. Klicka på knappen **[!UICONTROL Map]** bredvid fältet och mappa `Array[]`-objektet från Array-aggregatorns utdata till det.

1. Klicka på **[!UICONTROL OK]** för att stänga konfigurationen för modulen [!UICONTROL JSON].

1. Öppna konfigurationen för modulen [!UICONTROL Array Aggregator]. Ändra **[!UICONTROL Target structure]** från [!UICONTROL Custom] till fältet i modulen [!UICONTROL JSON] som motsvarar rotmatrisattributet. Mappa objekt från modulen [!DNL Google Sheets] till rätt fält.

1. Klicka på **[!UICONTROL OK]** för att stänga konfigurationen för modulen [!UICONTROL Array Aggregator].

1. Kör scenariot.

   Modulen [!UICONTROL JSON] matar ut rätt JSON-format.

1. Öppna inställningarna för modulen [!DNL Google Sheets] och öka [!UICONTROL Maximum number of returned rows] så att det blir större än antalet rader i kalkylbladet för att bearbeta alla data.

>[!ENDSHADEBOX]

## Felsökning

### Det går inte att mappa data från modulen [!UICONTROL Parse JSON]

Kontrollera att JSON-innehållet är korrekt mappat till modulen [!UICONTROL Parse JSON] och att datastrukturen är korrekt definierad. Mer information finns i [Omforma dataposter till JSON](#transforming-data-records-to-json) i den här artikeln.

### Modulen misslyckas när villkorssatser används i JSON

När du använder villkorssatser som `if` i JSON placerar du citattecknen utanför villkorssatsen.

>[!BEGINSHADEBOX]

**Exempel:**

![Citattecken i JSON](/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png)

>[!ENDSHADEBOX]
