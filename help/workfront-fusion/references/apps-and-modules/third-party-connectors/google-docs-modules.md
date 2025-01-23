---
title: Google Docs-moduler
description: Med Adobe Workfront Fusion [!DNL Google Docs] -modulerna kan du övervaka, skapa, redigera och hämta dokument i dina [!DNL Google Docs] och [!DNL Google Docs] (för [!DNL Google Workspace] användare).
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: cd44250d-c2cd-46b2-8773-15b30472a8d8
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3215'
ht-degree: 0%

---

# [!DNL Google Docs] moduler

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Google Docs] kan du övervaka, skapa, redigera och hämta dokument i dina [!DNL Google Docs]- och [!DNL Google Docs]-dokument (för [!DNL Google Workspace] användare).

Om du vill använda [!DNL Google Docs] med [!DNL Adobe Workfront Fusion] måste du ha ett [!DNL Google]-konto. Om du inte har något [!DNL Google]-konto än kan du skapa ett på hjälpsidan för [!DNL Google]-kontot.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Du måste ha ett Google-konto för att kunna använda [!DNL Google Docs]-moduler.

## Google Docs API-information

Google Docs Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://docs.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.4.13</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Docs]-moduler och deras fält

När du konfigurerar [!DNL Google Docs] moduler visar [!UICONTROL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Docs] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Dokument

* [[!UICONTROL Watch Documents]](#watch-documents)
* [[!UICONTROL List Documents]](#list-documents)
* [[!UICONTROL Get Content of a Document]](#get-content-of-a-document)
* [[!UICONTROL Create a Document]](#create-a-document)
* [[!UICONTROL Create a Document From a Template]](#create-a-document-from-a-template)
* [[!UICONTROL Insert a Paragraph to a Document]](#insert-a-paragraph-to-a-document)
* [[!UICONTROL Insert an Image to a Document]](#insert-an-image-to-a-document)
* [[!UICONTROL Replace an Image with a New Image]](#replace-an-image-with-a-new-image)
* [[!UICONTROL Replace Text in a Document]](#replace-text-in-a-document)
* [[!UICONTROL Download a Document]](#download-a-document)
* [[!UICONTROL Delete a Document]](#delete-a-document)

#### [!UICONTROL Watch Documents]

Den här utlösarmodulen returnerar dokumentinformation när ett nytt dokument skapas eller ändras i den valda mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Documents]</td> 
   <td> <p style="color: #000000;">Välj om du vill titta på skapade ([!UICONTROL By Created Date]) eller ändrade ([!UICONTROL By Modified Date]) dokument.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet som du vill övervaka.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera den mapp som du vill bevaka för skapade eller ändrade dokument.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera den mapp som du vill bevaka för skapade eller ändrade dokument.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet som du vill titta på.</p> <p>Obs! Om du har valt alternativet [!DNL Google Shared Drive] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det högsta antalet dokument som Workfront Fusion returnerar i en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Documents]

Den här åtgärdsmodulen hämtar en lista med dokument från den valda mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet som du vill visa dokument från.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera den mapp som du vill visa dokument från.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera den mapp som du vill visa dokument från.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet som du vill visa dokument från.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det maximala antalet dokument som [!DNL Workfront Fusion] returnerar i en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Content of a Document]

Den här åtgärdsmodulen hämtar ett angivet dokument.

Du kan behöva utöka din behörighet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get Content of a Document]</td> 
   <td> <p>Välj om du vill mappa dokument-ID:t för dokumentet eller välja dokumentet i listrutan manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet som innehåller dokumentet som du vill hämta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen som innehåller dokumentet som du vill hämta.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen som innehåller dokumentet som du vill hämta.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet som innehåller dokumentet som du vill hämta.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>Markera det objekt som du vill returnera i modulens utdata.</p> 
    <ul> 
     <li>[!UICONTROL Image] (standard)</li> 
     <li>[!UICONTROL Drawing]</li> 
     <li>[!UICONTROL Chart]</li> 
    </ul> <p>Obs!  <p>Använd värdet [!UICONTROL Inline Objects Array] i den här modulens utdata (i stället för [!UICONTROL inlineObjects]) om du vill mappa dessa objekt ytterligare.</p> <p>[!UICONTROL Inline Objects Array]-objekten sorteras i samma ordning som de visas i dokumentet. Det kommer att underlätta ytterligare bearbetning.</p> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document]

Med den här åtgärdsmodulen kan du skapa ett nytt dokument i den valda mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Ange dokumentets namn.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td> <p>Ange dokumentets innehåll. HTML stöds.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där du vill skapa ett dokument.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Välj den mapp där du vill skapa ett dokument.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Välj den mapp där du vill skapa ett dokument.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där du vill skapa ett dokument.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Header]</td> 
   <td> <p> Aktivera det här alternativet om du vill infoga sidhuvudet i dokumentet och sedan ange eller mappa texten i sidhuvudet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Footer] </td> 
   <td> <p>Aktivera det här alternativet om du vill infoga sidfoten i dokumentet och sedan ange eller mappa texten i sidhuvudet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document From a Template]

Den här åtgärdsmodulen skapar en kopia av ett befintligt malldokument och ersätter eventuella taggar. I den här modulen kan användare även ersätta bilder med nya bilder via URL.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Create a Document from a Template]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentmallen.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br>Välj det här alternativet om du vill välja dokumentmallen i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där mallen finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen där mallen finns.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen där mallen finns.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där mallen finns.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>Ange de värden som ska anges i stället för variablerna i det nya dokumentet.</p> 
    <ul> 
     <li><strong>[!UICONTROL Tags]</strong> <br>Ange taggarna som finns i dokumentmallen. Använd inte <code>&#123;&#123;&#125;&#125;</code>. Exempel: använd <code>name</code> i stället för <code>&#123;&#123;name&#125;&#125;</code>.</li> 
     <li><strong>[!UICONTROL Replaced Value]</strong><br>Ange värdet för taggen.</li> 
    </ul> <p>Variabeln <code> &#123;&#123;name&#125;&#125;</code> i källdokumentet visas som namnfält här, där värdet kan infogas, till exempel <code>John</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Images Replacement]</p> </td> 
   <td> <p>Ange länken till [!UICONTROL Image Object ID] och [!UICONTROL Image URL] som ska ersätta den aktuella bilden.</p> <p>Obs! Du kan hämta bild-ID:n med modulen [!UICONTROL Get a Document], där ID:n finns i arrayen [!UICONTROL Inline Object Array].</p> <p>Vi rekommenderar att du lägger till ALT-text i bilder i ditt [!DNL Google]-dokument. </p> <p>Så här lägger du till en ALT-text i bilden [!DNL Google Docs]:</p> 
    <ol> 
     <li value="1">Högerklicka på bilden.</li> 
     <li value="2">Välj alternativet [!UICONTROL ALT text].</li> 
     <li value="3">Ange [!UICONTROL ALT text] i fältet [!UICONTROL Title] och klicka på [!UICONTROL OK].</li> 
    </ol> <p>När ALT-texten har lagts till i bilden visas ALT-texten inom parentes i fältnamnet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>Ange det nya dokumentets namn.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där mallen finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Välj den mapp där du vill att dokumentet ska skapas.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Välj den mapp där du vill att dokumentet ska skapas.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där du vill att dokumentet ska skapas.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert a Paragraph to a Document]

Den här åtgärdsmodulen lägger till eller infogar ett nytt stycke i ett befintligt dokument.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentet.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Välj det här alternativet om du vill välja dokumentet i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill lägga till ett stycke finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera den mapp där dokumentet som du vill lägga till ett stycke finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera den mapp där dokumentet som du vill lägga till ett stycke finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Markera den delade enhet där dokumentet som du vill lägga till ett stycke finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert a Paragraph]</p> </td> 
   <td> <p>Välj hur du vill att den nya texten ska infogas i dokumentet.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>Ange det indexnummer där du vill infoga texten. Du kan använda modulen [!UICONTROL Get a Document] för att hämta indexnummer.</p> <p>Om du vill visa alla tecken (inklusive dolda) i dokumentet kan du använda tillägget [!UICONTROL Show]. Tillägget finns under [!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]. Sök efter [!UICONTROL Show] och installera tillägget [!UICONTROL Show].</p> </li> 
         <li> <p><strong>[!UICONTROL Inserted text]</strong> </p> <p>Ange den text som du vill infoga i dokumentet.</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>Markera det sidhuvud och den sidfot som du vill infoga textinnehållet i och ange den text som du vill infoga i motsvarande fält.</p> <p>Om sidhuvudet eller sidfoten redan innehåller text läggs den nya texten till före den befintliga texten.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>Lägger till den angivna texten i slutet av dokumentets brödtext.</p> <p>Det nya styckets format kopieras från stycket vid det aktuella infogningsindexet, inklusive listor och punkter.</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>Markera det sidhuvud och den sidfot som du vill infoga textinnehållet i och ange den text som du vill infoga i motsvarande fält.</p> <p>Om sidhuvudet eller sidfoten redan innehåller text läggs den nya texten till efter den befintliga texten.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Appended Text]</td> 
   <td>Ange eller mappa texten som du vill lägga till i dokumentet</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert an Image to a Document]

Den här åtgärdsmodulen infogar en bild från URL:en till dokumentet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentmallen.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Välj det här alternativet om du vill välja dokumentet i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill lägga till en bild finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen där dokumentet som du vill lägga till en bild finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen där dokumentet som du vill lägga till en bild finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där dokumentet som du vill lägga till en bild finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert an Image]</p> </td> 
   <td> <p>Välj hur du vill att den nya bilden ska infogas i dokumentet.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>Ange det indexnummer där du vill infoga bilden. Du kan använda modulen [!UICONTROL Get a Document] för att hämta [!UICONTROL Index number].</p> <p>Om du vill visa alla tecken (inklusive dolda) i dokumentet kan du använda tillägget [!UICONTROL Show]. Tillägget finns under [!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]. Sök efter [!UICONTROL Show] och installera tillägget [!UICONTROL Show].</p> </li> 
         <li> <p><strong>[!UICONTROL Image URL]</strong> </p> <p>Ange URL-adressen till bilden som du vill infoga i dokumentet.</p> <p>Den största bildstorleken är 50 MB. Får inte överskrida 25 megapixlar. Endast PNG-, JPEG- eller GIF-format stöds.</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>Markera det sidhuvud och den sidfot som du vill infoga bilden i och ange bildens URL till motsvarande fält.</p> <p>Den största bildstorleken är 50 MB. Bilden får inte överstiga 25 megapixlar. Endast PNG-, JPEG- eller GIF-format stöds.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>Lägger till en viss bild i slutet av dokumentets brödtextinnehåll.</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>Markera det sidhuvud och den sidfot som du vill infoga en bild i och ange den bild-URL som du vill infoga i motsvarande fält.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Height Magnitude in Points/Width Magnitude in Points]</p> </td> 
   <td> <p>Definiera storleken på den infogade bilden. Proportionerna behålls.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace an Image with a New Image]

Den här åtgärdsmodulen ersätter en befintlig bild. Den ursprungliga bildens proportioner bevaras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentmallen.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Välj det här alternativet om du vill välja dokumentet i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill ersätta en bild finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen där dokumentet som du vill ersätta en bild finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen där dokumentet som du vill ersätta en bild finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där dokumentet som du vill ersätta en bild finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Image URL]</p> </td> 
   <td> <p>Ange eller mappa URL-adressen för den nya bilden som ska ersätta den befintliga bilden.</p> <p>Bilderna visas i den ordning som de visas i dokumentet. <code>Body: Image No. 1</code> är till exempel den första bilden i dokumentet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace Text in a Document]

Den här åtgärdsmodulen ersätter text i ett dokument.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentmallen.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Välj det här alternativet om du vill välja dokumentet i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill lägga till text finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera den mapp där dokumentet som du vill lägga till text finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera den mapp där dokumentet som du vill lägga till text finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där dokumentet som du vill lägga till text finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace a Text]</p> </td> 
   <td> <p>Lägg till varje text som du vill ersätta.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Old text to be replaced]</strong> </p> <p>Ange den text som du vill ersätta.</p> </li> 
     <li> <p><strong>[!UICONTROL New text to be inserted]</strong> </p> <p>Ange den nya texten.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a Document]

Den här åtgärdsmodulen konverterar och hämtar det markerade dokumentet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill hämta finns.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen där dokumentet som du vill hämta finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen där dokumentet som du vill hämta finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Välj den delade enhet där dokumentet som du vill hämta finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Type] </p> </td> 
   <td> <p>Välj målfilsformat för det hämtade dokumentet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Document]

Den här åtgärdsmodulen tar bort ett dokument.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill ta bort finns.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera mappen där dokumentet som du vill ta bort finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera mappen där dokumentet som du vill ta bort finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Markera den delade enhet där dokumentet som du vill ta bort finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>Markera den enhet som innehåller dokumentet som du vill hämta och välj sedan ett dokument. Det här alternativet är tillgängligt om du har markerat [!DNL Google Docs] i fältet [!UICONTROL Choose a Drive].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> Markera eller mappa dokumentet som du vill ersätta en eller flera bilder i.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Make All Links in a Document Clickable]](#make-all-links-in-a-document-clickable)

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Ange en relativ sökväg till <code>https://docs.googleapis.com/</code>. Exempel: <code>/v1/documents/{presentationID}</code>. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code>. [!DNL Workfront Fusion] lägger till autentiseringsrubrikerna åt dig.</p> </td> 
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

**Exempel:** Följande API-anrop hämtar information om det angivna dokumentet i din Google Docs:

**URL:**

/v1/documents/1ujkf-GDgB0TQSYPrxbCSK4Uso54tHVMqHZEVZZxB6aY

**Metod:**

[!UICONTROL GET]

![](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

Information om det hämtade dokumentet finns i modulens utdata under [!UICONTROL Bundle] > [!UICONTROL Body].

![](/help/workfront-fusion/references/apps-and-modules/assets/api-output.png)

#### [!UICONTROL Make All Links in a Document Clickable]

Den här åtgärdsmodulen hittar alla länkar i dokumentet och gör dem klickbara.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Make All Links in a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>Välj det här alternativet om du vill mappa dokumentmallen.</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> Välj det här alternativet om du vill välja dokumentet i listrutan.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>Välj den typ av enhet där dokumentet som du vill göra länkar klickbara i finns. Det här alternativet är tillgängligt om du har markerat [!UICONTROL By Dropdown] i föregående fält.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>Markera den mapp där dokumentet som du vill göra länkarna klickbara i finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>Markera den mapp där dokumentet som du vill göra länkarna klickbara i finns och markera sedan dokumentet.</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google] delad enhet]</strong> (endast tillgänglig för [!DNL Google Workspace] användare)</p> <p>Välj om du vill [!UICONTROL Use Domain Admin Access]. Om du väljer [!UICONTROL Yes] utfärdas begäran som en domänadministratör och alla delade enheter där den som gjorde begäran är administratör returneras.</p> <p>Markera den delade enhet där dokumentet som du vill göra länkarna klickbara i finns och markera sedan dokumentet.</p> <p>Obs! Om du har valt alternativet [!DNL Google Docs] i det här fältet och inte är en [!DNL Google Workspace]-användare, returneras felet <code>[400] Invalid Value</code>.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>Markera den enhet som innehåller dokumentet som du vill uppdatera länkarna i och markera sedan ett dokument. Det här alternativet är tillgängligt om du har markerat [!DNL Google Docs] i [!UICONTROL Choose a Drive field].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> Markera eller mappa dokumentet som du vill uppdatera länkarna i.</p> </td> 
  </tr> 
 </tbody> 
</table>
