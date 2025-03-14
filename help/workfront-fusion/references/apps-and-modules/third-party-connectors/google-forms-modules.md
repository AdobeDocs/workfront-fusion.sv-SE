---
title: Google Forms moduler
description: Med  [!DNL Adobe Workfront Fusion Google Forms] -modulerna kan du övervaka, välja, lägga till, uppdatera eller ta bort svar på din Google Forms.
author: Becky
feature: Workfront Fusion
exl-id: dc017957-c0f8-4206-916f-21ccda346fb9
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1199'
ht-degree: 0%

---

# [!DNL Google Forms] moduler

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Google Forms] kan du övervaka, välja, lägga till, uppdatera eller ta bort svar på [!DNL Google Forms].

Om du vill använda [!DNL Google Docs] med [!DNL Adobe Workfront Fusion] måste du ha ett [!DNL Google]-konto. Om du inte har något [!DNL Google]-konto än kan du skapa ett på hjälpsidan för [!DNL Google]-kontot.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs</p>
   <p>eller</p>
   <p>Äldre: Workfront Fusion for Work Automation and Integration </p>
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

## Förutsättningar

Du måste ha ett [!DNL Google]-konto för att kunna använda [!DNL Google Forms]-moduler.

## Google Forms API-information

Google Forms Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## Skapa ett kalkylblad från formuläret

Om du vill arbeta med formulärsvaren måste du först skapa ett svarskalkylblad.

1. Öppna formuläret.
1. Gå till fliken **[!UICONTROL Responses]**.
1. Klicka på ikonen **[!UICONTROL Create Spreadsheet]** ![Kalkylblad](/help/workfront-fusion/references/apps-and-modules/assets/spreadsheet-icon.png).

1. Välj om du vill skapa ett nytt kalkylblad eller ett befintligt kalkylblad
1. Klicka på **[!UICONTROL Create]**.

## [!DNL Google Forms]-moduler och deras fält

När du konfigurerar [!DNL Google Forms] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Forms] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

#### [!UICONTROL Watch Responses]

Söker efter nya svar i formuläret.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>Markera det kalkylblad som innehåller svaren från formuläret som du vill bevaka för nya svar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Row with headers]</td> 
   <td>Ange tabellens rubrikrad. Standardraden är <code>A1:Z1</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>Ange hur du vill att värdena ska återges i utdata.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong> </p> <p>Värden beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> <code>$1. 23</code> .</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>Värden beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>1. 23</code> .</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>Värden beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> <code>=A1</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Date and time render option]</td> 
   <td>Välj hur du vill att datum, tidpunkter och längd ska visas i utdata. Det här fältet ignoreras om [!UICONTROL Value Render Option] är inställt på [!UICONTROL Formatted Value].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p> Ange det maximala antalet svar som [!DNL Workfront Fusion] kan arbeta med under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add a Response]](#add-a-response)
* [[!UICONTROL Delete a Response]](#delete-a-response)
* [[!UICONTROL Update a Response]](#update-a-response)

#### [!UICONTROL Add a Response]

Den här modulen lägger till ett nytt svar längst ned i formulärets kalkylblad.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>Markera det kalkylblad som innehåller tabellen där du vill lägga till ett svar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>Ange önskade värden för tabellkolumnerna. Kolumner är tillgängliga baserat på bladet.</p> <p>Använd följande värde för kolumnen [!UICONTROL Timestamp]:</p><pre>formatDate(now;DD/MM/YYYY HH:mm;UTC)</pre> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> De värden som användaren anger tolkas inte och lagras som de är. </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Värdena tolkas som om användaren skrev in dem i användargränssnittet. Nummer är tal, men strängar kan konverteras till tal, datum eller andra format enligt samma regler som används när text skrivs i en cell via [!DNL Google Sheets]-gränssnittet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Insert data option]</td> 
   <td> <p>Ange hur befintliga data ska ändras när nya data matas in. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Overwrite]</strong> </p> <p>De nya data skriver över befintliga data i de områden där de skrivs. Om du lägger till data i slutet av tabellen infogas nya rader eller kolumner så att data kan skrivas.</p> </li> 
     <li> <p><strong>[!UICONTROL Insert rows]</strong></p> <p>Rader infogas för nya data.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Response]

Den här modulen tar bort ett markerat svar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>Markera det kalkylblad som innehåller tabellen där du vill ta bort ett svar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>Ange eller mappa numret på den rad som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Response]

Den här modulen uppdaterar det valda svaret.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>Markera det kalkylblad som innehåller det ark där du vill uppdatera ett svar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>Ange eller mappa numret på den rad som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>Ange de nya värdena för de kolumner du vill använda. Kolumner är tillgängliga baserat på bladet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> De värden som användaren anger tolkas inte och lagras som de är. </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Värdena tolkas som om användaren skrev in dem i användargränssnittet. Nummer är tal, men strängar kan konverteras till tal, datum eller andra format enligt samma regler som används när text skrivs i en cell via [!DNL Google Sheets]-gränssnittet.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL Search Responses]](#search-responses)
* [[!UICONTROL Search Responses (Advanced])](#search-responses-advanced)

#### [!UICONTROL Search Responses]

Den här modulen returnerar svar som matchar de angivna villkoren.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
    <td>Anslutning</td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>Markera det formulär som du vill söka i.</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Sheet] </td>
   <td> <p>Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Column range]</td>
   <td> <p> Markera det kolumnintervall som du vill söka i.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Definiera det filter som du vill söka efter svar efter.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Sort Order] </td>
   <td> <p>Välj om returnerade svar ska sorteras i stigande eller fallande ordning.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Order By]</td>
   <td> <p> Markera den kolumn som du vill beställa returnerade svar från.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>Ange hur du vill att värdena ska återges i utdata.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong></p> <p>Värden beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> <code>$1. 23</code> .</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>Värden beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>1. 23</code> .</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>Värden beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1. 23</code> och <code>A2 </code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> <code>=A1</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Date and time render option]</td>
    <td>Välj hur du vill att datum, tidpunkter och längd ska visas i utdata. Det här fältet ignoreras om alternativet [!UICONTROL Value Render] är inställt på Formaterat värde. </td>
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Maximum number of returned responses]</td>
   <td> <p> Ange det maximala antalet svar som [!DNL Workfront Fusion] returnerar under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Responses (Advanced)]

Den här modulen utför en sökning med [[!DNL Google Charts Query Language]](https://developers.google.com/chart/interactive/docs/querylanguage). Modulen returnerar inget radnummer.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>Markera det kalkylblad som innehåller det blad du vill söka i.</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Sheet]</td>
   <td> <p> Markera bladet som innehåller formulärsvaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Definiera sökfrågan med <a href="https://developers.google.com/chart/interactive/docs/querylanguage">[!DNL Google Charts Query Language]</a>.</p> <p>Exempel: <code>select * where C = "John"</code> hämtar alla värden för raden där C-kolumnen är "John".</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Maximum number of returned rows]</td>
   <td> <p> Ange det maximala antalet svar som [!DNL Workfront Fusion] returnerar under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>
