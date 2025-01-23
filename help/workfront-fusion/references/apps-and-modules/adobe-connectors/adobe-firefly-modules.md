---
title: Adobe Firefly-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder  [!DNL Adobe Firefly] samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---

# [!DNL Adobe Firefly] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Firefly] samt ansluta det till flera tredjepartsprogram och -tjänster.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> <p>Nytt: [!UICONTROL Standard]</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront] Plan: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] Planen [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Innan du kan använda [!DNL Adobe Firefly]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Firefly]-konto.

## API-information för Adobe Firefly

Kopplingen Adobe Firefly använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.4.24</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till [!DNL Adobe Firefly]

Så här skapar du en anslutning för dina [!DNL Adobe Firefly]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning.

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
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console].</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## [!DNL Adobe Firefly]-moduler och deras fält

När du konfigurerar [!DNL Adobe Firefly] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Adobe Firefly] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Firefly API.

Mer information om tillgängliga API:er finns i [Adobe Firefly API](https://developer.adobe.com/firefly-services/docs/firefly-api/) i Adobe Developer-dokumentationen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Firefly] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Ange en relativ sökväg till <code>https://firefly-api-enterprise-stage.adobe.io/</code>.</p>
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
        <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p>
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

### Expandera en bild

Den här åtgärdsmodulen expanderar en bild, eventuellt med innehåll från en fråga som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Ange eller mappa en fråga för innehållet som du vill expandera bilden med. Om ingen fråga visas kommer bilden att expanderas med innehåll som matchar originalbilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar detta antal expanderade bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expanded image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>  <p>Välj en källfil från en tidigare modul eller mappa källfilens bildfilnamn och bildfil (data).</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den expanderade bilden ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]</td> 
   <td>Ange eller mappa ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. </td> 
  </tr> 
 </tbody> 
</table>

## Fylla en bild

Den här åtgärdsmodulen fyller det maskerade området i en bild, eventuellt med innehåll från en uppmaning som du anger.


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Ange eller mappa en fråga för innehållet som du vill fylla bilden med. Om ingen uppmaning visas fylls bilden med innehåll som matchar originalbilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar det här antalet fyllda bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filled image format]</td> 
   <td>Välj det filformat som den ifyllda bilden ska sparas som.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image]</td> 
   <td>  <p> Klicka på <b>Lägg till en bild</b>. Välj en källfil från en tidigare modul eller mappa källfilens bildfilnamn och bilddata.</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mask]</td> 
   <td>  <p> Klicka på <b>Lägg till en mask</b>. Välj en källfil från en tidigare modul eller mappa källfilens maskfilnamn och maskdata. Maskfilen representerar den anpassade mask som ska fyllas med genererat innehåll.</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den fyllda bilden ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>För varje bild som modulen ska generera klickar du på <b>Lägg till objekt<b> och anger eller mappar ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. Antalet frön som du lägger till måste vara lika med fältet Antal variationer.</td> 
  </tr> 
 </tbody> 
</table>

## Generera en bild

Den här åtgärdsmodulen genererar en bild som baseras på en fråga som du anger. Du kan också ange en valfri referensbild så matchar den genererade bilden stilen för referensbilden.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Prompt]</td> 
   <td>Ange eller mappa en fråga för den bild du vill skapa. Mer detaljskärpa ger dig större kontroll över vad som visas i bilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar detta antal bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som. Om du väljer standardformat kommer filformatet att vara JPEG om ingen referensbild finns. Om en referensbild anges kommer den genererade bildens filformat att vara detsamma som referensbilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>  <p>Välj en källfil från en tidigare modul eller mappa källfilens namn på referensbildfilen och referensbildfilen (data). Den genererade bilden skapas så att den matchar referensbildens format.</p> </td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presets]</td> 
   <td>Om du vill använda ett förinställt format klickar du på Lägg till objekt och anger eller mappar det format som du vill använda.<p>En lista med förinställda format finns i <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >Bildmodellformat</a> i utvecklardokumentationen för Adobe.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Negative prompt]</td> 
   <td>Ange eller mappa de ord som du vill undvika i det genererade innehållet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content class]</td> 
   <td>Välj om du vill att den genererade bilden ska vara mer lik ett foto eller mer lik en skapad bild. <ul><li><b>Foto</b><p>Ange värden för Aperture, Slutarhastighet (i sekunder) och visningsfält (i millimeter).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seed]</td> 
   <td>Ange eller mappa ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den genererade bilden ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Strength]</td> 
   <td>Ange eller mappa ett heltal som representerar intensiteten som den genererade bilden ska matcha stilen för den förinställda stilen eller referensbilden med. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visual intensity]</td> 
   <td>Ange eller mappa ett heltal som representerar den övergripande intensiteten för fotots befintliga visuella egenskaper. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>Om en språkinställning anges genererar modulen innehåll som är mer relevant för den angivna språkinställningen. <p>Språk måste anges i ISO 639-1-språkkoden och ISO 3166-1-regionen.</p><p> Exempel: <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>
