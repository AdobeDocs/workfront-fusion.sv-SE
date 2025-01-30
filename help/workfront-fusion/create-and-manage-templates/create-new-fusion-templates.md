---
title: Skapa nya mallar
description: Du kan skapa nya scenariomallar i  [!DNL Adobe] Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Skapa nya mallar

Du kan skapa nya scenariomallar i [!DNL Adobe] Workfront Fusion.

>[!TIP]
>
>Innan du skapar en ny mall kan du kontrollera fliken [!UICONTROL Public templates] för att se till att mallen som du vill skapa inte redan är tillgänglig.

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
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Skapa en ny mall

Du kan skapa en mall på ungefär samma sätt som när du skapar ett scenario. Fusion-administratörer kan också skapa mallar från befintliga scenarier.

* [Skapa en mall](#build-a-template)
* [Skapa en mall från ett scenario](#create-a-template-from-a-scenario)

### Skapa en mall

1. Klicka på **[!UICONTROL Templates]** ![Mallikon](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Klicka på **[!UICONTROL Create a new template]** i det övre högra hörnet.
1. (Valfritt) Byt namn på mallen genom att ersätta standardvärdet **[!UICONTROL New template name]** i det övre vänstra hörnet.
1. (Valfritt) Om du vill ändra språk på mallen klickar du på ikonen **[!UICONTROL Set up a template]** ![Scenarioinställningar](assets/scenario-settings-icon.png) och väljer språk i listrutan Språk.

   >[!IMPORTANT]
   >
   >Valet Språk motsvarar de tillgängliga språken i systeminställningarna och gäller endast namnet på den offentliga mallen och dess beskrivning. Du kan inte ändra ett mallspråk när mallen har sparats.

1. (Valfritt) Om du vill ange en beskrivning av mallen klickar du på ikonen **[!UICONTROL Set up a template]** ![Scenarioinställningar](assets/scenario-settings-icon.png) och anger beskrivningen.
1. Lägg till program, moduler och verktyg, med samma processer som att lägga till moduler i ett scenario.

   Instruktioner finns i artiklarna under [Lägg till moduler](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

   Mer information om hur du lägger till sammanhangsbaserad hjälp till modulerna finns i [Konfigurera guidefunktioner](#set-up-wizard-functionality) i den här artikeln.

   Mer information om hur du skapar ett scenario finns i [Arbetsflöde för att skapa ett scenario](/help/workfront-fusion/create-scenarios/plan-a-scenario/create-a-scenario-workflow.md).

   >[!NOTE]
   >
   >Om mallen innehåller moduler som kräver att anslutningen, inloggningsuppgifterna eller annan sekretesskänslig information läggs till, delas informationen inte med mallanvändarna.

1. (Valfritt) Klicka på **[!UICONTROL Run once]** om du vill testa mallen.
1. Klicka på ikonen **[!UICONTROL Save]** ![Spara ](assets/save-icon.png) för att spara mallen.

När du sparar mallen blir den synlig för dina teammedlemmar. Om du vill att mallen ska vara tillgänglig utanför ditt team måste du skicka in en begäran om att den ska godkännas och publiceras. Begäran skickas till Adobe Workfront Fusion-teamet för godkännande. När mallen har godkänts är den tillgänglig för andra utanför teamet.

Mer information om publiceringsmallar finns i [Publish och dela [!DNL Adobe Workfront Fusion] mallar](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md).

### Skapa en mall från ett scenario

>[!NOTE]
>
>Du måste vara en Fusion-administratör för att kunna skapa en mall från ett scenario.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario som du vill skapa en mall från.
1. Klicka på listrutan **Admin** uppe till höger på sidan.
1. Välj **Klona som mall**.

   Scenariot kopieras till en ny mallsida.
1. (Valfritt) Byt namn på mallen genom att ersätta standardvärdet **[!UICONTROL New template name]** i det övre vänstra hörnet.
1. (Valfritt) Om du vill ändra språk på mallen klickar du på ikonen **[!UICONTROL Set up a template]** ![Scenarioinställningar](assets/scenario-settings-icon.png) och väljer språk i listrutan Språk.

   >[!IMPORTANT]
   >
   >Valet Språk motsvarar de tillgängliga språken i systeminställningarna och gäller endast namnet på den offentliga mallen och dess beskrivning. Du kan inte ändra ett mallspråk när mallen har sparats.

1. (Valfritt) Om du vill ange en beskrivning av mallen klickar du på ikonen **[!UICONTROL Set up a template]** ![Scenarioinställningar](assets/scenario-settings-icon.png) och anger beskrivningen.
1. Redigera program, moduler och verktyg efter behov, med samma processer som när du lägger till moduler i ett scenario.

   Instruktioner finns i artiklarna under [Lägg till moduler](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

   Mer information om hur du lägger till sammanhangsbaserad hjälp till modulerna finns i [Konfigurera [!UICONTROL Wizard]-funktioner](#set-up-wizard-functionality) i den här artikeln.

   >[!NOTE]
   >
   >Om mallen innehåller moduler som kräver att anslutningen, inloggningsuppgifterna eller annan sekretesskänslig information läggs till, delas informationen inte med mallanvändarna.

1. (Valfritt) Klicka på **[!UICONTROL Run once]** om du vill testa mallen.
1. Klicka på ikonen **[!UICONTROL Save]** ![Spara ](assets/save-icon.png).

## Konfigurera [!UICONTROL Wizard]-funktioner {#set-up-wizard-functionality}

Med [!DNL Workfront Fusion template] [!UICONTROL Wizard] kan du ge framtida användare av mallen instruktioner eller information om de specifika fält som används i moduler.

1. När du skapar en mall klickar du på en modul som lagts till i mallen för att visa modulens fält.
1. Leta reda på fältet där du vill lägga till [!UICONTROL Wizard]-information och aktivera **[!UICONTROL Use in Wizard]** för det fältet.
1. Ange den information som du vill göra synlig för användare i fältet [!UICONTROL Help].
1. (Valfritt) Aktivera **[!UICONTROL Use as default value]** om du vill tillåta användare att se den här texten när de använder mallen.
1. Upprepa steg 2-4 för varje fält som du vill ange information för.
1. Klicka på **[!UICONTROL OK]** om du vill spara ändringarna och stänga modulen.
