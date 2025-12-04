---
title: Scenarieredigeraren
description: Med scenarioredigeraren kan du skapa och redigera scenarier i ett visuellt gränssnitt.
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: f968b9141173725160cea36575ad4e02a09a5e3f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---

# Scenarieredigeraren

Med scenarioredigeraren kan du skapa och redigera scenarier i ett visuellt gränssnitt.

![Scenarioredigerare](assets/scenario-editor.jpg)

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

Du kan behöva klicka på ikonen med tre punkter i området Kontroller för att visa några av dessa kontroller.

| Åtgärd | Information |
|----------|----------|
| Spara <p>![Ikonen Spara](assets/save-icon.png)</p> | När du har sparat ditt scenario kommer en ny version att finnas tillgänglig under menyn med tre punkter om du behöver komma åt den i framtiden. Tidigare sparade versioner är endast tillgängliga i 60 dagar. |
| Scenarioinställningar <p>![Ikon för scenarioinställningar](assets/scenario-settings-icon.png)</p> | Panelen för scenarioinställningar innehåller avancerade inställningar för scenariot. Mer information om tillgängliga inställningar finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md). |
| Anteckningar  <p>![Anteckningsikon](assets/notes-icon.png)</p> | Gör anteckningar om scenariot. Andra användare kan visa dessa anteckningar när de befinner sig i ett scenario. |
| Autojustera <p>![Ikon för automatisk justering](assets/auto-align-icon.png)</p> | Justera modulerna automatiskt i ditt scenario. |
| Sökmoduler ![Sökmoduler](assets/search-modules-icon.png)  </p> | Ange en sökterm för att söka efter en modul och klicka sedan på sökresultaten som ska hämtas till den modulen. Du kan söka efter modulnamn, ID, typ eller program. |
| Förklara flöde  <p>![Ikonen Förklara flöde](assets/explain-flow-icon.png) </p> | Visa en animering där rörliga punkter visar hur data flödar genom scenariot. |
| Utvecklingsverktyg <p>![DevTool-ikon](assets/devtool-icon.png)</p> | Med DevTool kan du kontrollera alla manuella körningar av ditt scenario, granska alla utförda åtgärder och se information om alla API-anrop som utförs. Du kan se vilken modul, åtgärd eller enskilt svar som orsakade felet och använda den kunskapen för att förfina ditt scenario. Mer information finns i [Felsöka ett scenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md). |
| Exportera utkast  <p>![Ikonen Exportera skiss](assets/export-blueprint-icon.png) </p> | Exportera en plan för det aktuella scenariot. |
| Importera utkast  <p>![Importera blåtrycksikon](assets/import-blueprint-icon.png) </p> | Importera en tidigare exporterad scenarioplan. |
| Föregående version  <p>![Ikon för föregående version](assets//previous-version-icon.png) </p> | Visa tidigare versioner av det här scenariot. |

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
