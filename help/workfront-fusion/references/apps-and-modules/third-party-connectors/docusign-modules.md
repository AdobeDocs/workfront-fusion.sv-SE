---
title: DocuSign-moduler
description: Med modulerna  [!DNL Adobe Workfront Fusion DocuSign] kan du övervaka och hämta kuvertstatus, söka efter och hämta kuvert eller hämta och skicka ett dokument för signering på ditt [!DNL DocuSign] konto.
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1934'
ht-degree: 0%

---

# DocuSign-moduler

Med Adobe Workfront Fusion [!DNL DocuSign]-modulerna kan du övervaka och hämta kuvertstatus, söka efter och hämta kuvert eller hämta och skicka ett dokument för signering på ditt [!DNL DocuSign]-konto.

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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL DocuSign]-konto för att kunna använda [!DNL DocuSign]-moduler.

## API-information för DocuSign

DocuSign-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>1.18.11</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL DocuSign] till Workfront Fusion {#connect-docusign-to-workfront-fusion}

Så här skapar du en anslutning för dina [!DNL DocuSign]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan [!UICONTROL Connection] när du börjar konfigurera den första [!DNL DocuSign]-modulen.
1. Ange följande:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Ange ett namn för den nya [!DNL DocuSign]-anslutningen.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td>Ange om du ansluter till en produktion i en icke-produktionsmiljö.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>Välj om du vill ansluta till kontot är ett produktionskonto eller ett demokonto.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **Fortsätt** för att spara anslutningen och återgå till modulen.

## [!DNL DocuSign]-moduler och deras fält

När du konfigurerar [!DNL DocuSign]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL DocuSign] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

#### [!UICONTROL Watch envelopes]

Den här utlösarmodulen startar ett scenario när ett kuvert skickas, levereras, signeras, slutförs eller avvisas.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">Ansluta dokument till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller de poster som du vill bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p> Välj vilken typ av händelse du vill bevaka.</p> 
    <ul> 
     <li>[!UICONTROL Document completed]</li> 
     <li>[!UICONTROL Document declined]</li> 
     <li>[!UICONTROL Document sent]</li> 
     <li>[!UICONTROL Document signed]</li> 
     <li>[!UICONTROL New document in Inbox]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Outputs]</p> </td> 
   <td> <p>Markera de fält som du vill inkludera i modulutdata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska arbeta med under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add a custom field]](#add-a-custom-field)
* [[!UICONTROL Add Recipient to Envelope]](#add-recipient-to-envelope)
* [[!UICONTROL Create a new envelope]](#create-a-new-envelope)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download a document]](#download-a-document)
* [[!UICONTROL Modify custom field]](#modify-custom-field)
* [[!UICONTROL Read an envelope]](#read-an-envelope)
* [[!UICONTROL Send envelope]](#send-envelope)
* [[!UICONTROL Upload a file to an envelope]](#upload-a-file-to-an-envelope)

#### [!UICONTROL Add a custom field]

Den här åtgärdsmodulen lägger till ett anpassat fält i dokumentet

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller dokumentet där du vill lägga till ett anpassat fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för kuvertet som innehåller dokumentet där du vill lägga till ett anpassat fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>Ange eller mappa ett namn för det nya fältet som du vill lägga till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>Aktivera det här alternativet om du vill att det tillagda fältet ska vara ett obligatoriskt fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>Aktivera det här alternativet om du vill att fältet ska vara synligt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>Ange eller mappa värdet (innehållet) för det tillagda fältet. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Recipient to Envelope]

Den här åtgärdsmodulen lägger till en eller flera mottagare i ett befintligt kuvert. Om kuvertet redan har skickats skickas ett e-postmeddelande till mottagaren. Den här modulen är inte giltig för kuvert som redan har slutförts.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt DocuSign-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Account] </td>
   <td> <p>Välj det konto som innehåller kuvertet där du vill lägga till mottagare.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Envelope ID]</td>
    <td>Markera eller mappa ID:t för kuvertet där du vill lägga till mottagaren.</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[!UICONTROL Recipient type]</td>
   <td> <p> Välj den typ av mottagare som du vill lägga till i kuvertet.</p> 
    <ul> 
     <li> <p>[!UICONTROL Agent]</p> </li> 
     <li> <p>[!UICONTROL Carbon copy]</p> </li> 
     <li> <p>[!UICONTROL Certified delivery]</p> </li> 
     <li> <p>[!UICONTROL In-person signer]</p> </li> 
     <li> <p>[!UICONTROL Intermediary]</p> </li> 
     <li> <p>[!UICONTROL Signer]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Email]</td>
   <td> <p>Ange eller mappa e-postadressen till mottagaren som du vill lägga till i kuvertet.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Name]</td>
   <td>Ange eller mappa namnet på mottagaren som du vill lägga till i kuvertet.</td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Routing order]</td>
   <td> <p>Ange eller mappa routningsnumret för mottagaren. Routningsnummer avgör i vilken ordning mottagarna tar emot och signerar dokumenten.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Email body]</td>
   <td>Ange eller mappa brödtexten (innehållet) i e-postmeddelandet som skickas till mottagaren.</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>Ange eller mappa ämnet för det e-postmeddelande som skickas till mottagaren.</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> Om du vill skicka ett privat meddelande till mottagaren anger eller mappar du texten i meddelandet. <p>Det är bara den valda mottagaren som ser det privata meddelandet samt det allmänna meddelandet. Det privata meddelandet får innehålla högst 1 000 tecken.</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>Välj den autentiseringsmetod som du vill använda för att bekräfta mottagarens identitet.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>Ange eller mappa åtkomstkoden.</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>Ange eller mappa telefonnumret.</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>Ange eller mappa telefonnumret.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a new envelope]

Den här åtgärdsmodulen skapar ett nytt kuvert från en mall. Det returnerar det nya kuvertets ID samt statusen för det nya kuvertet.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td>

<td> <p>Instruktioner om hur du ansluter ditt DocuSign-konto till Workfront Fusion finns i artiklarna under <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Account] </td>
   <td> <p>Välj det konto som innehåller kuvertet där du vill överföra en fil.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template]</td>
   <td> <p> Välj den mall som du vill skapa det nya kuvertet från. Mallar är tillgängliga baserat på den [!UICONTROL Account] du valt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>Välj om du vill spara kuvertet som ett utkast eller skicka det för signering.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>För varje mottagare som du vill lägga till i kuvertet klickar du på <b>Lägg till objekt</b> och anger följande information:
    <ul>
    <li><b>Åtkomstkod</b><p>Ange eller mappa koden som mottagaren använder för att komma åt kuvertet.<p></li>
    <li><b>E-post</b><p>Ange eller mappa mottagarens e-postadress.<p></li>
    <li><b>Namn</b><p>Ange eller mappa namnet på mottagaren.<p></li>
    <li><b>Rollnamn</b><p>Ange eller mappa rollnamnet för mottagaren.<p></li>
    <li><b>Routningsordning</b><p>Ange eller mappa routningsnumret för mottagaren. Routningsnummer avgör i vilken ordning mottagarna tar emot och signerar dokumenten.<p></li>
    </ul>
    </td>
    </tr>
  <tr> 
   <td role="rowheader">
     [!UICONTROL Allow Print and Sign]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill att mottagaren ska kunna skriva ut dokumentet och signera det.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Allow Reassign]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill att mottagaren ska kunna tilldela om dokumenten till en annan användare.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Allow Recipient Recursion]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta mottagarrekursion.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Authoritative copy]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill markera dokumenten i det här kuvertet som auktoritativa kopior.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Auto Navigation]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill ange automatisk navigering för mottagaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Brand ID]
   </td> 
   <td> <p>Ange eller mappa varumärkets ID.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Markup Enabled]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill aktivera dokumentkod.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Expire Enabled]
   </td> 
   <td> <p>Aktivera det här alternativet om du vill ange en förfallotid för kuvertet. Om du aktiverar det här alternativet fyller du i följande fält:<ul><li><b>Förfaller efter</b><p>Ange eller mappa det antal dagar efter vilket kuvertet förfaller.</p></li><li><b>Varning vid förfallodatum</b><p>Ange eller mappa det antal dagar innan ett påminnelsemeddelande skickas till mottagaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Body]
   </td> 
   <td> <p>Ange eller mappa brödtexten (innehållet) i e-postmeddelandet som medföljer kuvertet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL Subject]
   </td> 
   <td> <p>Ange eller mappa ämnet för e-postmeddelandet som medföljer kuvertet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>Ange eller mappa kontot som du vill använda för att komma åt [!DNL DocuSign]-API:t.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Ange eller mappa en sökväg i förhållande till <code>https://&lt;BASE_URI>/v2/accounts/&lt;ACCOUNT_ID>.</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Detta avgör begärans innehållstyp.</p> <p>Exempel:<code> {"Content-type":"application/json"}</code></p> <p>Obs! Om du får felmeddelanden och det är svårt att fastställa deras ursprung bör du överväga att ändra rubrikerna baserat på Workfront-dokumentationen. Om ditt anpassade API-anrop returnerar ett 422 HTTP-begärandefel kan du försöka med att använda rubriken"Content-Type":"text/plain".</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet resultat som ska bearbetas under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:** Listkuvert

Följande API-anrop returnerar kuvert från det angivna datumet i ditt [!DNL DocuSign]-konto:

**URL**: `/v2.1/accounts/{accountId}/envelopes/`

**Metod**: `GET`

**Frågesträng**:

* **Nyckel**: `from_date`

* **Värde**: `YYYY-MM-DD`

Anger när begäran börjar söka efter statusändringar för kuvert i kontot.

![Exempel på Docusign-konfiguration](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)

Resultatet finns i modulens Utdata under Paket > Brödtext > Omslag.

I vårt exempel returnerades 6 kuvert:

![Exempel på dokumentutdata](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

>[!ENDSHADEBOX]

#### [!UICONTROL Download a document]

Den här åtgärdsmodulen hämtar ett enstaka dokument.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller dokumentet som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för kuvertet som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Document ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för dokumentet som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Certificate]</td> 
   <td>Aktivera det här alternativet om du vill inkludera kuvertsigneringscertifikatet i hämtningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>Aktivera det här alternativet om du vill tillåta mottagarna att hämta dokument efter användar-ID. Om en användare till exempel ingår i två olika routningsordningar med olika synligheter, returnerar det här alternativet alla dokument från båda routningarna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>Aktivera det här alternativet om du vill att de PDF-byte som returneras i svaret ska krypteras för alla nyckelhanterare som har konfigurerats på ditt [!DNL DocuSign]-konto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>Välj språk.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td>Aktivera det här alternativet om du vill markera ändrade fält för den returnerade PDF som är markerade i gult och markera valfria signaturer eller initialer i rött.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>Aktivera det här alternativet om du vill aktivera vattenstämpelfunktionen. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify custom field]

Den här åtgärdsmodulen ändrar ett anpassat fält med fältnamnet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller dokumentet där du vill ändra ett anpassat fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för kuvertet som innehåller dokumentet där du vill ändra ett anpassat fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field ID]</td> 
   <td>Ange eller mappa ID:t för fältet som du vill ändra.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>Ange eller mappa namnet på fältet som du vill ändra.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>Aktivera det här alternativet om du vill att det ändrade fältet ska vara ett obligatoriskt fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>Aktivera det här alternativet om du vill att fältet ska vara synligt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>Ange eller mappa värdet (innehållet) för det ändrade fältet. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read an envelope]

Den här åtgärdsmodulen läser information om ett kuvert i [!DNL DocuSign] med kuvert-ID.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller dokumentet som du vill läsa information från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för kuvertet som innehåller dokumentet som du vill läsa information från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de egenskaper som du vill ska visas i modulens utdata. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send envelope]

Den här åtgärdsmodulen skickar ett utkast till mottagarna.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Markera det konto som innehåller det utkast som du vill skicka till mottagarna.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för det utkast som du vill skicka till mottagarna.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file to an envelope]

Den här modulen överför en angiven fil till ett befintligt kuvert i DocuSign.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL DocuSign]-konto till Workfront Fusion finns i <a href="#connect-docusign-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL DocuSign] till Workfront Fusion </a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>Välj det konto som innehåller kuvertet där du vill överföra en fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> Ange eller mappa ID:t för kuvertet där du vill överföra en fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Välj en källfil från en tidigare modul eller ange källfilens namn och data.</td> 
  </tr> 
 </tbody> 
</table>
