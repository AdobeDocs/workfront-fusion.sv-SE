---
title: Google Calendar-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Google Calendar samt ansluta den till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 6e514204-cd8e-4f30-bbbb-b8fbe48fc670
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '3312'
ht-degree: 0%

---

# [!DNL Google Calendar] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!UICONTROL Google Calendar] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

Du måste ha ett [!DNL Google]-konto för att kunna använda [!DNL Google Calendar]-moduler.

## API-information för Google Calendar

Google Calendar-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://www.googleapis.com/calendar/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v5.4.5</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Calendar]-moduler och deras fält

När du konfigurerar [!DNL Google Calendar] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Calendar] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Händelser](#events)
* [Kalendrar](#calendars)
* [Åtkomstkontrollregler](#access-control-rules)
* [Iteratorer (borttagna)](#iterators-deprecated)
* [Övriga](#other)

### Händelser

* [[!UICONTROL Watch events]](#watch-events)
* [[!UICONTROL Search events]](#search-events)
* [[!UICONTROL Get an event]](#get-an-event)
* [[!UICONTROL Create an event]](#create-an-event)
* [[!UICONTROL Update an event]](#update-an-event)
* [[!UICONTROL Delete an event]](#delete-an-event)


#### [!UICONTROL Watch events]

Den här utlösarmodulen kör ett scenario när en ny händelse läggs till, uppdateras, tas bort, startas eller avslutas i den kalender du anger. Modulen returnerar alla standardfält som är associerade med posten eller posterna, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>Markera den kalender som du vill att modulen ska arbeta med.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch Events]</td> 
   <td> <p>Välj om du vill se händelser efter Skapad den, Uppdaterad den, Startdatum eller Slutdatum.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show deleted events]</td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera händelser som har tagits bort.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] </td> 
   <td> <p>Ange den text som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p> Ange det maximala antalet händelser som [!DNL Workfront Fusion] kan arbeta med under en cykel (antalet upprepningar per scenariokörning). Om värdet är för högt kan anslutningen avbrytas på sidan om den angivna tredjepartstjänsten (timeout). [!DNL Workfront Fusion] har ingen påverkan på detta. Vi rekommenderar att du anger ett lägre värde och antingen definierar ett högre värde för det maximala antalet cykler eller kör scenariot oftare.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search events]

Den här åtgärdsmodulen söker efter en händelse i den valda kalendern.

Du anger kalendern och parametrarna för sökningen.

Modulen returnerar händelsens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender som du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p> Ange eller mappa datumet då händelsen startar. Den här modulen hämtar även händelser som börjar före det här datumet och som fortfarande inträffar på det angivna startdatumet. </p> <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> Ange eller mappa datumet när händelsen slutar. </p> <p> En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Single events]</td> 
   <td> <p> Aktivera det här alternativet om du vill behandla återkommande händelser som enskilda instanser. Om du till exempel har ett veckomöte och det här alternativet är aktiverat, returnerar modulen varje veckas möte som en separat händelse.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>Ange eller mappa söktermen som du vill söka efter. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td> <p>Välj ordningen för de händelser som returneras i resultatet.</p> 
    <ul> 
     <li><strong>[!UICONTROL Start Time]</strong>: Ordna efter startdatum och -tid (stigande). Detta är endast tillgängligt när du frågar efter enstaka händelser.</li> 
     <li><strong>[!UICONTROL Updated Time]</strong>: Ordna efter senaste ändringstid (stigande).</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>Ange det maximala antalet händelser som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an event]

Den här åtgärdsmodulen returnerar metadata för en enskild händelse i den angivna kalendern.

Du anger kalendern och händelsen.

Modulen returnerar ID:t för händelsen och alla associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Ange eller mappa ID:t för kalendern som innehåller händelsen som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID] </td> 
   <td> <p>Ange händelse-ID:t för den befintliga [!DNL Google Calendar]-händelsen som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an event]

Den här åtgärdsmodulen skapar en händelse.

Du anger kalendern och parametrarna för händelsen.

Modulen returnerar händelsens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create an Event]</td> 
   <td> <p>Välj hur du vill skapa händelsen.</p> 
    <ul> 
     <li><b>[!UICONTROL In Detail]</b><p>Med det här alternativet kan du ange mer information om händelsen.<br></p></li> 
     <li><b>[!UICONTROL Quickly]</b><p>Du behöver bara välja kalendern och ange ett namn för händelsen. Du kan inkludera tids- och platsinformation i namnet, så schemalägger [!DNL Google Calendar] händelsen för den platsen och tiden.</p></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender där du vill att händelsen ska visas.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Color]</td> 
   <td>Välj den färg som händelsen ska visa i kalendern.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event name]</td> 
   <td> <p> Ange eller mappa ett namn för händelsen. </p> <p>Obs! Om du har markerat [!UICONTROL Quick add] i fältet [!UICONTROL Create an event] kan du inkludera datum och tid för händelsen och [!DNL Workfront Fusion] skapar händelsen för det datumet och den tiden. Exempel: <code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>. Om du valde [!UICONTROL Quick add] men inte inkluderade ett datum och en tid i händelsenamnet, skapas händelsen från den aktuella tiden och varar en timme.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL All day event]</td> 
   <td>Aktivera det här alternativet om händelsen är en heldagshändelse (kräver inte start- och sluttider).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Start date]</td> 
   <td> <p>Om det här är en heldagshändelse anger du händelsens startdatum. </p> <p>En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL End date]</td> 
   <td> <p> Om det här är en heldagshändelse anger du slutdatumet för händelsen. </p> <p>En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för händelsen. Det här fältet stöder HTML.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Location]</td> 
   <td>Ange en plats för händelsen i textformuläret.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use the default reminder settings for this event]</td> 
   <td>Aktivera det här alternativet om du vill använda standardinställningar för påminnelser. Om du ställer in en anpassad påminnelse i fältet [!UICONTROL Reminder] ställs värdet in på Nej.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Reminder] </td> 
   <td> <p>Lägg till påminnelse för händelsen. För varje påminnelse väljer du den metod som du vill bli påmind med och definierar hur länge (i minuter) före händelsen som du vill bli påmind med.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attendees]</td> 
   <td>Lägg till deltagarna i evenemanget. Ange eller mappa namn och e-postadress för varje deltagare.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show me as]</td> 
   <td>Välj om du vill att personer som visar din kalender ska se dig som upptagen eller Tillgänglig under den här händelsen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Visibility] </td> 
   <td> <p>Välj synlighet för den här händelsen. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Default]</b></p> <p>Händelsen har den synlighet som du har angett i kalenderinställningarna.</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>Alla som kalendern delas med kan se den här händelsen.</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>Endast deltagare kan se den här händelsen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event creation]</td> 
   <td> <p>Välj om du vill skicka meddelanden om att en ny händelse har skapats till alla gäster, till icke-[!DNL Google Calendar] gäster eller till ingen.</p> <p>Tips! Vi rekommenderar att du bara använder alternativet [!UICONTROL None] för migreringsfall.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Guests can modify the event]</td> 
   <td> <p>Aktivera det här alternativet om du vill att gäster ska kunna ändra den här händelsen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Recurrence]</td> 
   <td>Lägg till regler för upprepning som du vill tillämpa på den här händelsen. Varje regel kräver en lista med [!UICONTROL RRULE], [!UICONTROL EXRULE], [!UICONTROL RDATE] och [!UICONTROL EXDATE] rader för en återkommande händelse. Observera att [!UICONTROL DTSTART]- och [!UICONTROL DTEND]-rader inte tillåts i det här fältet. Händelsens start- och sluttider anges i start- och slutfälten. Det här fältet utelämnas för enstaka händelser eller förekomster av återkommande händelser. Mer information finns i <a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a>.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an event]

Denna åtgärdsmodul ändrar en befintlig händelse.

Du anger kalender- och händelse-ID.

Modulen returnerar händelsens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar] </td> 
   <td> <p>Välj den kalender som du vill arbeta med.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID] </td> 
   <td> <p>Ange händelse-ID:t från den tidigare skapade [!DNL Google Calendar]-händelsen som du vill uppdatera.</p> </td> 
  </tr> 
 </tbody> 
</table>

Du kan uppdatera händelseinformationen genom att ange nya värden i det önskade fältet. Mer information om enskilda fält finns i [[!UICONTROL Create an event]](#create-an-event).

#### [!UICONTROL Delete an event]

Denna åtgärdsmodul tar bort en händelse.

Du anger kalender- och händelse-ID.

Modulen returnerar händelsens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Markera kalendern som innehåller händelsen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Event ID]</td> 
   <td> <p> Ange händelse-ID:t från en [!DNL Google Calendar]-händelse som du vill ta bort tidigare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notification about the event deletion]</td> 
   <td>Välj om du vill skicka meddelanden om borttagning av händelser till alla gäster, gäster som inte använder [!DNL Google Calendar] eller ingen.</td> 
  </tr> 
 </tbody> 
</table>

### Kalendrar

* [[!UICONTROL List calendars]](#list-calendars)
* [[!UICONTROL Get a calendar]](#get-a-calendar)
* [[!UICONTROL Create a calendar]](#create-a-calendar)
* [[!UICONTROL Update a calendar]](#update-a-calendar)
* [[!UICONTROL Delete a calendar]](#delete-a-calendar)
* [[!UICONTROL Clear a calendar]](#clear-a-calendar)

#### [!UICONTROL List calendars]

Den här åtgärdsmodulen returnerar kalendrarna i en användares kalenderlista.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Minimum access role]</td> 
   <td> <p>Välj den lägsta åtkomstrollen för användaren. Modulen returnerar kalendrar baserat på den här minimala åtkomstrollen.</p> 
    <ul> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>: Användaren kan läsa ledig/upptagen-information. </li> 
     <li><strong>[!UICONTROL Owner]</strong>: Användaren kan läsa och ändra händelser och få åtkomst till kontrollistor. </li> 
     <li><strong>[!UICONTROL Reader]</strong>: Användaren kan läsa händelser som inte är privata. </li> 
     <li><strong>[!UICONTROL Writer]</strong>: Användaren kan läsa och ändra händelser.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show hidden calendars]</td> 
   <td>Aktivera det här alternativet om du vill inkludera dolda kalendrar i listan som modulen returnerar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange det maximala antalet kalendrar som [!DNL Workfront Fusion] returnerar under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a calendar]

Den här åtgärdsmodulen hämtar en kalender.

Du anger ID:t för den kalender som du vill hämta.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a calendar]

Den här åtgärdsmodulen skapar en ny kalender.

Du anger ett namn för kalendern.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name]</td> 
   <td> <p> Ange ett namn för den nya kalendern.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a calendar]

Den här åtgärdsmodulen uppdaterar en kalender.

Du anger ID:t för den kalender som du vill uppdatera.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Markera den kalender som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar name]</td> 
   <td> <p> Ange ett nytt namn för kalendern.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a calendar]

Den här åtgärdsmodulen tar bort en kalender.

Du anger ID:t för den kalender som du vill ta bort.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>Ange eller mappa ID:t för kalendern som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clear a calendar]

Den här åtgärdsmodulen tar bort alla händelser från ett kontos primära kalender.

Du anger anslutningen som ansluter till kontot som innehåller kalendern som du vill rensa.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtkomstkontrollregler

* [[!UICONTROL List access control rules]](#list-access-control-rules)
* [[!UICONTROL Get an access control rule]](#get-an-access-control-rule)
* [[!UICONTROL Create an access control rule]](#create-an-access-control-rule)
* [[!UICONTROL Update an access control rule]](#update-an-access-control-rule)
* [[!UICONTROL Delete an access control rule]](#delete-an-access-control-rule)

#### [!UICONTROL List access control rules]

Den här åtgärdsmodulen returnerar reglerna i åtkomstkontrollistan i en kalender.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender som innehåller de åtkomstkontrollsregler som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange det maximala antalet resultat som [!DNL Workfront Fusion] returnerar under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an access control rule]

Den här åtgärdsmodulen returnerar metadata för en åtkomstkontrollsregel.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender som innehåller åtkomstkontrollsregeln som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Access control rule ID]</td> 
   <td>Välj den åtkomstkontrollsregel som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an access control rule]

Den här åtgärdsmodulen skapar en ny åtkomstkontrollsregel.

Du anger ett namn för kalendern.

Modulen returnerar ID:t för åtkomstkontrollsregeln och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Välj den kalender där du vill skapa en åtkomstkontrollsregel.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Role]</td> 
   <td> <p>Välj den roll som ska tilldelas åtkomstregeln. </p> 
    <ul> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>: Användaren kan läsa ledig/upptagen-information. </li> 
     <li><strong>[!UICONTROL Owner]</strong>: Användaren kan läsa och ändra händelser och få åtkomst till kontrollistor. </li> 
     <li><strong>[!UICONTROL Reader]</strong>: Användaren kan läsa händelser som inte är privata. </li> 
     <li><strong>[!UICONTROL Writer]</strong>: Användaren kan läsa och ändra händelser.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type]</td> 
   <td> <p>Välj typ av scope. </p> 
    <ul> 
     <li><strong>[!UICONTROL Default]</strong>: Den offentliga omfattningen. Det här är standardvärdet. </li> 
     <li><strong>[!UICONTROL User]</strong>: Begränsar omfattningen till en enskild användare. </li> 
     <li><strong>[!UICONTROL Group]</strong>: Begränsar omfattningen till en grupp. </li> 
     <li><strong>[!UICONTROL Domain]</strong>: Begränsar scopet till en domän. </li> 
    </ul> <p>Obs! Behörigheterna för [!UICONTROL Default], eller det offentliga, omfånget gäller för alla användare, autentiserade eller inte.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Value]</td> 
   <td>Ange e-postadressen till en användare eller grupp, eller namnet på en domän, beroende på typ av scope.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notifications]</td> 
   <td> <p>Aktivera det här alternativet om du vill skicka meddelanden om åtkomständringen. </p> <p>Obs! Inga meddelanden om borttagning av åtkomst visas. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an access control rule]

Den här åtgärdsmodulen uppdaterar en åtkomstkontrollsregel.

Du anger ett namn för kalendern.

Modulen returnerar ID:t för åtkomstkontrollsregeln och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Markera den kalender som innehåller åtkomstkontrollsregeln som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Access control rule ID]</td> 
   <td>Välj den åtkomstkontrollsregel som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Role]</td> 
   <td> <p>Välj den roll som ska tilldelas åtkomstregeln. </p> 
    <ul> 
     <li><strong>[!UICONTROL None]</strong>: Den här rollen ger ingen åtkomst.</li> 
     <li><strong>[!UICONTROL Free Busy Reader]</strong>: Användaren kan läsa ledig/upptagen-information. </li> 
     <li><strong>[!UICONTROL Owner]</strong>: Användaren kan läsa och ändra händelser och få åtkomst till kontrollistor. </li> 
     <li><strong>[!UICONTROL Reader]</strong>: Användaren kan läsa händelser som inte är privata. </li> 
     <li><strong>[!UICONTROL Writer]</strong>: Användaren kan läsa och ändra händelser.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Send notifications]</td> 
   <td> <p>Aktivera det här alternativet om du vill skicka meddelanden om åtkomständringen. </p> <p>Obs! Inga meddelanden om borttagning av åtkomst visas. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an access control rule]

Den här åtgärdsmodulen tar bort en åtkomstkontrollsregel.

Du anger ett namn för kalendern.

Modulen returnerar ID:t för åtkomstkontrollsregeln och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendar ID]</td> 
   <td> <p>Markera eller mappa ID:t för kalendern som innehåller den åtkomstkontrollsregel som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Access control rule ID]</td> 
   <td>Markera eller mappa ID:t för åtkomstkontrollsregeln som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

### Iteratorer (borttagna)

Modulerna [!UICONTROL iterate attachments] och [!UICONTROL iterate attendees] har tagits bort. Använd modulen [!UICONTROL Flow Control] > [!UICONTROL Iterator] för att iterera igenom bilagor eller deltagare. Mer information finns i [Iterator-modulen](/help/workfront-fusion/references/modules/iterator-module.md)

### Övriga

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Get Free/Busy Information]](#get-freebusy-information)

#### [!UICONTROL Make an API Call]

Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe [!DNL Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td>Ange en relativ sökväg till <code>https://www.googleapis.com/calendar</code>. Exempel: <code>/v3/users/me/calendarList</code></td> 
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

#### [!UICONTROL Get Free/Busy Information]

Den här åtgärdsmodulen returnerar ledig och upptagen-information för en uppsättning kalendrar.

Modulen returnerar ID:t för kalendern och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Google Calendar]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Minimum time]</td> 
   <td> <p> Ange början på intervallet som du vill hämta information för.</p> <p> En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum time]</td> 
   <td> <p> Ange slutet på intervallet som du vill hämta information för. </p> <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Calendars]</td> 
   <td> <p>För varje kalender som du vill hämta information från klickar du på <strong>Lägg till</strong> och anger eller mappar kalender-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Utlösa ett scenario före en händelse

Du kan utlösa ett scenario en viss tid före en händelse med hjälp av standardpåminnelser för [!DNL Google Calendar] och modulen [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook].

1. Använd modulen [!UICONTROL Google Calendar] >[!UICONTROL Update an event] för att lägga till en e-postpåminnelse till din händelse:

   ![](/help/workfront-fusion/references/apps-and-modules/assets/trigger-scen-before-event-350x209.png)

1. Skapa ett nytt scenario som börjar med modulen [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook].

   1. Kopiera postlådans e-postadress.
   1. Spara scenariot och kör det.

1. I [!DNL Gmail] omdirigerar du e-postpåminnelserna för [!DNL Google Calendar] till e-postadressen för postlådan:

   1. Öppna din **[!UICONTROL [!DNL Gmail] settings]**.
   1. Öppna fliken **[!UICONTROL Forwarding and POP/IMAP]**.
   1. Klicka på **[!UICONTROL Add a forwarding address].**
   1. Klistra in e-postadressen för de kopierade postlådorna, klicka på &#x200B;**[!UICONTROL Next]**, bekräfta genom att trycka på **[!UICONTROL Proceed]** i popup-fönstret och sedan klicka på **[!UICONTROL OK]**.

   1. I [!DNL Workfront Fusion] växlar du till det nya scenariot som ska slutföra körningen genom att ta emot bekräftelsemeddelandet via e-post.
   1. Klicka på bubblan ovanför modulen för att kontrollera modulens utdata.
   1. Expandera objektet `Text` och kopiera bekräftelsekoden:

      ![](/help/workfront-fusion/references/apps-and-modules/assets/confirmation-code-350x252.png)

   1. I Gmail klistrar du in bekräftelsekoden i redigeringsrutan och klickar på &#x200B;**[!UICONTROL Verify]**:

      ![](/help/workfront-fusion/references/apps-and-modules/assets/paste-code-350x46.png)

   1. Öppna fliken **[!UICONTROL Filters and Blocked Addresses]**.
   1. Klicka på **[!UICONTROL Create a new filter]**.
   1. Konfigurera ett filter för alla e-postmeddelanden som kommer från `     calendar-notification@google.com` och klicka på &#x200B;**[!UICONTROL Create a filter]**:
   1. Välj **[!UICONTROL Forward it to]** och välj e-postadressen för postlådorna i listan.
   1. Klicka på **[!UICONTROL Create filter]** för att skapa filtret.

1. (Valfritt) I [!DNL Workfront Fusion] lägger du till modulen [!UICONTROL Text parser] > [!UICONTROL Match pattern] efter modulen [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook] för att tolka e-postens HTML-kod så att du får den information du behöver.

   Du kan till exempel konfigurera modulen på följande sätt för att hämta händelsens ID:

   *Mönster*: `<meta itemprop="eventId/googleCalendar" content="(?<evenitID>.*?)"/>`

   *Text*: Objektet `HTML content` som skrivs ut från modulen [!UICONTROL Webhooks] >[!UICONTROL Custom mailhook].
