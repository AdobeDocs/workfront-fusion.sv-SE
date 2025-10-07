---
title: Uppdatera en modul till en ny version
description: Eftersom de applikationer som Workfront Fusion ansluter till kan uppdatera eller släppa nya versioner är det ibland nödvändigt att Fusion släpper uppdaterade moduler för dessa applikationer.
author: Becky
feature: Workfront Fusion
exl-id: b7f07fa5-9d81-48b3-b0ce-7a18b3b44508
source-git-commit: d0d9d7cdad993ecceaa0abf0ac69e9a9abd78b69
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Uppgradera en modul till en ny version

Eftersom de applikationer som Workfront Fusion ansluter till kan uppdatera eller släppa nya versioner är det ibland nödvändigt att Fusion släpper uppdaterade moduler för dessa applikationer.

Om en grön uppgraderingsmodulikon visas i en modul i ett scenario har Workfront Fusion släppt en ny version av den modulen.

![Ikon för uppdatering](assets/update-indicator-workfront.png)

Du kan uppdatera modulen utan att skapa ett nytt scenario.

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
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>[!UICONTROL Ultimate] Workfront: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
     <p>Du måste vara Workfront Fusion-administratör för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
