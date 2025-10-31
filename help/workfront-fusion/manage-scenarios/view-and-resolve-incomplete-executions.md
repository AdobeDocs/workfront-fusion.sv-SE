---
title: Visa och lösa ofullständiga körningar
description: Mappen [!UICONTROL Incomplete executions] lagrar scenariekörningar som inte slutfördes korrekt på grund av ett fel. Varje lagrad ofullständig körning kan lösas antingen manuellt eller automatiskt.
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: 42be02d6a59a5d7b8faccdcfe40e8b967153c6eb
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Visa och lösa ofullständiga körningar

Mappen [!UICONTROL Incomplete executions] lagrar scenariekörningar som inte slutfördes korrekt på grund av ett fel. Varje lagrad ofullständig körning kan lösas antingen manuellt eller automatiskt.

>[!NOTE]
>
>Som standard är lagring av ofullständiga körningar inaktiverat. Aktivera alternativet [!UICONTROL Allow storing incomplete executions] i scenariets avancerade inställningar om du vill aktivera det.
>
>Mer information om scenarioinställningar finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

## Markerad förhandsgranskning för hela artikeln {#highlighted-preview-article-level}

<span class="preview">Informationen på den här sidan hänvisar till funktioner som ännu inte är allmänt tillgängliga. Den är bara tillgänglig i förhandsvisningssandlådemiljön.</span>## Visa ofullständiga körningar

Om en modul påträffar ett fel under åtgärden läggs en ny ofullständig körning till i mappen Ofullständiga körningar. Varje ofullständig körning innehåller scenariots plan och alla paket som kan mappas till den misslyckade modulen. Du kan öppna listan över ofullständiga körningar genom att klicka på fliken [!UICONTROL Incomplete Executions] på sidan med scenariodetaljer.

<!--

![Incomplete executions tab](assets/incomplete-executions-tab-350x102.png)

-->

Mer information finns i [Fel som leder till ofullständiga körningar](#errors-resulting-into-incomplete-executions) i den här artikeln.

>[!NOTE]
>
>Den aktuella storleksgränsen för mappen för olösta ofullständiga körningar per scenario är 10 MB. Om ditt scenario överskrider denna gräns kan följande fel uppstå:
>
>`DLQ limit per scenario has been exceeded`
>
>Teamen är begränsade till totalt 500 MB för alla olösta ofullständiga körningar.
>
>Mer information finns i [Aktivera dataförlust](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) i artikeln Konfigurera scenarioinställningar.


## Lös ofullständiga körningar från fliken Ofullständiga körningar

När en ny ofullständig körning sparas kan du lösa den på följande sätt:

1. Öppna det påverkade scenariot.
1. Klicka på fliken **[!UICONTROL Incomplete Executions]**.
1. Leta reda på den ofullständiga körning som du vill lösa och klicka på **[!UICONTROL Details]**.
1. Öppna modulens logg där alla åtgärder i modulen visas.
1. Leta reda på den misslyckade åtgärden och klicka på **[!UICONTROL Resolve]**:

   ![Knappen Lös](assets/resolve-btn-350x188.png)



## Lös ofullständiga körningar från fliken Historik

Om du vill se loggen för alla åtgärder i modulen innan du försöker lösa den ofullständiga körningen kan du lösa den ofullständiga körningen från mappen [!UICONTROL History]:

1. Öppna det påverkade scenariot.
1. Klicka på fliken **[!UICONTROL History]**.
1. Leta reda på scenariets misslyckade körning och klicka på **[!UICONTROL Details]**.
1. Öppna modulens logg där alla åtgärder i modulen visas.
1. Leta reda på den misslyckade åtgärden och klicka på **[!UICONTROL Resolve]**:

   ![Knappen Lös](assets/resolve-btn-350x188.png)

## Alternativ för ofullständiga körningar

Följande alternativ på panelen [!UICONTROL Scenario settings] avgör om och hur de ofullständiga körningarna lagras:

* Tillåt lagring av ofullständiga körningar
* Sekventiell bearbetning
* Aktivera dataförlust

Mer information om de här alternativen finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

## Fel som leder till ofullständiga körningar

Det finns flera typer av fel som leder till att ofullständiga körningar lagras. Dessa kan omfatta:

* Valideringsfel som uppstår på grund av ofullständiga eller felaktiga data, huvudsakligen på grund av att ett objekt saknas som förväntas bearbeta alla data som går igenom en modul.
* Fel som uppstod när det slutliga målet inte var tillgängligt på grund av tillfälligt eller långvarigt anslutningsfel (t.ex. vid anslutning till e-post eller fjärr-FTP-server).

Om ett fel inträffar på den första modulen i scenariot avbryts körningen omedelbart och ingen ofullständig körning sparas.

Om ett fel inträffar i någon annan modul och det inte finns någon kopplad felhanterarväg händer något av följande:

* En ofullständig körningspost med automatiskt återförsök lagras för följande feltyper:

   * `ConnectionError`
   * `RateLimitError`
   * `OutOfSpaceError`
   * `ModuleTimeoutError`

* En ofullständig körningspost utan automatiskt försök lagras för följande feltyper:

   * `DataError`
   * `InvalidConfigurationError`
   * `InvalidAccessTokenError`
   * `UnexpectedError`
   * `MaxFileSizeExceededError`
   * `MaxResultsExceededError`

* Om feltypen är något annat än ovanstående misslyckas körningen.
