---
title: Slack moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Slack och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: c9c68a4c-f592-42d1-b15f-a525b9aa3944
source-git-commit: eb0518ba0d1a0c758cb547e362c722f4be3674c7
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 0%

---

# [!DNL Slack] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Slack] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs</p>
   <p>eller</p>
   <p>Äldre: Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront package: Your organization must purchase Adobe Workfront Fusion.</li><li>Ultimate Workfront-paket: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL Slack]-konto för att kunna använda [!DNL Slack]-moduler.

## Slack API-information

Slack Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>{{ifempty(parameters.domain, 'https://slack.com/api/')}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Slack]-moduler och deras fält

När du konfigurerar [!DNL Slack] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Slack] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Meddelanden](#messages)
* [Konversationer](#channels)
* [Övriga](#other)

### Meddelanden

* [Skapa ett meddelande](#create-a-message)
* [Ta bort ett meddelande](#delete-a-message)
* [Hämta ett meddelande för en privat kanal](#get-a-private-channel-message)
* [Hämta ett meddelande för offentlig kanal](#get-a-public-channel-message)
* [Uppdatera ett meddelande](#update-a-message)
* [Titta på privata kanalmeddelanden](#watch-private-channel-messages)
* [Titta på allmänna kanalmeddelanden](#watch-public-channel-messages)

### [!UICONTROL Create a Message]

Den här åtgärdsmodulen skapar ett nytt meddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Välj hur du vill markera kanalen där du vill skapa ett meddelande.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>I fältet <strong>[!UICONTROL Channel ID or name]</strong> anger eller mappar du kanal-ID:t eller namnet på den kanal där du vill skicka meddelandet.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Välj kanaltyp och sedan kanal.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>Ange textinnehållet i det meddelande som du vill skapa.</p> <p>Obs! Mer information om textformatering finns i <a href="https://api.slack.com/reference/surfaces/formatting">Formatera text för appytor</a> i [!DNL Slack] -dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL As user]</td> 
   <td>Aktivera det här alternativet om du vill publicera meddelandet som den användare som äger inloggningsuppgifterna som används i anslutningen för den här modulen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Thread message ID (time stamp)]</td> 
   <td>Om det nya meddelandet är ett svar anger du tidsstämpeln för det meddelande du vill svara på. Ange inte tidsstämpeln för ett meddelande som redan är ett svar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply broadcast]</td> 
   <td> <p>Välj <strong>[!UICONTROL Yes]</strong> om båda följande gäller:</p> 
    <ul> 
     <li> <p>Det nya meddelandet är ett svar på ett annat meddelande</p> </li> 
     <li> <p>Du vill att det nya meddelandet ska visas för alla i kanalen</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>För varje objekt som du vill bifoga till meddelandet klickar du på <b>Lägg till objekt</b> och fyller i informationen för objektet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Icon emoji]</td> 
   <td>Ange eller mappa det känslolägesikoner som ska användas som ikon för det här meddelandet, i formatet <code>:icon-name:</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Icon URL]</td> 
   <td>Ange eller mappa URL:en för bilden som ska användas som ikon för det här meddelandet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta att namn och kanaler använder formatet <code>@username</code> eller <code>#channel</code>. </p> <p>Mer information finns i <a href="https://api.slack.com/docs/formatting">Formatera text för appytor</a> i [!DNL Slack]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta automatisk tolkning. </p> <p>Mer information finns i <a href="https://api.slack.com/docs/formatting">Formatera text för appytor</a> i [!DNL Slack]-dokumentationen.</p> <p>Obs! Om du använde alternativen [!UICONTROL Link names] eller [!UICONTROL Parse message text] i det ursprungliga meddelandet bör du ange dem även när du kör modulen [!UICONTROL Update a Message].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use markdown]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta [!DNL Slack] att använda markering i texten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl primarily text-based content]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta borttagning av huvudsakligen textbaserat innehåll. </p> <p>Mer information om borttagning av länkar i [!DNL Slack] finns i <a href="https://api.slack.com/reference/messaging/link-unfurling">Ta bort länkar i meddelanden</a> i [!DNL Slack]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Unfurl media content]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta att medieinnehåll frigörs. </p> <p>Mer information om borttagning av länkar i [!DNL Slack] finns i <a href="https://api.slack.com/reference/messaging/link-unfurling">Ta bort länkar i meddelanden</a> i [!DNL Slack]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User name]</td> 
   <td>Ange det användarnamn som används för att skicka meddelandet. Om inget användarnamn anges används namnet "Bot".</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Delete a Message]

Den här åtgärdsmodulen tar bort ett angivet meddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Ange eller mappa kanal-ID:t.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Ange eller mappa tidsstämpeln för meddelandet som du vill ta bort.</p> <p>Obs! Tidsstämpeln kan hämtas med en annan modul, till exempel modulen Bevaka privata kanalmeddelanden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL As user]</td> 
   <td> <p> Aktivera det här alternativet om du vill ta bort meddelandet som användaren med de autentiseringsuppgifter som används i anslutningen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Private Channel Message]

Den här åtgärdsmodulen hämtar information om ett meddelande från en markerad kanal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Ange (mappa) kanal-ID:t.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> Ange eller mappa meddelandets tidsstämpel för meddelandet som du vill hämta information om.</p> <p>Obs! Tidsstämpeln kan hämtas med en annan modul, till exempel modulen [!UICONTROL Watch Private Channel Messages].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Public Channel Message]**

Den här åtgärdsmodulen returnerar ett meddelande med ett angivet ID från en angiven offentlig kanal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Ange eller mappa kanal-ID:t.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID (Time stamp)]</td> 
   <td> <p> Ange eller mappa meddelandets tidsstämpel för meddelandet som du vill hämta information om.</p> <p>Obs! Tidsstämpeln kan hämtas med en annan modul, till exempel modulen [!UICONTROL Watch Public Channel Messages].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Message]

Med den här åtgärdsmodulen kan du redigera ett befintligt meddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Choose how you want to select the message you want to .</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>In the <strong>[!UICONTROL Channel ID or name]</strong> field, enter or map the Channel ID or of the channel that contains the message, then enter the <strong>[!UICONTROL Time Stamp (Message ID)]</strong> of the message.</p> <p>Note: The Channel ID can be retrieved using the [!UICONTROL List Channels] module.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Select the type of channel, then select the channel, then select the message.</p> </li> 
    </ul> </td> 
  </tr> -->
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för kanalen som innehåller meddelandet som du vill uppdatera.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Message ID (Time stamp)]</p> </td> 
   <td> <p> Ange eller mappa meddelandets tidsstämpel för meddelandet som du vill hämta information om.</p> <p>Obs! Tidsstämpeln kan hämtas med en annan modul, till exempel modulen [!UICONTROL Watch Public Channel Messages].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Text]</p> </td> 
   <td> <p>Ange det nya textinnehållet i meddelandet som du vill uppdatera.</p> <p>Mer information finns i <a href="https://api.slack.com/docs/formatting">Formatera text för appytor</a> i [!DNL Slack]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL As user]</td> 
   <td>Aktivera det här alternativet om du vill uppdatera meddelandet som den användare som äger inloggningsuppgifterna som används i anslutningen för den här modulen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachments]</td> 
   <td>För varje objekt som du vill bifoga till meddelandet klickar du på <b>Lägg till objekt</b> och fyller i informationen för objektet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Link names]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta att namn och kanaler använder formatet <code>@username</code> eller <code>#channel</code>. </p> <p>Mer information finns i <a href="https://api.slack.com/docs/formatting">Formatera text för appytor</a> i [!DNL Slack]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse message text]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta automatisk tolkning. </p> <p> Mer information finns i <a href="https://api.slack.com/docs/formatting">Formatera text för appytor</a> i [!DNL Slack]-dokumentationen.</p> <p>Obs! Om du använde alternativen [!UICONTROL Link names] eller [!UICONTROL Parse message text] i det ursprungliga meddelandet bör du ange dem även när du kör modulen Uppdatera ett meddelande.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Watch Private Channel Messages]

Denna utlösarmodul startar scenariot när ett nytt meddelande läggs till i en privat kanal (grupp).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>Välj den privata kanal som du vill bevaka för nya meddelanden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet meddelanden som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Public Channel Messages]

Den här utlösarmodulen startar scenariot när ett nytt meddelande läggs till i en offentlig kanal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel] </td> 
   <td> <p>Välj den offentliga kanal som du vill bevaka för nya meddelanden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet meddelanden som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Konversationer

* [Skaffa en kanal](#get-a-channel)
* [Listkanaler](#list-channels)
* [Visa medlemmar i kanal](#list-members-in-channel)

#### [!UICONTROL Get a Channel]

Den här åtgärdsmodulen returnerar information om en arbetsytekanal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Channel ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för kanalen som du vill hämta information om.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </td> 
  </tr> 
 </tbody>

#### [!UICONTROL List Channels]

Den här sökmodulen returnerar en lista med alla kanaler på en arbetsyta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Exclude archived]</p> </td> 
   <td> <p>Välj [!UICONTROL Yes] om du vill exkludera arkiverade kanaler i resultat.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Välj den eller de kanaltyper som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet kanaler som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>
</table>

#### [!UICONTROL List Members in Channel]

Sökmodulen returnerar en lista med användare i den valda kanalen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
<tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Välj hur du vill markera meddelandet som du vill skicka.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>I fältet <strong>[!UICONTROL Channel ID or name]</strong> anger eller mappar du det kanal-ID eller den kanal som du vill visa användarna från.</p> <p>Obs! Channel-ID kan hämtas med modulen [!UICONTROL List Channels].</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Välj kanaltyp och sedan kanal.</p> </li> 
    </ul> </td> 
  </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet medlemmar som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Övriga

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Slack]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Slack]-modulerna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Slack]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code>https://slack.com/api/</code>. Exempel: <code>/users/identity</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td>Välj den bas-URL som du vill använda för API-anropet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Send access token]</td> 
   <td>Välj om du vill skicka åtkomsttoken som en rubrik eller som en frågeparameter.</td> 
  </tr> 
 </tbody> 
</table>

## Terminologi

Följande terminologi kan vara användbar när du konfigurerar [!DNL Slack] moduler:

* **DM**: [!UICONTROL Direct Message]
* **IM**: [!UICONTROL Instant Message]
* **Privat kanal**: tidigare [!UICONTROL Group]
* **Direktmeddelande**: tidigare [!UICONTROL IM]
* **Kanal**: [!UICONTROL Conversation] i API-dokumentationen, [!UICONTROL channel] i appen [!DNL Slack].
