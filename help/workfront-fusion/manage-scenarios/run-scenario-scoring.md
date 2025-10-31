---
title: Kör scenariobedömningsexperten
description: Scenariobedömningsexperten kan hjälpa dig att se till att ditt scenario är konfigurerat på ett sätt som följer bästa praxis. Den kontrollerar ditt scenario och ger rekommendationer om dess struktur och organisation.
author: Becky
feature: Workfront Fusion
exl-id: b668e7f6-dac5-4ac9-b3f3-109f70eaa2c4
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Kör scenariobedömningsexperten

>[!IMPORTANT]
>
>Scenariobedömningsexperten har tillfälligt inaktiverats.

Scenariobedömningsexperten kan hjälpa dig att se till att ditt scenario är konfigurerat på ett sätt som följer bästa praxis. Den kontrollerar ditt scenario och ger rekommendationer om dess struktur och organisation.

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

## Kör scenariobedömningsexperten

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill köra scenariobedömningsexperten.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på ikonen Scenario Scoring Expert ![Expert för bedömning av scenario](assets/scoring-expert-icon.png) längst ned på skärmen.

   Panelen Scenariobedömningsexpert öppnas.
1. Klicka på **Utvärdera**.

Scenario Scoring Expert returnerar poängen från 10 och visar vilka kontroller som har passerat eller misslyckats. Om en kontroll har misslyckats ger scenariobedömningsexperten rekommendationer för hur man ska se till att scenariot uppfyller dessa kontroller.

![Scenariopoäng](assets/scenario-score.png)

## Bedömningskontroller av scenarier

Scenariobedömningsexperten använder följande kontroller:

* Scenariot måste namnges.
* Alla moduler måste ha en etikett.
* Scenariot måste köras enligt ett angivet schema.

  Instruktioner finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).
* Scenens storlek för utkast måste vara mindre än 5 MB.

  Mer information finns i [Förberedelser för Fusion-prestanda](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#scenarios).
* Om en Workfront direktutlösarmodul används måste den filtreras.

  Instruktioner finns i [Evenemangsprenumerationsfilter i Workfront > [!UICONTROL Watch Events] module](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules).
