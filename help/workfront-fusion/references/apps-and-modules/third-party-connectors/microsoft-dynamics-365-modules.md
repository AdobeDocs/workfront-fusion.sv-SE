---
title: Microsoft Dynamics 365-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Microsoft Dynamics 365 samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: c377a24c2daeb25effffb28d9912d8c27ad0a08d
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics 365 modules]

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Microsoft Dynamics 365] samt ansluta det till flera tredjepartsprogram och -tjänster.

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365]-anslutningen stöder inte [!DNL Dynamics Finance and Operations].
>
>Mer information om [!DNL Microsoft Dynamics 365 Finance and Operations]-anslutningen finns i [[!DNL Microsoft Dynamics 365 Finance and Operations] moduler](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/dynamics-finance-operations-modules.md).

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Du måste ha ett [!DNL Microsoft Dynamics 365]-konto för att kunna använda [!DNL Microsoft Dynamics] 365.

## Anslut Microsoft Dynamics 365 till Workfront Fusion

Du kan skapa en anslutning till ditt [!DNL Microsoft Dynamics 365]-konto direkt inifrån en [!DNL Microsoft Dynamics 365]-modul.

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon [!DNL Microsoft Dynamics 365]-modul.


1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>Ange ett namn för anslutningen.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Environment]</td>
          <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Type]</td>
          <td>Välj om du vill ansluta till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>(Valfritt)</p></td>
          <td>Ange din [!DNL Microsoft Dynamics] [!UICONTROL Client ID].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Valfritt)</p></td>
          <td>Ange din [!DNL Microsoft Dynamics] [!UICONTROL Client Secret].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Ange den URL som din instans av Workfront ska använda för att autentisera anslutningen. <p>Standardvärdet är <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Resource]</td>
          <td>Ange adressen för ditt [!DNL Dynamics 365]-konto, utan <code>>https://</code>.</p>
        </tr>
      </tbody>
    </table>
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

>[!NOTE]
>
>Använd följande omdirigerings-URI när du registrerar [!DNL Workfront Fusion] i din [!DNL Microsoft Azure]-portal:
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## [!DNL Microsoft Dynamics 365]-moduler och deras fält

När du konfigurerar [!DNL Microsoft Dynamics 365] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Microsoft Dynamics 365] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

* [[!UICONTROL Watch Records (Real Time)]](#watch-records-real-time)
* [[!UICONTROL Watch Records (Scheduled)]](#watch-records-scheduled)

#### [!UICONTROL Watch Records (Real Time)]

Denna snabbutlösarmodul kör ett scenario när en post (objekt) som du anger skapas eller uppdateras i [!DNL Dynamics 365].

En webkrok krävs i den här modulen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj den webkrok som du vill använda för den här modulen. </p> <p>Så här lägger du till en ny webbkrok:</p> 
    <ol> 
     <li value="1"> <p>Klicka på <strong>[!UICONTROL Add]</strong> till höger om Webkrok-fältet</p> </li> 
     <li value="2"> <p>Skriv ett beskrivande namn för webkroken i fältet <strong>[!UICONTROL Webhook]</strong>.</p> </li> 
     <li value="3"> <p>I fältet <strong>[!UICONTROL Connection]</strong> väljer du den anslutning som du vill använda markerad</p> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </li> 
     <li value="4"> <p>Klicka på <strong>[!UICONTROL Save]</strong> om du vill spara din webkrok och gå tillbaka till modulen.</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Records (Scheduled)]

Denna schemalagda utlösarmodul kör ett scenario när en post i det objekt som du anger skapas eller uppdateras efter den senaste schemalagda körningen av detta scenario.

Modulens utdata anger om posten som hittades är ny eller uppdaterad. Om posten både lades till och uppdaterades under tidsperioden, returneras den som en ny post.

Detta sker regelbundet enligt ett schema som du anger.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> "
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>Välj om du vill att modulen ska bevaka <strong>[!UICONTROL New Records Only]</strong>, <strong>[!UICONTROL Updated Records Only]</strong> eller <strong>[!UICONTROL New and Updated Records]</strong>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Välj posttypen [!UICONTROL Microsoft Dynamics 365] som du vill att scenariot ska bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen. Fält är tillgängliga baserat på den valda entitetstypen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Create Record]](#create-record)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Delete Record]](#delete-record)
* [[!UICONTROL Read Records]](#read-records)
* [[!UICONTROL Update Record]](#update-record)


#### [!UICONTROL Create Record]

Den här åtgärdsmodulen skapar en entitet, till exempel en avtalad tid eller uppgift.

Du anger information om enheten som du vill skapa.

Modulen returnerar ID:t för den nya entiteten och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Välj den typ av enhet som du vill att modulen ska skapa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>Markera de fält som du vill inkludera värden för när posten skapas. Vilka fält som är tillgängliga beror på enhetstypen.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td> Det här är de fält som du markerade. Ange det värde som du vill att posten ska ha för en viss egenskap. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Record]

Den här åtgärdsmodulen tar bort en entitet.

Du anger ID:t för entiteten.

Modulen returnerar ID:t för entiteten och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>Välj den typ av enhet som du vill att modulen ska ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Ange eller mappa det unika [!DNL Microsoft Dynamics 365]-ID:t för posten som du vill att modulen ska ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Microsoft Dynamics 365]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Microsoft Dynamics 365]-modulerna.

Modulen returnerar information om statuskod, rubriker och brödtext. Du kan mappa den här informationen i efterföljande moduler i scenariot.

Mer information finns i [!DNL Microsoft]-dokumentationen om hur du använder [!DNL Dynamics 365 Customer Engagement Web API].

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Ange en relativ sökväg till <code>&lt;Instance URL>/api/data/v9.1/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> <p>För mer</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
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
 </tbody> 
</table>

#### [!UICONTROL Read Records]

Den här åtgärdsmodulen läser data från en enskild enhet i [!DNL Microsoft Dynamics 365].

Du anger ID:t för entiteten.

Modulen returnerar ID:t för entiteten och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Välj den typ av enhet som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa det unika [!DNL Microsoft Dynamics 365]-ID:t för posten som du vill att modulen ska läsa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Record]

Den här åtgärdsmodulen uppdaterar en entitet.

Du anger ID:t för entiteten.

Modulen returnerar ID:t för den uppdaterade posten och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Välj den typ av enhet som du vill att modulen ska uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>Markera de fält som du vill inkludera värden för när posten skapas. Vilka fält som är tillgängliga beror på enhetstypen.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td>Det här är de fält som du markerade. Ange det värde som du vill att posten ska ha för en viss egenskap.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa det unika [!DNL Microsoft Dynamics] 365-ID:t för posten som du vill att modulen ska uppdatera.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

#### [!UICONTROL Search Records]

Den här sökmodulen söker efter poster i ett objekt i [!DNL Microsoft Dynamics 365] som matchar den sökfråga du anger. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Microsoft Dynamics 365]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Microsoft Dynamics 365] till [!DNL Workfront Fusion]</a> i den här artikeln. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>Välj den typ av enhet som du vill att modulen ska uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filters]</td> 
   <td> <p>Välj det filter som du vill använda för sökningen.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Standard Filters]</strong> </p> <p>Ställ in filtret genom att markera ett fält och en operator och ange eller mappa värdet som du vill söka efter. Du kan använda AND- eller OR-regler för filtret.</p> </li> 
     <li> <p><strong>[!UICONTROL Query Functions]</strong> </p> <p>Ange den [!DNL Dynamics 365]-webb-API-frågefunktion som du vill använda för att söka. </p> <p>Mer information om frågefunktioner finns i <a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">Web API Query Function Reference</a> i dokumentationen för [!DNL Microsoft].</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>Ange i vilken ordning artiklar returneras. Du kan lägga till flera sorteringar.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>Ange fältet som du vill sortera resultaten efter.</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>Ange sorteringsriktningen (stigande eller fallande).</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>
