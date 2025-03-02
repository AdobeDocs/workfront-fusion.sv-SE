---
title: Översikt över scenarioinformation
description: Scenarioinformation i  [!DNL Adobe Workfront Fusion]
author: Becky
feature: Workfront Fusion
exl-id: a6d07ed9-aa55-4993-9f78-7e691aa61049
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Översikt över scenarioinformation

Sceninformationssidan är hemsidan för ett specifikt scenario. Den ger åtkomst till specifik information för scenariot som finns på sidan.

Du får även tillgång till scenarioredigeraren där du kan redigera scenariot.

Mer information om scenredigeraren finns i [Scenarioredigeraren](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)

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

## Öppna sidan [!UICONTROL Scenario detail]:

1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på ett scenario som du vill ha information om.

   eller

   Om du arbetar med scenariot i scenarioredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. På den sida som visas kan du granska elementen i tabellen nedan:

   ![Scenarioinformation](assets/scenario-detail-350x207.png)

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Modules diagram] </td> 
      <td>På den här fliken visas den visuella representationen av scenariot. Diagrammet är detsamma som du kommer att se i scenarioredigeraren.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Reports] tab </td> 
      <td> <p>Öppna den här fliken om du vill se ett diagram över antalet åtgärder som har utförts under de senaste 30 dagarna.</p>  </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL History] tab </td> 
      <td> <p>Öppna den här fliken om du vill se en historik över scenariot, inklusive ändringar som gjorts i scenariot. </p> <p>Fliken [!UICONTROL History] innehåller också en historik för scenariokörning för varje körning, som innehåller följande:</p> 
       <ul> 
        <li>Status för varje körning (slutförd eller fel)</li> 
        <li>Körningstid</li> 
        <li>Antal åtgärder</li> 
        <li>Storlek på dataöverföring</li> 
        <li>Länk till detaljerad information</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Incomplete executions]</td> 
      <td> <p>Fliken innehåller information om ofullständiga körningar av scenariot. Den innehåller följande information för varje ofullständig körning:</p> 
       <ul> 
        <li>Skapad den</li> 
        <li>Storlek på dataöverföring</li> 
        <li>Försök igen</li> 
        <li>Löst</li> 
        <li>Antal försök</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Activate scenario] (På/Av-knapp)</td> 
      <td>När ett scenario har skapats måste det aktiveras för att det ska kunna köras enligt schemat. Genom att klicka på knappen På/Av i det övre högra hörnet kan du aktivera eller inaktivera scenariot. När det är aktiverat körs scenariot enligt dess schema.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Edit]</td> 
      <td>Klicka på scenariodiagrammet för att öppna scenarioredigeraren och göra ändringar i scenariot.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Options]</td> 
      <td> <p>Den här menyn innehåller extra alternativ utan att du behöver öppna scenarioredigeraren. Bland dessa finns:</p> 
       <ul> 
        <li>[!UICONTROL Scheduling]</li> 
        <li>[!UICONTROL Rename]</li> 
        <li>[!UICONTROL Clone]</li> 
        <li>[!UICONTROL Delete]</li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Currently running]</td> 
      <td>I det här området visas information om den aktuella körningen.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL History] panel</p> <p> </p> </td> 
      <td> <p>I det här området visas information om den senaste körningen av scenariot. För varje körning visas:</p> 
       <ul> 
        <li>Körningsdatum</li> 
        <li>Status (lyckades eller misslyckades)</li> 
        <li>Körningstid</li> 
        <li>Storlek på dataöverföring</li> 
        <li>Länk till detaljerad information</li> 
       </ul> </td> 
     </tr> 
         <tr> 
      <td role="rowheader"> <p>[!UICONTROL Events] panel</p>  </td> 
      <td>I det här området visas information om händelser som är relaterade till scenariot.  </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Processing banner]</p>  </td>

   <td>Om ditt scenario har körts nyligen kan du se en banderoll som läser:<p><code>Data is still being processed. Only partial scenario history will show until processing is complete.</code></p>Detta visas när körningsinformationen skrivs till lagringen. Bearbetningen sker omedelbart efter att scenariot har körts. och bör inte vara längre än några minuter. Detaljer om scenariokörningen kanske inte visas när körningen bearbetas.</td> 
     </tr> 
    </tbody> 
   </table>
