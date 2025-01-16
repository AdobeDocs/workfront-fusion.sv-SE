---
title: CSV
description: Med Adobe Workfront Fusion CSV-modulerna kan du skapa CSV-filer och tolka CSV-text från ett mottaget textvärde eller en fil.
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---

# CSV

Med modulerna [!DNL Adobe Workfront Fusion] [!UICONTROL CSV] kan du skapa CSV-filer och tolka CSV-text från ett mottaget textvärde eller en fil.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet], [!UICONTROL [!DNL Workfront Fusion] för Automatisering av arbete]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## [!UICONTROL Create CSV]

Med [!UICONTROL Create CSV]-aggregatorn kan du skapa en csv-text från mottagna textvärden.

Mer information om aggregerare finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Markera modulen som du använder för att sammanställa de fält du behöver.</td>
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

Mer information om aggregerare finns i [Aggregatormodulen i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/modules/aggregator-module.md).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td>Välj den programmodul som du använder för att samla in de fält som du behöver.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data Structure]</td> 
   <td> <p>Välj datastrukturen för att samla fälten på det sätt du vill. När du har definierat datastrukturen kan du mappa objekten till motsvarande fält.</p> <p>Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">Datastrukturer i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
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


<p>Låt oss anta att du vill exportera dina Google-kontakter till en CSV-fil med två kolumner, "Fullständigt namn" och "E-post". Utdatapaketet från modulen [!UICONTROL Google Contacts] &gt;[!UICONTROL Get contacts from a group] har följande struktur. E-postadresserna lagras inuti <code>[!UICONTROL Emails[]]</code>-objektet, som är en array med samlingar, där varje samling innehåller två objekt: <code>Label</code> och <code>Email</code>.</p>
<p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png" style="width: 350;height: 546;"> </p>
<p>Om du använder den enkla [!DNL Create CSV]-modulen visas en lista med kryssrutor som motsvarar ett pakets objekt på den översta nivån. Om du försöker kryssa för <code>Full name</code> och <code>Emails</code> objekt skapar modulen [!UICONTROL Create CSV] följande utdata, vilket förmodligen inte är vad du vill ha:</p>
<p>"emails","fullName"</p>
<p>"[object Object]","Shon Winer"</p>
<p>"[object Object]","Lizeth Fulmore"</p>
<p>"[object Object]","Hilario Gullatt"</p>
<p>"[object Object]","Abby Eisenbarth"</p>
<p>Eftersom objektet <code>Full Name</code> är av enkel typ Text exporteras det bara fint. Men objektet <code>Emails</code>, som är av en komplex typ Array med samlingar, exporteras som [object Object], vilket är hur samlingar och arrayer omformas till text som standard. Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Objektdatatyper i Adobe Workfront Fusion</a>.</p>
<p>Om du i stället vill exportera innehåll för <code>Email </code>-objektet i den första samlingen av <code>Emails[]</code>-arrayen måste du använda [!UICONTROL Create CSV (advanced)]-modulen. Med modulen kan du definiera enskilda kolumner i CSV-filen och mappa objekt till dem, inklusive de kapslade.</p>
<ol>
<li value="1">Infoga modulen [!UICONTROL Create CSV (advanced)] i ett scenario och öppna dess konfiguration.</li>
<li value="2">Klicka på knappen <strong>[!UICONTROL Add]</strong> bredvid fältet [!UICONTROL Data structure] för att skapa en ny datastruktur.</li>
<li value="3"> <p>Skriv ett namn för datastrukturen och klicka på knappen <strong>[!UICONTROL Add item]</strong> för att lägga till de enskilda kolumnerna. Om du vill exportera två kolumner: "Fullständigt namn" och "E-post" ser datastrukturen ut så här:</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png" style="width: 350;height: 524;"> </p> </li>
<li value="4"> <p>När du har definierat datastrukturen ska fält som motsvarar varje enskild kolumn visas i konfigurationen för modulen [!UICONTROL Create CSV (advanced)] så att du kan mappa objekten. Ta det första objektet från arrayen <code>[!UICONTROL Emails[]]</code> och mappa objektet <code>Email </code> till fältet/kolumnen E-post:</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png" style="width: 350;height: 308;"> </p> </li>
<li value="5"> <p>Kör scenariot. Eftersom objektet <code>Emails[1]: Email</code> som är mappat till kolumnen"E-post" är av enkel typ, exporteras det korrekt nu:</p> <p>"Fullständigt namn","E-post"</p> <p>"Shon Winer","Shon@Winer.com"</p> <p>"Lizeth Fulmore","Lizeth@Fulmore.com"</p> <p>"Hilario Gullatt","Hilario@Gullatt.com"</p> <p>"Abby Eisenbarth","Abby@Eisenbarth.com"</p> </li>
</ol>
</div>

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
   <td>Ange eller mappa den CSV-fil som du vill analysera.<p>Obs! <p>Om dina data kommer i binär form (vanligtvis från en fil) måste du använda funktionen "toString()" för att konvertera binära data till [!UICONTROL String]:</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png" style="width: 350;height: 123;"></p></p></td> 
  </tr> 
 </tbody> 
</table>
