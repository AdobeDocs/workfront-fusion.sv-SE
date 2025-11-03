---
content-type: reference
title: Feltyper
description: Ibland kan ett fel inträffa när ett scenario körs. Detta händer vanligtvis om en tjänst inte är tillgänglig på grund av ett fel med anslutningen till en tjänst eller om en validering misslyckas. I den här artikeln beskrivs de vanligaste felen som kan uppstå.
author: Becky
feature: Workfront Fusion
exl-id: abf5f844-d13b-416e-a8b8-2d4ee1786262
source-git-commit: 99621f57da1eb294834a0eacfe527dcf017408e9
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%

---

# Feltyper

Ibland kan ett fel inträffa när ett scenario körs. Detta händer vanligtvis om en tjänst inte är tillgänglig på grund av ett fel med anslutningen till tjänsten eller om en validering misslyckas.

Adobe Workfront Fusion skiljer mellan flera grundläggande feltyper. Vilken typ av fel det är beror på vad ditt Fusion-scenario kommer att göra härnäst.

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

+++## Anslutningsfel 

`ConnectionError`

Anslutningsfel är ett av de vanligaste felen. De orsakas oftast av att tredjepartstjänsten inte är tillgänglig av olika orsaker, till exempel överbelastning, underhåll eller driftstopp. Standardhanteringen av det här felet beror på vilken modul som påträffade felet.

* Om felet inträffar i den första modulen avslutas körningen av scenariot med ett varningsmeddelande. Workfront Fusion försöker sedan upprepade gånger att köra scenariot igen med ökande tidsintervall. Om alla försök misslyckas inaktiverar Workfront Fusion scenariot.
* Om anslutningsfelet inträffar i en annan modul än i den första, är följande steg beroende av alternativet Tillåt lagring av ofullständiga körningar i scenariets avancerade inställningar:

   * Om det här alternativet är aktiverat flyttas körningen av scenariot till mappen [!UICONTROL Incomplete executions] där Workfront Fusion upprepade gånger försöker köra scenariot igen med ökande tidsintervall. Om alla försök misslyckas finns körningen kvar i mappen Ofullständiga körningar i väntan på manuell lösning av användaren.

     Mer information om ofullständiga körningar finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).
   * Om det här alternativet är inaktiverat avslutas körningen av scenariot med ett fel följt av en återställningsfas. Workfront Fusion försöker sedan upprepade gånger att köra scenariot igen med ökande tidsintervall. Om alla försök misslyckas inaktiverar Workfront Fusion scenariot.

  Mer information om inställningen Tillåt lagring av ofullständiga körningar finns i [Tillåt lagring av ofullständiga körningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) i artikeln Konfigurera scenarioinställningar.

### Öka tidsintervall

Algoritmen för ökning av tidsintervall mellan försök när ett fel inträffar kallas exponentiell säkerhetskopiering. De ökande tidsintervallen anges enligt följande:

1. 10 minuter
1. 1 timme
1. 3 timmar
1. 12 timmar
1. 24 timmar

Med de ökande tidsintervallen förhindras ofta utförda scenarier från att använda åtgärder vid upprepade misslyckade försök.

>[!BEGINSHADEBOX]

**Exempel:**

Ett scenario innehåller [!DNL Google Sheets]-utlösaren [!UICONTROL Watch Rows]. [!DNL Google Sheets] är inte tillgängligt på 30 minuter på grund av underhåll när Workfront Fusion startar scenariot, så det går inte att hämta nya rader. Scenariot stoppas och försöker igen om 10 minuter. Eftersom [!DNL Google Sheets] fortfarande inte är tillgängligt kan Workfront Fusion fortfarande inte få information om nya rader. Nästa omgång av scenariot är schemalagd om en timme. [!DNL Google Sheets] är tillgängligt igen för tillfället och scenariot kan köras.

>[!ENDSHADEBOX]

## Datafel

`DataError`

Ett datafel genereras när ett objekt är felaktigt mappat och inte godkänns vid den validering som utförs på Workfront Fusion-sidan eller på tredjepartstjänstens sida.

Om det här felet inträffar flyttas scenariot, fram till där modulen misslyckades, till mappen för ofullständiga körningar, där du kan felsöka problemet. Scenariot avbryts dock inte och fortsätter att köras enligt schemat. Om du vill stoppa körningen av scenariot när ett datafel visas aktiverar du alternativet Sekventiell bearbetning på panelen Scenarioinställningar.

Om du inte har aktiverat alternativet [!UICONTROL Allow storing incomplete executions] i scenarioinställningarna avslutas körningen av scenariot med felet och en återställning utförs.

## Fel vid duplicering av data

`DuplicateDataError`

Om Workfront Fusion försöker infoga samma paket två gånger i en tjänst som inte tillåter dubblettdata, genereras ett dubblettdatafel. Om detta fel inträffar fortsätter Workfront Fusion på samma sätt som för datafel.

Mer information finns i [Datafel](#data-error) i den här artikeln.


## Ogiltigt åtkomsttokenfel

`InvalidAccessTokenError`

Ett ogiltigt åtkomsttokenfel inträffar när Workfront Fusion inte kan komma åt ditt konto som registrerats hos en tredjepartstjänst. Detta inträffar vanligtvis när du återkallar åtkomsträttigheter för Workfront Fusion vid administration av en viss tjänst, men scenarier där tjänsten används fortsätter att köras enligt schemat.

Om det här felet inträffar stoppas körningen av scenariot omedelbart. Resten av scenariot med början från modulen där felet inträffade, flyttas till mappen för ofullständiga körningar.

## Hastighetsbegränsningsfel

`RateLimitError`

Om en gräns som angetts av en viss tjänst överskrids genereras ett hastighetsbegränsningsfel. Om det här felet inträffar fortsätter Workfront Fusion på samma sätt som för anslutningsfelet.

Mer information finns i [Anslutningsfel](#connection-error) i den här artikeln.

## Ofullständigt datafel

`IncompleteDataError`

Ett ofullständigt datafel inträffar bara med utlösare. Det här felet genereras om en utlösare inte kan hämta nödvändiga data från en viss tjänst.

Om ett scenario avslutas med `IncompleteDataError` beror det ytterligare beteendet på inställningen [!UICONTROL Max number of consecutive errors].

Mer information finns i [Antal efterföljande fel](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) i artikeln Konfigurera scenarioinställningar.

>[!BEGINSHADEBOX]

**Exempel:**

Ett scenario har Workfront-utlösaren [!UICONTROL Watch Record] inställd på att bevaka dokument. Scenariot körs medan du överför ett stort dokument, till exempel en lång video. Eftersom [!UICONTROL Workfront Fusion] försöker hämta videon medan den fortfarande överförs till Workfront avslutas scenariot med `IncompleteDataError`.

>[!ENDSHADEBOX]

## Körningsfel

`RuntimeError`

Alla fel som uppstår under scenariokörning och som inte är en av dessa feltyper rapporteras som `RunTimeError`.

Om ett scenario avslutas med `RuntimeError` beror det ytterligare beteendet på inställningen [!UICONTROL Max number of consecutive errors].

Mer information finns i [Antal efterföljande fel](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors) i artikeln Konfigurera scenarioinställningar.


>[!NOTE]
>
>Om ett scenario börjar med en direktutlösare och påträffar det här felet, ignoreras inställningen [!UICONTROL Max number of consecutive errors] och scenariot inaktiveras omedelbart.
>&#x200B;>Mer information finns i [Direktutlösare](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers) i översikten över artikelmodulerna.

## Inkonsekvens-fel

`InconsistencyError`

Om något av dessa fel inträffar under implementerings- eller återställningsfasen avslutas scenariot med ett inkonsekvens-fel.

Om det här felet uppstår i ett scenario stoppas körningen av scenariot omedelbart.

## Varning

När du kör ett scenario kan du få en varning som informerar dig om ett problem. En varning förhindrar inte att scenariot slutförs korrekt.

En varning kan till exempel visas när den största tillåtna filstorleken överskrids och alternativet [!UICONTROL Enable data loss] inaktiveras.

## Resurser

Mer information om mappning finns i [Mappningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md).

Mer information om ofullständiga körningar finns i [Visa och lös ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Mer information om scenarioinställningspanelen finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).

Mer information om scheman finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

Mer information om scenariofunktioner finns i [Scenariokörning, cykler och faser](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

Mer information om alternativet Aktivera dataförlust finns i [Aktivera dataförlust](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss) i artikeln Konfigurera scenarioinställningar.
