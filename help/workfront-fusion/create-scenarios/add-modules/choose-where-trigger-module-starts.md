---
title: Välj var en utlösarmodul ska starta
description: Vissa utlösarmoduler låter dig välja det första paket från vilket du vill att hämtningen av paket ska starta.
author: Becky
feature: Workfront Fusion
exl-id: 83628fa5-82e2-4f67-bfed-70a4c3c19f7f
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Välj var en utlösarmodul ska starta

Vissa utlösarmoduler låter dig välja det första paket från vilket du vill att hämtningen av paket ska starta.

Du kan också ange om du vill hämta alla paket eller bara paketen från efter ett visst datum.

Mer information om utlösarmoduler finns i avsnittet [Utlösarmoduler](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) i översikten över artikelmodulen.

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

+++## Välj var en utlösarmodul ska starta

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill välja var utlösaren ska börja.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Konfigurera och spara en utlösarmodul.

   eller

   Högerklicka på ikonen för utlösarmodulen och välj **Välj var du vill starta**.

   ![Välj var du vill börja](assets/choose-where-to-start.png)

1. Välj ett alternativ i rutan **[!UICONTROL Choose where to start]** som visas.

   Vilka alternativ som visas beror på möjligheterna med en viss tjänst. De kan omfatta följande:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody>
    <tr>
    <td>[!UICONTROL From now on] (standard)</td>
    <td>Hämtar alla paket som lagts till eller uppdaterats (beroende på inställningar) efter att det här alternativet har valts</td>
    </tr>
     <tr>
    <td>[!UICONTROL Since specific date]</td>
    <td>Hämtar alla paket som lagts till eller uppdaterats (beroende på inställningar) efter ett angivet datum och en angiven tid</td>
      </tr>
      <tr>
    <td>[!UICONTROL All]</td>
    <td>Hämtar alla tillgängliga paket</td>
     </tr>
      <tr>
    <td>[!UICONTROL Choose manually]</td>
    <td>Gör att du kan välja det första paket från vilket hämtningen av paket ska börja</td>
     </tr>
     </tbody>
   </table>
