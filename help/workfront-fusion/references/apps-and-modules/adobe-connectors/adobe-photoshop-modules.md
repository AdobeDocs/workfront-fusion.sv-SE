---
title: Adobe Photoshop moduler
description: Med Adobe Photoshop-modulerna kan du starta ett Adobe Workfront Fusion-scenario baserat på händelser i ditt Adobe Photoshop-konto, skapa, läsa eller uppdatera avtal och andra poster, söka efter poster med villkor som du anger och överföra dokument.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0e41d1af-af69-4f9b-a5b3-479562254084
source-git-commit: a68de976258d17631459f0951d28657fd0e0dcf6
workflow-type: tm+mt
source-wordcount: '4738'
ht-degree: 0%

---

# [!DNL Adobe Photoshop] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Photoshop] samt ansluta det till flera tredjepartsprogram och -tjänster.


Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Innan du kan använda [!DNL Adobe Photoshop]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Photoshop]-konto.
* Du måste ha en Firefly Services-licens.
* Du måste ha ett klient-ID och en klienthemlighet. Du kan köpa dessa från Adobe Developer Console.

## Adobe Photoshop API-information

Adobe Photoshop Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://image.adobe.io/pie/psdService</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.12.31</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till [!DNL Adobe Photoshop]

Så här skapar du en anslutning för dina [!DNL Adobe Photoshop]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning i någon av modulerna.

1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Välj om du vill använda en JWT-anslutning eller en server-till-server-anslutning.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Om du använder en JWT-anslutning anger du [!DNL Adobe] [!UICONTROL Technical account ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Om du använder en JWT-anslutning anger du [!DNL Adobe] [!UICONTROL Organization ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Om du använder en JWT-anslutning anger du den privata nyckel som skapades när dina autentiseringsuppgifter skapades i [!DNL Adobe Developer Console]. </p>
          <p>Så här extraherar du din privata nyckel eller ditt certifikat:</p>
          <ol>
            <li value="1">
              <p>Klicka på <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Välj vilken typ av fil du extraherar.</p>
            </li>
            <li value="3">
              <p>Markera filen som innehåller den privata nyckeln eller certifikatet.</p>
            </li>
            <li value="4">
              <p>Ange lösenordet för filen.</p>
            </li>
            <li value="5">
              <p>Klicka på <b>Spara</b> för att extrahera filen och återgå till anslutningsinställningarna.</p>
            </li>
          </ol>
        </td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## [!DNL Adobe Photoshop]-moduler och deras fält

När du konfigurerar [!DNL Adobe Photoshop]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Adobe Photoshop] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Använda PSD-redigeringar](#apply-psd-edits)
* [Korrigera en bild automatiskt](#auto-color-correct-an-image)
* [Konvertera bildformat](#convert-image-format)
* [Skapa en mask](#create-a-mask)
* [Skapa en ny PSD](#create-a-new-psd)
* [Redigera textlager](#edit-text-layers)
* [Redigera textlager (äldre)](#edit-text-layers-legacy)
* [Kör en åtgärd-JSON](#execute-an-action-json)
* [Kör djuposkärpa](#execute-depth-blur)
* [Utför Photoshop-åtgärder](#execute-photoshop-actions)
* [Kör produktbeskärning](#execute-product-crop)
* [Hämta lagerinformation](#get-layer-info)
* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Ta bort bakgrund](#remove-background)
* [Ersätta ett smart objekt](#replace-a-smart-object)
* [Ersätta ett smart objekt (äldre)](#replace-a-smart-object-legacy)
* [Ändra bildstorlek](#resize-an-image)
* [Vattenstämpla en bild](#watermark-an-image)

### Använda PSD-redigeringar

I den här åtgärdsmodulen används en rad dokument- och lagernivåredigeringar.

Den här modulen stöder stora filer. Mer information om stora filer finns i [Arbeta med stora filer](/help/workfront-fusion/references/scenarios/fusion-large-files.md).

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Image size) Height]</p>
      </td>
      <td> Ange eller mappa bildens höjd i pixlar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Image size) Width]</p>
      </td>
      <td> Ange eller mappa bildens bredd i pixlar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Canvas size) Top]</p>
      </td>
   <td> Ange eller mappa, i pixlar, y-koordinaten för dokumentets övre vänstra hörn. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Canvas size) Bottom]</p>
      </td>
   <td> Ange eller mappa, i pixlar, y-koordinaten för dokumentets nedre högra hörn. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Canvas size) Left]</p>
      </td>
   <td> Ange eller mappa, i pixlar, x-koordinaten för dokumentets övre vänstra hörn. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Canvas size) Right]</p>
      </td>
   <td> Ange eller mappa, i pixlar, x-koordinaten för dokumentets nedre högra hörn. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document) Trim]</p>
      </td>
   <td> Välj Genomskinliga pixlar om du vill basera beskärningen på genomskinliga pixlar i bilden. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Default font]</p>
      </td>
   <td> Ange det fullständiga postscript-namnet för det teckensnitt som ska användas som dokumentets globala standard. Det här teckensnittet används för alla textlager som saknar teckensnitt och inget annat teckensnitt har angetts specifikt för det lagret. Om det här teckensnittet saknas börjar det alternativ som anges i Hantera saknade teckensnitt gälla. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> För varje teckensnitt som dokumentet behöver klickar du på Lägg till objekt och anger teckensnittets lagringsplats och filplats. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Välj den åtgärd som ska utföras om det finns ett eller flera saknade teckensnitt i dokumentet. <ul><li><code>fail</code>: Jobbet kommer inte att lyckas och statusen kommer att ställas in på misslyckades, med information om felet som finns i statusavsnittet.</li><li><code>useDefault</code>: Jobbet kommer att lyckas och alla saknade teckensnitt kommer att ersättas med ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> För varje lager som du vill lägga till klickar du på Lägg till objekt och fyller i lagerinformationen. <p>Mer information om lageralternativ finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/modifyDocumentAsync">Tillämpa PSD-redigeringar</a> i Adobe Photoshop-dokumentationen.  </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje redigerad fil som du vill skapa klickar du på Lägg till objekt och anger lagringsplats, plats och typ enligt tabellen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Välj den filtyp som du vill konvertera filen till. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Trim to Canvas]</p>
      </td>
   <td>Välj om återgivningarna måste ha arbetsytans storlek. True trimmar återgivningarna till Canvas-storlek, medan False gör återgivningslagrets storlek</td> 
    </tr>
    </tbody>
</table>

### Korrigera en bild automatiskt

Den här åtgärdsmodulen korrigerar automatiskt den angivna bilden.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill färgkorrigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL-adressen eller sökvägen till filen som du vill färgkorrigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Välj den filtyp som du vill konvertera filen till. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
    </tbody>
</table>

### Konvertera bildformat

Den här åtgärdsmodulen konverterar en fil till JPEG, PNG, PSD eller TIFF.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där den fil som du vill ta bort bakgrunden från lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill ta bort bakgrunden från. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje konverterad fil som du vill skapa klickar du på Lägg till objekt och anger lagringsplats, plats och typ enligt tabellen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Välj den filtyp som du vill konvertera filen till. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
    </tbody>
</table>

### Skapa en mask

Den här åtgärdsmodulen returnerar en PNG-fil med en mask runt motivet.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill skapa en mask från lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill skapa en mask från. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att maskfilen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där maskfilen ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Välj om utdatabilden ska ha RGB- eller RGBA-färg. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Välj om masken ska vara mjuk (luddig) eller binär. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Välj Prestanda om du vill optimera hastigheten eller Gruppera om du vill tillåta väntetid. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Välj om efterbearbetning ska aktiveras.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>Standard är 4.0</td> 
    </tr> 
    </tbody>
</table>

### Skapa en ny PSD

Den här åtgärdsmodulen skapar en ny PSD med valfria lager och skapar återgivningar eller sparar som en PSD.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Image size) Height]</p>
      </td>
      <td> Ange eller mappa bildens höjd i pixlar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document > Image size) Width]</p>
      </td>
      <td> Ange eller mappa bildens bredd i pixlar. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document) Resolution]</p>
      </td>
   <td> Ange eller mappa bildens upplösning i pixlar per tum. Den här måste vara mellan 72 och 300. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document) Mode]</p>
      </td>
   <td> Välj läge för bilden. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document) Fill]</p>
      </td>
   <td> Välj om du vill att fyllningen för bakgrundslagret ska vara genomskinlig, vit eller bakgrundsfärgen för bilden. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options > Document) Depth]</p>
      </td>
   <td> Markera bildens bitdjup. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Layers]</p>
      </td>
   <td> För varje lager som du vill lägga till klickar du på Lägg till objekt och fyller i lagerinformationen. <p>Mer information om lageralternativ finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Skapa PSD</a> i Adobe Photoshop-dokumentationen.  </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Global font]</p>
      </td>
   <td> Ange det fullständiga postscript-namnet för det teckensnitt som ska användas som dokumentets globala standard. Det här teckensnittet används för alla textlager som saknar teckensnitt och inget annat teckensnitt har angetts specifikt för det lagret. Om det här teckensnittet saknas börjar det alternativ som anges i Hantera saknade teckensnitt gälla. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> För varje teckensnitt som dokumentet behöver klickar du på Lägg till objekt och anger teckensnittets lagringsplats och filplats. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Manage missing fonts]</p>
      </td>
   <td> Välj den åtgärd som ska utföras om det finns ett eller flera saknade teckensnitt i dokumentet. <ul><li><code>fail</code>: Jobbet kommer inte att lyckas och statusen kommer att ställas in på misslyckades, med information om felet som finns i statusavsnittet.</li><li><code>useDefault</code>: Jobbet kommer att lyckas och alla saknade teckensnitt kommer att ersättas med ArialMT.</li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje fil som du vill skapa klickar du på Lägg till objekt och anger lagringsplats, plats och typ enligt tabellen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Välj den filtyp som du vill konvertera filen till. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Other fields]</td>
      <td>
        <p><p>Mer information om utdataalternativ finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/createDocumentAsync">Skapa PSD</a> i Adobe Photoshop-dokumentationen.  </p>
      </td>
    </tr>
    </tbody>
</table>

### Redigera textlager

Den här åtgärdsmodulen redigerar textlager i en Photoshop-fil. Du kan ange separata redigeringsdetaljer för flera lager i samma fil.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Välj den åtgärd som ska utföras om det finns ett eller flera saknade teckensnitt i dokumentet. Om teckensnittet inte anges används standardteckensnittet.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Ange det fullständiga postscript-namnet för det teckensnitt som ska användas som dokumentets globala standard. Det här teckensnittet används för alla textlager som saknar teckensnitt och inget annat teckensnitt har angetts specifikt för det lagret. Om det här teckensnittet saknas börjar det alternativ som anges i Hantera saknade teckensnitt gälla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Ange teckensnittets lagringsplats och filplats. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>För varje textlager som du vill redigera klickar du på <b>Lägg till objekt</b> och anger lageralternativen.<p>Mer information om lageralternativ finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Redigera text</a> i Adobe Photoshop-dokumentationen.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
  </tbody>
</table>

### Redigera textlager (äldre)

Den här åtgärdsmodulen redigerar ett textlager i en Photoshop-fil.

Om du vill redigera flera lager använder du modulen [Redigera textlager](#edit-text-layers) .

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Manage missing fonts]</td>
      <td>
        <p>Välj den åtgärd som ska utföras om det finns ett eller flera saknade teckensnitt i dokumentet. Om teckensnittet inte anges används standardteckensnittet.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Default font]  </td>
      <td>
        <p>Ange det fullständiga postscript-namnet för det teckensnitt som ska användas som dokumentets globala standard. Det här teckensnittet används för alla textlager som saknar teckensnitt och inget annat teckensnitt har angetts specifikt för det lagret. Om det här teckensnittet saknas börjar det alternativ som anges i Hantera saknade teckensnitt gälla.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Options) Fonts]</p>
      </td>
   <td> Ange teckensnittets lagringsplats och filplats. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Layers]</td>
   <td> <p>Mer information om lageralternativ finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/editTextLayerAsync">Redigera textlager</a> i Adobe Photoshop-dokumentationen.</p>  </td>     </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Output file storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
  </tbody>
</table>


### Kör en åtgärd-JSON

Den här åtgärdsmodulen kör Photoshop-åtgärder med JSON-kommandon.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action JSON]</td>
      <td>
        <p>Ange JSON-kommandot för det funktionsmakro du vill utföra.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fonts / Patterns / Brushes / Additional images]</td>
      <td>
        <p>För varje teckensnitt, mönster, pensel eller ytterligare bild som du vill använda i den här åtgärden klickar du på Lägg till objekt och anger objektets lagringsplats och filplats.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill använda. </td> 
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje fil som du vill skapa klickar du på Lägg till objekt och anger lagringsutrymme, plats, typ och överskrivningsalternativ enligt tabellen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) File URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
      </tbody>
</table>

### Kör djuposkärpa

Den här åtgärdsmodulen kör djuposkärpa på den markerade filen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) File URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Mer information om andra alternativ för djuposkärpa finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Kör djuposkärpa </a> i dokumentationen för Adobe Photoshop API.</p>
      </td>
    </tr>
  </tbody>
</table>

### Utför Photoshop-åtgärder

Den här åtgärdsmodulen kör en Photoshop-åtgärd på den markerade bilden.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill redigera lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill redigera. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Actions file storage]</td>
      <td>
        <p>Välj filtjänsten där åtgärdsfilen lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Actions file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen för åtgärdsfilen. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Action name]</p>
      </td>
   <td> Om du bara vill köra en viss åtgärd kan du ange vilken åtgärd som ska spelas upp från ActionSet. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Font / Pattern / Brush storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill använda lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Font / Pattern / Brush file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill använda. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) File URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Mer information om andra alternativ för djuposkärpa finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Kör djuposkärpa </a> i dokumentationen för Adobe Photoshop API.</p>
      </td>
    </tr>
  </tbody>
</table>

### Kör produktbeskärning

Den här åtgärdsmodulen kör produktbeskärning på den valda bilden.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill beskära lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL-adressen eller sökvägen till filen som du vill beskära. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Unit]</p>
      </td>
   <td> Välj om du vill beskriva justeringen av höjd och bredd i pixlar eller i procent. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> Ange eller mappa den mängd breddutfyllnad som du vill lägga till. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Height]</p>
      </td>
   <td> Ange eller mappa den höjd som du vill lägga till. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den redigerade filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) File URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där den redigerade filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Outputs) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns.</p>
      </td>
    </tr>
   <tr>
      <td role="rowheader">[!UICONTROL Other fields]</td>
      <td>
        <p>Mer information om andra alternativ för djuposkärpa finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/applyDepthBlurAsync">Kör djuposkärpa </a> i dokumentationen för Adobe Photoshop API.</p>
      </td>
    </tr>
  </tbody>
</table>

### Hämta lagerinformation

Denna åtgärdsmodul hämtar lagerinformation från den angivna PSD-filen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Input file storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill hämta lagerinformation från lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Input file URL]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill hämta lagerinformation från. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Thumbnails]</p>
      </td>
   <td> Välj den typ av fil som du vill att miniatyrbilderna ska vara. Miniatyrbilder är små förhandsvisningar för alla återgivningsbara lager.</td> 
    </tr>
  </tbody>
</table>

### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Photoshop API.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Ange en relativ sökväg till <code>https://image.adobe.io/pie/psdService</code>. Exempel: <code>/photoshopActions</code></p>
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
        <p>Ange frågesträngen för begäran.</p>
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

### Ta bort bakgrund

Den här åtgärdsmodulen identifierar huvudmotivet i bilden och tar bort bakgrunden.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där den fil som du vill ta bort bakgrunden från lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill ta bort bakgrunden från. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Color space]</p>
      </td>
   <td>Välj om utdatabilden ska ha RGB- eller RGBA-färg. </td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Mask format]</p>
      </td>
   <td>Ange om kanterna på bilden ska vara mjuka (luddiga) eller binära. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Optimize]</p>
      </td>
   <td>Välj Prestanda om du vill optimera hastigheten eller Gruppera om du vill tillåta väntetid. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Post process]</p>
      </td>
   <td>Välj om efterbearbetning ska aktiveras.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Version]</p>
      </td>
   <td>Standard är 4.0</td> 
    </tr> 
    </tbody>
</table>

### Ersätta ett smart objekt

Den här åtgärdsmodulen ersätter ett smart objekt i ett PSD-lager och skapar nya återgivningar.

I den här modulen används API-version 2 för smarta objekt.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där det smarta objektet lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa det smarta objektets URL eller sökväg. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>För varje lager som du vill lägga till i det smarta objektet klickar du på Lägg till och anger objektets namn eller ID, filtjänsten där det smarta objektet lagras och lagrets URL eller bana.<p>Beskrivningar av de avancerade inställningarna i det här området finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Ersätta ett smart objekt</a> i Photoshop API-dokumentationen </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Resize image during place]</p>
      </td>
   <td> Välj om du vill ändra storlek på bilden.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje ny återgivning som du vill att modulen ska skapa klickar du på Lägg till objekt och fyller i följande fält. Du kan ha högst 25 utdatafiler.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Outputs) Type]</p>
      </td>
   <td> Välj filtyp för den redigerade filen. </td> 
    </tr>
     </tbody>
</table>

### Ersätta ett smart objekt (äldre)

Den här åtgärdsmodulen ersätter ett smart objekt i ett PSD-lager och skapar nya återgivningar.

Den här modulen använder den äldre versionen av smarta objekt.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där det smarta objektet lagras.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Input) File location]</p>
      </td>
   <td> Ange eller mappa det smarta objektets URL eller sökväg. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Layers]</p>
      </td>
   <td>För varje lager som du vill lägga till i det smarta objektet klickar du på Lägg till och anger objektets namn eller ID, filtjänsten där det smarta objektet lagras och lagrets URL eller bana.<p>Beskrivningar av de avancerade inställningarna i det här området finns i <a href="https://developer.adobe.com/firefly-services/docs/photoshop/api/#operation/replaceSmartObjectAsync">Ersätta ett smart objekt</a> i Photoshop API-dokumentationen </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje ny återgivning som du vill att modulen ska skapa klickar du på Lägg till objekt och fyller i följande fält. Du kan ha högst 25 utdatafiler.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> Utdatafilens bredd i pixlar. De ursprungliga proportionerna bevaras i modulen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tbody>
</table>

### Ändra bildstorlek

Den här åtgärden ändrar storlek på en bild med samma proportioner.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill ändra storlek på lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till filen som du vill ändra storlek på.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Outputs]</td>
      <td>
        <p>För varje konverterad fil som du vill skapa klickar du på Lägg till objekt och anger lagringsutrymme, plats och andra alternativ som visas i den här tabellen.</p>
      </td>
    </tr>
    <tr>
    <tr>
      <td role="rowheader">[!UICONTROL Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att den nya filen ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen till den plats där den nya filen ska lagras.  Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Width]</p>
      </td>
   <td> Utdatafilens bredd i pixlar. De ursprungliga proportionerna bevaras i modulen. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Max width]</p>
      </td>
   <td>När bredden är 0 kan Max med anges för att få storleken. Maximal bredd har företräde eftersom den är mindre än dokumentbredden.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tr>
        <tr>
      <td role="rowheader">
        <p>[!UICONTROL Trim to canvas]</p>
      </td>
   <td>Välj Ja om du vill trimma återgivningarna till arbetsytans storlek eller Nej om du vill göra återgivningslagrets storlek.</td> 
    </tr>
    </tbody>
</table>

### Vattenstämpla en bild

Den här åtgärdsmodulen lägger till en vattenstämpel till den markerade bilden.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Photoshop] finns i <a href="#create-a-connection-to-adobe-photoshop" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Photoshop]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Base > Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där filen som du vill lägga till en vattenstämpel finns.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Base > Input) File location]</p>
      </td>
   <td> Ange eller mappa URL-adressen eller sökvägen till filen som du vill lägga till en vattenstämpel i. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Watermark > Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där vattenstämpeln som du vill lägga till finns.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Watermark > Input) Storage]</td>
      <td>
        <p>Välj den filtjänst där vattenstämpeln som du vill lägga till finns.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark > Bounds) Height]</p>
      </td>
   <td>Ange eller mappa vattenstämpelns önskade höjd i pixlar.</td> 
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark > Bounds) Width]</p>
      </td>
   <td> Ange eller mappa önskad bredd för vattenstämpeln i pixlar. </td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark > Bounds) Left]</p>
      </td>
   <td> Ange eller mappa det avstånd i pixlar från bildens vänstra sida som vattenstämpeln ska vara.</td> 
    </tr>  
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Watermark > Bounds) Top]</p>
      </td>
   <td> Ange eller mappa det avstånd i pixlar från bildens överkant som vattenstämpeln ska vara.</td> 
    </tr>  
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Storage]</td>
      <td>
        <p>Välj den filtjänst där du vill att filen med vattenstämpel ska lagras.</p><p>Om du väljer Fusion internal storage blir filen tillgänglig för senare moduler, men filen blir inte tillgänglig utanför scenariot.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) File location]</p>
      </td>
   <td> Ange eller mappa URL:en eller sökvägen där filen med vattenstämpel ska lagras. Detta är bara nödvändigt om du inte har valt Fusion intern lagring för utdatalagringen.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Type]</p>
      </td>
   <td>Välj den filtyp som du vill konvertera filen till. </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL (Output) Width]</p>
      </td>
   <td> Utdatafilens bredd i pixlar. De ursprungliga proportionerna bevaras i modulen. </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL (Output) Overwrite]</td>
      <td>
        <p>Välj om den nyligen redigerade filen ska skriva över alla utdatafiler som redan finns. Detta gäller endast filer i Adobe-lagringsutrymme.</p>
      </td>
    </tbody>
</table>
