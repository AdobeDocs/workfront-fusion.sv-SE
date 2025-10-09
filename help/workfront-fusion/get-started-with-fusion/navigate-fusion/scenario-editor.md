---
title: Scenarieredigeraren
description: Med scenarioredigeraren kan du skapa och redigera scenarier i ett visuellt gränssnitt.
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: ce2a41a9708bb0e611ab4056aac733d58d27d7a9
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---

# Scenarieredigeraren

Med scenarioredigeraren kan du skapa och redigera scenarier i ett visuellt gränssnitt.

![Scenarioredigerare](assets/scenario-editor.jpg)

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

## Öppna scenarioredigeraren och lägg till en modul:

1. Klicka på **[!UICONTROL Scenarios]** ![Scenarioikonen](assets/scenarios-icon.png) i den vänstra panelen.
1. Klicka på frågetecknet ![frågeikonen](assets/question-mark-full-size.png) och sök efter och klicka sedan på det program eller den tjänst som du vill börja med. Mer information om hur du konfigurerar en modul finns i [Konfigurera en modul](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).

## Tillgängliga scenarioredigeringsåtgärder

### Kör ditt scenario

| Åtgärd | Information |
|----------|----------|
| Testkör scenariot | Kontrollera att scenariot fungerar som du tänkt dig innan du aktiverar det. När det är aktiverat körs scenariot enligt dess schema. Om allt inte fungerar som det ska läser du [Lägg till felhantering](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md) för att lära dig hur du hanterar fel. |

![kör scenario-knapp](assets/run-your-scenario.png)

### Schemaläggning

| Åtgärd | Information |
|----------|----------|
| Schemalägg scenariot | Som standard körs ett scenario var 15:e minut. Du kan ändra detta genom att definiera när och hur ofta ett aktiverat scenario körs. Fusionsscenarier kan schemaläggas så att de körs så ofta som var femte minut. Mer information finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md). |

![Schemaläggningspanelen](assets/scheduling-scenario-editor.png)

### Kontroller

| Åtgärd | Information |
|----------|----------|
| Spara | När du har sparat ditt scenario kommer en ny version att finnas tillgänglig under menyn med tre punkter om du behöver komma åt den i framtiden. Tidigare sparade versioner är endast tillgängliga i 60 dagar. |
| Scenarioinställningar | Panelen för scenarioinställningar innehåller avancerade inställningar för scenariot. Mer information om tillgängliga inställningar finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). |
| Anteckningar | Gör anteckningar om scenariot. Andra användare kan visa dessa anteckningar när de befinner sig i ett scenario. |
| Autojustera | Justera modulerna automatiskt i ditt scenario. |
| Förklara flöde | Visa en animering där rörliga punkter visar hur data flödar genom scenariot. |
| Utvecklingsverktyg | Med utvecklingsverktyget kan du kontrollera alla manuella körningar av ditt scenario, granska alla utförda åtgärder och se information om alla API-anrop som utförs. Du kan se vilken modul, åtgärd eller enskilt svar som orsakade felet och använda den kunskapen för att förfina ditt scenario. Mer information finns i [Felsöka ett scenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Mer | På menyn Mer kan du importera eller exportera utkast och återställa scenariot till tidigare versioner. |

![Kontrollpanelen](assets/controls-editor-scenario.png)

### verktyg

| Åtgärd | Information |
|----------|----------|
| Flödeskontroll | Konfigurera inställningar för att styra hur data flödar genom dem. Mer information finns i [länken behövs]. |
| verktyg | Verktygsavsnittet innehåller flera användbara moduler som kan förbättra dina scenarier. Mer information finns i [länken behövs]. |
| Textparser | Använd textanalysverktyget för att tolka text som ska användas i andra scenariomoduler. Textparsern kräver ingen anslutning. Mer information finns i [länken behövs]. |

![verktygspanelen](assets/tools-scenario-editor.png)

### Favoriter

Du kan använda ikonen Favoriter för att lägga till moduler som du använder ofta.

![Panelen Favoriter](assets/favorites-scenario-editor.png)
