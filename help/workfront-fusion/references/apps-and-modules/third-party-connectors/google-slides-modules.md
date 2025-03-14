---
title: Google Presentationsmoduler
description: Med Adobe Workfront Fusion Google Presentations-modulerna kan du skapa, uppdatera, lista och/eller ta bort presentationer och ladda upp bilder till presentationer i ditt Google Presentationer.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 6f5f97b9-b06a-4336-b349-ee9e2606d4bf
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 0%

---

# [!DNL Google Slides] moduler

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Google Slides] kan du skapa, uppdatera, lista och/eller ta bort presentationer och överföra bilder till presentationer i ditt [!DNL Google Slides]-konto.

Om du vill använda [!DNL Google Slides] med [!DNL Workfront Fusion] måste du ha ett [!DNL Google]-konto. Om du inte har något [!DNL Google]-konto än kan du skapa ett på hjälpsidan för [!DNL Google]-kontot.

Du behöver också [!DNL Google Slides] i din [!DNL Google Drive].

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

Du måste ha ett [!DNL Google]-konto för att kunna använda [!DNL Google Slides]-moduler.

## API-information för Google-bilder

Google Slides-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://slides.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.5.9</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Slides]-moduler och deras fält

När du konfigurerar [!DNL Google Slides]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Google Slides] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Presentation](#presentation)
* [Övriga](#other)

### Presentation

* [[!UICONTROL Add/Delete a Slide]](#adddelete-a-slide)
* [[!UICONTROL Create a Presentation From a Template]](#create-a-presentation-from-a-template)
* [[!UICONTROL Get a Page/Thumbnail]](#get-a-pagethumbnail)
* [[!UICONTROL Get a Presentation]](#get-a-presentation)
* [[!UICONTROL List Presentations]](#list-presentations)
* [[!UICONTROL Refresh a Chart]](#refresh-a-chart)
* [[!UICONTROL Upload an Image To a Presentation]](#upload-an-image-to-a-presentation)
* [[!UICONTROL Watch Presentations]](#watch-presentations)

#### [!UICONTROL Add/Delete a Slide]

Den här åtgärdsmodulen skapar en bildruta eller tar bort en befintlig bildruta i den angivna presentationen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the method]</td> 
   <td> <p>Välj om du vill lägga till en ny bildruta eller ta bort en bildruta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Enter a Slide ID]</td> 
   <td> <p>Om du tar bort en bildruta väljer du om du vill ange bildrute-ID:t manuellt eller markera bildrutan i en lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Presentation ID]</td> 
   <td> <p>Markera presentationen eller mappa presentations-ID:t för presentationen som du vill lägga till eller ta bort en bildruta för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Slide Object ID]</td> 
   <td> <p>Om du tar bort en bildruta och väljer att ange bildrutan manuellt anger eller mappar du bildrute-ID:t. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Predefined layout type]</td> 
   <td> <p> Välj den fördefinierade bildlayout som du vill använda den nya bilden på. Ange värden för ytterligare fält (till exempel [!UICONTROL Title]).</p> 
    <ul> 
     <li>[!UICONTROL Blank layout, with no placeholders]</li> 
     <li>[!UICONTROL Layout with a caption at the bottom]</li> 
     <li>[!UICONTROL Layout with a title and subtitle]</li> 
     <li>[!UICONTROL Layout with a title and body]</li> 
     <li>[!UICONTROL Layout with a title and two columns]</li> 
     <li>[!UICONTROL Layout with only a title]</li> 
     <li>[!UICONTROL Layout with a section title]</li> 
     <li>[!UICONTROL Layout with a title and subtitle on one side and description on the other]</li> 
     <li>[!UICONTROL Layout with one title and one body, arranged in a single column]</li> 
     <li>[!UICONTROL Layout with a main point]</li> 
     <li>[!DNL Layout with a big number heading]</li> 
    </ul> <p>Det här fältet är tillgängligt om du har valt att lägga till en bildruta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Content]</td> 
   <td> <p>Ange eller mappa textinnehållet för bildrutan. Fälten är tillgängliga baserat på den mall du har valt.</p> <p>Det här fältet är tillgängligt om du har valt att lägga till en bildruta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Presentation From a Template]

Den här åtgärdsmodulen skapar en ny presentation genom att kopiera en presentation och ersätta alla taggar som `{{Name}}`, `{{Email}}` i med angivna data.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>Ange ett namn för den nya presentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy a Presentation]</td> 
   <td> <p> Välj alternativet om du kopierar en befintlig presentation:</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy of Existing Presentation ID]</td> 
   <td> <p> Ange sökvägen eller presentations-ID för en befintlig presentation som du vill kopiera. Det här fältet visas om du skapar presentationen [!UICONTROL By Mapping].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Välj [!DNL Google Drive] där de presentationer du vill visa finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> <p>Det här fältet visas om du skapar presentationen [!UICONTROL By Dropdown].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Markera presentationen eller ange eller mappa presentations-ID:t för presentationen som du vill använda som mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>Lägg till värdena:</p> 
    <ul> 
     <li><strong>[!UICONTROL Tag]</strong>: Ange den tagg som du vill ersätta i presentationen. Exempel: <code>&#123;&#123;Name&#125;&#125;</code></li> 
     <li><strong>[!UICONTROL Replaced Value]</strong>: Ange det värde som den befintliga taggen ska ersättas med. Om till exempel strängen <code>&#123;&#123;Name&#125;&#125;</code> i presentationen och det ersatta värdet är Sample, ersätts <code>&#123;&#123;Name&#125;&#125;</code> med <code>Sample</code>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Drive Location]</td> 
   <td> <p>Välj den [!DNL Google Drive] där du vill lagra eller lägga till den nya presentationen:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Document's Location]</p> </td> 
   <td> <p>Välj den mapp där du vill lagra eller lägga till presentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared] </td> 
   <td> <p>Välj om du vill dela presentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sharing with Other's Email Address]</td> 
   <td> <p> Ange den e-postadress som du vill dela presentationen med. Om du aktiverar alternativet Delat utan att ange ett e-postmeddelande i det här fältet kan presentationen delas med alla.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Page/Thumbnail]

Den här åtgärdsmodulen hämtar den senaste versionen av den angivna sidan eller av miniatyrbilden för en sida i presentationen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation and Page ID]</td> 
   <td> <p> Välj om du vill ange en presentation och ett sid-ID manuellt eller markera dem i en lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Välj det presentations-ID som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page Object ID]</td> 
   <td> <p> Markera den bildruta som du vill visa information om sidobjekt för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Page Thumbnail]</td> 
   <td> <p> Markera kryssrutan om du vill visa sidminiatyrinformation.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Presentation]

Den här åtgärdsmodulen hämtar den senaste versionen av en angiven presentation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Välj [!DNL Google Drive] där de presentationer du vill visa finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Välj den presentation som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Presentations]

Den här modulen hämtar en lista över alla presentationer på den angivna platsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive location]</td> 
   <td> <p>Välj [!DNL Google Drive] där de presentationer du vill visa finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p>Välj mappsökväg för de presentationer som du vill visa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal presentationer som du vill att modulen ska returnera under en körningscykel för ett scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Refresh a Chart]

Åtgärdsmodulen uppdaterar diagramdata som lagras i en presentation som anges av ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation ID]</td> 
   <td> <p> Välj om du vill ange ett presentations-ID manuellt eller välja det i en lista.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Om du väljer presentationen från en lista väljer du [!DNL Google Drive] där presentationerna som du vill visa finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>Markera presentationen eller ange eller mappa presentations-ID:t för presentationen som innehåller det diagram som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Chart Object ID]</td> 
   <td> <p> Om du anger data manuellt anger eller mappar du ID:t för det diagram du vill uppdatera.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload an Image To a Presentation]

Överför en bild med angivna data.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>Välj hur du vill välja presentationen som du överför en bild till.</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!DNL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Om du väljer i en listruta väljer du [!DNL Google Drive] där presentationen du vill lägga till en bild finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> Välj presentations-ID för presentationen som du överför en bild till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the Method]</td> 
   <td> <p> Välj hur du vill ersätta bilden.</p>
   <ul>
   <li><p><b>Överföra en bild genom att ersätta texttaggen</b></p><p>I fältet Värden klickar du på <b>Lägg till objekt</b> för varje bild som du vill överföra och anger bildens tagg och URL-adress för den nya bilden.</p></li>
   <li><p><b>Överföra en bild genom att ersätta bilden</b></p><p>I fältet Värden klickar du på <b>Lägg till objekt</b> och anger bildens objekt-ID, ersättningsmetod och URL för den nya bilden för varje bild som du vill överföra.</p></li>
   </ul>
  <p>Obs! Bilderna måste vara mindre än 50 MB, får inte vara större än 25 megapixlar och måste vara i PNG-, JPEG- eller GIF-format.</p>   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Presentations]

Den här utlösarmodulen startar ett scenario när en ny presentation skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch] </td> 
   <td> <p>Välj alternativet att titta på presentationerna:</p> 
    <ul> 
     <li> <p>[!UICONTROL Created Date]</p> </li> 
     <li> <p>[!UICONTROL Modified Date]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet presentationer som Workfront Fusion ska returnera under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [[!UICONTROL Insert Links in a Presentation]](#insert-links-in-a-presentation)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Insert Links in a Presentation]

Med den här modulen kan alla länkar i en presentation klickas eller infogas en länk i alla matchade indatatexter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>Välj hur du vill välja presentationen som du överför en bild till.</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>Välj [!DNL Google Drive] där de presentationer du vill visa finns:</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] Delad enhet]</li> 
    </ul> <p>Det här fältet visas om du skapar presentationen [!UICONTROL By Dropdown].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>Välj mappsökväg för de presentationer som du vill visa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select]</td> 
   <td> <p>Välj om du vill göra alla länkar i en presentation klickbara eller om du vill infoga en länk i alla matchande indatatexter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text Inputs]</td> 
   <td>Om du infogar en länk, för varje textobjekt som du vill lägga till en länk för, klickar du på <b>Lägg till objekt</b> och anger texten och den associerade länken. Varje gång objektet visas i presentationen länkas det automatiskt till den angivna platsen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Utför ett godtyckligt auktoriserat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Slides]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Ange en relativ sökväg till <code>https://developers.google.com/slides/</code>. Exempel: Presentation.</p> <p>En lista över tillgängliga slutpunkter finns i <a href="https://developers.google.com/slides/reference/rest">[!DNL Google Slides] API-dokumentationen </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Ange önskade begäranderubriker. Du behöver inte lägga till auktoriseringshuvuden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Ange frågesträngen för begäran.</p> </td> 
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

>[!BEGINSHADEBOX]

**Exempel:** Om du använder ett API-anrop kan du få presentationsinformation för det presentations-ID du har angett. Du kan hitta presentations-ID:t i URL:en när du öppnar presentationen i [!DNL Google Slides].

![Exempel på API-anrop](/help/workfront-fusion/references/apps-and-modules/assets/api-call-350x13.png)

Följande API-anrop returnerar presentationsinformationen:

![Presentationsinformation](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details.png)

Det går att hitta matchningar av sökningen i modulens utdata under [!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL presentationId].

I det här exemplet returnerades de begärda presentationsdetaljerna:

![Presentationsinformation](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details-2.png)

>[!ENDSHADEBOX]
