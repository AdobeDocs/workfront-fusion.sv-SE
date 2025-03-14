---
title: SharePoint moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Microsoft SharePoint Online och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2526'
ht-degree: 0%

---

# Microsoft SharePoint Online

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder Microsoft SharePoint Online och ansluta det till flera tredjepartsprogram och -tjänster.

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

Om du vill använda Microsoft SharePoint Online-moduler måste du ha ett Microsoft SharePoint Online-konto.

## SharePoint API-information

SharePoint Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## Anslut Microsoft SharePoint Online till [!DNL Workfront Fusion] {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [Anslut Microsoft SharePoint Online till [!DNL Workfront Fusion] med ett [!DNL Microsoft] konto](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [Anslut Microsoft SharePoint Online till [!DNL Workfront Fusion] med avancerade inställningar](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)

### Anslut Microsoft SharePoint Online till [!DNL Workfront Fusion] med ett [!DNL Microsoft]-konto

Du kan skapa en anslutning till Microsoft SharePoint Online med ditt [!DNL Microsoft]-konto. Instruktioner om hur du ansluter ditt [!DNL Sharepoint]-konto till [!DNL Workfront Fusion] finns i [Skapa en anslutning till  [!DNL Adobe Workfront Fusion] - Grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

### Anslut Microsoft SharePoint Online till [!DNL Workfront Fusion] med avancerade inställningar

Om du vill ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion] utan ett [!DNL Microsoft]-konto behöver du ett klient-ID, klienthemlighet och klient-ID.

1. Klicka på **[!UICONTROL Add]** uppe i rutan **Microsoft SharePoint Online** för att öppna rutan **[!UICONTROL Create a connection]**.

1. (Valfritt) Ändra standardvärdet **[!UICONTROL Connection name]**.
1. Klicka på **[!UICONTROL Show advanced settings]**.
1. Ange Microsoft SharePoint Online **[!UICONTROL Client ID]** och **[!UICONTROL Client Secret]**.

1. Klicka på **[!UICONTROL Continue]**.
1. I inloggningsfönstret som visas anger du dina inloggningsuppgifter för att logga in på appen om du inte redan har gjort det.
1. (Villkorligt) Om en **[!UICONTROL Allow]**-knapp visas klickar du på knappen för att ansluta appen till [!DNL Workfront Fusion].

## Microsoft SharePoint Online-moduler och deras fält

När du konfigurerar Microsoft SharePoint Online-moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare fält i Microsoft SharePoint Online visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Enhetsobjekt](#drive-item)
* [Objekt](#item)
* [Lista](#list)
* [Sida (Beta)](#page-beta)
* [Plats](#site)
* [Övriga](#other)

### Enhetsobjekt

* [Skapa en fil](#create-a-file)
* [Skapa en mapp](#create-a-folder)
* [Hämta en fil](#get-a-file)
* [Bevaka mappobjekt](#watch-folder-items)

#### Skapa en fil

Den här modulen returnerar ändringar som har gjorts i SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Välj hur du vill identifiera platsen för mappen som du vill hämta ändringar i.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> och <strong>[!UICONTROL Folder ID]</strong> för den plats där du vill skapa filen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Välj den plats där du vill skapa filen. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
      <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p>
  </tr>  </tbody> 
</table>

#### Skapa en mapp

Den här åtgärdsmodulen skapar en ny mapp i SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Välj hur du vill identifiera platsen för mappen som du vill skapa.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> och <strong>[!UICONTROL Folder ID]</strong> för den plats där du vill skapa mappen.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Välj den plats där du vill skapa mappen. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder name]</td> 
   <td>Ange eller mappa ett namn för den nya mappen.</td> 
  </tr>
  </tbody> 
</table>

#### Hämta en fil

Den här åtgärdsmodulen hämtar den angivna SharePoint-filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Välj hur du vill identifiera platsen för filen som du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL File ID]</strong> för filen som du vill hämta.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Välj plats för filen. </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### Bevaka mappobjekt

Den här utlösarmodulen startar ett scenario när ett objekt uppdateras i en mapp som du väljer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Välj hur du vill identifiera platsen för filen som du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL folder ID]</strong> i fälten som visas.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Välj platsen för mappen som du vill bevaka. </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange det maximala antalet objekt som [!DNL Workfront Fusion] ska returnera under en körningscykel för scenario.</td> 
  <tr>
  </tr>
</tbody> 
</table>

### Objekt

* [[!UICONTROL Copy an item]](#copy-an-item)
* [[!UICONTROL Create an item]](#create-an-item)
* [[!UICONTROL Delete an item]](#delete-an-item)
* [[!UICONTROL Get an Item]](#get-an-item)
* [[!UICONTROL List Items]](#list-items)
* [[!UICONTROL Move Item]](#move-an-item)
* [[!UICONTROL Update an item]](#update-an-item)
* [[!UICONTROL Watch Items] (schemalagd)](#watch-items-scheduled)


#### [!UICONTROL Copy an Item]

Den här åtgärdsmodulen kopierar ett befintligt objekt i en SharePoint-lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ange plats-, enhet- och mapp-ID</td> 
   <td> <p>Välj hur du vill identifiera platsen och enheten som innehåller det objekt du vill kopiera.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> och <strong>[!UICONTROL Item ID]</strong> för objektet som du vill kopiera.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>I fältet Objekttyp väljer du om du ska flytta ett fält eller en mapp.  Markera platsen som innehåller det objekt du vill kopiera, markera sedan listan och markera objektet. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> Ange eller mappa ID:t för mappen som du vill kopiera objektet till. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>Ange eller mappa ett namn för den nya kopian av objektet. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an item]

Den här åtgärdsmodulen skapar ett nytt objekt i en SharePoint-lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Create an Item]</td> 
   <td> <p>Välj hur du vill identifiera platsen och enheten där du vill skapa ett objekt.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> och <strong>[!UICONTROL List ID]</strong> där du vill skapa objektet.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera den plats som innehåller listan där du vill skapa ett objekt och markera sedan listan. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>För varje fält som du vill ange för det nya objektet klickar du på <b>Lägg till objekt</b> och anger fältets nyckel (som identifierar fältet) och det värde som du vill att det nya objektet ska ha för fältet.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an item]

Den här åtgärdsmodulen tar bort ett befintligt objekt i en SharePoint-lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Välj hur du vill identifiera den plats och lista som innehåller det objekt du vill ta bort.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL Item ID]</strong> för objektet som du vill ta bort.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller det objekt du vill ta bort, markera listan och markera sedan objektet. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Item]

Den här åtgärdsmodulen returnerar data för ett angivet objekt.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get an Item]</td> 
   <td> <p>Välj hur du vill identifiera den plats och lista som innehåller det objekt du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL Item ID]</strong> för objektet som du vill returnera data för.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller listan som du vill hämta ett objekt från, markera listan och markera sedan objektet. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Items]

Den här åtgärdsmodulen hämtar en lista med alla objekt i en angiven lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Items]</td> 
   <td> <p>Välj hur du vill identifiera listan som du vill hämta objekt från.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> och <strong>[!UICONTROL List ID]</strong> för listan som du vill visa objekt för.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller listan som du vill hämta objekt från och markera sedan listan. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal objekt som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Item]

Den här åtgärdsmodulen kopierar ett befintligt objekt i en SharePoint-lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ange plats-, enhet- och mapp-ID</td> 
   <td> <p>Välj hur du vill identifiera platsen och listan som innehåller objektet som du vill flytta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL Item ID]</strong> för objektet som du vill flytta.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from list that you follow]</strong> </p> <p>I fältet Objekttyp väljer du om du ska flytta ett fält eller en mapp. Markera platsen som innehåller det objekt du vill kopiera, markera sedan listan och markera objektet. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination ID]</td> 
   <td> Ange eller mappa ID:t för mappen som du vill flytta objektet till. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td>Ange eller mappa ett namn för det flyttade objektet. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an item]

Den här åtgärdsmodulen uppdaterar ett befintligt objekt i en SharePoint-lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update an Item]</td> 
   <td> <p>Välj hur du vill identifiera platsen och listan som innehåller objektet som du vill uppdatera.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL List ID]</strong> och <strong>[!UICONTROL Item ID]</strong> för objektet som du vill uppdatera.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller det objekt som du vill uppdatera, markera listan och markera sedan objektet. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td>För varje fält som du vill uppdatera för det nya objektet klickar du på <b>Lägg till objekt</b> och anger fältets nyckel (som identifierar fältet) och det nya värde som du vill att objektet ska ha för fältet.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Items] (schemalagd)

Den här utlösarmodulen startar ett scenario när ett objekt skapas eller ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Välj om du vill bevaka listor efter skapandetid (nya objekt) eller efter ändringstid (uppdaterade objekt).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site and List ID]</td> 
   <td> <p>Välj hur du vill identifiera webbplatsen och listan som du vill bevaka.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> och <strong>[!UICONTROL List ID]</strong> som du vill bevaka.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Markera den plats som du vill bevaka och markera sedan listan. De här listrutorna hämtar bara de webbplatser som följer.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal objekt som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Lista

* [[!UICONTROL Create a List]](#create-a-list)
* [[!UICONTROL Get a List]](#get-a-list)
* [[!UICONTROL List Lists]](#list-lists)
* [[!UICONTROL Watch Lists]](#watch-lists)

#### [!UICONTROL Create a List]

Den här åtgärdsmodulen skapar en ny lista i SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Site ID]</td> 
   <td> <p>Välj hur du vill identifiera den plats där du vill skapa en lista.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> där du vill skapa en lista.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Välj den plats där du vill skapa en lista. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display Name]</td> 
   <td>Ange eller mappa ett namn för den nya listan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för den nya listan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Add Columns]</td> 
   <td>För varje kolumn som du vill ange för den nya listan klickar du på <b>Lägg till objekt </b>, anger en <strong>[!UICONTROL Name]</strong> för fältet och väljer <strong>[!UICONTROL Type]</strong> för värdet som du vill att den nya kolumnen ska ha.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a List]

Den här åtgärdsmodulen returnerar data i en angiven lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a List]</td> 
   <td> <p>Välj hur du vill identifiera den plats och lista som innehåller det objekt du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa det <strong>[!UICONTROL Site ID]</strong> och <strong>list-ID</strong> som du vill returnera.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller listan som du vill hämta och markera sedan listan. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Lists]

Den här åtgärdsmodulen hämtar en lista över alla objekt på en angiven plats.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List Lists]</td> 
   <td> <p>Välj hur du vill identifiera webbplatsen som du vill hämta listor från.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> som innehåller de listor som du vill returnera.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera den plats som innehåller de listor som du vill hämta. Listrutan hämtar bara de webbplatser du följer.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal listor som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Lists]

Den här utlösarmodulen startar ett scenario när en lista skapas eller ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Lists]</td> 
   <td>Välj om du vill bevaka listor efter skapandetid (nya objekt) eller efter ändringstid (uppdaterade objekt).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site ID]</td> 
   <td> <p>Välj hur du vill identifiera webbplatsen som du vill bevaka för listor.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> där du vill bevaka listor.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list that you follow]</strong> </p> <p>Markera den plats som du vill titta på. Listrutan hämtar bara den webbplats som du följer.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal listor som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sida (Beta)

>[!NOTE]
>
>API:er i `beta`-versionen i [!DNL Microsoft Graph] kan komma att ändras. Det går inte att använda dessa API:er i produktionsprogram.

#### [!UICONTROL Get a Page]

Denna åtgärdsmodul returnerar data för en angiven sida.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Page]</td> 
   <td> <p>Välj hur du vill identifiera sidan som du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong> och <strong>[!UICONTROL Page ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera den webbplats som innehåller den sida som du vill hämta och markera sedan sidan.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Plats

* [[!UICONTROL Get a Site]](#get-a-site)
* [[!UICONTROL Search Sites]](#search-sites)

#### [!UICONTROL Get a Site]

Den här åtgärdsmodulen returnerar data för en angiven plats.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get a Site]</td> 
   <td> <p>Välj hur du vill identifiera sidan som du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Välj den plats som du vill hämta.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Sites]

Den här åtgärdsmodulen söker efter platser med en parameter som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword of Display Name]</td> 
   <td> <p>Ange eller mappa söktermen som du vill söka efter webbplatserna för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal webbplatser som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [Hämta ändringar](#get-changes)
* [Göra ett API-anrop](#make-an-api-call)
* [Se händelser](#watch-events)

#### Hämta ändringar

Den här modulen hämtar tillägg, uppdateringar och borttagningar som gjorts i mappen SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Site, Drive, and Folder IDs]</td> 
   <td> <p>Välj hur du vill identifiera platsen och enheten som innehåller objektet som du vill uppdatera.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>Ange eller mappa <strong>[!UICONTROL Site ID]</strong>, <strong>[!UICONTROL Drive ID]</strong> och <strong>[!UICONTROL Folder ID]</strong> i fälten som visas.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera platsen som innehåller objektet som du vill uppdatera, markera enheten och markera sedan mappen. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Token]</td> 
   <td> Token identifierar från vilken punkt modulen ska börja hämta ändringar.  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft SharePoint Online-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Microsoft SharePoint Online till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till <code>https://graph.microsoft.com</code>. Exempel:<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Välj den typ av data som du vill skicka i API-anropet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Se händelser

Den här snabbutlösarmodulen startar ett scenario när ett objekt läggs till, uppdateras eller tas bort i SharePoint.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to [!DNL Workfront Fusion], see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj en befintlig webkrok eller klicka på Lägg till och ange anslutningen för att skapa en ny webkrok.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>
