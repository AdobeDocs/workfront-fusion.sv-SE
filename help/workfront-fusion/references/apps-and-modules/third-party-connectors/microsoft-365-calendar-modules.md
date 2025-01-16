---
title: Microsoft Office 365-kalender
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Microsoft Office 365-kalender samt ansluta den till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: fdecf740-e735-4569-b1a2-7c25c751ba42
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1586'
ht-degree: 0%

---

# [!DNL Microsoft Office 365 Calendar]

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Microsoft Office 365 Calendar] samt ansluta det till flera tredjepartsprogram och -tjänster.

Om du vill använda [!DNL Office 365 Calendar] med [!DNL Adobe Workfront Fusion] måste du ha ett [!DNL Office 365 Excel]-konto. Du kan skapa en på [www.office.com](https://www.office.com/).

Instruktioner om hur du ansluter Office 365-kontot till [!DNL Workfront Fusion] finns i [Skapa en anslutning till Adobe [!DNL Workfront Fusion]  - Grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

När du har gett ditt samtycke omdirigeras du tillbaka till administrationssidan för [!UICONTROL Workfront Fusion] där du kan fortsätta skapa ditt scenario.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Du måste ha ett [!DNL Microsoft Office 365 Calendar]-konto för att kunna använda [!DNL Microsoft Office 365 Calendar]-moduler.

## API-information för Microsoft Office 365-kalender

Microsoft Office 365 Calendar-anslutningen har följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## Ansluter tjänsten [!DNL Office 365 Calendar] till [!DNL Workfront Fusion]

Instruktioner om hur du ansluter ditt [!DNL Office 365 Calendar]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

## [!DNL Microsoft Office 365 Calendar]-moduler och deras fält

När du konfigurerar [!DNL Microsoft Office 365 Calendar] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Microsoft Office 365 Calendar] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Händelse](#event)
* [Kalender](#calendar)
* [Övriga](#other)

### Händelse

* [[!UICONTROL Watch Events]](#watch-events)
* [[!UICONTROL Search Events]](#search-events)
* [[!UICONTROL Get an Event]](#get-an-event)
* [[!UICONTROL Create an Event]](#create-an-event)
* [[!UICONTROL Update an Event]](#update-an-event)
* [[!UICONTROL Delete an Event]](#delete-an-event)

#### [!UICONTROL Watch Events]

Den här utlösarmodulen hämtar information om en händelse när händelsen skapas, uppdateras, tas bort, startas eller avslutas i den valda kalendern.

>[!NOTE]
>
>Om du vill bevaka om en händelseserie har tagits bort väljer du [!UICONTROL By Updated Time] i fältet [!UICONTROL Watch events]. Den här modulen bevakar inte borttagna enstaka händelser eller borttagna händelseserier.


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch events]</td> 
   <td> <p>Välj hur du vill se händelser.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By Created Time]</strong> </p> <p>Håll utkik efter nya händelser.</p> </li> 
     <li> <p><strong>[!UICONTROL By Updated Time]</strong> </p> <p>Håll utkik efter uppdaterade händelser.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>Välj den [!UICONTROL calendar group] som innehåller kalendern där du vill bevaka händelser.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>Välj den kalender som du vill titta på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Ange filtervillkoren för att filtrera resultaten efter ämne, händelse-ID eller brödtext.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange det maximala antalet meddelanden som [!DNL Workfront Fusion] ska returnera under en körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Events]

Den här sökmodulen hämtar information om en händelse när händelsen skapas, uppdateras, tas bort, startas eller avslutas i den valda kalendern.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>Välj den [!UICONTROL calendar group] som innehåller kalendern där du vill bevaka händelser.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>Välj den kalender som du vill titta på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Ange filtervillkoren för att filtrera resultaten. Du kan filtrera efter följande egenskaper:</p> 
    <ul> 
     <li>[!UICONTROL Subject]</li> 
     <li>[!UICONTROL Event ID]</li> 
     <li>[!UICONTROL Created Date Time]</li> 
     <li>[!UICONTROL Last Modified Date Time]</li> 
     <li>[!UICONTROL Body Preview]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>Välj hur du vill ordna resultaten.</p> 
    <ul> 
     <li><strong>[!UICONTROL Subject]</strong>, stigande eller fallande</li> 
     <li><strong>[!UICONTROL Created Date Time]</strong>, stigande eller fallande</li> 
     <li><strong>[!UICONTROL Last Modified Date Time]</strong>, stigande eller fallande</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange det maximala antalet händelser som [!DNL Workfront Fusion] ska returnera under en körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Event]

Den här åtgärdsmodulen hämtar information om den angivna händelsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Ange eller mappa ID:t för händelsen som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an Event]

Denna åtgärdsmodul skapar en ny händelse.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange eller mappa en titel för den skapade händelsen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> Ange en enstaka tidpunkt när händelsen börjar i en kombinerad datum- och tidsbeteckning. Använd formatet <code>({date}T{time}</code>, till exempel <code>2017-08-29T04:00:00.0000000</code>. En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> Ange en enda tidpunkt när händelsen slutar i en kombinerad datum- och tidsbeteckning. Använd formatet <code>{date}T{time}</code>, till exempel <code>2017-08-29T04:00:00.0000000</code>. En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>Välj om du vill aktivera en påminnelse för den här händelsen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>Ange eller mappa antalet minuter innan händelsen börjar när påminnelsen ska utlösas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj hur viktig den här händelsen är.</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>Välj känsligheten för den här händelsen.</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Personal]-meddelande.</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Private]-meddelande. Den här händelsen vidarebefordras eller omdirigeras inte av mottagarens inkorgsregler.</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Confidential]-meddelande. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>Ange om brödtexten ska vara oformaterad text eller HTML.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>Ange eller mappa texten i meddelandet som är associerat med händelsen. Det kan vara i HTML eller textformat (som anges i fältet [!UICONTROL Body Content Type] ovan).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>Ange information om händelsens plats.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>Välj <strong>[!UICONTROL Yes]</strong> om du vill att inbjudaren ska skicka ett svar på händelseinbjudan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>Välj hur du vill att händelsen ska visas för personer som visar kalendern.</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!UICONTROL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>Lägg till deltagare för evenemanget.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange deltagarens namn.</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>Ange deltagarens e-postadress.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>Ange eller mappa de kategorier som du vill att händelsen ska visas som i kalendern.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an Event]

Den här åtgärdsmodulen uppdaterar en befintlig händelse.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td>Ange, mappa eller välj ID:t för händelsen som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange eller mappa en titel för den skapade händelsen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> Ange en enstaka tidpunkt när händelsen börjar i en kombinerad datum- och tidsbeteckning. Använd formatet <code>{date}T{time}</code>, till exempel <code>2017-08-29T04:00:00.0000000</code>. En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> Ange en enda tidpunkt när händelsen slutar i en kombinerad datum- och tidsbeteckning. Använd formatet <code>({date}T{time}</code>, till exempel <code>2017-08-29T04:00:00.0000000</code>. En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>Välj om du vill aktivera en påminnelse för den här händelsen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>Ange eller mappa antalet minuter innan händelsen börjar när påminnelsen ska utlösas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj hur viktig den här händelsen är.</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>Välj känsligheten för den här händelsen.</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Personal]-meddelande.</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Private]-meddelande. Den här händelsen vidarebefordras eller omdirigeras inte av mottagarens inkorgsregler.</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>Mottagaren ser ett [!UICONTROL Please treat this as Confidential]-meddelande. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>Ange om meddelandets brödtext är oformaterad text eller HTML.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>Ange eller mappa texten i meddelandet som är associerat med händelsen. Det kan vara i HTML eller textformat (som anges i fältet [!UICONTROL Body Content Type] ovan).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>Ange information om händelsens plats.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>Välj <strong>[!UICONTROL Yes]</strong> om du vill att inbjudaren ska skicka ett svar på händelseinbjudan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>Välj hur du vill att händelsen ska visas för personer som visar kalendern.</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!DNL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>Lägg till deltagare för evenemanget.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange deltagarens namn.</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>Ange deltagarens e-postadress.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>Ange eller mappa de kategorier som du vill att händelsen ska visas som i kalendern.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Event]

Denna åtgärdsmodul tar bort en befintlig händelse.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Ange eller mappa ID:t för händelsen som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Kalender

* [[!UICONTROL List Calendars]](#list-calendars)
* [[!UICONTROL Get a Calendar]](#get-a-calendar)
* [[!UICONTROL Create a Calendar]](#create-a-calendar)
* [[!UICONTROL Update a Calendar]](#update-a-calendar)
* [[!UICONTROL Delete a Calendar]](#delete-a-calendar)

#### [!UICONTROL List Calendars]

Den här sökmodulen hämtar en lista över alla autentiserade användares kalendrar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>Markera [!UICONTROL calendar group] som innehåller de kalendrar som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange det maximala antalet kalendrar som [!DNL Workfront Fusion] ska returnera under en körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Calendar]

Den här åtgärdsmodulen hämtar information om en enskild kalender.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>Ange eller mappa ID:t för den kalender som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Calendar]

Den här åtgärdsmodulen skapar en ny kalender i ditt Google-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar name]</td> 
   <td> <p>Ange ett namn för den nya kalendern.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Calendar]

Denna åtgärdsmodul redigerar en befintlig kalender.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>Ange [!UICONTROL Calendar ID] för kalendern som du vill uppdatera. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Calendar name]</td> 
   <td> <p>Ange ett namn för den nya kalendern.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Calendar]

Denna åtgärdsmodul tar bort en befintlig kalender.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>Ange [!UICONTROL Calendar]-ID:t för kalendern som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

### Övriga

#### [!UICONTROL Make an API Call]

Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till <code>https://graph.microsoft.com</code>. Exempel:<code> /v1.0/me/events</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] lägger till autentiseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!   <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
