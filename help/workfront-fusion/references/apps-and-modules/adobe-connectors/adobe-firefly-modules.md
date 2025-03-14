---
title: Adobe Firefly moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder  [!DNL Adobe Firefly] samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2251'
ht-degree: 0%

---

# [!DNL Adobe Firefly] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Firefly] samt ansluta det till flera tredjepartsprogram och -tjänster.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Innan du kan använda [!DNL Adobe Firefly]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Firefly]-konto.

## Adobe Firefly API-information

Adobe Firefly Connector använder följande:

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

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning i någon av modulerna.

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

### Expandera en bild

Den här åtgärdsmodulen expanderar en bild, eventuellt med innehåll från en fråga som du anger.

Den här modulen fungerar med Firefly API V3 Async. Den tidigare versionen av den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden.

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
   <td role="rowheader">[!UICONTROL Source]</td> 
   <td>Ange hur du ska tillhandahålla källfilen:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expanded image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand by]</td> 
   <td>  <p>Välj om du vill expandera bilden genom att använda bildplacering eller en mask.</p> 
   <ul>
   <li><b>Placement</b><p>Ange den vågräta och lodräta justeringen och den monterade bildens indrag från kanterna.</p></li>
   <li><b>Mask</b><p>Markera maskens källfil och om masken ska inverteras.</p></li>
   </ul>
</td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den höjd och bredd som du vill att den expanderade bilden ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>För varje bild som modulen ska generera klickar du på <b>Lägg till objekt</b> och anger eller mappar ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. Antalet frön som du lägger till måste vara lika med fältet Antal variationer.</td> 
  </tr> 
 </tbody> 
</table>

### Expandera en bild (inaktuell)

Den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden. Använd modulen Expandera en bild i stället.

### Fylla en bild

Den här åtgärdsmodulen fyller det maskerade området i en bild, eventuellt med innehåll från en uppmaning som du anger.

Den här modulen fungerar med Firefly API V3 Async. Den tidigare versionen av den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image > Source]</td> 
   <td>Ange hur du ska tillhandahålla bildkällfilen:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mask > Source]</td> 
   <td>Ange hur du ska tillhandahålla maskens källfil:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
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
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>För varje bild som modulen ska generera klickar du på <b>Lägg till objekt</b> och anger eller mappar ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. Antalet frön som du lägger till måste vara lika med fältet Antal variationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den fyllda bilden ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>Om en språkinställning anges genererar modulen innehåll som är mer relevant för den angivna språkinställningen. <p>Språk måste anges i ISO 639-1-språkkoden och ISO 3166-1-regionen.</p><p> Exempel: <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>

### Fylla en bild (inaktuell)

Den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden. Använd modulen Fyll en bild i stället.

## Generera en bild

Den här åtgärdsmodulen genererar en bild som baseras på en fråga som du anger. Du kan också ange en valfri referensbild så matchar den genererade bilden stilen för referensbilden.

Den här modulen fungerar med Firefly API V3 Async. Den tidigare versionen av den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden.

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
   <td>Ange eller mappa en fråga för den bild som du vill generera. Mer detaljskärpa ger dig större kontroll över vad som visas i bilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar detta antal bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som. Om du väljer standard kommer filformatet att vara JPEG om ingen referensbild finns. Om en referensbild anges kommer den genererade bildens filformat att vara detsamma som referensbilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure > Image reference]</td> 
    <td>Välj hur du ska ange källfilen för den nya bildens struktur:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure > Strength]</td> 
    <td>Ange ett tal mellan 0 och 100 för att kontrollera hur strikt Firefly följer källbildens struktur. Ett högre värde innebär att Firefly följer bilden mer strikt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style > Image reference]</td> 
    <td>Ange hur du ska ange källfilen för den nya bildens format:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure > Strength]</td> 
    <td>Ange ett tal mellan 0 och 100 för att kontrollera hur strikt Firefly följer källbildens format. Ett högre värde innebär att Firefly följer bilden mer strikt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style > Presets]</td> 
   <td>Om du vill använda ett förinställt format klickar du på Lägg till objekt och anger eller mappar det format som du vill använda.<p>En lista med förinställda format finns i <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >Bildmodellformat</a> i dokumentationen för Adobe-utvecklare.</td> 
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
   <td>För varje bild som modulen ska generera klickar du på <b>Lägg till objekt</b> och anger eller mappar ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. Antalet frön som du lägger till måste vara lika med fältet Antal variationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den genererade bilden ska ha.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Visual intensity]</td> 
   <td>Ange eller mappa ett heltal som representerar den övergripande intensiteten för fotots befintliga visuella egenskaper. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>Om en språkinställning anges genererar modulen innehåll som är mer relevant för den angivna språkinställningen. <p>Språk måste anges i ISO 639-1-språkkoden och ISO 3166-1-regionen.</p><p> Exempel: <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tileable]</td> 
   <td>Aktivera det här alternativet om du vill generera en bild som kan upprepas oändligt i alla riktningar.</td> 
  </tr> 
 </tbody> 
</table>

### Generera en bild (inaktuell)

Den här modulen har tagits bort och kommer att tas bort inom den närmaste framtiden. Använd modulen Generera en bild i stället.

### Generera en oseparerad objektfil

Den här åtgärdsmodulen kombinerar bilder som skapats av Firefly för att skapa en sammansatt bild.

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
   <td>Ange eller mappa en fråga för den bild som du vill generera. Mer detaljskärpa ger dig större kontroll över vad som visas i bilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar detta antal bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content classs]</td> 
   <td>Välj om du vill att den genererade bilden ska vara mer som ett foto eller som en teckning.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Image > Source]</td> 
    <td>Välj hur du ska ange källfilen för den nya bildens struktur:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som. Om du väljer standard kommer filformatet att vara JPEG om ingen referensbild finns. Om en referensbild anges kommer den genererade bildens filformat att vara detsamma som referensbilden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style > Image reference]</td> 
    <td>Ange hur du ska ange källfilen för den nya bildens format:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Structure > Strength]</td> 
    <td>Ange ett tal mellan 0 och 100 för att kontrollera hur strikt Firefly följer källbildens format. Ett högre värde innebär att Firefly följer bilden mer strikt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style > Presets]</td> 
   <td>Om du vill använda ett förinställt format klickar du på Lägg till objekt och anger eller mappar det format som du vill använda.<p>En lista med förinställda format finns i <a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >Bildmodellformat</a> i dokumentationen för Adobe-utvecklare.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den genererade sammansatta bilden ska ha. </td> 
  </tr> 
 </tbody> 
</table>

### Generera liknande bilder

Den här åtgärdsmodulen genererar bilder som liknar den källbild du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Firefly]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number of variations]</td> 
   <td>Ange ett tal mellan 1 och 4. Modulen genererar detta antal bildvariationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generated image format]</td> 
   <td>Välj det filformat som den expanderade bilden ska sparas som. Om du väljer standard kommer filformatet att vara JPEG om ingen referensbild finns. Om en referensbild anges kommer den genererade bildens filformat att vara detsamma som referensbilden.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Image > Source]</td> 
    <td>Välj hur du ska ange källfilen för den nya bildens struktur:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Style > Image reference]</td> 
    <td>Ange hur du ska ange källfilen för den nya bildens format:<ul><li><p><b>Fil</b></p><p>Välj en källfil från en tidigare modul eller mappa källfilens referensbildfilnamn och referensbildfil.</p></li><li><p><b>Förutsedd URL</b></p><p>Ange eller mappa URL:en för källbilden.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size]</td> 
   <td>Välj den storlek som du vill att den genererade sammansatta bilden ska ha. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Seeds]</td> 
   <td>För varje bild som modulen ska generera klickar du på <b>Lägg till objekt</b> och anger eller mappar ett heltal. Du kan använda samma startvärde i en annan expanderingsmodul om du vill generera en liknande bild med olika format. Antalet frön som du lägger till måste vara lika med fältet Antal variationer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tileable]</td> 
   <td>Aktivera det här alternativet om du vill generera en bild som kan upprepas oändligt i alla riktningar.</td> 
  </tr> 
 </tbody> 
</table>


### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Firefly API.

Specifika tillgängliga API:er finns i [Adobe Firefly API](https://developer.adobe.com/firefly-services/docs/firefly-api/) i Adobe Developer-dokumentationen.

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
        <p>Ange en relativ sökväg till <code>https://firefly-api.adobe.io/</code>.</p>
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

