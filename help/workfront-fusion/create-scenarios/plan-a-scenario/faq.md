---
title: Vanliga frågor om scenarioplanering
description: Informationen i den här artikeln kan vara användbar när du börjar skapa scenarier i Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6a1d672d-0bd7-4a3a-b96d-6d8b4c97522d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# Vanliga frågor om scenarioplanering

Informationen i den här artikeln kan vara användbar när du börjar skapa scenarier i Workfront Fusion.

## Vad är ett scenario?

### Svar

Ett scenario definierar en sekvens av steg som ska köras av Adobe Workfront Fusion. För varje scenario anger du datakällan, vilka data som ska användas och hur data ska behandlas. Med Fusion kan du skapa enkla eller komplexa scenarier som uppfyller användningsexemplen för din organisation.

Mer information om scenarier finns i [Översikt över scenarier](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md).

## Hur många moduler kan jag använda i ett scenario?

### Svar

Du kan använda så många moduler du vill i ett scenario. Du kan dela upp moduler i flöden och ange vilka data som ska flöda genom varje flöde. Du kan också använda utdata från en modul som indata till en annan modul.

Även om det inte finns någon gräns för antalet moduler i ett scenario, kan fler än 150 moduler påverka scenariots prestanda.

Mer information om moduler finns i [Modulöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md).

## Kan Workfront Fusion användas med filer?

### Svar

Ja. Workfront Fusion kan ta emot, spara, omvandla, konvertera och kryptera filer. Fusion har också ett stort antal inbyggda funktioner som gör att användarna kan arbeta effektivt och kreativt med de data som finns i filerna.

Mer information om hur du arbetar med filer i Fusion finns i [Mappa en fil mellan moduler](/help/workfront-fusion/create-scenarios/map-data/map-files.md).

## Vissa utlösare gör att scenarier kan köras direkt. Vad betyder&quot;direkt&quot;?

### Svar

Scenarier kan köras i intervall enligt det schema du anger, till exempel varje timme eller var femte minut. Det finns särskilda utlösare, så kallade direktutlösare (webhooks), som kan starta ditt scenario omedelbart efter att de har tagit emot data från en viss tjänst. Fusion bearbetar mottagna data direkt, utan att vänta på nästa schemalagda körning.

Mer information om skillnaden mellan avsökda utlösare och direktutlösare finns i [Utlösarmoduler](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) i översikten över artikelmodulen.

## Vad är en operation?

### Svar

En åtgärd är en åtgärd som utförs av en modul. En åtgärd inträffar t.ex. varje gång en utlösare körs och varje gång en åtgärd utför en åtgärd.

En del Fusion-planer baseras på det antal operationer som din organisation använder.

Mer information om åtgärder finns i [Åtgärder](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md).

## Vad är dataöverföring?

### Svar

Dataöverföring avser mängden data som överförs genom ditt scenario. Ett scenario som till exempel hämtar en 100 kB-bild från Workfront och sedan överför bilden till en dokumentlagringsleverantör. Mängden data som används i detta scenario är 200 kB.

## Vad är en anslutning?

### Svar

En anslutning är länken mellan ditt Workfront Fusion-konto och den tredjepartstjänst du vill använda. Anslutningen kan skapas när du redigerar ett scenario.

Mer information finns i [Anslutningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).

## Vad är aggregatorer?

### Svar

En [!UICONTROL Aggregator] sammanfogar data i en enda samling. Ett exempel på detta är filer som komprimeras till ett ZIP-arkiv och skickas som en e-postbilaga.

Mer information finns i [[!UICONTROL Aggregator] modul](/help/workfront-fusion/references/modules/aggregator-module.md).

## Vad händer om jag låter Workfront Fusion bearbeta ett e-postmeddelande som innehåller mer än en bifogad fil?

### Svar

Om du använder [!UICONTROL Email]-modulen [!UICONTROL Retrieve attachments] skickas varje bifogad fil individuellt genom resten av modulerna i scenariot. Liknande moduler är också tillgängliga i andra program som tar emot flera filer samtidigt.
