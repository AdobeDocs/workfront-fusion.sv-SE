---
title: Bredda moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!UICONTROL Widen] samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 0%

---

# [!DNL Widen] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!UICONTROL Widen] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Du måste ha ett [!UICONTROL Widen]-konto för att kunna använda [!UICONTROL Widen]-moduler.

## Bredd API-information

För Widen-anslutningen används följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.10.11</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Widen] till Workfront Fusion  {#connect-widen-to-workfront-fusion}

Du kan skapa en anslutning till ditt [!DNL Widen]-konto direkt inifrån en [!DNL Widen]-modul.

1. Klicka på [!DNL Widen] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Välj den miljö och typ av konto som du ansluter till. Detta är endast till för information och visas i området Anslutningar i Fusion.
1. Välj den [!DNL Widen]-domän som du vill ansluta till.
1. Ange token för ditt [!DNL Widen]-konto. Instruktioner om hur du hittar denna token finns i [[!DNL Widen] API FAQs](https://community.widen.com/collective/s/article/API-FAQs).
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Widen]-moduler och deras fält

När du konfigurerar [!DNL Widen]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Widen] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösarmoduler](#trigger-modules)
* [Åtgärdsmoduler](#action-modules)
* [Sökmoduler](#search-modules)

### Utlösarmoduler

#### [!UICONTROL Watch assets]

Den här utlösarmodulen startar ett scenario när en resurs skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p>Välj om du vill titta på nya resurser eller uppdaterade resurser.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Välj de egenskaper som du vill inkludera i modulutdata utöver resursfälten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill inkludera i modulutdata.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska arbeta med under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärdsmoduler

* [[!UICONTROL Add assets to collections]](#add-assets-to-collections)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download File]](#download-file)
* [[!UICONTROL Read asset info]](#read-asset-info)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Upload a file]](#upload-a-file)

#### [!UICONTROL Add assets to collections]

Den här åtgärdsmodulen lägger till en eller flera resurser i samlingar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>För varje samling som du vill lägga till resurserna i klickar du på <strong>[samlings-ID]</strong> och anger eller mappar [!UICONTROL Collection ID].</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> För varje resurs som du vill lägga till i en samling klickar du på <strong>[!UICONTROL Assets ID]</strong> och anger eller mappar resurs-ID:t.</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska arbeta med under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Widen]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Widen]-modulerna.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Välj om du vill använda den senaste versionen av [!DNL Widen] API eller version 1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange eller mappa URL:en för ditt API-anrop.</td> 
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
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download File]

Den här åtgärdsmodulen hämtar en resurs från ditt [!DNL Widen]-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read asset info]

Den här åtgärdsmodulen hämtar en enskild resurs med dess unika ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill läsa information för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Välj de egenskaper som du vill inkludera i modulutdata utöver resursfälten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill inkludera i modulutdata.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

Den här åtgärdsmodulen tar bort en eller flera resurser från samlingar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td>För varje samling som du vill ta bort resurser från klickar du på <strong>[samlings-ID]</strong> och anger eller mappar [!UICONTROL Collection ID].</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> För varje resurs som du vill ta bort från en samling klickar du på <strong>[!UICONTROL Assets ID]</strong> och anger eller mappar resurs-ID:t.</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska arbeta med under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

Den här åtgärdsmodulen uppdaterar metadatafälten för en resurs.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Ange eller mappa ID:t för resursen där du vill uppdatera metadata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata type]</td> 
   <td> <p>Välj metadatatyp för de metadata som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Markera de metadatafält som du vill uppdatera. Ange fältets nya värde för varje fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska arbeta med under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

Den här åtgärdsmodulen överför en fil till ditt [!DNL Widen]-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Profile]</td> 
   <td> <p>Välj den överföringsprofil som du vill att modulen ska använda.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Method]</td> 
   <td> <p>Välj hur du vill överföra filen.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL From File]</strong> </p> <p>Markera eller mappa källfilen från en tidigare modul.</p> </li> 
     <li> <p><strong>[!UICONTROL By URL]</strong> </p> <p>Ange eller mappa URL:en för filen som du vill överföra.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>Ange eller mappa ett namn för den överförda filen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata Type]</td> 
   <td>Välj metadatatyp för filen som du vill överföra.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Markera de metadatafält som du vill ta med i filöverföringen. Ange fältets [!UICONTROL value] för varje fält.</td> 
  </tr> 
 </tbody> 
</table>

### Sökmoduler

* [[!UICONTROL Read collection assets]](#read-collection-assets)
* [[!UICONTROL Search assets]](#search-assets)

#### [!UICONTROL Read collection assets]

Den här åtgärdsmodulen hämtar en lista med resurser i en samling.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Ange eller mappa ID:t för samlingen som innehåller de resurser som du vill läsa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>Ange eller mappa numret för det första objektet som du vill visa. Detta är ett sätt att numrera posterna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>Välj den egenskap som du vill sortera resurserna efter. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>Välj om du vill sortera resurser i stigande eller fallande ordning.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill inkludera i modulutdata.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search assets]

Den här sökmodulen hämtar en lista med resurser som matchar de specifika sökvillkoren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>Instruktioner om hur du ansluter ditt [!DNL Widen]-konto till Workfront Fusion finns i <a href="#connect-widen-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Widen] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search query]</td> 
   <td> <p>Ange de villkor som du vill använda för att söka efter resurser.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>Välj hur du vill sortera resurserna. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>Välj om du vill sortera resurser i stigande eller fallande ordning.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include deleted]</td> 
   <td>Aktivera det här alternativet om du vill ta med borttagna resurser i sökningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Include archived]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera arkiverade resurser i sökningen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search document text]</td> 
   <td>Aktivera det här alternativet om du vill ta med dokumenttext i sökningen eller ange till false om du bara vill ta med resurser där titeln matchar sökvillkoren.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Offset]</td> 
   <td>Ange eller mappa numret för det första objektet som du vill hämta information för. Detta är ett sätt att numrera posterna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scroll]</td> 
   <td>Aktivera det här alternativet om du vill tillåta rullning.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>Välj de egenskaper som du vill inkludera i modulutdata utöver resursfälten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill inkludera i modulutdata.</td> 
  </tr> 
 </tbody> 
</table>
