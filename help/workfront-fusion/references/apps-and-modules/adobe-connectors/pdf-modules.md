---
title: Adobe PDF Services
description: Adobe PDF Services
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: e6fbbc20-4315-4668-9e11-af7cfa82ae66
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '3623'
ht-degree: 0%

---

# [!DNL Adobe PDF Services]

Med [!DNL Adobe Workfront Fusion] [!DNL Adobe PDF Services] kan du extrahera data från en PDF-fil eller generera en ny PDF-fil från data du anger. Dessutom kan du konvertera en mängd olika filtyper till PDF-filer eller PDF-filer till andra filtyper. Med PDF Services kan du också kombinera, komprimera och läsa metadata för en PDF-fil samt styra lösenordsskyddet för filen.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

Mer information om API:t som används för PDF Services finns i [Adobe API för dokumentgenerering](https://www.adobe.io/apis/documentcloud/dcsdk/doc-generation.html).

## Säkerhetsaspekter vid användning av [!DNL Adobe PDF Services]

[!DNL Adobe PDF Services] kan läsa, konvertera eller ändra dina filer, men varken [!DNL Adobe] eller [!DNL Workfront Fusion] lagrar dina filer eller data. Detta innebär att

* Du behåller kontrollen över dina filer, inklusive deras säkerhet
* Du behöver inte ha något [!UICONTROL Adobe]-lagringskonto eller molnlagringskonto för att kunna använda PDF Services.

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

Om du vill skapa en OAuth Server-till-Server-anslutning måste du lägga till Adobe PDF Services-API:t i Adobe Developers Console. När du lägger till API:t väljer du alternativet OAuth Server-till-server.

Instruktioner finns i [Lägg till API i projekt med OAuth](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/) i dokumentationen för Adobe-utvecklare.

## API-information för Adobe PDF Services

Adobe PDF Services Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://pdf-services-stage.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.1.4</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till [!DNL Adobe PDF Services]

Så här skapar du en anslutning för dina [!DNL Adobe PDF Services]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid anslutningsrutan i någon [!DNL Adobe PDF Services]-modul.

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
            <p>Välj om du vill skapa en server-till-server-anslutning eller en JWT-anslutning.</p>
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
          <td>Ange din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du hittar autentiseringsuppgifter finns i <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Referenser</a> i dokumentationen för Adobe-utvecklare.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du hittar autentiseringsuppgifter finns i <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Referenser</a> i dokumentationen för Adobe-utvecklare.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Technical account ID] (endast JWT)</td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Technical account ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du hittar autentiseringsuppgifter finns i <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Referenser</a> i dokumentationen för Adobe-utvecklare.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Organization ID] (endast JWT)</td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Organization ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du hittar autentiseringsuppgifter finns i <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Referenser</a> i dokumentationen för Adobe-utvecklare.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Meta scopes] (endast JWT)</td>
          <td>
            Ange eventuella metaomfång som behövs för anslutningen.
          </td>
        </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Om du har valt en JWT-anslutning anger du den privata nyckel som skapades när dina autentiseringsuppgifter skapades i [!DNL Adobe Developer Console]. </p>
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
              <p>Klicka på <b>[!UICONTROL Save]</b> för att extrahera filen och återgå till anslutningsinställningarna.</p>
            </li>
          </ol>
        </td>
      </tr>
       </tbody>
    </table>
1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.


## [!DNL Adobe PDF Services]-moduler och deras fält

När du konfigurerar [!DNL PDF Services] visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En fetstilt titel i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Combine PDF files]](#combine-pdf-files)
* [[!UICONTROL Compress PDF files]](#compress-pdf-files)
* [[!UICONTROL Convert document to PDF file]](#convert-document-to-pdf-file)
* [[!UICONTROL Convert HTML to PDF file]](#convert-html-to-pdf-file)
* [[!UICONTROL Convert image to PDF file]](#convert-image-to-pdf-file)
* [[!UICONTROL Convert PDF to document]](#convert-pdf-to-document)
* [[!UICONTROL Convert PDF to image]](#convert-pdf-to-image)
* [[!UICONTROL Extract Text / Table]](#extract-text--table)
* [[!UICONTROL Generate document]](#generate-document)
* [[!UICONTROL Linearize a PDF file]](#linearize-a-pdf-file)
* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [[!UICONTROL OCR for PDF file]](#ocr-for-pdf-file)
* [[!UICONTROL Page manipulation]](#page-manipulation)
* [[!UICONTROL PDF accessibility auto-tag]](#pdf-accessibility-auto-tag)
* [[!UICONTROL PDF file properties]](#pdf-file-properties)
* [[!UICONTROL Protect PDF file]](#protect-pdf-file)
* [[!UICONTROL Remove protection of a PDF file]](#remove-protection-of-a-pdf-file)
* [Dela en PDF-fil](#split-a-pdf-file)

### [!UICONTROL Combine PDF files]

Den här åtgärdsmodulen tar flera PDF-filer och kombinerar dem i en enda PDF-fil. Den här modulen kan till exempel kombinera alla dokument i ett [!UICONTROL Workfront]-projekt till en enda PDF när projektet har slutförts.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents]</td> 
   <td> <p>Du kan använda en aggregeringsmodul för att samla dokument som ska kombineras till en PDF, eller så kan du lägga till dokumenten manuellt. </p> <p>Vi rekommenderar att du använder en [!UICONTROL Array Aggregator]-modul för att sammanställa utdata från en tidigare modul. Genom att använda en aggregator behöver du inte känna till namn, plats eller antal filer som ska kombineras. Att använda en aggregator är därför mycket flexiblare och mer skalbart än att manuellt ange de dokument som ska kombineras.</p> <p>Om du vill använda filmodulen [!UICONTROL Combine PDF] med en aggregator måste du aktivera mappning i fältet [!UICONTROL Documents]. </p> <p>I det här exemplet identifierar modulen [!UICONTROL Read Related Records] dokument som är kopplade till ett projekt och modulen [!UICONTROL Download Documents] hämtar vart och ett av dem. Alla PDF-filer samlas i en array, som skickas till [!UICONTROL Combine PDF]-filmodulen.</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/combine-example-350x104.png" style="width: 350;height: 104;"> </p> <p>Du kan också ange dokument manuellt.</p> <p>För varje dokument som ska inkluderas i den kombinerade PDF:</p> 
    <ol> 
     <li value="1"> <p>Klicka på [!UICONTROL Add a Document]</p> </li> 
     <li value="2"> <p>I fältet [!UICONTROL Source file] markerar du modulen som matar ut dokumentet som du vill inkludera, eller mappar källfilens namn och data. </p> </li> 
     <li value="3"> <p>(Valfritt) Om du bara vill inkludera vissa sidor från källfilen, för varje sidintervall som du vill lägga till, klickar du på <strong>[!UICONTROL Add item]</strong> i fältet [!UICONTROL Pages], anger den första och sista sidan i sidintervallet som ska inkluderas och klickar på <strong>[!UICONTROL Add]</strong>. Du kan inkludera mer än ett sidintervall från ett enstaka dokument.</p> </li> 
     <li value="4"> <p>Klicka på <strong>[!UICONTROL Add]</strong>. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Compress PDF files]

Den här åtgärdsmodulen tar en PDF-fil och komprimerar den. Detta kan vara användbart för att spara bandbredd eller minne.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compression level]</td> 
   <td>Välj den komprimeringsnivå som du vill använda.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert document to PDF file]

Det här verktyget konverterar ett dokument till en PDF-fil. Källfilen måste ha något av följande dokumentformat:

* DOC
* XLS
* PPT
* TXT
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste ha något av följande format:</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>XLS</p> </li> 
     <li> <p>PPT</p> </li> 
     <li> <p>TXT</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>Välj standardspråk för källdokumentet. Detta gör att modulen kan välja ett lämpligt teckensnitt, om det inte finns något teckensnitt i källfilen.</p> <p>Välj bland följande språk:</p> 
    <ul> 
     <li> <p>en-US (standard): engelska (USA)</p> </li> 
     <li> <p>ca-ES: Katalanska (Spanien)</p> </li> 
     <li> <p>cs-CZ: Tjeckiska (Tjeckien)</p> </li> 
     <li> <p>da-DK: danska (Danmark)</p> </li> 
     <li> <p>de-DE: German (Germany)</p> </li> 
     <li> <p>en-AE: Engelska (Förenade Arabemiraten)</p> </li> 
     <li> <p>en-GB: Engelska (Storbritannien)</p> </li> 
     <li> <p>en-IL: Engelska (Israel)</p> </li> 
     <li> <p>en-US: Engelska (USA)</p> </li> 
     <li> <p>es-ES: Spanska (Spanien)</p> </li> 
     <li> <p>es-MX: Spanska (Mexiko)</p> </li> 
     <li> <p>eu-ES: Baskiska (Spanien)</p> </li> 
     <li> <p>fi-FI: Finska (Finland)</p> </li> 
     <li> <p>fr-CA: Franska (Kanada)</p> </li> 
     <li> <p>fr-FR: Franska (Frankrike)</p> </li> 
     <li> <p>fr-MA: Franska (Marocko)</p> </li> 
     <li> <p>hr-HR: Kroatiska (Kroatien)</p> </li> 
     <li> <p>hu-HU: Ungerska (Ungern)</p> </li> 
     <li> <p>IT-IT: Italienska (Italien)</p> </li> 
     <li> <p>ja-JP: Japanska (Japan)</p> </li> 
     <li> <p>kr-KR: Koreanska (Sydkorea)</p> </li> 
     <li> <p>Anm. NO: Norska bokmål (Norge)</p> </li> 
     <li> <p>nl-NL: Nederländska (Nederländerna)</p> </li> 
     <li> <p>pl-PL: Polska (Polen)</p> </li> 
     <li> <p>pt-BR: Portugisiska (Brasilien)</p> </li> 
     <li> <p>pt-PT: Portugisiska (Portugal)</p> </li> 
     <li> <p>ro-RO: Rumänska (Rumänien)</p> </li> 
     <li> <p>RU: Ryska (Ryssland)</p> </li> 
     <li> <p>sk-SK: Slovakiska (Slovakien)</p> </li> 
     <li> <p>sl-SI: Slovenska (Slovenien)</p> </li> 
     <li> <p>sv-SE: Swedish (Sweden)</p> </li> 
     <li> <p>tr-TR: Turkiska (Turkiet)</p> </li> 
     <li> <p>uk-UA: Ukrainska (Ukraina)</p> </li> 
     <li> <p>zh-CN: Kinesiska (fastlandet Kina)</p> </li> 
     <li> <p>zh-TW: Kinesiska (Taiwan)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert HTML to PDF file]

Med det här verktyget kan du konvertera en HTML-fil till en PDF-fil.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Viktigt: Source-filen måste vara i HTML- eller ZIP-format. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON]</td> 
   <td> <p>Om HTML refererar till JavaScript-variabler kan du ta med dessa variabler här. </p> <p>För varje variabel klickar du på <strong>[!UICONTROL Add item]</strong> och tar med variabelns nyckel och värde.</p> <p>Obs!   
     <ul> 
      <li> <p>När du skapar en PDF från en ZIP-fil måste källmaterialet innehålla ett skriptelement som: <code> &lt;script src='./json.js' type='text/javascript'&gt;&lt;/script&gt;</code> </p> </li> 
      <li> <p>När du skapar en PDF från en URL, injiceras innehållet i det här JSON-objektet i den virtuella webbläsaren innan sidan återges. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include header and footer]</td> 
   <td> <p>Aktivera det här alternativet om du vill skapa sidhuvuden och sidfötter för PDF-dokumentet.</p> 
    <ul> 
     <li> <p>Rubriken innehåller ett datum och dokumenttiteln.</p> </li> 
     <li> <p>Sidfoten innehåller filnamnet och ett sidnummer.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page width]</td> 
   <td>Ange papperets bredd i tum. I modulen används den här informationen för att formatera sidorna i den skapade PDF-filen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page height]</td> 
   <td>Ange papperets höjd i tum. I modulen används den här informationen för att formatera sidorna i den skapade PDF-filen.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert image to PDF file]

Det här verktyget konverterar en bild till en PDF-fil.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och bildfil.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to document]

Med det här verktyget kan du konvertera en PDF-fil till ett dokument. Du kan välja något av följande format för utdatafilen.

* DOC
* DOCX
* PPTX
* XSX
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>Välj det format som du vill att filerna ska skrivas ut som:</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>DOCX</p> </li> 
     <li> <p>PPTX</p> </li> 
     <li> <p>XSX</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>Välj standardspråk för källdokumentet. Detta gör att modulen kan välja ett lämpligt teckensnitt, om det inte finns något teckensnitt i källfilen.</p> <p>Välj bland följande språk:</p> 
    <ul> 
     <li> <p>en-US (standard): engelska (USA)</p> </li> 
     <li> <p>ca-ES: Katalanska (Spanien)</p> </li> 
     <li> <p>cs-CZ: Tjeckiska (Tjeckien)</p> </li> 
     <li> <p>da-DK: danska (Danmark)</p> </li> 
     <li> <p>de-DE: German (Germany)</p> </li> 
     <li> <p>en-AE: Engelska (Förenade Arabemiraten)</p> </li> 
     <li> <p>en-GB: Engelska (Storbritannien)</p> </li> 
     <li> <p>en-IL: Engelska (Israel)</p> </li> 
     <li> <p>en-US: Engelska (USA)</p> </li> 
     <li> <p>es-ES: Spanska (Spanien)</p> </li> 
     <li> <p>es-MX: Spanska (Mexiko)</p> </li> 
     <li> <p>eu-ES: Baskiska (Spanien)</p> </li> 
     <li> <p>fi-FI: Finska (Finland)</p> </li> 
     <li> <p>fr-CA: Franska (Kanada)</p> </li> 
     <li> <p>fr-FR: Franska (Frankrike)</p> </li> 
     <li> <p>fr-MA: Franska (Marocko)</p> </li> 
     <li> <p>hr-HR: Kroatiska (Kroatien)</p> </li> 
     <li> <p>hu-HU: Ungerska (Ungern)</p> </li> 
     <li> <p>IT-IT: Italienska (Italien)</p> </li> 
     <li> <p>ja-JP: Japanska (Japan)</p> </li> 
     <li> <p>kr-KR: Koreanska (Sydkorea)</p> </li> 
     <li> <p>Anm. NO: Norska bokmål (Norge)</p> </li> 
     <li> <p>nl-NL: Nederländska (Nederländerna)</p> </li> 
     <li> <p>pl-PL: Polska (Polen)</p> </li> 
     <li> <p>pt-BR: Portugisiska (Brasilien)</p> </li> 
     <li> <p>pt-PT: Portugisiska (Portugal)</p> </li> 
     <li> <p>ro-RO: Rumänska (Rumänien)</p> </li> 
     <li> <p>RU: Ryska (Ryssland)</p> </li> 
     <li> <p>sk-SK: Slovakiska (Slovakien)</p> </li> 
     <li> <p>sl-SI: Slovenska (Slovenien)</p> </li> 
     <li> <p>sv-SE: Swedish (Sweden)</p> </li> 
     <li> <p>tr-TR: Turkiska (Turkiet)</p> </li> 
     <li> <p>uk-UA: Ukrainska (Ukraina)</p> </li> 
     <li> <p>zh-CN: Kinesiska (fastlandet Kina)</p> </li> 
     <li> <p>zh-TW: Kinesiska (Taiwan)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to image]

Det här verktyget konverterar en PDF-bild till en bild i PNG- eller JPEG-format, som sedan skrivs ut som en lista eller kombineras till en ZIP-fil.

Om du skriver ut som en ZIP-fil konverteras PDF till en bild per sida och varje bild avslutas med sidnumret. Bildfilerna kombineras sedan till en ZIP-fil.

En fil med namnet&quot;TestFile&quot; med 8 sidor ger till exempel 8 bilder med namnet&quot;TestFile_1&quot; till&quot;TestFile_8&quot;. Modulens utdata är en ZIP-fil som innehåller de 8 bilderna.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>Välj det format som du vill att filerna ska skrivas ut som:</p> 
    <ul> 
     <li>PNG</li> 
     <li>JPEG</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output type]</td> 
   <td> <p>Välj om du vill att filerna ska skrivas ut som en fillista eller som en ZIP-fil.</td> 
  </tr> 
  <tr> 
 </tbody> 
</table>

### [!UICONTROL Extract Text / Table]

Med den här åtgärdsmodulen kan du extrahera data från en PDF-fil. Modulen matar ut enskilda textelement, t.ex. ett stycke eller texten i en enda cell i en tabell.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Elements that should be extracted as JSON]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Text]</p> </li> 
     <li> <p>[!UICONTROL Tables]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Extract Bounding boxes?]</td> 
   <td>Aktivera det här alternativet om du vill extrahera data om textens begränsningsram.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include styling information for output?]</td> 
   <td>Aktivera det här alternativet om du vill lägga till formatinformation i JSON-utdata.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Generate document]

Modulen [!UICONTROL Generate document] är ett kraftfullt sätt att skapa en PDF som innehåller data som du väljer. Du kan formatera den med hjälp av en [!DNL Microsoft Word]-mall eller genom att ange data i JSON-format.

Mer information om funktionen [!UICONTROL [!DNL Adobe PDF Services] Generate document] finns i [Översikt över dokumentgenerering](https://www.adobe.io/apis/documentcloud/dcsdk/docs.html) i [!DNL Adobe Document Services]-dokumentationen.

* [Använd modulen [!UICONTROL Generate document] med en  [!DNL Microsoft Word] mall](#use-the-generate-document-module-with-a-microsoft-word-template)
* [Använd modulen [!UICONTROL Generate document] med JSON](#use-the-generate-document-module-with-json)

#### Använd modulen [!UICONTROL Generate document] med en [!DNL Microsoft Word]-mall


>[!NOTE]
>
>Mer information om Microsoft Word-mallar finns i [Microsoft Word-mallmoduler](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-word-templates-modules.md).
>
>Du behöver inte använda Microsoft Word-mallmoduler för att använda en Microsoft Word-mall med PDF Services Generate-dokumentmodulen.


Om du vill använda modulen [!UICONTROL Generate document] med en [!UICONTROL Microsoft Word]-mall måste du först skapa mallen. Sök efter&quot;Skapa en mall&quot; i dokumentationen för [!DNL Microsoft Office] om du vill ha anvisningar.

Fyll i fälten i modulen [!UICONTROL Generate document] enligt följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Den här källfilen är mallen [!DNL Microsoft Word] som används i modulen för att skapa nya PDF.</p> <p>Vi rekommenderar att du skapar ett projekt i [!DNL Workfront] för de [!DNL Microsoft Word] -mallar som du använder i [!DNL Workfront Fusion]. Du kan sedan använda modulen [!DNL Workfront] &gt; [!UICONTROL Download document] för att hämta rätt mall till ditt scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>Välj format för det genererade dokumentet.</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>Fyll i följande för varje värdetagg i mallen som du vill ersätta med text:</p> 
    <ul> 
     <li> <p>[!UICONTROL Key]</p> <p>Ange en tangent. I mallen är nyckeln texten som visas i värdetaggen. Om du till exempel vill placera text i värdetaggen <code>&#123;&#123;name&#125;&#125;</code> anger du <code>name </code> i nyckelfältet.</p> </li> 
     <li> <p>Värdetyp</p> <p>Ange om data i värdefältet är ett värde, ett objekt eller en array med objekt.</p> </li> 
     <li> <p>[!UICONTROL Value]</p> <p>Ange eller mappa texten som du vill ska visas i det genererade dokumentet i stället för värdetaggen.</p> </li> 
    </ul> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/generate-with-template-350x241.png" style="width: 350;height: 241;"> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Använd modulen [!UICONTROL Generate document] med JSON

Om du vill använda modulen [!UICONTROL Generate document] med JSON fyller du i fälten enligt följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>Välj format för det genererade dokumentet.</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>Om du vill använda JSON i den här modulen måste du aktivera mappning för det här fältet.</p> <p>Ange eller mappa det JSON-objekt som dokumentet ska skapas från. </p> <p>Du kan skriva JSON direkt i det här fältet eller mappa JSON-utdata från en JSON-modul.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Linearize a PDF file]

Det här verktyget linjäriserar ett PDF-dokument och skapar ett webboptimerat PDF-dokument. Ett linjärt PDF-dokument kan visas sida för sida utan att hela dokumentet behöver hämtas.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Göra ett anpassat API-anrop

Den här åtgärdsmodulen är en anpassad HTTP-begäran till PDF Services API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> Ange en relativ sökväg eller en URL. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger automatiskt till auktoriseringshuvuden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>För varje fält som du vill lägga till i API-anropet klickar du på <b>Lägg till objekt</b> och anger fältets nyckel och valfria värde.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


### [!UICONTROL OCR for PDF file]

Det här verktyget utför optisk teckenigenkänning (OCR) på en fil och skapar en PDF.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>Välj språk för det här dokumentet.<p>Mer information om språkalternativ finns i <a href="#convert-document-to-pdf-file" class="MCXref xref" >Konvertera dokument till PDF-fil</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL OCR type]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Modified original image] text ser till att texten är sökbar och markeringsbar, men ändrar den ursprungliga bilden under rensningsprocessen (till exempel skevar den) innan ett osynligt textlager placeras över den. Den här typen tar bort oönskade artefakter och kan i vissa fall leda till ett mer läsbart dokument. </p> </li> 
     <li> <p>[!UICONTROL Unchanged original image] text lägger också över ett sökbart textlager över originalbilden, men i det här fallet ändras inte originalbilden. Den här typen ger maximal återgivning av originalbilden.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Page manipulation]

I den här modulen kan du välja mellan att rotera eller ta bort sidor i ett PDF-dokument. Du kan till exempel ändra stående till liggande eller ta bort vissa sidor från PDF-dokumentet.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> <p>Välj den åtgärd som du vill utföra på filen.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Delete]</b> </p> <p>Välj det här alternativet om du vill ta bort sidor från dokumentet.</p><p>För varje sidintervall som du vill ta bort klickar du på <strong>[!UICONTROL Add]</strong> och anger sedan sidintervallets första och sista sida. </p> <p>Obs!   
     <ul> 
      <li> <p>Du kan använda negativa tal för att räkna tillbaka från slutet av dokumentet. Den sista sidan i ett dokument är -1, den andra till den sista sidan är -2 och så vidare.</p> </li> 
      <li> <p>Om du vill ta bort en enstaka sida anger du samma sidnummer som både början och slutet av intervallet.</p></ul> </li> 
     <li> <p><b>[!UICONTROL Rotate]</b> </p> <p>Välj det här alternativet om du vill rotera sidor och sedan ange vinkeln, i grader medsols, som du vill rotera dokumentsidorna i förhållande till deras startorientering.</p> <p>Rotera sidan 90 eller 270 grader om du vill rotera från stående till liggande eller tvärtom.</p> <p>Om en sida är upp och ned roterar du den 180 grader.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pages]</td> 
   <td> <p>För varje sidintervall som du vill ta bort klickar du på <strong>[!UICONTROL Add]</strong> och anger sedan sidintervallets första och sista sida. </p> <p>Obs!   
     <ul> 
      <li> <p>Du kan använda negativa tal för att räkna tillbaka från slutet av dokumentet. Den sista sidan i ett dokument är -1, den andra till den sista sidan är -2 och så vidare.</p> </li> 
      <li> <p>Om du vill ta bort en enstaka sida anger du samma sidnummer som både början och slutet av intervallet.</p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska arbeta med under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF accessibility auto-tag]

Den här åtgärdsmodulen skapar en PDF som är taggad för hjälpmedelsanvändning. Den skapar också en valfri Microsoft Excel-rapport med felmeddelanden och förslag på korrigeringar.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shift Headings]</td> 
   <td> <p>Aktivera det här alternativet om du vill flytta rubriker i dokumentet.</p> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generate Report]</td> 
   <td> <p>Aktivera det här alternativet om du vill generera en rapport som listar tillgänglighetsproblem i PDF tillsammans med deras plats, och ger förslag på hur du kan åtgärda dessa problem.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF file properties]

Det här verktyget extraherar grundläggande information om dokumentet, till exempel:

* Antal sidor
* PDF
* Om filen är krypterad
* Om filen är linjär
* Om filen innehåller inbäddade filer

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Protect a PDF file]

Det här verktyget skyddar ett PDF-dokument med ett användar- eller ägarlösenord. Den anger även begränsningar för vissa funktioner som utskrift, redigering och kopiering i PDF-dokumentet. Du väljer vilken typ av innehåll som ska krypteras och krypteringsalgoritmen.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password Protection Type]</td> 
   <td> <p>Aktivera det här alternativet om du vill använda lösenord för att kryptera PDF-indatadokumentet. Om du aktiverar det här alternativet måste du ange och ange ett värde för ett eller båda av följande: </p> 
    <ul> 
     <li> <p>[!UICONTROL User Password]</p> </li> 
     <li> <p>[!UICONTROL Owner Password] </p> </li> 
    </ul> <p>Lösenordet kan innehålla upp till 128 tecken.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encryption Algorithm]</td> 
   <td> <p>Välj krypteringsalgoritm. </p> 
    <ul> 
     <li> <p>[!UICONTROL AES-128 encryption]</p> <p>Lösenordet stöder endast LATIN-I-tecken. </p> </li> 
     <li> <p>[!UICONTROL AES-256 encryption]</p> <p>Lösenordet stöder Unicode-teckenuppsättningen</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content to Encrypt]</td> 
   <td> <p>Välj vilken typ av innehåll som ska krypteras.</p> 
    <ul> 
     <li> <p>[!UICONTROL All content]</p> </li> 
     <li> <p>[!UICONTROL All content except metadata]</p> </li> 
     <li> <p>[!UICONTROL Only embedded data] </p> </li> 
    </ul> <p>Om du väljer [!UICONTROL Only embedded data] kommer alla angivna åtkomstbehörigheter att bli ineffektiva.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permissions]</td> 
   <td> <p>Välj de behörigheter du vill inkludera för utskrift, redigering eller kopiering av innehåll.</p> <p>Behörighetsinställningar används bara om [!UICONTROL Owner Password] har angetts i fältet [!UICONTROL Password Protection Type].</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Remove protection of a PDF file]

Det här verktyget tar bort skydd (lösenord) från ett PDF-dokument.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password]</td> 
   <td>Ange lösenordet som skyddar filen.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Split a PDF file]

Den här åtgärdsmodulen delar upp ett PDF-dokument i flera mindre dokument. Du anger om du vill dela upp den efter antal filer, sidor per fil eller sidintervall.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som ska användas för den här modulen.</p> Instruktioner om hur du skapar en anslutning till [!DNL Adobe PDF Services] finns i <a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe PDF Services]</a> i den här artikeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p>Källfilen måste vara i PDF-format.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split option]</td> 
   <td>Välj hur du vill dela filen. 
   <ul>
   <li><p><b>Sidintervall</b></p><p>För varje sidintervall som du vill dela upp i ett separat dokument klickar du på <b>Lägg till</b> och anger den sida som du vill börja på och den sida som du vill avsluta.</p></li>
   <li><p><b>Antal sidor</b></p><p>Ange antalet sidor som du vill inkludera i de nya dokumenten.</p></li>
   <li><p><b>Filkonto</b></p><p>Ange antalet filer i samma storlek som du vill dela dokumentet i.</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

