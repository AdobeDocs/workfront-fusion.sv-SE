---
title: Modulöversikt
description: 'Adobe Workfront Fusion skiljer ut fem typer av moduler: åtgärdsmoduler, sökmoduler, utlösarmoduler, aggregatorer och iteratorer. Aggregatorer och iteratorer är för avancerade scenarier.'
author: Becky
feature: Workfront Fusion
exl-id: 4c8fe028-8425-426d-a006-f0c66871b3cd
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# Modulöversikt

Adobe Workfront Fusion skiljer ut fem typer av moduler:

* Åtgärdsmoduler
* Sökmoduler
* Utlösarmoduler
* Aggregatorer
* Iteratorer

Aggregatorer och iteratorer är för avancerade scenarier.

## Åtgärdsmoduler

Åtgärdsmoduler är den vanligaste typen av modul. En typisk åtgärdsmodul utför en åtgärd och returnerar ett paket som sedan skickas vidare till nästa modul för bearbetning.

Till skillnad från utlösarmoduler kan åtgärdsmoduler placeras i början, mitten eller slutet av ett scenario.

Scenarier kan innehålla ett obegränsat antal åtgärdsmoduler, men ett stort antal moduler (150+) kan påverka prestandan.

>[!BEGINSHADEBOX]

**Exempel:**

* **[!DNL Workfront]>[!UICONTROL Upload a file]** skickar en fil till [!DNL Workfront] och returnerar dess identifierare.
* **[!UICONTROL Image]>[!UICONTROL Resize]** tar emot en bild, ändrar storlek på den till angivna mått och överför den storleksändrade bilden till nästa åtgärd.

>[!ENDSHADEBOX]

Åtgärdstypen har fyra undertyper:

* Skapa
* Läs
* Uppdatera
* Ta bort

Undertypen Uppdatera innehåller följande tre åtgärder:

* **Radera innehållet i ett fält**. Den här åtgärden utförs när innehållet i fältet utvärderas till nyckelordet `erase` (ska inte blandas ihop med `empty`).

  ![Ta bort nyckelord](assets/erase-content-of-field.png)

* **Ändra inte innehållet i ett fält**. Den här åtgärden utförs när fältet lämnas tomt eller innehållet i fältet utvärderas till tomt (representeras med null i JSON).

  ![Tomt paket](assets/leave-content-field-unchanged.png)

* **Ersätt innehållet i ett fält**. Denna operation äger rum i alla andra fall än de som beskrivs ovan.

>[!NOTE]
>
>* Om du inte ser nyckelordet `erase` på mappningspanelen är modulen inte en uppdateringsmodul eller så har den inte uppdaterats till de senaste specifikationerna för appen.
>* `Empty` ändrar inte fältinnehållet. Om du behöver radera fältet kan du använda följande formel:
>
>   ![Om tom](assets/formula-ifempty-name-erase.png)
>
>* Det går inte att låta ett fält vara oförändrat när dess innehåll utvärderas som tomt.

## Sökmoduler

Sökmodulerna returnerar noll, ett eller flera paket, som sedan skickas vidare till nästa modul för bearbetning.

Du kan placera sökmoduler i början, mitten eller slutet av ett scenario.

Scenarier kan innehålla ett obegränsat antal sökmoduler, men ett stort antal moduler (150+) kan påverka prestandan.

>[!BEGINSHADEBOX]

**Exempel:**

**[!DNL Workfront]>[!UICONTROL Read Related Records]** läser poster som matchar den sökfråga du anger, i ett visst överordnat objekt.

>[!ENDSHADEBOX]

## Utlösarmoduler

Utlösare genererar paket när en viss tjänst har ändrats, till exempel när en post skapas eller uppdateras.

Utlösare returnerar noll, ett eller flera paket, som sedan skickas till nästa modul för bearbetning.

Eftersom utlösare gör att scenarier börjar köras, kan de bara placeras i början av ett scenario.

Varje scenario kan bara innehålla en utlösare.

[!DNL Workfront Fusion] använder två typer av utlösare: avsökningsutlösare och direktutlösare.

### Avsökningsutlösare

Avsökningsutlösare avsöker regelbundet en viss tjänst även om det inte har skett någon förändring sedan föregående scenario kördes. Vi rekommenderar att du schemalägger ett scenario som innehåller en avsökningsutlösare som körs med regelbundna intervall. Om det finns en ändring som matchar utlösarens konfiguration returnerar utlösaren paket som innehåller information om ändringen. Om det inte finns någon ändring som matchar konfigurationen kommer utlösaren inte att generera några paket.

Instruktioner om hur du schemalägger ett scenario finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Med avsökningsutlösare kan du välja det första paket som de ska skicka via en panel som visas automatiskt när du har sparat en utlösare eller ändrat utlösarinställningarna. Det här valet påverkar bara den första körningen av modulen. När modulen har körts en gång bevakar efterföljande körningar endast ändringar som inträffar efter den senaste körningen.

Mer information finns i [Välja var en utlösarmodul ska starta](/help/workfront-fusion/create-scenarios/add-modules/choose-where-trigger-module-starts.md).

>[!BEGINSHADEBOX]

**Exempel:**

* **[!DNL Workfront]>[!UICONTROL Watch records]** returnerar poster som nyligen har lagts till efter den senaste körningen av scenariot.

* **[!DNL Google Sheets]>[!UICONTROL Watch Rows]** returnerar nya rader som lagts till efter den senaste gången scenariot kördes.

>[!ENDSHADEBOX]

### Direktutlösare

Direktutlösare gör att en tjänst kan meddela [!DNL Workfront Fusion] om en ändring omedelbart efter att den har utförts. Vi rekommenderar att du schemalägger ett scenario som innehåller en direktutlösare som körs omedelbart.

Instruktioner finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Mer information om hur inkommande data hanteras av en direktutlösare finns i [Direktutlösare (webhooks)](/help/workfront-fusion/references/modules/webhooks-reference.md).

>[!BEGINSHADEBOX]

**Exempel:**

* **[!DNL Workfront]>[!UICONTROL Watch Events]** returnerar information när en viss typ av händelse inträffar i Workfront, till exempel när en uppgift skapas.
* **[!DNL Google Sheets]>[!UICONTROL Watch Changes]** returnerar information när en cell uppdateras.

>[!ENDSHADEBOX]

## Aggregatorer

En aggregeringsmodul samlar ihop flera paket i ett och samma paket.

Aggregatorer returnerar bara ett paket, som sedan skickas vidare till nästa modul för vidare bearbetning.

Du kan bara placera aggregerare mitt i ett scenario.

Scenarier kan innehålla ett obegränsat antal aggregerare, men ett stort antal moduler (150+) kan påverka prestandan.

>[!BEGINSHADEBOX]

**Exempel:**

* **[!UICONTROL Archive]>[!UICONTROL Create an archive]** komprimerar flera filer till ett zip-arkiv.
* **[!UICONTROL CSV]>[!UICONTROL Aggregate to CSV]** sammanfogar flera strängar från en CSV-fil till en enda rad.
* **[!UICONTROL Tools]>[!UICONTROL Text aggregator]** kombinerar flera strängar till en enda sträng.

>[!ENDSHADEBOX]

Mer information finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

## Iteratorer

En iterator är en typ av modul som delar upp arrayer i separata paket.

Iteratorer returnerar ett eller flera paket som sedan skickas vidare till nästa modul för bearbetning.

Du kan bara placera iteratorer mitt i ett scenario.

Scenarier kan innehålla ett obegränsat antal iteratorer, men ett stort antal moduler (150+) kan påverka prestandan.

>[!BEGINSHADEBOX]

**Exempel:**

**[!UICONTROL Email]>[!UICONTROL Retrieve attachments]** delar upp en matris med bilagor i separata paket.

>[!ENDSHADEBOX]

Mer information finns i [Interpolatormodulen](/help/workfront-fusion/references/modules/iterator-module.md) och [Mappa en array](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).
