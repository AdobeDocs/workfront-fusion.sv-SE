---
title: Visa och lösa ofullständiga körningar
description: Mappen [!UICONTROL Incomplete executions] lagrar scenariekörningar som inte slutfördes korrekt på grund av ett fel. Varje lagrad ofullständig körning kan lösas antingen manuellt eller automatiskt.
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: 3d06958b6f706f4f974230853fb6553232656fd3
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---

# Visa och lösa ofullständiga körningar

Mappen [!UICONTROL Incomplete executions] lagrar scenariekörningar som inte slutfördes korrekt på grund av ett fel. Varje lagrad ofullständig körning kan lösas antingen manuellt eller automatiskt.

>[!NOTE]
>
>Som standard är lagring av ofullständiga körningar inaktiverat. Aktivera alternativet [!UICONTROL Allow storing incomplete executions] i scenariets avancerade inställningar om du vill aktivera det.
>
>Mer information om scenarioinställningar finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

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

## Visa ofullständiga körningar

Om en modul påträffar ett fel under åtgärden läggs en ny ofullständig körning till i mappen Ofullständiga körningar. Varje ofullständig körning innehåller scenariots plan och alla paket som kan mappas till den misslyckade modulen. Du kan öppna listan över ofullständiga körningar genom att klicka på fliken [!UICONTROL Incomplete Executions] på sidan med scenariodetaljer.

<!--

![](assets/incomplete-executions-tab-350x102.png)

-->

Mer information finns i [Fel som leder till ofullständiga körningar](#errors-resulting-into-incomplete-executions) i den här artikeln.

>[!NOTE]
>
>Den aktuella storleksgränsen för mappen för olösta ofullständiga körningar per organisation är 500 MB. Om din organisation överskrider denna gräns kan följande fel uppstå:
>
>`"There is NOT ENOUGH SPACE to add a bundle to the IEQ. The reason is: Too many incomplete executions."`
>
>Mer information finns i [Aktivera dataförlust](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) i artikeln Konfigurera scenarioinställningar.


## Lös ofullständiga körningar från fliken Ofullständiga körningar

När en ny ofullständig körning sparas kan du lösa den på följande sätt:

1. Öppna det påverkade scenariot.
1. Klicka på fliken **[!UICONTROL Incomplete Executions]**.
1. Leta reda på den ofullständiga körning som du vill lösa och klicka på **[!UICONTROL Details]**.


## Lös ofullständiga körningar från fliken Historik

Om du vill se loggen för alla åtgärder i modulen innan du försöker lösa den ofullständiga körningen kan du lösa den ofullständiga körningen från mappen [!UICONTROL History]:

1. Öppna det påverkade scenariot.
1. Klicka på fliken **[!UICONTROL History]**.
1. Leta reda på scenariets misslyckade körning och klicka på **[!UICONTROL Details]**.
1. Öppna modulens logg där alla åtgärder i modulen visas.
1. Leta reda på den misslyckade åtgärden och klicka på **[!UICONTROL Resolve]**:

   ![](assets/resolve-btn-350x188.png)

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

* Om feltypen är `ConnectionError`, `RateLimitError`, `OutOfSpaceError` eller `ModuleTimeoutError` lagras en ofullständig körningspost med automatiskt återförsök.
* Om feltypen är `DataError`, `InvalidConfigurationError`, `InvalidAccessTokenError`, `UnexpectedError`, `MaxFileSizeExceededError` eller `MaxResultsExceededError` lagras en ofullständig körningspost utan autoåterförsök.
* Om feltypen är något annat än ovanstående misslyckas körningen.
