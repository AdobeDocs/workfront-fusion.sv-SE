---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Hantera låsta scenarier
description: Hantera låsta scenarier i  [!DNL Adobe Workfront Fusion]
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Hantera låsta scenarier

I vissa fall kan ett scenario vara tillfälligt låst i [!DNL Workfront Fusion]. Låsta scenarier låses upp automatiskt inom 2-4 timmar. Du kan låsa upp scenarier manuellt, men det rekommenderas inte i allmänhet.

Scenarier kan vara låsta av flera skäl:

* Workfront Fusion stöder inte parallell bearbetning av schemalagda scenarier. Dessa scenarier är låsta i början av scenariot och olåsta när det är klart. Om körningen avbryts kanske scenariot inte låses upp. Detta kan inträffa när en användare manuellt framtvingar ett stopp av scenariot eller när det uppstår ett systemproblem.

* Workfront Fusion Engineering Team kan låsa ett scenario eftersom det orsakar prestandaproblem eller andra problem.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> <p>Nytt: [!UICONTROL Standard]</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront]: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara administratör för [!DNL Workfront Fusion] för din organisation.</p>
     <p>Du måste vara administratör för [!DNL Workfront Fusion] för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
