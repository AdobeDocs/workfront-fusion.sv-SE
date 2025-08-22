---
title: Gränssnittsmoduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Bynder] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 0a45f8a7-12cc-41cc-9135-92f4779afac0
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# [!DNL Bynder] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Bynder] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Du måste ha ett [!DNL Bynder]-konto för att kunna använda [!DNL Bynder]-moduler.

## API-information för gränder

Bynder-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.25.21</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Bynder] till Workfront Fusion  {#connect-bynder-to-workfront-fusion}

>[!NOTE]
>
>Bynder använder behörighetskoden/typen för att uppdatera token-tilldelning. Det här är den enda anslagstyp som Fusion Bynder-kopplingen använder.

* [Skapa en anslutning till  [!DNL Bynder] från Workfront Fusion](#create-a-connection-to-bynder-from-workfront-fusion)
* [Generera en [!UICONTROL Client ID] och [!UICONTROL Client Secret] i [!DNL Bynder]  (valfritt)](#generate-a-client-id-and-client-secret-in-bynder-optional)

### Skapa en anslutning till [!DNL Bynder] från Workfront Fusion

Du kan skapa en anslutning från Workfront Fusion till ditt [!DNL Bynder]-konto direkt inifrån en [!DNL Bynder]-modul.

1. Klicka på [!DNL Bynder] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Välj den [!DNL Bynder]-domän som du vill ansluta till.
1. (Valfritt) Klicka på **[!UICONTROL Advanced settings]** och ange sedan [!UICONTROL Client ID] och [!UICONTROL Client Secret].

   Instruktioner om hur du genererar klient-ID och klienthemlighet finns i [Skapa ett klient-ID och klienthemlighet i [!DNL Bynder] (valfritt)](#generate-a-client-id-and-client-secret-in-bynder-optional) i den här artikeln.

1. I fönstret [!UICONTROL login] anger du ditt användarnamn (e-postadress) och lösenord.
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

### Generera en [!UICONTROL Client ID] och [!UICONTROL Client Secret] i [!DNL Bynder] (valfritt)

Om du vill skapa en anslutning med klient-ID och klienthemlighet kan du generera dem från ditt [!DNL Bynder]-konto. Klient-ID och Klienthemlighet genereras när du skapar en app i [!DNL Bynder].

Instruktioner om hur du skapar ett program i [!DNL Bynder] finns i [OA 2.0-appar](https://developer-docs.bynder.com/api/authentication-oauth2-oauth-apps/) i [!DNL Bynder]-dokumentationen.

>[!NOTE]
>
>* När du skapar appen i [!DNL Bynder] anger du följande som `redirect uri`:
>
>   * Amerikanskt kluster: `https://app.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * EU-kluster: `https://app-eu.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * Azure-kluster: `https://app-az.workfrontfusion.com/oauth/cb/workfront-bynder`
>* Bynder använder behörighetskoden/typen för att uppdatera token-tilldelning. Det här är den enda anslagstyp som Fusion Bynder-kopplingen använder.

## [!DNL Bynder]-moduler och deras fält

När du konfigurerar [!DNL Bynder]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Bynder] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärder](#actions)
* [Sökningar](#searches)
* [Utlösare](#triggers)

### Åtgärder

* [[!UICONTROL Add a tag to assets]](#add-a-tag-to-assets)
* [[!UICONTROL Add assets to a collection]](#add-assets-to-a-collection)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download asset]](#download-asset)
* [[!UICONTROL Read asset metadata]](#read-asset-metadata)
* [[!UICONTROL Remove a tag] från resurser](#remove-a-tag-from-assets)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Upload asset]](#upload-asset)

#### [!UICONTROL Add a tag to assets]

Den här åtgärdsmodulen lägger till en tagg i en eller flera resurser

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>Ange eller mappa ID:t för taggen som du vill lägga till i resurser.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>För varje resurs som du vill tagga klickar du på <strong>[!UICONTROL Add item]</strong> och anger eller mappar sedan resurs-ID:t.</p> </td> 
  </tr> 
 </tbody> 
 </table>

#### [!UICONTROL Add assets to a collection]

Den här åtgärdsmodulen lägger till en eller flera resurser i en samling.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Ange eller mappa ID:t för samlingen där du vill lägga till resurser.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>För varje resurs som du vill lägga till i samlingen klickar du på <strong>[!UICONTROL Add item]</strong> och anger eller mappar sedan resurs-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Bynder]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Bynder]-modulerna.

När du konfigurerar den här modulen visas följande fält.

Modulen returnerar en statuskod tillsammans med rubrikerna och brödtexten för API-anropet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Ange en relativ sökväg till <code>https://{your-bynder-domain}/api/{api-version}/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
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

#### [!UICONTROL Download asset]

Den här åtgärdsmodulen hämtar en enskild resurs.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Ange eller mappa ID:t för resursen som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset version]</td> 
   <td> <p>Ange eller mappa den version av resursen som du vill hämta. Om du vill hämta den senaste versionen av resursen lämnar du fältet tomt.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read asset metadata]

Den här åtgärdsmodulen läser metadata för en resurs.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Ange eller mappa ID:t för resursen som du vill hämta metadata för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove a tag from assets]

Den här åtgärdsmodulen tar bort en tagg från en eller flera resurser

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag ID]</td> 
   <td> <p>Ange eller mappa ID:t för taggen som du vill ta bort från resurserna.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>För varje resurs som du vill ta bort en tagg från klickar du på <strong>[!UICONTROL Add item]</strong> och anger eller mappar sedan resurs-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

Den här åtgärdsmodulen tar bort en eller flera resurser från en samling.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>Ange eller mappa ID:t för samlingen där du vill ta bort resurser.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset IDs]</td> 
   <td> <p>För varje resurs som du vill ta bort från samlingen klickar du på <strong>[!UICONTROL Add item]</strong> och anger eller mappar sedan resurs-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

Den här åtgärdsmodulen uppdaterar metadata för en befintlig resurs.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td>Ange eller mappa ID:t för resursen som du vill uppdatera metadata för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Markera de fält som du vill ange information för och ange eller mappa sedan den information som du vill uppdatera metadata med till dessa fält. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Metaproperties]</p> </td> 
   <td>Välj de alternativ som du vill uppdatera och ange eller mappa sedan informationen till dessa egenskaper. Metaegenskaper är information om resursen som inte representerar specifika fält i resursen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload asset]

Den här åtgärdsmodulen överför en enskild resurs.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save as]</td> 
   <td> <p>Välj hur du vill spara filen som du överför.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL New asset]</strong> </p> <p>Markera de fält och metaegenskaper som du vill ange information för och ange sedan informationen i fälten.</p> <p>Ange eller mappa ID:t för det varumärke som du vill använda för den överförda resursen.</p> </li> 
     <li> <p><strong>[!UICONTROL New asset version]</strong> </p> <p>Ange ID:t för resursen som du överför en ny version för.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asynchronous file upload]</td> 
   <td>Aktivera det här alternativet när du överför stora filer. Detta förhindrar att stora filer blockerar scenariokörning.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL List record]](#list-record)
* [[!UICONTROL Search Assets]](#search-assets)

#### [!UICONTROL List record]

Sökmodulen hämtar alla objekt av en viss typ.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill visa.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Read all collections]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read information about all tags]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Read all assets of a collection]</strong> </p> <p>Ange eller mappa ID:t för samlingen som du vill visa resurser för.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i modulens utdata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Assets]

Den här sökmodulen söker efter resurser baserat på de villkor du anger.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td> <p>Ange sökvillkoren. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>Markera fältet som du vill använda i sökningen</p> </li> 
     <li> <p><strong>[!UICONTROL Logical Operator]</strong> </p> <p>Välj den operator som du vill använda i sökningen.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Ange eller mappa värdet som du vill söka efter i det markerade fältet. Värdetypen ska vara densamma som datatypen för det markerade fältet. </p> <p>Mer information om datatyper finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Objektdatatyper</a>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Välj om du vill returnera den första matchande resursen eller alla matchande resurser.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Markera fältet som du vill sortera efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort Direction]</td> 
   <td> <p>Välj om du vill sortera stigande eller fallande.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i modulens utdata.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Utlösare

#### [!UICONTROL Watch assets]

Den här utlösarmodulen startar ett scenario när en resurs skapas eller uppdateras.

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">Händelsetyp</td>
    <td>Välj om du vill starta scenariot när en ny resurs skapas eller när en befintlig resurs uppdateras.</td>
  </tr> 
  <tr>
     <td role="rowheader">[!UICONTROL Collections]</td>
   <td> <p>Välj den samling som du vill bevaka för nya resurser. Om du vill bevaka alla samlingar lämnar du det här fältet tomt.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">Utdata</td>
    <td>Markera de fält som du vill inkludera i utdata.</td>
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Limit]</td>

<td> <p>Ange det högsta antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>
