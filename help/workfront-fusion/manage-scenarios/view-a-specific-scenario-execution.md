---
title: Visa en specifik scenariekörning
description: Du kan visa information om en viss scenariokörning, inklusive filtrering och sökning efter scenariohändelser.
author: Becky
feature: Workfront Fusion
source-git-commit: 5915476de34a883560d207d101a14e5b24abf3da
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Visa en specifik scenariekörning

Du kan visa information om en viss scenariokörning, inklusive filtrering och sökning efter scenariohändelser.

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

## Visa en specifik körning

Du kan visa en körning från scenariohistoriken.


1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på scenariot.

   eller

   Om du arbetar med scenariot i scenredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. Klicka på **Historik** bredvid namnet på scenariot.
   ![fliken Historik](assets/history-tab.png)


1. Leta reda på den körning som du vill visa och klicka på **Detaljer** längst till höger på raden för den körningen. Länken [!UICONTROL details] är bara synlig om körningen har tillgängliga detaljer.

   Scendiagrammet öppnas med körningsinformationspanelen öppen till höger.

   Moduler som genererade utdata för den här körningen är markerade med gröna titlar.

   Moduler som inte kördes är nedtonade.

1. Om du vill visa utdata från en modul klickar du på utdatadetaljbubblan nära modulen. Talet i bubblan representerar antalet paket som modulen genererar.

   ![Utdatabubbla nära en modul](assets/output-bubble.png)

1. Klicka på filtret för att visa de paket som passerat genom ett filter. Siffran nära filtret representerar antalet paket som passerat filtret.
1. Om du vill söka efter en specifik modul eller händelse på körningspanelen anger du söktermen i rutan **Sökningshändelser**. Resultaten visas när du skriver.
1. Om du vill begränsa sökresultaten på körningspanelen efter status som Slutfört eller Varning klickar du på listrutan **Statusfilter** och väljer status.
