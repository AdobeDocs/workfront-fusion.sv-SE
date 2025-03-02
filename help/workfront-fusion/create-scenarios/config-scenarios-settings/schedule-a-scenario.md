---
content-type: reference
title: Schemalägg ett scenario
description: Som standard körs ett scenario var 15:e minut. Du kan ändra detta genom att definiera när och hur ofta ett aktiverat scenario körs. Fusionsscenarier kan schemaläggas så att de körs så ofta som var femte minut.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Schemalägg ett scenario

Som standard körs ett scenario var 15:e minut. Du kan ändra detta genom att definiera när och hur ofta ett aktiverat scenario körs. Fusionsscenarier kan schemaläggas så att de körs så ofta som var femte minut.

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
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront] Plan: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] Planen [!DNL Workfront Fusion] ingår.</li></ul>
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

## Schemalägg ett scenario

1. Klicka på fliken **Scenario** i den vänstra panelen.
1. Välj det scenario som du vill schemalägga.
1. Klicka på **[!UICONTROL Options]** > **[!UICONTROL Scheduling]** i det övre högra hörnet på sidan Scenarioinformation

   eller

   Klicka på ikonen **[!UICONTROL Scheduling]** (klocka) i scenariots utlösarmodul.

1. Ange information i följande fält:

   <table style="table-layout:auto">   
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Run scenario]</td> 
      <td> <p>Välj med vilken frekvens du vill köra scenariot och välj sedan intervallet.</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL At regular intervals]</strong> </p> <p>Ange antalet minuter mellan körningar. Standardvärdet är 15 minuter.</p> </li> 
        <li> <p><strong>[!UICONTROL Once]</strong> </p> <p>Ange det datum och den tidpunkt då du vill att scenariot ska köras. Använd formatet <code>MM/DD/YYYY h:mm A</code>. Exempel: <code>06/25/2019 11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Every day]</strong> </p> <p>Ange den tidpunkt då du vill att scenariot ska köras. Använd formatet <code>h:mm A</code>. Exempel: <code>11:00 PM</code>.</p> </li> 
        <li> <p><strong>[!UICONTROL Days of the week]</strong> </p> <p>Dagar: Välj de veckodagar som du vill att scenariot ska köras. Du kan välja en eller flera dagar.</p> <p>Tid: Ange den tidpunkt då du vill att scenariot ska köras på de valda dagarna. Använd formatet <code>h:mm A</code>. Exempel: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Days of the month]</strong> </p> <p>Dagar: Välj de dagar i månaden som du vill att scenariot ska köras. Du kan välja en eller flera dagar.</p> <p>Tid: Ange den tidpunkt då du vill att scenariot ska köras på de valda dagarna. Använd formatet <code>h:mm A</code>. Exempel: <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Specified dates]</strong> </p> <p>Månader: Välj de månader som du vill köra scenariot. Du kan välja en eller flera månader.</p> <p>Dagar: Välj de dagar i månaden som du vill att scenariot ska köras. Du kan välja en eller flera dagar.</p> <p>Tid: Ange den tidpunkt då du vill att scenariot ska köras på de valda dagarna. Använd formatet <code>h:mm A</code>. Exempel: <code>11:00 PM</code></p> </li> 
       </ul> <p>Obs! Det måste finnas ett datum för att ett scenario ska kunna köras på det datumet. Ett scenario som till exempel bara är schemalagt för den 31:e månaden kommer inte att köras i februari, april, juni, september eller november eftersom dessa månader inte har en 31:a dag.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Advanced scheduling]</td> 
      <td>Du kan definiera tidsintervall under vilka ditt scenario ska köras. Du kan ange tidsintervall, veckodagar eller månader. För varje intervall klickar du på <strong>[!UICONTROL Add]</strong> och fyller i fälten enligt beskrivningen i fältet [!UICONTROL Run scenario].</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>Ange det datum och den tidpunkt efter vilken du vill att scenariot ska köras. Använd formatet <code>MM/DD/YYYY h:mm A</code>. Exempel: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL End]</td> 
      <td>Ange det datum och den tidpunkt då du vill att scenariot ska köras. Använd formatet <code>MM/DD/YYYY h:mm A</code>. Exempel: <code>06/25/2019 11:00 PM</code>.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL OK]** om du vill spara schemainställningarna och återgå till scenariot.
