---
title: Adobe Workfront Planning-moduler
description: Med  [!DNL Adobe Workfront Planning] modulerna kan du starta ett Adobe Workfront Fusion-scenario baserat på händelser i ditt [!DNL Adobe] Workfront Planning-konto, skapa, läsa eller uppdatera avtal och andra poster, söka efter poster med villkor som du anger och överföra dokument.
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 0%

---

# [!DNL Adobe Workfront Planning] moduler

Med modulerna [!DNL Adobe Workfront Planning] kan du utlösa ett scenario när händelser inträffar i Workfront Planning. Du kan också skapa, läsa, uppdatera och ta bort poster eller utföra ett anpassat API-anrop till ditt [!DNL Adobe Workfront Planning]-konto.

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

+++# Förutsättningar

Du måste ha följande för att få tillgång till Workfront Planning:

* Ett nytt Workfront-paket och en ny licens. Workfront Planning är inte tillgängligt för tidigare Workfront-paket eller licenser.
* Ett Workfront Planning-paket.
* Din organisations instans av Workfront måste integreras med Adobe Unified Experience.

## Information om Adobe Workfront Planning API

Adobe Workfront Planning Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://{{connection.host}}/maestro/api/{{common.maestroApiVersion}}/</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till [!DNL Adobe Workfront Planning] {#create-a-connection-to-adobe-workfront-planning}

Du kan skapa en anslutning till ditt [!DNL Workfront Planning]-konto direkt inifrån en Workfront Fusion-modul.

1. Klicka på [!DNL Adobe Workfront Planning] bredvid anslutningsrutan i någon **[!UICONTROL Add]**-modul.

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
          <td>Ange din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Valfritt)</p></td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]</td>
          <td>Ange den URL som din instans av Workfront ska använda för att autentisera anslutningen. <p>Standardvärdet är <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>Ange värdprefixet.<p>Standardvärdet är <code>origin-</code>.</p>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## [!DNL Adobe Workfront Planning]-moduler och deras fält

När du konfigurerar Workfront-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Workfront-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)
* [Okategoriserad](#uncategorized)

### Utlösare

#### Se händelser

Den här utlösarmodulen startar ett scenario när en post, posttyp eller arbetsyta skapas, uppdateras eller tas bort i Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>Välj den webkrok som du vill använda eller klicka på Lägg till för att skapa en ny.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Object type]</td>
      <td>Välj om du vill bevaka poster, posttyper eller arbetsytor.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>Välj om du vill titta på det gamla eller nya läget.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Utlös ett scenario när posten ändras till <b></b> för ett givet värde.</p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Utlös ett scenario när posten ändrar <b> från</b> ett givet värde.</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Om du tittar på inspelningar väljer du den Workspace du vill titta efter.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Om du tittar på poster väljer du vilken typ av post du vill bevaka.</td>
    </tr>
    </tr>
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Du kan ställa in filter så att endast poster som uppfyller de villkor du väljer bevakas.</p> <p>För varje filter anger du fältet som du vill att filtret ska utvärderas, operatorn och värdet som du vill att filtret ska tillåta. Du kan använda mer än ett filter genom att lägga till OCH-regler.</p> <p>Obs! Du kan inte redigera filter i befintliga Workfront-webbplatser. Om du vill ställa in olika filter för Workfront-händelseprenumerationer tar du bort den aktuella webbkroken och skapar en ny.</p> <p>Mer information om händelsefilter finns i <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Evenemangsprenumerationsfilter i Workfront &gt; [!UICONTROL Watch Events] moduler</a> i Workfront modulartikel.</p> </td> 
     </tr> 
    <tr>
      <td role="rowheader">[!UICONTROL Objects to watch]</td>
      <td>Välj om du vill hålla utkik efter nya. uppdaterade, nya och uppdaterade eller borttagna poster.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Exclude updates made by this connection]</p>
      </td>
      <td>Aktivera det här alternativet om du vill förhindra att scenariot aktiveras när en ändring görs av anslutningen som används av modulen. Detta förhindrar att en annan instans av scenariot utlöses om det här scenariot utför en utlösande åtgärd.</td> 
      </tr>
  </tbody>
</table>

### Åtgärder

* [Ta bort en posttyp](#delete-a-record-type)
* [Göra ett anpassat AI-anrop](#make-a-custom-api-call)

#### Ta bort en posttyp

Den här åtgärdsmodulen tar bort en enskild posttyp i Workfront Planning med dess ID.

>[!WARNING]
>
>Om du tar bort en posttyp i Workfront Planning tas även alla poster i posttyptabellen bort.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>Ange eller mappa ID:t för den posttyp som du vill ta bort.</td> 
      </tr>
  </tbody>
</table>

#### Göra ett anpassat API-anrop

Den här modulen gör ett anpassat API-anrop till API:t [!DNL Adobe Workfront Planning].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Ange en sökväg i förhållande till <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>För varje nyckel/värde-par som du vill lägga till i frågesträngen klickar du på <b>Lägg till objekt</b> och anger nyckel och värde.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>


### Sökningar

#### Sök poster

Den här åtgärdsmodulen hämtar en lista med poster baserat på villkor som du anger.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>Ange eller mappa den Workspace som innehåller de poster som du vill söka efter.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type]</p>
      </td>
      <td>Välj den posttyp som du vill söka efter.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record Fields]</p>
      </td>
      <td>Leta reda på fältet, markera operatorn och ange eller mappa värdet som du vill söka efter för varje fält som du vill använda i sökningen. Fältet är tillgängligt baserat på vald posttyp.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Condition for filters]</p>
      </td>
      <td>Välj villkor för dina filter:<ul><li><b>OCH</b><p>Modulen returnerar poster som uppfyller <b>alla</b> av de fältvärden som du markerade.</p></li><li><b>ELLER</b><p>Modulen returnerar poster som uppfyller <b>något</b> av de fältvärden som du har valt.</p></li></ul></td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Limit]</p>
      </td>
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
      </tr>
  </tbody>
</table>


### Okategoriserad


#### Skapa en post

Den här åtgärden skapar en enda post i Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record type ID]</p>
      </td>
      <td>Ange eller mappa den typ av post som du vill skapa. Tillgängliga posttyper baseras på ditt Workfront Planning-konto.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Andra fält</p>
      </td>
      <td>Ange de värden som du vill att den nya posten ska ha. Dessa fält baseras på den posttyp som du har valt.</td> 
      </tr>
     <tr>
  </tbody>
</table>

### Ta bort en post

Den här åtgärdsmodulen tar bort den angivna posten i Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Ange eller mappa ID:t för den post som du vill ta bort.</td> 
      </tr>
  </tbody>
</table>

### Hämta en post

Den här åtgärdsmodulen hämtar en enskild post från [!DNL Adobe Workfront Planning], som anges av dess ID.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record ID]</td>
      <td>Ange eller mappa ID:t för den post som du vill hämta.</td>
    </tr>
  </tbody>
</table>

### Hämta poster efter posttyp

Den här åtgärdsmodulen hämtar alla poster av den angivna typen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Markera eller mappa arbetsytan som innehåller de poster som du vill hämta.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Record type]</td>
      <td>Välj den typ av post som du vill hämta.</td>
    </tr>
     <!--<tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> -->
  </tbody>
</table>

### Hämta posttyper

Den här åtgärdsmodulen hämtar en lista med posttyper i ett [!DNL Adobe Workfront Planning]-konto.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Markera eller mappa arbetsytan som innehåller de posttyper som du vill hämta.</td>
    </tr>
  </tbody>
</table>

### Uppdatera post

Den här åtgärden uppdaterar en enda post i Workfront Planning.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Workfront Planning] finns i <a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Workfront Planning]</a> i den här artikeln.</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Record ID]</p>
      </td>
      <td>Ange eller mappa den typ av post som du vill uppdatera. Tillgängliga posttyper baseras på ditt Workfront Planning-konto.</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>Andra fält</p>
      </td>
      <td>Ange de nya värden som du vill att posten ska ha. Dessa fält baseras på den posttyp som du har valt.</td> 
      </tr>
     <tr>
  </tbody>
</table>


## Använd JSONata för läsbar `record-types`-nedbrytning

I följande JSONata-uttryck skapas ett läsbart resultat av planeringsfrågan som ger dig uppdelningen av posttyper. Detta gör att posttypens namn, fältnamn och fältalternativens namn (där det är tillämpligt) kan läsas av ett namn och behåller resten av strukturen intakt.

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

Mer information om hur du använder JSONata-moduler finns i [JSONata-moduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md).

