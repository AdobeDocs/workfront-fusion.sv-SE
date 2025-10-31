---
title: Uppdatera en modul till en ny version
description: Eftersom de applikationer som Workfront Fusion ansluter till kan uppdatera eller släppa nya versioner är det ibland nödvändigt att Fusion släpper uppdaterade moduler för dessa applikationer.
author: Becky
feature: Workfront Fusion
exl-id: b7f07fa5-9d81-48b3-b0ce-7a18b3b44508
source-git-commit: 93d06cb917680f9cabc1bad6be0f9cd843449d07
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---

# Uppgradera en modul till en ny version

Eftersom de applikationer som Workfront Fusion ansluter till kan uppdatera eller släppa nya versioner är det ibland nödvändigt att Fusion släpper uppdaterade moduler för dessa applikationer.

Om en grön uppgraderingsmodulikon visas i en modul i ett scenario har Workfront Fusion släppt en ny version av den modulen.

![Ikon för uppdatering](assets/update-indicator-workfront.png)

Du kan uppdatera modulen utan att skapa ett nytt scenario.

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

## Uppgradera en Workfront-modul till en ny version

1. Klicka på ikonen **Uppgraderingsmodul** ![Uppgraderingsikon](assets/upgrade-icon.png) i modulen som du vill uppgradera till en ny version.
   ![Ikon för uppdatering](assets/update-indicator-workfront.png)
1. Välj något av följande:

   * Om du vill välja en ny modul som ska ersätta den här modulen (i stället för att uppgradera modulen) klickar du på **Välj ny** och fortsätter sedan enligt beskrivningen i [Uppgradera en modul som inte är från Workfront till en ny version](#upgrade-a-non-workfront-module-to-a-new-version).
   * Om du bara vill uppgradera den här modulen och behålla modulkonfigurationen klickar du på **Uppgradera**.
   * Om du vill uppgradera alla Workfront-moduler i scenariot klickar du på **Uppgradera alla**.

1. Spara scenariot.

>[!NOTE]
>
>Om du har uppgraderat Workfront-moduler rekommenderar vi att du öppnar dem och kontrollerar modulkonfigurationen.

## Uppgradera en modul från andra program än Workfront till en ny version

1. Klicka på ikonen **Uppgraderingsmodul** ![Uppgraderingsikon](assets/upgrade-icon.png) i modulen som du vill uppgradera till en ny version.
   ![Ikon för uppdatering](assets/update-indicator.png)
1. Klicka på **Välj ny**.
1. Markera den modul som du vill ersätta den tidigare modulen.
1. Konfigurera modulen med samma inställningar som den befintliga modulen.
1. Koppla den nya modulen till scenariot på samma plats som den befintliga modulen.
1. Ta bort den gamla modulen.
1. Spara scenariot.
