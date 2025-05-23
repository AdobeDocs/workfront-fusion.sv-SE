---
title: ServiceNow-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder  [!DNL ServiceNow] samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 7b236869-bd83-4db5-a363-d6570f6e4aff
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 0%

---

# [!DNL ServiceNow] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL ServiceNow] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Du måste ha ett [!DNL ServiceNow]-konto för att kunna använda [!DNL ServiceNow]-moduler.

## ServiceNow API-information

ServiceNow-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://{{connection.instance}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.5.13</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL ServiceNow] till [!DNL Workfront Fusion]

Så här skapar du en anslutning för dina [!DNL ServiceNow]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan [!UICONTROL Connection] när du börjar konfigurera den första [!DNL ServiceNow]-modulen.
1. Ange följande:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>Ange ett namn för den nya [!DNL ServiceNow]-anslutningen.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Password]</p> </td> 
      <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Username]</p> </td> 
      <td>Ange ditt [!DNL ServiceNow]-användarnamn.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Password]</p> </td> 
      <td>Ange ditt ServiceNow-lösenord.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Instance]</p> </td> 
      <td> <p>Ange adressen för ditt [!DNL ServiceNow]-konto utan <code>https://</code> (vanligtvis <code>&lt;company>.service-now.com</code>).</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **Fortsätt** för att spara anslutningen och återgå till modulen.

   <!--Markdown placeholder-->

## [!UICONTROL ServiceNow]-moduler och deras fält

När du konfigurerar [!DNL ServiceNow] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL ServiceNow] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* Om en anpassad post har valts i ett [!UICONTROL Record type]-fält kan det ta lite tid att läsa in anpassade fält.
>
>* Om det inte finns några egna poster är listrutan Posttyp tom.

### Utlösare

#### [!UICONTROL Watch records]

Den här utlösarmodulen aktiverar ett scenario när en post skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Välj om tabellen du vill titta på är en anpassad tabell eller en standardtabell.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Välj vilken typ av värden du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill att modulen ska visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Välj om du vill bevaka nya poster eller uppdaterade poster.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Deactivate a User]](#deactivate-a-user)
* [[!UICONTROL Delete a record]](#delete-a-record)
* [[!UICONTROL Download an attachment]](#download-an-attachment)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Upload an attachment]](#upload-an-attachment)
* [[!UICONTROL Update a record]](#update-a-record)

#### [!UICONTROL Create a record]

Denna åtgärdsmodul skapar en ny [!DNL ServiceNow]-post.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Välj om du vill skapa en post i en anpassad tabell eller en standardtabell.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av [!DNL ServiceNow]-post som du vill att modulen ska skapa. Du kan sedan fylla i de tillgängliga fälten för den här posttypen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL ServiceNow]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL ServiceNow]-modulerna.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Relative URL]</td> 
   <td> Ange en relativ sökväg till <code>https://&ltinstance_url&gt/api/</code>. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> </td> 
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

#### [!UICONTROL Deactivate a User]

Den här åtgärdsmodulen inaktiverar en användare i [!DNL ServiceNow] genom att använda system-ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User System ID]</td> 
   <td> Ange eller mappa det unika [!DNL ServiceNow]-ID:t för användaren som du vill att modulen ska inaktivera.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a record]

Den här åtgärdsmodulen tar bort en incident eller en användare.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj om du vill ta bort en incident eller en användare.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL System ID]</td> 
   <td>Ange eller mappa det unika [!DNL ServiceNow]-ID:t för posten som du vill att modulen ska ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download an attachment]

Den här åtgärdsmodulen hämtar en bifogad fil i en [!DNL ServiceNow]-post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment System ID]</td> 
   <td> Ange eller mappa det unika [!DNL ServiceNow]-ID:t för den bifogade filen som du vill att modulen ska hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser en [!DNL ServiceNow]-post med system-ID.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record System ID]</td> 
   <td>Ange eller mappa det unika [!DNL ServiceNow]-ID:t för posten som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Välj om posten du vill läsa finns i en anpassad tabell eller i en standardtabell.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av [!DNL ServiceNow]-post som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Välj vilken typ av värden du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill att modulen ska visa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

Denna åtgärdsmodul skapar en ny [!DNL ServiceNow]-post.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record System ID]</td> 
   <td>Ange eller mappa det unika [!DNL ServiceNow]-ID:t för posten som du vill att modulen ska uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Välj om posten som ska uppdateras finns i en anpassad tabell eller i en standardtabell.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av [!DNL ServiceNow]-post som du vill att modulen ska uppdatera. Du kan sedan fylla i de tillgängliga fälten för den här posttypen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload an attachment]

Den här åtgärdsmodulen överför en bifogad fil till en [!DNL ServiceNow]-post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table name]</td> 
   <td>Ange eller mappa namnet på tabellen där du vill överföra den bifogade filen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL System ID]</td> 
   <td>Ange eller mappa det unika [!DNL ServiceNow]-ID:t för objektet som du vill överföra den bifogade filen till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

#### [!UICONTROL Search for records]

Den här modulen söker efter poster med hjälp av villkor som du väljer.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ServiceNow-kontot till [!DNL Workfront Fusion] finns i <a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL ServiceNow] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table type]</td> 
   <td>Välj om tabellen du vill söka i är en anpassad tabell eller en standardtabell.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill söka efter.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Välj om du vill att modulen ska returnera alla poster som matchar villkoret, eller bara den första posten som matchar det. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximal count of records]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search type]</td> 
   <td> <p>Välj vilken typ av sökning du vill att modulen ska utföra</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Advanced query]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL Search Query]</p> <p>Ange den anpassade sökfrågan. Mer information om [!DNL ServiceNow] anpassade sökfrågor finns i <a href="https://docs.servicenow.com/bundle/orlando-platform-user-interface/page/use/common-ui-elements/reference/r_OpAvailableFiltersQueries.html">ServiceNow-frågedokumentationen</a>.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Simple]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL Search Criteria]</p> <p>Ange villkoren som du vill att modulen ska söka efter. </li> 
       <li> <p>[!UICONTROL Sort by]</p> <p>Ange vilket fält du vill att modulen ska sortera resultaten efter och om de ska sorteras stigande eller fallande.</p> </li> 
      </ul> </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Display]</td> 
   <td>Välj vilken typ av värden du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill att modulen ska visa.</td> 
  </tr> 
 </tbody> 
</table>
