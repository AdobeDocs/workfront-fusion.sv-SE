---
title: Direktutlösare (webhooks)
description: Många tjänster tillhandahåller webbhookar för att leverera snabbmeddelanden när en viss förändring inträffar i tjänsten. Om du vill bearbeta dessa meddelanden rekommenderar vi att du använder snabbutlösare. I den här artikeln beskrivs användningen och funktionaliteten hos direktutlösare i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 5bfda2b2-dc1c-4ff6-9236-b480bfda2e58
source-git-commit: 4c0f050e40d28f236d6086e7dccea53d49252aa8
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Direktutlösare (webhooks)

Många tjänster tillhandahåller webhooks för att leverera snabbmeddelanden när en viss ändring (händelse) inträffar i tjänsten. Om du vill bearbeta de här händelserna rekommenderar vi att du använder snabbutlösare. Direktutlösare visar taggen `Instant` i listan med moduler för en given koppling.

![](assets/instant.png)

>[!TIP]
>
>Du kan kontrollera listan med moduler i en koppling för att se om den har en direktutlösare, eller så kan du kontrollera den anslutarens dokumentation under [Fusion-program och deras modulreferenser](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
>
>Dokumentation om Adobe Workfront direktutlösare finns i [Utlösare](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#triggers) i artikeln Workfront-moduler.

Om en anslutning inte innehåller någon webkrok kan du göra något av följande:

* Skapa en anpassad webkrok med Webkrok-modulen.
Mer information finns i [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).
* Använd avsökningsutlösare för att regelbundet avsöka tjänsten.
Mer information finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)

En videointroduktion till webbhooks i Workfront Fusion finns på:

* [Introduktion till Webhooks](https://video.tv.adobe.com/v/3427025/){target=_blank}
* [Mellanliggande webbhooks](https://video.tv.adobe.com/v/3427030/){target=_blank}

## Schemalägg direktutlösare

När du konfigurerar en direktutlösare uppmanas du att välja när den körs.

![](assets/schedule-setting.png)

Välj `Immediately` om du vill köra scenariot omedelbart när [!DNL Workfront Fusion] tar emot nya händelser från tjänsten. Dessa händelser skickas omedelbart till en kö och bearbetas sedan i scenariot en i taget i samma ordning som data tas emot.

När scenariot körs räknas det totala antalet väntande händelser som väntar i kön, och scenariot utför så många cykler som det finns väntande händelser, och en händelse bearbetas per cykel.

Mer information om cykler finns i [Scenariokörning, cykler och faser](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

>[!NOTE]
>
>* En cykel är inte detsamma som en scenariokörning. Det kan finnas flera cykler i en och samma scenario.
>* När du kör ett scenario med en utlösare som är schemalagd att köras `Immediately` gäller följande undantag:
>
>     * Intervallet mellan två körningar omfattas inte av minimiintervallet enligt prissättningsplanen.
>
>       När till exempel scenariot har slutförts kontrolleras webbkrokens kö igen. Om det finns några väntande webbhooks körs scenariot omedelbart igen och alla väntande webbhooks bearbetas igen.
>   
>     * Inställningen för maximalt antal cykler ignoreras och ställs in på 100, vilket innebär att högst 100 väntande webbhooks bearbetas under en enda scenariokörning (med en hastighet på 1 händelse per cykel).
>


Om du använder någon annan schemainställning än [!UICONTROL Immediately] körs scenariot med de intervall du anger. Eftersom det går att samla in flera webbböcker i kön under intervallet rekommenderar vi att du anger ett högre värde för alternativet [!UICONTROL Maximum number of cycles] än standardvärdet 1 för att bearbeta fler webbhooks i en enda scenariokörning:

1. Klicka på ikonen [!UICONTROL Scenario settings] ![](assets/scenario-settings-icon.png) längst ned i ditt scenario.
1. På panelen **[!UICONTROL Scenario settings]** som visas anger du en siffra i fältet **[!UICONTROL Max number of cycles]** som anger antalet händelser från kön som du vill köra varje gång du kör scenariot.

Återstående händelser i kön bearbetas nästa gång scenariot körs, upp till det antal som anges i fältet Max antal cykler.

## Webkrokskyddsräcken

För att säkerställa goda prestanda har Workfront Fusion följande skyddsräcken på plats för webhooks.

### Kursgränser

Den aktuella hastighetsgränsen är 5 webbhooks per sekund. Om gränsen överskrids returneras en `429`-statuskod.

### Inaktiva webhooks förfaller

En webkrok som inte har tilldelats något scenario på mer än 120 timmar tas bort.

### Webkrok-nyttolaster

[!DNL Workfront Fusion] lagrar webkrocknyttolaster i 30 dagar. Om du får åtkomst till en webkrok-nyttolast mer än 30 dagar efter att den skapades uppstår felet [!UICONTROL `Failed to read file from storage.`]

### Felhantering

När det finns ett fel i ditt scenario med en direktutlösare:

* Stoppar omedelbart när scenariot är inställt på att köra [!UICONTROL Immediately].
* Stoppar efter 3 misslyckade försök (3 fel) när scenariot är inställt på att köras enligt schema.

Om ett fel inträffar under scenariokörningen placeras händelsen tillbaka i kön under snabbutlösarens återställningsfas. I sådana fall kan du åtgärda scenariot och köra det igen.

Mer information finns i [Återställning](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) i artikeln Scenariokörning, cykler och faser.

Om det finns en Webkroks svarsmodul i ditt scenario skickas felet till Webkroks svar. Webkroks svarsmodul körs alltid sist (när alternativet [!UICONTROL Auto commit] i scenarieinställningarna inte är aktiverat).

Mer information finns i [Svara på webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md#responding-to-webhooks) i artikeln Webbhooks.

### Webkroks-inaktivering

Webhooks inaktiveras automatiskt om något av följande gäller:

* Webbkroken har inte varit ansluten till något scenario på mer än fem dagar.
* Webkroken används bara i inaktiva scenarier, som har varit inaktiva i mer än 30 dagar.

Inaktiverade webhooks tas bort och avregistreras automatiskt om de inte är anslutna till några scenarier och har varit i inaktiveringsstatus i över 30 dagar.

## Anpassade webbhotell

Du kan skapa egna webbböcker. Mer information finns i [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

## Resurs

Mer information om cykler finns i [Scenariokörning, cykler och faser](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).
