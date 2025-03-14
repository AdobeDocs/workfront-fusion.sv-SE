---
title: Bildmoduler
description: Med Adobe Workfront Fusion Image-modulerna kan du hämta information om en viss bild (mått, typ o.s.v.), konvertera en bild till ett annat filformat och direkt ändra bildens storlek.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---

# Bildmoduler

Med modulerna [!DNL Adobe Workfront Fusion] [!UICONTROL Image] kan du hämta information om en viss bild (dimensioner, typ och så vidare), konvertera en bild till ett annat filformat och direkt ändra bildens storlek.

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

## [!UICONTROL Image]-moduler och deras fält

När du konfigurerar den här modulen visas följande fält. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

* [[!UICONTROL Convert a format]](#convert-a-format)
* [[!UICONTROL Extract metadata]](#extract-metadata)
* [[!UICONTROL Resize]](#resize)

### [!UICONTROL Convert a format]

Den här transformerarmodulen ändrar formatet för en bildfil. Den här modulen är kompatibel med följande format:

* PNG
* JPG
* GIF
* BMP

Både källfilen och utdata måste ha något av dessa format. Modulen [!UICONTROL Image] >[!UICONTROL Convert a format] kan till exempel omvandla en PNG-fil till en BMP-fil eller en BMP till en JPG.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output format]</td> 
   <td>Välj det format som du vill att modulen ska konvertera källfilen till. </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Extract metadata]

Den här transformatormodulen returnerar grundläggande information om en modul.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Resize]

Den här transformerarmodulen ändrar en bilds höjd och bredd enligt de villkor du anger.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to]</td> 
   <td>Välj om du vill behålla förhållandet mellan höjd och bredd eller ändra dimensionerna till en angiven höjd och bredd.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL According to]</td> 
   <td> <p>Välj hur du vill att modulen ska avgöra bildens nya storlek. Det här fältet visas om du har valt att behålla förhållandet mellan höjd och bredd i fältet Jag vill. Andra fält visas baserat på valet i det här fältet.</p> 
    <ul> 
     <li> <p>[!UICONTROL Maximum width]</p> <p>Minskar en bild till en bredd som du anger. Höjden beräknas automatiskt.</p> </li> 
     <li> <p>[!UICONTROL Maximum height]</p> <p>Förminskar en bild till en höjd som du anger. Bredden beräknas automatiskt.</p> </li> 
     <li> <p>[!UICONTROL Maximum height or width]</p> <p>Minskar en bild så att dess höjd och bredd inte överskrider de värden du anger. Eftersom det här alternativet behåller förhållandet mellan höjd och bredd kan en av dimensionerna vara mindre än den angivna. Om till exempel både höjd och bredd anges som 40, kommer en bild på 400x300 att minskas till 40x30.</p> </li> 
     <li> <p>[!UICONTROL Minimum width]</p> <p>Förstorar en bild till en bredd som du anger. Höjden beräknas automatiskt.</p> </li> 
     <li> <p>[!UICONTROL Minimum height]</p> <p>Förstorar en bild till en höjd som du anger. Bredden beräknas automatiskt.</p> </li> 
     <li> <p>[!UICONTROL Minimum height or width]</p> <p>Förstorar en bild så att dess höjd och bredd inte är mindre än de värden du anger. Eftersom det här alternativet bevarar förhållandet mellan höjd och bredd kan en av dimensionerna vara större än angivet. Om till exempel både höjd och bredd anges som 300 förstoras en bild på 40 x 30 till 400 x 300.</p> </li> 
     <li> <p>[!UICONTROL Percent]</p> <p>Ändrar bildstorleken med ett procentvärde baserat på det värde du anger. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Width]</td> 
   <td>Ange eller mappa önskad bredd för den storleksändrade bilden i pixlar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Height]</td> 
   <td>Ange eller mappa den önskade höjden på den storleksändrade bilden i pixlar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Change by percentage]</td> 
   <td>Om du har valt att ändra bilden i procent anger eller mappar du den procentandel du vill ändra bilden med.</td> 
  </tr> 
 </tbody> 
</table>

## Felsökning

### Åtgärden avslutades med ett fel

en åtgärd kan avslutas med ett fel på grund av någon av följande orsaker:

* Mottagna data är inte i JPG/GIF/PNG/BMP-format
* Gränsen för maximal bredd/höjd överskreds när bildens dimensioner ändrades. Bildstorleken får inte överskrida 3 840 px bredd och 2 160 px höjd
* Den största tillåtna storleken för en bild överskreds när bildens dimensioner eller format ändrades.
