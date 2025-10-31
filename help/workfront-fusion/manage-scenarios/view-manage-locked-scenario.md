---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Hantera låsta scenarier
description: Hantera låsta scenarier i Adobe Workfront Fusion
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Hantera låsta scenarier

I vissa fall kan ett scenario vara tillfälligt låst i Workfront Fusion. Låsta scenarier låses upp automatiskt inom 2-4 timmar. Du kan låsa upp scenarier manuellt, men det rekommenderas inte i allmänhet.

Scenarier kan vara låsta av flera skäl:

* Workfront Fusion stöder inte parallell bearbetning av schemalagda scenarier. Dessa scenarier är låsta i början av scenariot och olåsta när det är klart. Om körningen avbryts kanske scenariot inte låses upp. Detta kan inträffa när en användare manuellt framtvingar ett stopp av scenariot eller när det uppstår ett systemproblem.

* Workfront Fusion Engineering Team kan låsa ett scenario eftersom det orsakar prestandaproblem eller andra problem.

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

## Lås upp ett låst scenario

Låsta scenarier låser upp 2-4 timmar från den tidpunkt de låstes. Du kan låsa upp ett scenario manuellt innan det är schemalagt att låsas upp automatiskt.

>[!WARNING]
>
>Om du låser upp ett scenario manuellt kan det orsaka fel i körningarna av ett scenario. Vi rekommenderar att du endast låser upp scenarier manuellt när ett scenario är låst på grund av att körningar körs och stoppas som en del av utformningen av scenariot. I andra fall rekommenderar vi att du väntar på att scenariot ska låsas upp automatiskt.


Så här låser du upp ett låst scenario manuellt:

1. Gå till sidan Scenarioinformation i det låsta scenariot.
1. Klicka på **[!UICONTROL Options]** i skärmens övre högra hörn.
1. Välj **[!UICONTROL Unlock execution]**.
1. Klicka på **[!UICONTROL Unlock]**.
   ![Lås upp scenario](assets/unlock-scenario.png)
