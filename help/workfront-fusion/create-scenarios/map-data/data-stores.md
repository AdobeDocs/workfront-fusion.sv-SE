---
title: Datalager i Adobe Workfront Fusion
description: Ett datalager, som liknar en databas eller en enkel tabell, kan lagra data från scenarier, vilket gör det möjligt att överföra data mellan enskilda scenarier eller scenariokörningar. Du kan använda ett datalager för att lagra nya data från olika system under synkroniseringen.
author: Becky
feature: Workfront Fusion
exl-id: 8bfa3201-45db-49d7-985d-9c324acd56b6
source-git-commit: b59532d96d64f77c04d31d03f6ae5addf15c0dd7
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 0%

---

# Skapa och hantera datalager

Ett datalager, som liknar en databas eller en enkel tabell, kan lagra data från scenarier, vilket gör det möjligt att överföra data mellan enskilda scenarier eller scenariokörningar. Du kan använda ett datalager för att lagra nya data från olika system under synkroniseringen.

Med datalagermodulerna kan du utföra följande åtgärder på poster i Adobe Workfront Fusion datalager:

* Lägg till
* Ersätt
* Uppdatering
* Hämta
* Ta bort
* Sök
* Antal

Mer information om hur du använder datalagermoduler finns i [[!UICONTROL Data store] moduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md).

En videointroduktion till datalager i Workfront Fusion finns på:

* [Datalager](https://video.tv.adobe.com/v/3427029/){target=_blank}

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

## Tillgängligt datautrymme

Om din organisation använder den nya Workfront-planmodellen (Select-, Prime- och Ultimate-paket) påverkar din organisations plan storleken och antalet datalager som är tillgängliga i Fusion-instansen.

### Ultimate

Fusion-instanser i Ultimate-paketet tar emot:

* 100 MB ledigt utrymme
* 50 datalager

### Select- och Prime-planer

Fusion-instanser på Select- eller Prime-paket tar emot :-->

* 100 MB för de första 500 kB-åtgärderna.

* 10 MB för varje ytterligare 100 K-åtgärd.

  En organisation med 600 kB-åtgärder får till exempel 110 MB.

Varje team i organisationen kan ha upp till 50 datalager. Den kombinerade storleken på dessa datalager får inte överskrida organisationens totala datalagringsstorlek.

## Skapa ett datalager i Workfront Fusion

* [Konfigurera datalagret](#set-up-the-data-store)
* [Ställ in datastrukturen](#set-up-the-data-structure)

### Konfigurera datalagret

Innan du kan använda ett datalager i en modul måste du skapa datalagret i Workfront Fusion.

>[!NOTE]
>
>Din organisation har ett begränsat antal tillgängliga datalager. Om du försöker skapa fler datalager än vad du har tillgängligt returnerar Workfront ett [!UICONTROL Maximum stores reached]-fel.
>
>Mer information finns i [Maximalt antal arkiv har nått fel](#maximum-stores-reached-error) i den här artikeln.

1. Logga in på ditt Workfront Fusion-konto.
1. Klicka på **[!UICONTROL Data stores]** i den vänstra navigeringspanelen.
1. Klicka på **[!UICONTROL Add data store]** i skärmens övre högra hörn.
1. Ange inställningar för det nya datalagret.

   En rubrik med fet stil i ett fält i en Workfront Fusion-modul anger en obligatorisk inställning.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Data store name] </td> 
      <td> <p>Ange ett namn för datalagret. </p> </td> 
     </tr> 
     <tr> 
      <td> <p>[!UICONTROL Data Structure]</p> </td> 
      <td> <p>En datastruktur är en lista med kolumner för en tabell. Den här listan anger kolumnnamnet och datatypen.</p> <p>Gör något av följande:</p> 
       <ul> 
        <li><b>Välj en datastruktur som redan har skapats</b></li> 
        <li><b>Lägg till en ny datastruktur</b> <p>Klicka på <strong>[!UICONTROL Add]</strong> om du vill skapa en ny datastruktur.</p> <p>Mer information finns i avsnittet <a href="#set-up-the-data-structure" class="MCXref xref">Konfigurera datastrukturen</a> i den här artikeln.</p> </li> 
        <li style="font-weight: bold;"> <p>Lämna fältet tomt</p> <p style="font-weight: normal;">Om du inte markerar eller lägger till en datastruktur kommer databasen endast att innehålla primärnyckeln. En sådan databastyp är användbar om du bara vill spara nycklar och bara vill veta om det finns en viss nyckel i databasen eller inte.</p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td>Datalagringsstorlek i MB</td> 
      <td> <p>Allokera storleken på datalagret från din totala interna datalagring.</p> <p> Standardvärdet är 10 MB. Om du har mindre än 10 MB oallokerat datalagringsutrymme från din tilldelning på 95 MB är standardstorleken mängden oallokerat lagringsutrymme.  <p>Obs! Det reserverade beloppet kan ändras när som helst.</p>  </td> 
     </tr> 
    </tbody> 
   </table>

### Ställ in datastrukturen

1. Klicka på **[!UICONTROL Add]** när du skapar eller redigerar ett datalager.
1. Konfigurera följande fält i rutan **[!UICONTROL Add data structure]** som visas:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Data structure name]</td> 
      <td> <p> Ange ett namn för den nya datastrukturen.</p> </td> 
     </tr> 
     <tr> 
      <td> <p>[!UICONTROL Specification]</p> </td> 
      <td> <p>Gör något av följande för att konfigurera kolumnerna i datalagret.</p> 
       <ul> 
        <li> <p>Klicka på <strong>[!UICONTROL Add item]</strong> om du vill ange egenskaperna för en kolumn manuellt.</p> <p>Ange <strong>[!UICONTROL Name]</strong> och <strong>[!UICONTROL Type]</strong> för datalagerkolumnen och definiera motsvarande egenskaper.</p> </li> 
        <li> <p>Klicka på <strong>[!UICONTROL Generator]</strong> för att fastställa kolumnerna från exempeldata som du anger.</p> 
         <div class="example" data-mc-autonum="<b>Example: </b>">
          <span class="autonumber"><span><b>Exempel: </b></span></span> 
          <p>I följande JSON-exempeldata skapas tre kolumner: namn, ålder och telefonnummer. Telefonnummer är en samling mobiltelefonnummer och telefonnummer.</p> 
          <p><code>&lbrace;</code> </p> 
          <p><code>"name":"John",</code> </p> 
          <p><code>"age":30,</code> </p> 
          <p><code>"phone number": &lbrace;</code> </p> 
          <p><code>"mobile":"987654321",</code> </p> 
          <p><code>"landline":"123456789"</code> </p> 
          <p><code>&rbrace;</code> </p> 
          <p><code>&rbrace;</code> </p> 
          <p>De tomma kolumnerna i datalagervyn:</p> 
          <p> <img src="assets/empty-columns-350x132.png" style="width: 350;height: 132;"> </p> 
          <p>Du kan lägga till värden i datalagret manuellt eller med datalagermodulerna i Workfront Fusion.</p> 
         </div> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Strict] </td> 
      <td> <p>Aktivera det här alternativet för att säkerställa att nyttolasten matchar datastrukturerna. Nyttolaster som innehåller extra artiklar som inte har angetts i datastrukturen nekas.</p> </td> 
     </tr> 
    </tbody> 
   </table>

## Redigera ett befintligt datalager

Du kan redigera egenskaperna och innehållet i ett befintligt datalager i området [!UICONTROL Data stores] i Workfront Fusion.

* [Redigera egenskaperna för ett datalager](#edit-the-properties-of-a-data-store)
* [Redigera innehållet i ett datalager](#edit-the-contents-of-a-data-store)

### Redigera egenskaperna för ett datalager

Egenskaperna för ett datalager omfattar datastrukturen som används i datalagret samt storleken på datalagret.

1. Klicka på **[!UICONTROL Data stores]** ![ikonen för datalagring](assets/data-store-icon.png) i den vänstra navigeringspanelen för att öppna området [!UICONTROL Data stores].
1. Klicka på **[!UICONTROL Edit]** ![Redigera datalager](assets/data-store-edit.png) bredvid datalagret som du vill redigera.
1. (Valfritt) Om du vill ändra den datastruktur som används av det här datalagret till en annan befintlig datastruktur väljer du den i listrutan **[!UICONTROL Data structure]**.

   eller

   (Valfritt) Om du vill ändra datastrukturen som används av det här datalagret till en helt ny datastruktur, se [Konfigurera datastrukturen](#set-up-the-data-structure) i den här artikeln.

1. (Valfritt) Ändra storleken på datalagret genom att ange den nya storleken i fältet **[!UICONTROL Data storage size in MB]**.
1. Klicka på **[!UICONTROL Save]**.

### Redigera innehållet i ett datalager

1. Klicka på ikonen **[!UICONTROL Data Store]** ![ för datalagring ](assets/data-store-icon.png) i den vänstra navigeringspanelen för att öppna området [!UICONTROL Data Store].
1. Klicka på **[!UICONTROL Browse]** bredvid det datalager som du vill redigera.
1. (Valfritt) Ändra ordning på kolumner genom att dra dem till önskad plats.
1. (Valfritt) [!UICONTROL Edit] en enskild cell genom att klicka på ikonen **[!UICONTROL Edit]** i den cellen och sedan ange önskat värde.
1. (Valfritt) Lägg till ett nytt objekt i datalagret genom att klicka på **[!UICONTROL Add]** och sedan ange informationen för det nya objektet.
1. Klicka på **[!UICONTROL Save]**.

## Felsökning

* [Återställa förlorade data från ett datalager](#restoring-lost-data-from-a-data-store)
* [Slut på utrymme-fel](#out-of-space-error)
* [Högsta antal arkiv har nåtts](#maximum-stores-reached-error)

### Återställa förlorade data från ett datalager

Det finns för närvarande inget verktyg som kan automatisera återställning av förlorade data.

#### Tillfällig lösning

1. Granska alla körningsloggar för scenarier där objekt infogades i datalagret.

   Mer information om hur du undersöker körningsloggar finns i [Visa körningshistorik för ett scenario](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md).

1. Kopiera data.
1. Infoga data i datalagret igen.

   Mer information om hur du infogar data i ett datalager finns i [Redigera innehållet i ett datalager](#edit-the-contents-of-a-data-store) i den här artikeln.

### [!UICONTROL Out of space]-fel

Ett [!UICONTROL Out of Space]-fel inträffar eftersom dina tidigare skapade datalager redan har tilldelats ditt allokerade datalager.

#### Tillfällig lösning

1. Redigera alla befintliga datalager för att utnyttja mindre utrymme. Detta frigör utrymme för ditt nya datalager.

   Mer information finns i [Redigera egenskaperna för ett datalager](#edit-the-properties-of-a-data-store) i den här artikeln.

>[!NOTE]
>
>Vi rekommenderar att du inte tilldelar allt utrymme till ett enda datalager om du inte är säker på att du inte behöver fler datalager.

### [!UICONTROL Maximum stores reached]-fel

Ett [!UICONTROL Maximum stores reached]-fel inträffar eftersom din organisation har använt alla tillgängliga datalager.

#### Tillfällig lösning

Om du vill minska antalet befintliga datalager kan du göra något av följande:

* Kombinera befintliga datalager
* Ta bort oanvända datalager
