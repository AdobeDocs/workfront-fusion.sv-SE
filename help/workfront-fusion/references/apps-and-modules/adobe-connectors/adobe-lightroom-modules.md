---
title: Adobe Lightroom moduler
description: Med Adobe Lightroom-modulerna kan du starta ett Adobe Workfront Fusion-scenario baserat på händelser i ditt Adobe Lightroom-konto.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
source-git-commit: 4f97980dce7c8df47ab73d51537d4700ac34dedf
workflow-type: tm+mt
source-wordcount: '2376'
ht-degree: 0%

---

# [!DNL Adobe Lightroom] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Lightroom] samt ansluta det till flera tredjepartsprogram och -tjänster.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
      <td>
        <p>[!UICONTROL Pro] eller senare</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
      <td>
        <p>[!UICONTROL -plan], [!UICONTROL -arbete]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td>
      <td >
        <p>[!UICONTROL Workfront Fusion for Work Automation and Integration]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Produkt</td>
      <td>Din organisation måste köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</td>
    </tr>
    </tr>
  </tbody>
</table>


&#42;Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

&#42;&#42;Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL [Adobe Workfront Fusion] licenses]](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Innan du kan använda [!DNL Adobe Lightroom]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Lightroom]-konto.

## Adobe Lightroom API-information

Adobe Lightroom Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://lr.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.17.128</td> 
  </tr>
 </tbody> 
 </table>



## Skapa en anslutning till Adobe Lightroom

Så här skapar du en anslutning för dina [!DNL Adobe Lightroom]-moduler:

1. Klicka på **[!UICONTROL Lägg till]** bredvid rutan Anslutning i en modul.

1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL -anslutningsnamn]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL -typ]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL -klient-ID]</td>
        <td>Ange ditt [!UICONTROL Adobe] [!UICONTROL klient-ID]. Detta finns i avsnittet med information om [!UICONTROL -autentiseringsuppgifter] i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL -klienthemlighet]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL -klienthemlighet]. Detta finns i avsnittet med information om [!UICONTROL -autentiseringsuppgifter] i [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Fortsätt]** för att spara anslutningen och återgå till modulen.




## Adobe Lightroom-moduler och deras fält

När du konfigurerar [!DNL Adobe Lightroom] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Adobe Lightroom] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Övriga](#other)
* [Assets](#assets)
* [Album](#albums)

### Övriga

* [Hälsokontroll](#health-check)
* [Hämta användarkatalogmetadata](#retrieve-user-catalog-metadata)

#### Hälsokontroll

Den här åtgärdsmodulen hämtar ett version-ID för Lightroom-servern som visar om Lightroom-tjänsten körs.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -autentiseringsuppgifter]</td>
      <td>
        <p>Om du vill ange specifika autentiseringsuppgifter för att säkerställa att en viss server körs klickar du på Lägg till objekt och anger autentiseringsuppgifterna.</p><p>Autentiseringsrubriker läggs till automatiskt.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Hämta användarkatalogmetadata

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -autentiseringsuppgifter]</td>
      <td>
        <p>Om du vill ange specifika inloggningsuppgifter för att säkerställa att du har åtkomst till rätt användarkonto klickar du på Lägg till objekt och anger inloggningsuppgifterna.</p><p>Autentiseringsrubriker läggs till automatiskt.</p>
      </td>
    </tr>
  </tbody>
</table>

### Assets

* [Skapa en originalfil för en resurs](#create-an-asset-external-xmp-develop-setting-file)
* [Skapa en resurs](#create-an-asset)
* [Skapa en extern XMP-framkallningsinställningsfil](#create-an-asset-external-xmp-develop-setting-file)
* [Generera återgivningar för en originalfil](#generate-renditions-for-an-original-file)
* [Hämta en katalogresurs](#get-a-catalog-asset)
* [Hämta den senaste resursinställningen för extern XMP-utveckling](#get-the-latest-asset-external-xmp-develop-setting-file)
* [Hämta den senaste resursåtergivningen](#get-the-latest-asset-rendition)
* [Hämta resurser](#retrieve-assets)

#### Skapa en originalfil för en resurs

Den här åtgärdsmodulen skapar och överför en originalfil för en resurs.


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som du vill skapa och överföra en fil för.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Längd på innehåll i byte]</td>
      <td>
        <p>Ange eller mappa innehållets längd i byte.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -byteintervall]</td>
      <td>
        <p>Ange eller mappa byteintervallet för begäran, inklusive första och sista byte och enhetslängd enligt RFC 2616. Ska endast inkluderas när data är för stora för att överföras i ett enda anrop.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -innehållstyp]</td>
      <td>
        <p>Välj innehållstyp för den nya filen.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Skapa en resurs

Den här åtgärdsmodulen skapar en ny resurs med initiala metadata och importinformation.


<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen där resursen ska skapas.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa den nya resursens ID.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurstyp]</td>
      <td>
        <p>Välj om resursen är en bild eller en video.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL DateTime-användare har skapats]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Date capture]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00</code>.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Skapa en extern XMP-framkallningsinställningsfil

Den här åtgärdsmodulen stöder två arbetsflöden. Det första arbetsflödet är att överföra den externa XMP-filen med framkallningsinställningar för resursen. Det andra arbetsflödet är att skapa en extern XMP-framkallningsinställningsfil genom att kopiera från en annan resurs externa xmp-framkallningsinställningsfil.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Längd på innehåll i byte]</td>
      <td>
        <p>Ange eller mappa innehållets längd i byte.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ladda upp ny eller kopiera XMP/framkallningsfil]</td>
      <td>
        <p>Välj om du vill överföra en ny fil eller kopiera en fil från en befintlig resurs.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som du vill överföra eller kopiera en fil till.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Link to XMP/develop file]</td>
      <td>
        <p>Ange eller mappa en länk till filen som du vill överföra eller kopiera.</p><p>Filen måste vara JSON om du kopierar en fil, eller XML om du överför en fil.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Generera återgivningar för en originalfil

Den här åtgärdsmodulen genererar återgivningar asynkront för en originalfil.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -återgivningstyp(er) (semikolonavgränsad)]</td>
      <td>
        <p>Ange återgivningstypen för den återgivning som du vill skapa. Om du anger mer än en typ avgränsar du dem med ett semikolon (;). <p>Möjliga typer:</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Längd på innehåll i byte]</td>
      <td>
        <p>Ange eller mappa innehållets längd i byte.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som du vill skapa en återgivning av en fil för.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Hämta en katalogresurs

Denna åtgärdsmodul hämtar information om en enskild resurs i en katalog. Katalogen måste ägas av den användare vars autentiseringsuppgifter representeras i anslutningen som används i den här modulen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som du vill hämta information för.</p>
      </td>
    </tr>
  </tbody>
</table>


#### Hämta den senaste resursinställningsfilen för extern XMP-utveckling

Den här åtgärdsmodulen hämtar den senaste resursens externa XMP-inställningsfil.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som är associerad med XMP framkallningsinställningsfil.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Hämta den senaste resursåtergivningen

Den här åtgärdsmodulen hämtar den senaste resursåtergivningen av den angivna typen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som är associerad med XMP framkallningsinställningsfil.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -återgivningstyp]</td>
      <td>
        <p>Välj vilken typ av återgivning du vill hämta.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Hämta resurser

Den här åtgärdsmodulen hämtar resurser som ägs av användaren vars autentiseringsuppgifter representeras i anslutningen som används i den här modulen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Startar tidsstämpel]</td>
      <td>
        <p>Ange eller mappa en tidsstämpel. Modulen returnerar poster som har uppdaterats efter den här tidsstämpeln.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Returnera resurser som hämtats före]</td>
      <td>
        <p>Ange ett datum med formatet <code>YYYY-MM-DDT00:00:00</code>. Modulen returnerar resultat som hämtats före detta datum.</p><p> Det här fältet kan inte användas med fältet <code>Return assets captured after</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximalt antal returnerade resurser]</td>
      <td>
        <p>Ange det högsta antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256 Hash-värde för originalfilen]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Dölja resurser som finns i högar?"]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset subtype values]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID:n]</td>
      <td>
        <p>Ange eller mappa upp till 100 resurs-ID:n, avgränsade med kommatecken.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Types of assets to exclude]</td>
      <td>
        <p>Välj om du vill exkludera fullständiga eller ofullständiga resurser. Om du vill inkludera alla resurser lämnar du det här fältet tomt.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL -gruppvärden]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -namnvärden]</td>
      <td>
        <p></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -favoritstatus]</td>
      <td>
        <p></p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### Album

* [Lägga till resurser i ett album](#add-assets-to-an-album)
* [Skapa ett album](#create-an-album)
* [Ta bort ett album](#delete-an-album)
* [Hämta ett album](#get-an-album)
* [Visa resurser i ett album](#list-assets-of-an-album)
* [Hämta album](#retrieve-albums)
* [Uppdatera ett album](#update-album)

#### Lägga till resurser i ett album

Den här åtgärdsmodulen lägger till en eller flera resurser i det angivna albumet. Du kan lägga till upp till 50 resurser i en körningscykel.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för den katalog som innehåller det album du vill lägga till resurser i.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -album-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för det album du vill lägga till resurser i.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Assets]</td>
      <td>
        <p>För varje resurs som du vill lägga till i albumet klickar du på <b>Lägg till objekt</b> och anger följande fält.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL -resurs-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för resursen som du vill lägga till i albumet</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Är den här resursen ett albumomslag?]</td>
      <td>
        <p>Välj om du vill att resursen ska visas som den bild som representerar albumet.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL -ordning]</td>
      <td>
        <p></p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL -metadata]</td>
      <td>
        <p>Ange eller mappa alla metadata som du vill inkludera med resursen. Detta måste vara en enda textsträng med en maxlängd på 1-24 tecken.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL fjärr-ID]</td>
      <td>
        <p>Ange en identifierare för resursen.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Skapa ett album

Den här åtgärdsmodulen skapar ett nytt album i Lightroom.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen där du vill skapa ett album.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -album-ID]</td>
      <td>
        <p>Ange eller mappa ett ID för det nya albumet.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -undertyp]</td>
      <td>
        <p>Välj undertyp för albumet.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL API-nyckel]</td>
      <td>
        <p>Ange API-nyckeln för den tjänst som skapar albumet.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL DateTime-användare har skapats]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Datetime user updated]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -albumnamn]</td>
      <td>
        <p>Ange eller mappa ett namn för det nya albumet.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Cover ID]</td>
      <td>
        <p>Ange eller mappa ID:t för en resurs som ska användas som omslag till det här albumet.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL fjärr-ID]</td>
      <td>
        <p>Ange en identifierare för resursen.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL skapad den]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL uppdaterat den]</td>
      <td>
        <p>Ange eller mappa ett datum med formatet <code>YYYY-MM-DDT00:00:00-00:00Z</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Är albumet borttaget?]</td>
      <td>
        <p>Aktivera det här alternativet om externt tillhörande innehåll har tagits bort.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL för platsen för att redigera närliggande innehåll]</td>
      <td>
        <p>Om det finns en URL där användare kan redigera innehåll i det här albumet anger du URL:en här.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL för platsen för att visa anslutet innehåll]</td>
      <td>
        <p>Om det finns en URL där användarna kan visa innehållet i det här albumet anger du URL:en här.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Ta bort ett album

Den här åtgärdsmodulen tar bort ett album.

Det borttagna albumet måste ha skapats av samma klientprogram som nu tar bort det, och det måste vara av undertypen `project` eller `project_set`.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller det album du vill ta bort.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -album-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för det album du vill ta bort.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ta bort underordnade album?]</td>
      <td>
        <p>Välj om du vill ta bort underordnade album för det borttagna albumet.</p>
      </td>
    </tr>
  </tbody>
</table>

### Hämta ett album

Den här åtgärdsmodulen hämtar angivet album

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller det album som du vill hämta.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -album-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för det album du vill hämta.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Visa resurser i ett album

Den här åtgärdsmodulen hämtar en lista med resurser i det angivna albumet.



#### Hämta album

Den här åtgärdsmodulen hämtar en lista med album i den angivna katalogen.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller album som du vill hämta.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -undertyper]</td>
      <td>
        <p>Ange eller mappa ID:t för det album du vill hämta.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -namn på album som ska föregå aktuella resultat]</td>
      <td>
        <p>Om du sidnumrerar dina resultat anger eller mappar du namnet på det sista albumet på föregående sida.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Maximalt antal returnerade album]</td>
      <td>
        <p>Ange det maximala antalet resurser som [!DNL Workfront Fusion] ska returnera under en körningscykel. Standardvärdet för det här fältet är 100. Den här modulen kan returnera fler album än den här gränsen om flera album vid gränsen har samma <code>name_after</code>-värde.</p>
      </td>
    </tr>
  </tbody>
</table>

#### Uppdatera album

Den här åtgärdsmodulen uppdaterar det angivna albumet.

Det uppdaterade albumet måste ha skapats av samma klientprogram som nu uppdaterar det, och det måste vara av undertypen `project` eller `project_set`.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL -anslutning]</td>
      <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Lightroom] finns i <a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Lightroom]</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -katalog-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för katalogen som innehåller det album som du vill uppdatera.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL -album-ID]</td>
      <td>
        <p>Ange eller mappa ID:t för det album du vill uppdatera.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
      <td>
      <td>Beskrivningar av andra fält i den här modulen finns i <a href="#create-an-album" class="MCXref xref" >Skapa ett album</a> i den här artikeln.</td>
      </td>
    </tr>
  </tbody>
</table>
