---
title: Visa och lösa ofullständiga körningar
description: Mappen [!UICONTROL Incomplete executions] lagrar scenariekörningar som inte slutfördes korrekt på grund av ett fel. Varje lagrad ofullständig körning kan lösas antingen manuellt eller automatiskt.
author: Becky
feature: Workfront Fusion
exl-id: 974b32b4-d86a-48cd-a8d4-1ae2cf309b9b
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---

# Visa ett scenario körningshistorik

Du kan visa information om händelser eller körningar i ett scenario eller söka efter specifika data i alla körningar i scenariot.

En scenariokörning representerar en enda körning av scenariot.

En scenariohändelse är en ändring av scenariot, till exempel redigering, aktivering eller inaktivering.

>[!NOTE]
>
>Ett scenario historik visar alla händelser och körningar i ett scenario de senaste 30 dagarna.

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

## Visa scenariohistorik


### Visa scenariohistorik på fliken Historik

Fliken [!UICONTROL History] visar fler detaljer än vad som är tillgängligt på sidan [!UICONTROL Scenario detail]. Du kan även filtrera och sortera körningarna på fliken [!UICONTROL History].

1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på scenariot.

   eller

   Om du arbetar med scenariot i scenredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. Klicka på **Historik** bredvid namnet på scenariot.
   ![fliken Historik](assets/history-tab.png)

   Följande information visas för varje körning av scenariot:

   * Datum när körningen var **[!UICONTROL Started]**
   * Körnings-ID
   * **[!UICONTROL Status]** (lyckades eller misslyckades)
   * Kör **[!UICONTROL Duration]**
   * Antal **[!UICONTROL Operations]**
   * Storlek på **[!UICONTROL Data Transfer]**

   >[!NOTE]
   >
   >Scenhistoriken visar ett **Bearbetningsemblem** bredvid scenarier som nyligen har körts, medan körningsinformationen skrivs till lagringen. Bearbetningen sker omedelbart efter att scenariot har körts. och bör inte vara längre än några minuter. Detaljer om scenariokörningen kanske inte visas när körningen bearbetas.

1. Om du vill visa information om en viss scenariokörning klickar du på **Detaljer** längst till höger. Länken [!UICONTROL details] är bara synlig om körningen har tillgängliga detaljer.
1. Om du vill visa händelser växlar du **Visa händelser** på.


### Visa scenariohistorik på sidan Scenarioinformation


1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på scenariot.

   eller

   Om du arbetar med scenariot i scenredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. Klicka på fliken **[!UICONTROL History]** i den högra panelen.
1. (Valfritt) Om du vill ha detaljerad information om en vald scenariokörning klickar du på körningen i den högra panelen.

   Mer information om att bearbeta paket finns i [Körningsflöde för scenarier](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md)

   >[!NOTE]
   >
   >* Scenhistoriken visar ett **Bearbetningshistorik** bredvid scenarier som nyligen har körts, medan körningsinformationen skrivs till lagringen. Bearbetningen sker omedelbart efter att scenariot har körts. och bör inte vara längre än några minuter. Detaljer om scenariokörningen kanske inte visas när körningen bearbetas.

1. Klicka på fliken **Händelser** om du vill visa händelser.

## Filtrera historiken för scenariokörning

Du kan filtrera körningshistoriken så att endast körningar med angivna värden visas.

1. Öppna helsideshistoriken för ett scenario enligt beskrivningen i [Visa historik för scenariokörning på fliken [!UICONTROL History] ](#view-scenario-history-on-the-history-tab) i den här artikeln.
1. Klicka på ikonen [!UICONTROL filter] ![Scenariofilterikon](assets/fusion-scenario-filter-icon.png) i kolumnrubriken som du vill filtrera efter.
1. Ange de värden som du vill filtrera efter i dialogrutan [!UICONTROL filter].
1. Klicka på **[!UICONTROL Save]**.

Filterikonen är orange i kolumner med ett aktivt filter.

<!-- don't see how to do this
## Sort the scenario execution history

You can sort the scenario execution history.

1. Open the full-page history for a scenario as described in [View scenario execution history on the [!UICONTROL History] tab](#view-scenario-execution-history-on-the-history-tab) in this article.
1. Click the [!UICONTROL Sort] icon in the header of the column you want to filter by.
1. Optional: To reverse the order of the sort, click the [!UICONTROL Sort] icon again.
-->

## Sök i alla körningar av ett scenario

1. Öppna helsideshistoriken för ett scenario enligt beskrivningen i [Visa historik för scenariokörning på fliken [!UICONTROL History] ](#view-scenario-history-on-the-history-tab) i den här artikeln.
1. Klicka på **[!UICONTROL Fulltext search]** högst upp i listan över körningar.

   eller

   Skriv **Ctrl+Skift+F** (Windows) eller **Cmd+Skift+F** (Mac)
Fönstret [!UICONTROL Search in history] öppnas.

1. (Valfritt) Om du vill söka efter körningar som innehåller specifik text anger du texten i sökfältet i fönstret **[!UICONTROL Search in history]**.

   Om du vill söka efter exakt text omger du texten med citattecken (&quot;exempel&quot;).

   >[!INFO]
   >
   >**Exempel:** Om du vill hitta den körning som skapade ett visst projekt anger du projekt-ID:t i fältet [!UICONTROL Fulltext search].
   >
   >&quot;625ef2ef0006036bd1794b6e52d737c5&quot;

1. (Valfritt) Om du vill begränsa sökningen efter datumintervall markerar du start- och slutdatum för den önskade sökningen i området [!UICONTROL By date range].

   >[!NOTE]
   >
   >* Körningar är bara tillgängliga under de senaste 30 dagarna.
   >
   >* [!DNL Workfront Fusion] lagrar webkrocknyttolaster i 30 dagar. Om du får åtkomst till en webkrok-nyttolast mer än 30 dagar efter att den skapades uppstår felet [!UICONTROL Failed to read file from storage.]


1. (Valfritt) Om du vill begränsa sökningen efter status väljer du önskad status i listrutan **[!UICONTROL By status]**.


   Tillgängliga statusvärden är:

   * [!UICONTROL All]

   * [!UICONTROL Error]

   * [!UICONTROL Warning]

   * [!UICONTROL Success]

1. (Valfritt) Ändra den ordning som resultatet visas i listrutan **[!UICONTROL Sort by dates]**.

1. (Valfritt) Klicka på ikonen **[!UICONTROL Copy execution ID]** om du vill kopiera ett scenario-körnings-ID <img src="assets/copy-fusion-execution-id-icon.png"> i raden för önskad körning.

1. (Valfritt) Klicka på resultatet av [!UICONTROL Fulltext search] för att undersöka scenariomodulens utdatapaket som innehåller informationen.
