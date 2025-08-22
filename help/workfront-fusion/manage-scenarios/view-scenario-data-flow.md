---
title: Visa dataflöde i ett scenario
description: Du kan titta på ett scenario som körs för att se hur data flödar genom det.
author: Becky
feature: Workfront Fusion
exl-id: 24eeb1d3-b5a7-4486-8d0b-0a43eb154e8e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Visa dataflöde i ett pågående scenario

Du kan titta på ett scenario som körs för att se hur data flödar genom det.

När ett scenario körs markeras den aktiva modulen med en växande ring runt modulen. Ringen visar bara att modulen körs, inte dess förlopp. Moduler som körs snabbt kan bara visa en liten del av ringen.

![Ring runt modul](assets/ring-around-module.png)

När modulen har körts visas en utdataindikator.

![Utdataindikator](assets/data-flow-output.png)

Om modulen bearbetar mer än en stötfångare visas ringen för varje bearbetat paket och utdataindikatorn räknas upp för varje paket som den matar ut.

Mer information om dataflöde för scenarier finns i [Körningsflöde för scenarier](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md).

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

## Visa dataflöde i ett pågående scenario

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill visa dataflöde.
1. Om scenariot inte körs aktiverar du det eller klickar på **Kör en gång** för att starta scenariokörningen.
1. Välj den körning som du vill visa i avsnittet Körs för närvarande på körningshistorikpanelen.

![Kör](assets/currently-running.png) just nu
