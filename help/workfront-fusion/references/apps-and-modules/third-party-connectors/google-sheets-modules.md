---
title: Google bladmoduler
description: För att kunna använda  [!DNL Google Sheets] med [!DNL Adobe Workfront Fusion],you need the [!UICONTROL Workfront Fusion Google Sheets] tillägget (valfritt, men krävs för direktutlösare).
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 80965570-2937-4ac8-97c0-54f7a813ec50
source-git-commit: 994dffd83d5b7d8b72396f147df352dfb74d6219
workflow-type: tm+mt
source-wordcount: '3464'
ht-degree: 0%

---

# [!DNL Google Sheets] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Google Sheets] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i [Skapa en anslutning till  [!DNL Adobe Workfront Fusion] - Grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Du måste ha ett [!UICONTROL Google]-konto för att kunna använda [!UICONTROL Google Sheets]-moduler.

## API-information för Google Sheets

Kopplingen Google Sheets använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://sheets.googleapis.com/v4</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.5.7</td> 
  </tr>
 </tbody> 
 </table>

## Google bladmoduler och deras fält

När du konfigurerar [!DNL Google Forms] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Sheets] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Utlösare

#### [!UICONTROL Watch Rows]

Hämtar värden från nya rader i kalkylbladet.

Modulen hämtar endast nya rader som inte har fyllts i tidigare. Utlösaren bearbetar inte en överskriven rad.

>[!IMPORTANT]
>
>Om kalkylbladet innehåller en tom rad bearbetas inga rader efter den tomma raden.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det kalkylblad som innehåller det blad du vill titta på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som du vill bevaka för en ny rad.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table contains headers]</td> 
   <td> <p> Ange om kalkylbladet innehåller en rubrikrad.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>Modulen hämtar inte rubrikraden som utdata. </p> <p>Variabelnamn i utdata anropas av rubrikerna.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>Modulen hämtar även den första tabellraden</p> <p>Variabelnamn i utdata kallas A, B, C, D och så vidare.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Row with headers] </td> 
   <td> <p>Ange intervallet för rubrikraden. Exempel: <code>A1:F1</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL First table row]</td> 
   <td> <p>Ange intervallet för tabellens första rad. Exempel: <code>A1:F1</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Value render option]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Värdena beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Värdena beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Värdena beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Date and time render option]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Datum-, tid-, datum- och tidsfält skrivs ut som dubbletter i serienummerformat, ifyllda med Lotus 1-2-3. Hela sifferdelen av värdet (vänster om decimaltalet) är antalet dagar sedan den 30 december 1899. Med bråkdelen (höger om decimaltecknet) räknas tiden som en bråkdel av dagen. Till exempel blir 1 januari 1900 kl. 12.5, 2 eftersom det är 2 dagar efter 30 december 1899 och 5,5 eftersom kl. 12.00 är en halv dag. 1 februari 1900 kl. 17.00 blir 33.625. Detta behandlar år 1900 korrekt som ett skottår.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Datum-, tid-, datum- och tidsfält genereras som strängar i det angivna talformatet (vilket beror på kalkylbladets språkområde).</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska arbeta med under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add a Row]](#add-a-row)
* [[!UICONTROL Add a Sheet]](#add-a-sheet)
* [[!UICONTROL Clear a Cell]](#clear-a-cell)
* [[!UICONTROL Clear a Row]](#clear-a-row)
* [[!UICONTROL Create a Spreadsheet]](#create-a-spreadsheet)
* [[!UICONTROL Delete a Row]](#delete-a-row)
* [[!UICONTROL Delete a Sheet]](#delete-a-sheet)
* [[!UICONTROL Get a Cell]](#get-a-cell)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Update a Cell]](#update-a-cell)
* [[!UICONTROL Update a Row]](#update-a-row)

#### [!UICONTROL Add a Row]

Den här modulen lägger till en rad i ett blad.

När du konfigurerar [!DNL Google Sheets] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Sheets] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mode]</td> 
   <td> <p>Välj om du vill markera kalkylbladet och bladet manuellt eller genom mappning.</p> <p>Obs! Manuell mappning är användbar, till exempel när ett nytt kalkylblad skapas i ett [!DNL Workfront Fusion]-scenario och du vill lägga till data i det nya kalkylbladet direkt i scenariot.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad du vill lägga till en rad i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Range]</td> 
   <td>Markera det kolumnintervall som du vill arbeta med.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Ange om kalkylbladet innehåller rubrikraden.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>Modulen hämtar inte rubrikraden som utdata. </p> <p>Variabelnamn i utdata anropas av rubrikerna.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>Modulen hämtar även den första tabellraden</p> <p>Variabelnamn i utdata kallas A, B, C, D och så vidare.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Values] </td> 
   <td> <p>Ange eller mappa cellerna på raden som du vill lägga till.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Värdena tolkas som om användaren skrev in dem i användargränssnittet. Nummer är tal, men strängar kan konverteras till tal, datum eller andra format enligt samma regler som används när text skrivs i en cell via [!DNL Google Sheets]-gränssnittet.</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> De värden som användaren anger tolkas inte och lagras som de angetts. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Insert data option]</td> 
   <td> <p>Ange hur befintliga data ska ändras när nya data matas in. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Insert rows]</strong></p> <p>Rader infogas för nya data.</p> </li> 
     <li> <p><strong>[!UICONTROL Overwrite]</strong> </p> <p>De nya data skriver över befintliga data i de områden där de skrivs. Om du lägger till data i slutet av tabellen infogas nya rader eller kolumner så att data kan skrivas.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add a Sheet]

Skapar en ny tabell i ett markerat kalkylblad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det Google-kalkylblad där du vill lägga till ett blad.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Properties]</td> 
   <td> 
    <ul> 
     <li> <p style="font-weight: bold;">[!UICONTROL Title]</p> <p>Ange namnet på det nya bladet.</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Index]</p> <p>Ange arkpositionen. Standardvärdet är 0 (vilket innebär att arket placeras överst).</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a Cell]

Tar bort ett värde från en angiven cell.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det Google-kalkylblad som innehåller det blad du vill ta bort cellen från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som du vill ta bort en cell från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Ange eller mappa ID:t för cellen som du vill ta bort. Exempel: <code>A5</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a Row]

Tar bort värden från en angiven rad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det [!DNL Google]-kalkylblad som innehåller det blad du vill ta bort en rad från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p> Markera det blad som du vill ta bort data från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row number]</td> 
   <td> <p>Ange numret på den rad som du vill ta bort data från. Exempel: <code> 23</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Spreadsheet]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title] </td> 
   <td> <p>Ange namnet på ett nytt kalkylblad.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Locale]</td> 
   <td> <p>Ange språkinställningen för kalkylbladet i något av följande format:</p> 
    <ul> 
     <li>en ISO 639-1-språkkod som <code>en</code></li> 
     <li>en ISO 639-2-språkkod som <code>haw</code>, om det inte finns någon 639-1-kod</li> 
     <li>en kombination av ISO-språkkoden och landskoden, t.ex. <code>en_US</code></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recalculation interval]</td> 
   <td> <p>Hur lång tid det tar att vänta innan flyktiga funktioner beräknas om:</p> <ul><li><p style="font-weight: bold;">[!UICONTROL On change]</p> <p>Volatila funktioner uppdateras vid varje förändring.</p></li><li> <p style="font-weight: bold;">[!UICONTROL On change and every minute]</p> <p>Volatila funktioner uppdateras vid varje förändring och varje minut.</p></li> <li><p style="font-weight: bold;">[!UICONTROL On change and hourly]</p> <p>Volatila funktioner uppdateras vid varje förändring och varje timme.</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Time zone]</td> 
   <td> <p> Välj tidszon för kalkylbladet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Number format]</td> 
   <td> <p>Markera standardformatet för alla celler i kalkylbladet.</p> <p><strong>[!UICONTROL Text]</strong>: Textformatering. Exempel: <code>1000. 12</code></p> <p><strong>[!UICONTROL Number]</strong>: Talformatering. Exempel: <code>1,000.12</code></p> <p><strong>[!UICONTROL Percent]</strong>: Procentformat. Exempel: <code>10. 12%</code></p> <p><strong>[!UICONTROL Currency]</strong>: Valutaformatering. Exempel: <code>$1,000.12</code></p> <p><strong>[!UICONTROL Date]</strong>: Datumformatering. Exempel: <code>9/26/2008</code></p> <p><strong>[!UICONTROL Time]</strong>: Tidsformatering. Exempel: <code>3:59:00 PM</code></p> <p><strong>[!UICONTROL Date time]</strong>: Formatering av datum och tid. Exempel: <code>9/26/08 15:59:00</code> </p> <p><strong>[!UICONTROL Scientific]</strong>: Formatering av vetenskapliga tal. Exempel: <code>1. 01E+03</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheets] </td> 
   <td> <p>För varje blad som du vill lägga till i kalkylbladet klickar du på <strong>[!UICONTROL Add item]</strong> och anger eller mappar en rubrik för kalkylbladet och kalkylbladets index. Ett index på 0 representerar det första bladet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Row]

Tar bort en angiven rad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det Google-kalkylblad som innehåller det blad du vill ta bort en rad från.</p> </td> 
  </tr> 
  <tr> 
   <td>Blad </td> 
   <td> <p>Markera det blad du vill ta bort en rad från.</p> </td> 
  </tr> 
  <tr> 
   <td>Radnummer</td> 
   <td> <p>Ange numret på den rad som du vill ta bort. Exempel: <code>23</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Sheet]

Tar bort ett visst blad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Cell]

Hämtar ett värde från en markerad cell.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera bladet som innehåller cellen som du vill hämta data från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Ange ID:t för cellen som du vill hämta data från. Exempel: <code>A6</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Värdena beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Värdena beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Värdena beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!DNL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!DNL Serial number]</p> <p>Datum-, tid-, datum- och tidsfält skrivs ut som dubbletter i serienummerformat, ifyllda med Lotus 1-2-3. Hela sifferdelen av värdet (vänster om decimaltalet) är antalet dagar sedan den 30 december 1899. Med bråkdelen (höger om decimaltecknet) räknas tiden som en bråkdel av dagen. Till exempel blir 1 januari 1900 kl. 12.5, 2 eftersom det är 2 dagar efter 30 december 1899 och 5,5 eftersom kl. 12.00 är en halv dag. 1 februari 1900 kl. 17.00 blir 33.625. Detta behandlar år 1900 korrekt som ett skottår.</p></li><li> <p style="font-weight: bold;">[!DNL Formatted string]</p> <p>Datum-, tid-, datum- och tidsfält genereras som strängar i det angivna talformatet (vilket beror på kalkylbladets språkområde).</p> </li><ul></td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [Fusion App]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td>Ange en relativ sökväg till <code>https://sheets.googleapis.com/v4/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] lägger till autentiseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!   <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Cell]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera bladet som du vill uppdatera en cell i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cell] </td> 
   <td> <p>Ange ID:t för cellen som du vill uppdatera. Exempel: <code>A5</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value]</td> 
   <td> <p>Ange cellens nya värde.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Värdena tolkas som om användaren skrev in dem i användargränssnittet. Nummer är tal, men strängar kan konverteras till tal, datum eller andra format enligt samma regler som används när text skrivs i en cell via [!DNL Google Sheets]-gränssnittet.</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> De värden som användaren anger tolkas inte och lagras som de angetts. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Row]

Med den här modulen kan du ändra cellinnehållet i en markerad rad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mode]</td> 
   <td> <p>Välj om du vill markera kalkylbladet och bladet manuellt eller genom mappning.</p> <p>Obs! Manuell mappning är användbar, till exempel när ett nytt kalkylblad skapas i [!UICONTROL Workfront Fusion]-scenariot och du vill lägga till data direkt i det nya kalkylbladet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som du vill uppdatera en rad i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row number]</td> 
   <td> <p> Ange numret på den rad som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Ange om kalkylbladet innehåller rubrikraden.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Yes]</strong> </p> <p>Modulen hämtar inte rubrikraden som utdata. </p> <p>Variabelnamn i utdata anropas av rubrikerna.</p> </li> 
     <li> <p><strong>[!UICONTROL No]</strong> </p> <p>Modulen hämtar även den första tabellraden</p> <p>Variabelnamn i utdata kallas A, B, C, D och så vidare.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Values] </td> 
   <td> <p>Ange eller mappa värdena till cellerna i raden som du vill ändra (uppdatera).</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>Värdena tolkas som om användaren skrev in dem i användargränssnittet. Nummer är tal, men strängar kan konverteras till tal, datum eller andra format enligt samma regler som används när text skrivs i en cell via [!DNL Google Sheets]-gränssnittet.</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> De värden som användaren anger tolkas inte och lagras som de angetts. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL Get Range Values]](#get-range-values)
* [[!UICONTROL List Sheets]](#list-sheets)
* [[!UICONTROL Search Rows]](#search-rows)
* [[!UICONTROL Search Rows (Advanced)]](#search-rows-advanced)

#### [!UICONTROL Get Range Values]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera den tabell som du vill hämta intervallinnehållet från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Range] </td> 
   <td> <p>Ange det intervall som du vill hämta. Exempel: <code>A1:D25</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p>Markera den här rutan om tabellen har en rubrikrad</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Row with headers]</td> 
   <td>Ange intervallet för tabellrubrikerna. Exempel <code>A1:F1</code>. Om du lämnar fältet tomt hanterar [!DNL Workfront Fusion] den första raden i det angivna intervallet som rubrik.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Värdena beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Värdena beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Värdena beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Datum-, tid-, datum- och tidsfält skrivs ut som dubbletter i serienummerformat, ifyllda med Lotus 1-2-3. Hela sifferdelen av värdet (vänster om decimaltalet) är antalet dagar sedan den 30 december 1899. Med bråkdelen (höger om decimaltecknet) räknas tiden som en bråkdel av dagen. Till exempel blir 1 januari 1900 kl. 12.5, 2 eftersom det är 2 dagar efter 30 december 1899 och 5,5 eftersom kl. 12.00 är en halv dag. 1 februari 1900 kl. 17.00 blir 33.625. Detta behandlar år 1900 korrekt som ett skottår.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Datum-, tid-, datum- och tidsfält genereras som strängar i det angivna talformatet (vilket beror på kalkylbladets språkområde).</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Sheets]

Den här modulen returnerar en lista med alla tabeller i ett kalkylblad.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det [!DNL Google]-kalkylblad som innehåller de blad som du vill visa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Rows]

Söker igenom rader med filteralternativen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [Fusion App]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera kalkylbladet [!DNL Google].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som du vill söka efter raderna i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Table contains headers]</td> 
   <td> <p> Ange om kalkylbladet innehåller rubrikraden. Om alternativet [!UICONTROL Yes] är markerat hämtar modulen inte rubrikraden eftersom utdata och variabelnamn i utdata sedan anropas av rubrikerna. Om alternativet [!UICONTROL No] är markerat hämtar modulen också den första tabellraden och variabelnamnen i utdata kallas sedan bara A, B, C, D och så vidare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column range]</td> 
   <td>Välj det kolumnintervall du vill arbeta med. Exempel: <code>A-F</code></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Filter]</td> 
   <td> <p>Ange det filter som du vill använda för att söka efter rader.</p> <!--<p>For more information about filters, see <a href="/help/workfront-fusion/create-scenarios/add-modules/" class="MCXref xref">Add a filter to a scenario in [!UICONTROL Adobe Workfront Fusion]</a>.</p>--> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort order]</td> 
   <td>Välj om du vill sortera stigande eller fallande.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td>Välj den kolumn som du vill sortera efter.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Formatted value]</p> <p>Värdena beräknas och formateras i svaret enligt cellens formatering. Formateringen baseras på kalkylbladets språkområde, inte på den begärande användarens språkområde. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"$1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Unformatted value]</p> <p>Värdena beräknas, men formateras inte i svaret. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta, returnerar <code>A2</code> talet <code>"1.23"</code>.</p></li><li> <p style="font-weight: bold;">[!UICONTROL Formula]</p> <p>Värdena beräknas inte. Svaret innehåller formlerna. Om <code>A1</code> till exempel är <code>1.23</code> och <code>A2</code> är <code>=A1</code> och formaterad som valuta returnerar <code>A2</code> <code>"=A1"</code>.</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL Serial number]</p> <p>Datum-, tid-, datum- och tidsfält skrivs ut som dubbletter i serienummerformat, ifyllda med Lotus 1-2-3. Hela sifferdelen av värdet (vänster om decimaltalet) är antalet dagar sedan den 30 december 1899. Med bråkdelen (höger om decimaltecknet) räknas tiden som en bråkdel av dagen. Till exempel blir 1 januari 1900 kl. 12.5, 2 eftersom det är 2 dagar efter 30 december 1899 och 5,5 eftersom kl. 12.00 är en halv dag. 1 februari 1900 kl. 17.00 blir 33.625. Detta behandlar år 1900 korrekt som ett skottår.</p> </li><li><p style="font-weight: bold;">[!UICONTROL Formatted string]</p> <p>Datum-, tid-, datum- och tidsfält genereras som strängar i det angivna talformatet (vilket beror på kalkylbladets språkområde).</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned rows]</td> 
   <td>Ange det maximala antalet rader som [!DNL Workfront Fusion] ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Rows (Advanced)]

Returnerar resultat som matchar de angivna villkoren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Sheets]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>Markera det Google-kalkylblad som innehåller det blad du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sheet] </td> 
   <td> <p>Markera det blad som innehåller de rader som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>Använd [!DNL Google Charts Query Language]. Exempel: <code>select * where B = "John"</code></p> <p>Mer information om [!DNL Google Charts Query Language] finns i <a href="https://developers.google.com/chart/interactive/docs/querylanguage">Språkreferens för frågor</a> i [!DNL Google]-dokumentationen.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Användningsbegränsningar

Om felet `429: RESOURCE_EXHAUSTED` inträffar har du överskridit API-hastighetsgränsen.

API:t [!DNL Google Sheets] har en gräns på 500 begäranden per 100 sekunder per projekt och 100 begäranden per 100 sekunder per användare. Begränsningar för läsning och skrivning spåras separat. Det finns ingen gräns för daglig användning.

Mer information finns på [developers.google.com/sheets/api/limits](https://developers.google.com/sheets/api/limits).

## Tips och tricks

* [Hämta tomma celler från ett [!DNL Google] blad](#get-empty-cells-from-a-google-sheet)
* [Lägga till en knapp i ett blad för att köra ett scenario](#add-a-button-in-a-sheet-to-run-a-scenario)

### Hämta tomma celler från en [!DNL Google Sheet]

Om du vill hämta tomma celler kan du använda modulen [!UICONTROL Search Rows (Advanced)]. Använd den här formeln för att hämta kolumner som är tomma.

```
select * where E is null
```

Här är &quot;E&quot; kolumnen och &quot;är null&quot; är villkoret. Du kan skapa en mer avancerad fråga med Google frågespråk. Mer information finns i [Google Query Lang](https://developers.google.com/chart/interactive/docs/querylanguage) i Google-dokumentationen.

### Lägga till en knapp i ett blad för att köra ett scenario

1. I [!DNL Workfront Fusion] infogar du modulen **[!UICONTROL Webhook]** > **[!UICONTROL Custom webhooks]** i scenariot och konfigurerar den. Instruktioner finns i [Webbhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

1. Kopiera webbhollens URL.
1. Kör scenariot.
1. I Google Sheets väljer du **[!UICONTROL Insert]** > **[!UICONTROL Drawing]**.. på huvudmenyraden.

1. Klicka på **[!UICONTROL Text box]** -ikonen ![Textrutan](/help/workfront-fusion/references/apps-and-modules/assets/text-box.png) i fönstret [!UICONTROL Drawing].
1. Utforma en knapp och klicka på knappen **[!UICONTROL Save and Close]** i det övre högra hörnet:
1. Knappen placeras i kalkylbladet. Klicka på de tre lodräta prickarna i knappens övre högra hörn:
1. Välj **[!UICONTROL Assign script..].** på menyn.
1. Ange namnet på skriptet (funktion), t.ex. `runScenario`, och klicka på **[!UICONTROL OK]**:
1. Välj **[!UICONTROL Tools]** > **[!UICONTROL Script editor]** på huvudmenyraden.

1. Infoga följande kod:

   * Namnet på funktionen måste motsvara det namn du angav i steg 9.
   * Ersätt URL:en med webboks-URL:en som du kopierade i steg 2.

     ```
     function runScenario() {
     UrlFetchApp.fetch("&lt;webhook you copied>");
     }
     ```

1. Tryck på **[!UICONTROL Ctrl+S]** för att spara skriptfilen, ange ett projektnamn och klicka på **[!UICONTROL OK]**.

1. Växla tillbaka till [!DNL Google Sheets] och klicka på den nya knappen.
1. Bevilja nödvändig behörighet till skriptet:
1. Kontrollera att scenariot har körts i [!DNL Workfront Fusion].

## Lagra datum i ett kalkylblad

Om du lagrar ett datumvärde i ett kalkylblad utan formatering, visas det i kalkylbladet som text i ISO 8601-format. [!DNL Google Sheets] formler eller funktioner som fungerar med datum som inte förstår den här texten (Exempel: formel `=A1+10`) visar dock följande fel:

![Fel](/help/workfront-fusion/references/apps-and-modules/assets/mceclip6-350x87.png)

Om du vill att [!DNL Google Sheets] ska förstå datumet formaterar du det med funktionen `formatDate`. Det korrekta format som skickas till funktionen som det andra argumentet beror på kalkylbladets språkinställningar.

Mer information om den här funktionen finns i [[!UICONTROL formatDate] (datum; format; [tidszon])](/help/workfront-fusion/references/mapping-panel/functions/date-and-time-functions.md#formatdate-date-format-timezone) i artikeln Datum- och tidsfunktioner.

Så här avgör du korrekt format:

1. I Google Sheets väljer du **[!UICONTROL File]** > **[!UICONTROL Spreadsheet]** inställningar på huvudmenyn för att verifiera och ange språkområdet.

1. När du har verifierat eller angett rätt språkområde bestämmer du motsvarande datum- och tidsformat genom att välja **[!UICONTROL Format]** > **[!UICONTROL Number]** på huvudmenyn. Formatet visas bredvid menyalternativet Datum och tid:

1. Om du vill skapa rätt format som ska skickas till funktionen [!UICONTROL formatDate()] läser du listan med [token för datum- och tidsformatering](/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md).

>[!BEGINSHADEBOX]

**Exempel:**

För formatet `MM/DD/YYYY HH:mm:ss` (för USA):

![Tidsformel för språkinställning](/help/workfront-fusion/references/apps-and-modules/assets/locale-time-350x83.png)

>[!ENDSHADEBOX]

## Utnyttjar [!DNL Google Sheets] funktioner

Om du vill använda en inbyggd funktion från Google Sheets kan du utnyttja den. Mer information finns i [Använd [!DNL Google Sheets] funktioner](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md#use-google-sheets-functions) i artikeln Mappa ett objekt med funktioner.

## Förhindra att [!DNL Google Sheets] ändrar siffror till datum

Om en sträng med tal som du använder som text tolkas som ett datum i ett [!DNL Google]-kalkylblad, kan du förformatera talet som oformaterad text för att förhindra detta. Om du t.ex. skriver 1-2019 och tänker skriva det som text, kan Google tolka det som ett datum.

1. I [!DNL Google Sheets] markerar du kolumnen eller cellen som innehåller talet eller talen.
1. Klicka på **[!UICONTROL Format]** > **[!UICONTROL Number]** > **[!UICONTROL Plain text]**.

En annan tillfällig lösning i [!DNL Workfront Fusion] är att skriva en apostrof (&#39;) före ett tal, till exempel &#39;1-2019 eller &#39;1/47. Apostrofen visas inte i cellen när data har skickats från [!DNL Workfront Fusion].
