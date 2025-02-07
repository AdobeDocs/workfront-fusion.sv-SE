---
title: CSV
description: Med Adobe Workfront Fusion CSV-modulerna kan du skapa CSV-filer och tolka CSV-text från ett mottaget textvärde eller en fil.
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 5971b2210eaac8f8a75fd7a4aac5a9f7954d27ef
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 0%

---

# CSV

Med modulerna [!DNL Adobe Workfront Fusion] [!UICONTROL CSV] kan du skapa CSV-filer och tolka CSV-text från ett mottaget textvärde eller en fil.

Eftersom det här är en transformator behöver dessa moduler ingen anslutning.

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

## [!UICONTROL Create CSV]

Med [!UICONTROL Create CSV]-aggregatorn kan du skapa en csv-text från mottagna textvärden.

Mer information om aggregerare finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Markera modulen som matar ut de fält som du vill använda för att skapa CSV-filen.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Aggregated Fields]</td>
        <td>Markera de fält som du vill samla i listan med tillgängliga fält.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Include headers in the first row]</td>
        <td>Välj det här alternativet om du vill ta med rubrikerna i resultatet.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Group by]</td>
        <td>Ange filtret för att gruppera resultaten. Ange till exempel ett datum.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Stop processing after an empty aggregation]</td>
        <td>Välj det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td>
    </tr>
</table>

## [!UICONTROL Create CSV (advanced)]

Med [!UICONTROL Create CSV (advanced)]-aggregatorn kan du skapa en CSV-text från mottagna textvärden. Den använder en datastruktur som definierar CSV-kolumnerna i den resulterande CSV-filen. När kolumnerna har definierats visas de som fält i CSV-modulen och kan mappas till en senare modul i scenariot.

Mer information om aggregerare finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
        <td>Markera modulen som matar ut de fält som du vill använda för att skapa CSV-filen.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>Välj datastrukturen för att samla fälten på det sätt du vill. När du har definierat datastrukturen kan du mappa objekten till motsvarande fält.</p> <p>Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">Datastrukturer</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include headers in the first row] </td> 
   <td>Välj det här alternativet om du vill ta med rubrikerna i resultatet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by] </td> 
   <td>Ange filtret för att gruppera resultaten. Ange till exempel ett datum. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation] </td> 
   <td>Välj det här alternativet om du vill stoppa scenariot när det inte finns några resultat. </td> 
  </tr> 
 </tbody> 
</table>


>[!BEGINSHADEBOX]

**Exempel**:

I det här exemplet visas hur du exporterar Google-kontakter till en CSV-fil med två kolumner som kallas &quot;Fullständigt namn&quot; och &quot;E-post&quot;. Utdatapaketet från modulen [!UICONTROL Google Contacts] > [!UICONTROL Get contacts from a group] har följande struktur. E-postadresserna lagras i <code>[!UICONTROL Emails[]]</code> objekt, som är en array med samlingar, där varje samling innehåller två objekt: <code>Label</code> och <code>e-post</code>.
![Omformar](/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png)

Den enkla [!DNL Create CSV]-modulen erbjuder en lista med kryssrutor som motsvarar ett pakets objekt på den översta nivån. Om du försöker välja <code>Fullständigt namn</code> och <code>e-postmeddelanden</code> [!UICONTROL Create CSV]-modulen skapar följande utdata, vilket kanske inte är vad du vill ha:

```
"emails","fullName"
"[object Object]","Shon Winer"
"[object Object]","Lizeth Fulmore"
"[object Object]","Hilario Gullatt"
"[object Object]","Abby Eisenbarth"
```

Eftersom objektet <code>har fullständigt namn</code> är av typen Text, som exporteras som förväntat. Objektet <code>e-postmeddelanden</code>, som är av en komplex typ Array med samlingar, exporteras som [object ] , vilket är hur samlingar och arrayer omformas till text som standard.

Mer information finns i [Objektdatatyper](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).


Exportera innehåll i <code>e-postmeddelandet </code>objekt i den första samlingen av <code>e-postmeddelanden[]</code> i stället måste du använda modulen [!UICONTROL Create CSV (advanced)]. Med den här modulen kan du definiera enskilda kolumner i CSV-filen och mappa objekt till dem, inklusive de kapslade kolumnerna.

1. Infoga modulen [!UICONTROL Create CSV (advanced)] i ett scenario.
1. Klicka på knappen <strong>[!UICONTROL Add]</strong> bredvid fältet [!UICONTROL Data structure] för att skapa en ny datastruktur.
1. Ange ett namn för datastrukturen och klicka på <strong>[!UICONTROL Add item]</strong> för att lägga till de enskilda kolumnerna. Om du vill exportera två kolumner: &quot;Fullständigt namn&quot; och &quot;E-post&quot; ser datastrukturen ut så här:

   ![Utdata från Google Contacts](/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png)

1. När du har definierat datastrukturen visas fält som motsvarar varje enskild kolumn i konfigurationen för modulen [!UICONTROL Create CSV (advanced)] så att du kan mappa objekten. Ta det första objektet från <code>[!UICONTROL Emails[]]</code> matris och mappa objektet <code>E-post </code>till fältet/kolumnen E-post:

   ![Skapa avancerad CSV-modul](/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png)

1. Kör scenariot. Eftersom objektet <code>skickar e-post[1]: E-post</code> mappad till kolumnen&quot;E-post&quot; är av enkel typ Text, den exporteras korrekt.

```
"Full Name","Email"
"Shon Winer","Shon@Winer.com"
"Lizeth Fulmore","Lizeth@Fulmore.com"
"Hilario Gullatt","Hilario@Gullatt.com"
"Abby Eisenbarth","Abby@Eisenbarth.com"
```

>[!ENDSHADEBOX]

## [!UICONTROL Parse CSV]

Med transformatorn [!UICONTROL Parse CSV] kan du tolka CSV-text från ett mottaget textvärde eller en fil.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of columns]</td> 
   <td>Ange antalet kolumner i CSV-filen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV contains headers]</td> 
   <td> <p>Välj det här alternativet om den första raden i CSV-texten innehåller rubriker.</p> <p>Obs! Modulen använder inte dessa rubriker för att etikettera kolumnerna i utdata. I stället ser det här fältet till att sidhuvudena inte inkluderas i utdata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL delimiterType]</td> 
   <td> <p>Välj avgränsare för CSV-filen. Avgränsaren är det texttecken som anger gränsen mellan separata värden eller fält.</p> 
    <ul> 
     <li>[!UICONTROL Comma]</li> 
     <li>[!UICONTROL Tab]</li> 
     <li> <p>[!UICONTROL Other]</p> <p>Om du väljer [!UICONTROL Other] anger du avgränsningstecknet som CSV-filen använder för att avgränsa värden. Du måste ange exakt ett tecken.<br></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve quotes inside unquoted field]</td> 
   <td>Aktivera det här alternativet om du vill bevara citattecken.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV]</td> 
   <td>Ange eller mappa den CSV-fil som du vill analysera.<p>Obs! <p>Om dina data kommer i binär form (vanligtvis från en fil) måste du använda funktionen "toString()" för att konvertera binära data till [!UICONTROL String]:</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png"></p></p></td> 
  </tr> 
 </tbody> 
</table>
