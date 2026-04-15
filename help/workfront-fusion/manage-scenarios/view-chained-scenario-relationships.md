---
title: Visa kedjade scenarierelationer
description: Du kan mappa relationerna mellan överordnade och underordnade scenarier.
author: Becky
feature: Workfront Fusion
source-git-commit: e7b12ec51474440990cc28996bc70fd97688b082
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Visa och hantera kopplade scenariorelationer

Du kan mappa relationerna mellan överordnade och underordnade scenarier. Du kan också använda kartan för att hoppa till olika scenarier i kedjan.

Mer information om kedjade scenarier finns i [Kedja flera scenarier tillsammans](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md).

Mer information om hur du konfigurerar kedjade scenarier finns i [Kedjemoduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md)

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

## Visa en karta över kedjade relationer

Du kan visa en karta över det aktuella scenariot och dess överordnade eller underordnade scenarier. Kartan visar ett diagram över dataflödet i de kedjade scenarierna.

![Kopplade scenarierelationer](assets/chained-scenario-relationships-2.png)

<!--get a better picture-->

Så här visar du relationskartan för ett kedjat scenario:

1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på scenariot.

   eller

   Om du arbetar med scenariot i scenredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. Klicka på fliken **Relationer**.

   ![Fliken Relationer](assets/relations-tab.png)

1. Mer information om varje kedjat scenario finns i taggarna.

   Varje scenario har en eller flera av följande taggar:

   * Rot: Scenariot är början av kedjan och har inget överordnat scenario.
   * Överordnad: Scenariot är ett överordnat scenario.
   * Underordnat: Scenariot är ett underordnat scenario. Ett scenario kan vara både överordnat och underordnat.
   * Aktuell: Detta är det scenario som användaren för närvarande visar. Detta är med andra ord det scenario från vilket användaren öppnade relationskartan.

   ![Scenariotaggar i relationskarta](assets/chained-scenario-maps-tag.png)
1. (Valfritt) Håll pekaren över scenariot om du vill visa ett litet diagram över ett scenario.
1. (Valfritt) Om du vill gå direkt till ett annat scenario från kartan klickar du på scenariot.

   Det klickade scenariot öppnas i ett annat fönster.
1. (Valfritt) Om du vill växla mellan vågrät och lodrät vy av kartan klickar du på **Vågrät** eller **Lodrät** uppe till höger på sidan Scenarioinformation.
1. (Valfritt) Om du vill visa en förenklad vy av kartan markerar du det nedre högra hörnet på sidan.

   Detta kan vara praktiskt om kedjekartan är stor eller komplex.

   * Om du bara visar en del av kartan blir den delen mörkare på den förenklade kartan.
   * Det aktuella scenariot är markerat med blått på den förenklade kartan.


