---
title: Marketo moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Marketo] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1880'
ht-degree: 0%

---

# [!DNL Marketo] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Marketo] samt ansluta det till flera tredjepartsprogram och -tjänster.

En videointroduktion till Marketo Connector finns på:

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

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

Du måste ha ett [!DNL Marketo]-konto för att kunna använda [!DNL Marketo]-moduler.

## Marketo API-information

Marketo Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.14.19</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Marketo] till Workfront Fusion {#connect-marketo-to-workfront-fusion}

Du kan skapa en anslutning till ditt [!DNL Marketo]-konto direkt inifrån en [!DNL Marketo]-modul.

1. Klicka på **Lägg till** bredvid anslutningsfältet i en Marketo-modul.
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
          <p>Ange ett namn för den nya anslutningen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Välj om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Account / Munchkin ID]</td>
        <td>
          <p>Ange ditt [!DNL Marketo]-konto eller [!DNL Marketo] [!UICONTROL Munchkin]-ID. Detta är den unika delen av bas-URL:en eller slutpunkten som tilldelats ditt konto och som du använder för att komma åt [!DNL Marketo] via dess [!UICONTROL REST]-API. Instruktioner om hur du hittar detta finns i [Bas-URL](https://developers.marketo.com/rest-api/base-url/) i [!DNL Marketo]-dokumentationen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange ditt Marketo klient-ID. Instruktioner om hur du hittar det här finns i [Autentisering](https://developers.marketo.com/rest-api/authentication/) i [!DNL Marketo]-dokumentationen.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din Marketo-klienthemlighet. Instruktioner om hur du hittar dessa finns i [Autentisering](https://developers.marketo.com/rest-api/authentication/) i [!DNL Marketo]-dokumentationen.</td>
      </tr>
     </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Marketo] moduler och deras fält

När du konfigurerar [!DNL Marketo]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Marketo] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

* [[!UICONTROL Watch events (Instant)]](#watch-events-instant)
* [[!UICONTROL Watch records]](#watch-records)

#### [!UICONTROL Watch events (Instant)]

Den här utlösarmodulen startar ett scenario när en post skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>Ange den webkrok som du vill att modulen ska använda.</p> <p>Mer information om webbhooks finns i <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webbhooks</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch records]

Den här utlösarmodulen startar ett scenario när en post skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Activity]</strong> </p> <p>Välj den aktivitetstyp som du vill bevaka. </p> <p>Modulen söker endast efter nya aktiviteter.<br></p> </li> 
     <li> <p><strong>[!UICONTROL Lead]</strong> </p> <p>I fältet <b>Händelsetyp</b> väljer du om du vill söka efter nya poster, uppdaterade poster, både nya och uppdaterade poster eller specifika fältuppdateringar. Om du väljer att bevaka specifika fältuppdateringar markerar du det fält som du vill att modulen ska bevaka.</p> </li> 
     <li> <p><strong>[!UICONTROL Program]</strong> </p> <p>I fältet <b>Händelsetyp</b> väljer du om du vill söka efter nya poster, uppdaterade poster eller både nya och uppdaterade poster.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add Leads to a List]](#add-leads-to-a-list)
* [[!UICONTROL Clone a Program]](#clone-a-program)
* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Custom API call]](#custom-api-call)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Remove Leads from a List]](#remove-leads-from-a-list)
* [[!UICONTROL Schedule a Campaign]](#schedule-a-campaign)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Upload a File]](#upload-a-file)

#### [!UICONTROL Add Leads to a List]

Den här åtgärdsmodulen lägger till en eller flera leads till en lista med lead-ID:t. Du kan lägga till upp till 300 leads i taget.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Ange eller mappa ID:t för listan där du vill lägga till leads.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>För varje lead som du vill lägga till i listan klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar sedan ID:t för det lead som du vill lägga till. Du kan lägga till upp till 300 leads för modulen som ska läggas till i listan.</p> <p>Klicka på kartväxeln för att mappa en befintlig samling leads som du vill lägga till i listan.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Clone a Program]

Den här åtgärdsmodulen gör en kopia av ett program med det befintliga programmets ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Existing Program ID]</td> 
   <td>Ange eller mappa ID:t för programmet som du vill kopiera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Program Name]</p> </td> 
   <td> <p>Ange eller mappa ett namn för det nya programmet</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Ange eller mappa ID:t för mappen där du vill att det nya programmet ska placeras.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a record]

Denna åtgärdsmodul skapar en ny post i [!DNL Marketo]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Folder]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>Om du skapar ett företag eller en lead markerar du de fält som du vill ange värden för när den nya posten skapas och anger sedan värden för dessa fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Type]</td> 
   <td>Om du skapar ett program väljer du vilken typ av program du vill skapa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Channel] </td> 
   <td>Om du skapar ett program väljer du den programkanal där du vill skapa programmet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Program Name]</td> 
   <td>Om du skapar en mapp eller ett program anger eller mappar du ett namn för den nya posten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>Om du skapar en mapp eller ett program anger eller mappar du en beskrivning av den nya posten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID]</td> 
   <td>Om du skapar en mapp eller ett program anger eller mappar du ID:t för den överordnade mappen där du vill skapa den nya posten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>Om du skapar ett program lägger du till kostnader.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>Om du skapar ett program lägger du till taggar</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Marketo]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Marketo]-modulerna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code>https://{your-base-url}.mktorest.com/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
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
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>För varje fält som du vill lägga till i API-anropet klickar du på <b>Lägg till objekt</b> och anger fältets nyckel och värde.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

Den här åtgärdsmodulen hämtar en fil med hjälp av fil-ID:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Ange eller mappa ID:t för filen som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser information om en post med hjälp av dess ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> 
    <ul> 
     <li> <p>[!UICONTROL Campaign]</p> </li> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL List]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Välj den information som du vill inkludera i utdatapaketet för den här modulen. Fälten är tillgängliga baserat på den [!UICONTROL Record Type] du har valt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL &lt;Object> ID]</td> 
   <td>Ange eller mappa ID:t för objektet som du vill hämta information om.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Leads from a List]

Den här åtgärdsmodulen tar bort en eller flera leads från en lista med lead-ID:t. Du kan ta bort upp till 300 leads i taget.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Ange eller mappa ID:t för listan där du vill ta bort leads.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Lead IDs]</td> 
   <td> <p>För varje lead som du vill ta bort från listan klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar sedan ID:t för det lead som du vill ta bort. Du kan lägga till upp till 300 leads för modulen som ska tas bort från listan. </p> <p>Klicka på kartväxeln för att mappa en befintlig samling leads som du vill ta bort från listan.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Schedule a Campaign]

Den här åtgärdsmodulen schemalägger en befintlig kampanj för ett visst datum.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Ange eller mappa ID:t för kampanjen som du vill schemalägga.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Schedule for Date]</p> </td> 
   <td>Välj det datum då du vill att kampanjen ska köras. Om fältet lämnas tomt körs kampanjen fem minuter efter att scenariot börjar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

Den här åtgärdsmodulen uppdaterar en befintlig post med dess ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> 
    <ul> 
     <li> <p>[!UICONTROL Company]</p> </li> 
     <li> <p>[!UICONTROL Lead]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Company] / [!UICONTROL Lead] / [!UICONTROL Program ID]</td> 
   <td>Ange eller mappa ID:t för den post som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select fields to map]</td> 
   <td>Om du uppdaterar ett företag eller en lead markerar du de fält som du vill uppdatera värden för och anger sedan värden för dessa fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Program Name]</td> 
   <td>Om du uppdaterar ett program anger eller mappar du ett nytt namn för programmet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>Om du uppdaterar ett program anger eller mappar du en ny beskrivning av programmet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Om du uppdaterar ett program anger eller mappar du ett nytt startdatum för programmet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Om du uppdaterar ett program anger eller mappar du ett nytt slutdatum för programmet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Costs]</td> 
   <td>Om du uppdaterar ett program lägger du till några kostnader.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td>Om du uppdaterar ett program lägger du till taggar</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

Den här åtgärdsmodulen överför en ny fil till [!UICONTROL Marketo].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Ange eller mappa ID:t för mappen där du vill att den nya filen ska placeras.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange en beskrivning för den överförda filen.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL List records]](#list-records)
* [[!UICONTROL Search Records]](#update-a-record)

#### [!UICONTROL List records]

Denna åtgärdsmodul hämtar alla poster av en viss typ.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill visa.</p> 
    <ul> 
     <li> <p>[!UICONTROL Read all campaigns]</p> </li> 
     <li> <p>[!UICONTROL Read all programs]</p> </li> 
     <li> <p>[!UICONTROL Read all leads] </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field]</td> 
   <td>Om du har valt att hämta leads väljer du om du vill hämta leads från en lista eller från ett program.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Välj den information som du vill inkludera i utdatapaketet för den här modulen. Fälten är tillgängliga baserat på den [!UICONTROL Record Type] du har valt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Records]

Den här sökmodulen hämtar en lista med poster som matchar specifika sökvillkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Marketo]-konto till Workfront Fusion finns i <a href="#connect-marketo-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Marketo] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj den typ av post som du vill söka efter.</p> 
    <ul> 
     <li> <p>[!UICONTROL Campaigns]</p> </li> 
     <li> <p>[!UICONTROL Leads]</p> </li> 
     <li> <p>[!UICONTROL Programs]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Field]</p> </td> 
   <td> <p>Markera fältet som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value / values]</td> 
   <td>Ange värdet för det fält som du vill söka efter. Om fältet tillåter dig att söka efter flera värden, för varje värde som du vill söka efter, klickar du på <b>[!UICONTROL Add item]</b> och anger värdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
