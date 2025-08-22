---
title: MariaDB-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL MariaDB] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 41179cfe-c0f9-4d18-ab7e-374670ac688b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# [!DNL MariaDB] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL MariaDB] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL MariaDB]-konto för att kunna använda [!DNL MariaDB]-moduler.

## Anslut [!DNL MariaDB] till Workfront Fusion

Du kan skapa en anslutning till ditt [!DNL MariaDB]-konto direkt inifrån en [!DNL MariaDB]-modul.

1. Klicka på [!DNL MariaDB] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Konfigurera följande fält:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Ange ett namn för den nya anslutningen.</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om den här anslutningen är avsedd för en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL Host]</td> 
      <td> <p>Ange IP-adressen eller värdnamnet för databasinstansen. Värden måste vara åtkomlig utanför nätverket.</p> <p>Exempel: <code>[!DNL mariadb.hwoh2j5h.us-east-1.rds.amazon.com]</code></p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Port]</td> 
      <td>Standardporten är 3306. Om du använder en port som inte är standard anger du det här numret till din port. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Database ]</td> 
      <td>Ange namnet på den databas som du vill interagera med.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL User]</td> 
      <td>Ange ditt användarnamn.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Password]</td> 
      <td>Ange ditt lösenord.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL MariaDB] moduler och deras fält

När du konfigurerar [!DNL MariaDB]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL MariaDB] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Kör en fråga (avancerat)

Den här åtgärdsmodulen hämtar information från databasen baserat på en fråga som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL MariaDB]-konto till Workfront Fusion finns i <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL MariaDB] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Ange den SQL-fråga som du vill att modulen ska använda för att hämta data.</p> <p>Viktigt: Variabler som används i frågan saneras inte. Se till att du sanerar variablerna på rätt sätt för att förhindra SQL-injektion.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Select rows from a table (advanced)]

Den här modulen läser post från din databas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL MariaDB]-konto till Workfront Fusion finns i <a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL MariaDB] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table]</td> 
   <td> <p>Markera den tabell som innehåller de poster som du vill läsa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Ange med vilket filter du vill markera rader</p> 
    <ul> 
     <li> <p>Markera fältet som du vill söka efter</p> </li> 
     <li> <p>Välj den operator som du vill använda för sökningen</p> </li> 
     <li> <p>Ange eller mappa värdet som du vill söka efter.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort] </td> 
   <td> <p>För varje nivå som du vill att resultaten ska sorteras efter klickar du på <strong>[!UICONTROL Add item]</strong> och väljer sedan det fält som du vill sortera resultaten efter och om du vill sortera stigande eller fallande</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
