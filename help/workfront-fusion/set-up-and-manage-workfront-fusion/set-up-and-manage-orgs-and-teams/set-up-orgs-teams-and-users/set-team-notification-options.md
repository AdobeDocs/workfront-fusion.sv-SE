---
title: Ange alternativ för teammeddelanden
description: Alternativen för e-postmeddelanden anges på teamnivå.
author: Becky
feature: Workfront Fusion
exl-id: 570a09fc-01a9-4952-8a2b-8bfdd86d0bd8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# Ange alternativ för teammeddelanden

I din organisation använder Adobe Unified Shell får du meddelanden via Adobe Notifications.

Om din organisation inte har migrerats till Adobe Unified Shell kan du välja vilka meddelanden ett team får. Meddelanden anges på teamnivån.

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

## Ange meddelandealternativ

Om din organisation inte är ansluten till Adobe Unified Shell kan du ange meddelandeinställningar direkt i Fusion.

Alternativen för e-postmeddelanden anges på teamnivå.

1. Klicka på **[!UICONTROL Team]** i den vänstra navigeringspanelen
1. Välj fliken **[!UICONTROL Notification Options]**.
1. Aktivera de meddelanden som du vill att teamet ska ta emot.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Warning in scenario run]</td> 
      <td> <p>Få ett e-postmeddelande när det finns en varning i en scenariokörning</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Errors in scenario run]</td> 
      <td>Få ett e-postmeddelande när ett fel uppstår i en scenariokörning.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Scenario deactivation]</p> </td> 
      <td><p>Få ett e-postmeddelande när ett scenario inaktiveras.</p><p>I vissa fall kan ett scenario avaktiveras av Workfront Fusion-tekniker eftersom scenariot ger upphov till prestandaproblem eller andra problem. I dessa fall får du inga meddelanden i Workfront Fusion. </p></td>

</tr>
</tbody>
</table>

Ändringar av meddelandealternativen sparas automatiskt.
