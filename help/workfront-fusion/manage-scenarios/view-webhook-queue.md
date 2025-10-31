---
title: kS-kön
description: Många tjänster tillhandahåller webbhookar för att leverera snabbmeddelanden när en viss förändring inträffar i tjänsten. Direktutlösare, som också kallas webhooks, kan använda dessa händelser för att börja scenarier. Händelserna hamnar i webbhakens kö medan de väntar på bearbetning, till exempel när scenariot redan körs. Du kan visa webbkrokens kö.
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Visa en webkroks kö

Många tjänster tillhandahåller webbhookar för att leverera snabbmeddelanden när en viss förändring inträffar i tjänsten. Direktutlösare, som också kallas webhooks, kan använda dessa händelser för att börja scenarier. Händelserna hamnar i webbhakens kö medan de väntar på bearbetning, till exempel när scenariot redan körs. Du kan visa webbkrokens kö.

Inkommande webkrockdata lagras alltid i kön oavsett hur du har angett alternativet Data är konfidentiellt på panelen för scenarioinställningar. När data har bearbetats i ett scenario tas de bort permanent från kön.

Mer information om webbhooks finns i [Direktutlösare (webbhooks)](/help/workfront-fusion/references/modules/webhooks-reference.md).

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

## Visa en webkroks kö

Alla meddelanden från inkommande webbhooks lagras i webbkrokens kö.

Om ett scenario har en kö visas en banderoll i det scenariot:

![Köbanderoll](assets/queue-banner.png)

Så här visar du en webkroks kö:

1. Klicka på **[!UICONTROL Webhooks]** på menyn till vänster.
1. Leta reda på webbkroken som du vill visa kön för.
1. Leta reda på antalet händelser i knappen Händelser som tagits emot.

   ![Webkrok-kö](assets/webhook-queue.png)

1. Klicka på knappen om du vill visa information om händelser i kön.
