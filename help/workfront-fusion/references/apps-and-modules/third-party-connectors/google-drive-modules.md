---
title: Google Drive-moduler
description: Modulerna  [!DNL Adobe Workfront Fusion Google Drive] gör att du kan övervaka, söka, skapa, uppdatera, ta bort och hantera filer, mappar och delade enheter i din [!DNL Google Drive].
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 0%

---

# [!DNL Google Drive] moduler

Med Adobe Workfront Fusion [!DNL Google Drive]-modulerna kan du övervaka, söka, skapa, uppdatera, ta bort och hantera filer, mappar och delade enheter i [!DNL Google Drive].

I ett Adobe Workfront Fusion-scenario kan du ansluta ditt [!DNL Google Drive]-konto till flera tredjepartsprogram och -tjänster.

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

## API-information för Google Drive

Google Drive-anslutningen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://www.googleapis.com/drive/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v4.1.22</td> 
  </tr>
 </tbody> 
 </table>



## Ansluter [!DNL Google Drive] till Workfront Fusion

Om du använder [!DNL @gmail.com] eller [!DNL @googlemail.com] måste du skapa en OAuth-klient på [!DNL Google Cloud Platform] för att få tillgång till din [!UICONTROL Client ID] och [!UICONTROL Client Secret].

Stegvisa instruktioner om hur du skapar OAuth-klienten (och hämtar [!UICONTROL Client ID] och [!UICONTROL Client Secret]) finns i [Ansluta Adobe Workfront Fusion till [!DNL Google Services] med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## [!DNL Google Drive]-moduler och deras fält

När du konfigurerar [!DNL Google Drive]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Google Drive] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

* [[!UICONTROL Watch all files]](#watch-all-files)
* [[!UICONTROL Watch comments]](#watch-comments)
* [[!UICONTROL Watch files in folder]](#watch-files-in-folder)
* [[!UICONTROL Watch shared files]](#watch-shared-files)

#### [!UICONTROL Watch all files]

Den här utlösarmodulen startar ett scenario när en fil i [!DNL Google Drive] läggs till eller ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>Välj vilken typ av filer du vill bevaka.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Documents] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Spreadsheets] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Slides] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Drawings] till.</td>
  </tr>  
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Välj om du vill titta på nya filer och alla ändringar, eller bara nya filer.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Ange det högsta antal resultat som Workfront Fusion ska hämta under en cykel (antalet upprepningar per scenario-körning).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Comments]

Den här utlösarmodulen startar ett scenario när en kommentar läggs till eller ändras i den valda filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File]</td> 
   <td>Markera filen som du vill bevaka för kommentarer.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Välj om du endast vill bevaka alla ändringar eller om det finns nya kommentarer</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned comments]</td> 
   <td>Ange det maximala antalet kommentarer som Workfront Fusion ska returnera under en cykel (antalet upprepningar per scenario-körning).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch files in folder]

Den här utlösarmodulen startar ett scenario när en fil läggs till eller ändras i den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Select the folder to be watched]</td>
    <td >Markera den mapp på enheten där du vill titta på filerna.</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL What files to watch]</td>
   <td> <p>Välj vilken typ av filer du vill bevaka.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Documents] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Spreadsheets] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Slides] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Drawings] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Watch]</td>
    <td>Välj om du vill titta på nya filer och alla ändringar, eller bara nya filer.</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL Maximum number of downloaded files]</td>
    <td>Ange det högsta antal resultat som Workfront Fusion ska hämta under en cykel (antalet upprepningar per scenario-körning).</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch shared files]

Startar när en ny fil delas med dig eller när en befintlig delad fil uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select the folder to be watched]</td> 
   <td>Markera den delade mapp som du vill bevaka filerna i.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL What files to watch]</td> 
   <td> <p>Välj vilken typ av filer du vill bevaka.</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL Convert [!DNL Google Documents] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Documents] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Spreadsheets] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Spreadsheets] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Slides] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Slides] till.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Convert [!DNL Google Drawings] filer att formatera]</td>
    <td>Välj det filformat som du vill konvertera [!DNL Google Drawings] till.</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td>Välj om du vill titta på nya filer och alla ändringar, eller bara nya filer.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of downloaded files]</td> 
   <td>Ange det högsta antal resultat som Workfront Fusion ska hämta under en cykel (antalet upprepningar per scenario-körning).</td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Copy a file]](#copy-a-file)
* [[!UICONTROL Create a fFolder]](#create-a-folder)
* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Get a share link]](#get-a-share-link)
* [[!UICONTROL Move a file to trash]](#move-a-filefolder-to-trash)
* [[!UICONTROL Search for Files/Folders]](#search-for-filesfolders)
* [[!UICONTROL Update a File]](#update-a-file)
* [[!UICONTROL Upload a File]](#upload-a-file)

#### [!UICONTROL Copy a file]

Den här åtgärdsmodulen kopierar en fil till den nya platsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som du vill kopiera en fil till.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>Markera mappen som innehåller filen som du vill kopiera.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill kopiera.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the copy]</td> 
   <td>Ange en rubrik för den nya filen. Lämna fältet tomt om du inte vill ändra det ursprungliga filnamnet.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a folder]

Den här åtgärdsmodulen skapar en mapp på den angivna platsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål där du vill skapa en mapp.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New folder location]</td> 
   <td>Navigera till den plats där du vill skapa en ny mapp.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the new folder]</td> 
   <td>Ange ett namn för mappen som du skapar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Share folder]</td> 
   <td>Välj det här alternativet om du vill dela mappen med någon som har länken [!UICONTROL Share]. I annat fall är delningslänken bara till för ägaren.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a file]

Den här åtgärdsmodulen tar permanent bort en fil eller mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

Den här åtgärdsmodulen hämtar filen med det angivna ID:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Documents] filer att formatera]</td> 
   <td>Välj det filformat som du vill konvertera [!DNL Google Documents] till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Spreadsheets] filer att formatera]</td> 
   <td>Välj det filformat som du vill konvertera [!DNL Google Spreadsheets] till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Slides] filer att formatera]</td> 
   <td>Välj det filformat som du vill konvertera [!DNL Google Slides] till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert [!DNL Google Drawings] filer att formatera]</td> 
   <td>Välj det filformat som du vill konvertera [!DNL Google Drawings] till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a share link]

Den här åtgärdsmodulen hämtar delningslänken för en fil i Google Drive.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill hämta delningslänken för.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a file to trash]

Den här åtgärdsmodulen flyttar en fil eller mapp till papperskorgen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill flytta till papperskorgen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search for Files/Folders]

Den här sökmodulen söker efter filer eller mappar baserat på sökvillkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj den målenhet som du vill söka efter.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL List a folder]</td> 
   <td>Navigera till mappen som du vill söka efter filer eller mappar.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td> <p> Välj om du vill söka efter filer, mappar eller både och.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Search]</p> </td> 
   <td> <p>Välj den typ av sökning du vill utföra.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Search within file/folder names]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Ange en del av filnamnet eller det fullständiga filnamnet (inklusive suffixet) som du vill söka efter.</p> </li> 
       <li> <p><strong>[!UICONTROL Search Options]</strong> </p> <p>Välj om du vill söka efter den exakta termen eller om du vill söka efter namn som innehåller söktermen.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Fulltext] sökning</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Ange de sökord du vill söka efter i din [!DNL Google Drive].</p> </li> 
      </ul> </li> 
     <li> <p><strong>Ange anpassad sökfråga</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Ange den anpassade sökfrågan. Mer information finns i avsnittet [!UICONTROL Search for Files] i artikeln.</p> </li> 
       <li> <p><strong>Lägg till den markerade mappen ovan i frågan</strong> </p> <p>Söker efter mappen i den överordnade samlingen. Detta söker efter alla filer och mappar som finns direkt i den ovan markerade mappen.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td>Ange det högsta antalet filer eller mappar som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td>Aktivera det här alternativet för att säkerställa att scenariot inte stoppas om modulen inte returnerar några resultat.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a File]

Den här åtgärdsmodulen uppdaterar metadata eller innehåll i en fil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som innehåller filen som du vill uppdatera.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Move to a folder]</td> 
   <td>Om du vill flytta filen till en viss mapp markerar du mappen som du vill flytta filen till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>Ange en rubrik för den uppdaterade filen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Change a file content]</td> 
   <td>Välj om du vill ersätta innehållet i filen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Om du ersätter innehållet väljer du en källfil från en tidigare modul eller mappar källfilens namn och data.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Conver a file]</td> 
   <td>Aktivera det här alternativet om du vill konvertera filen till motsvarande Google-filformat.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

Överför en fil till din [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till Workfront Fusion finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Destination]</td> 
   <td> <p>Välj det mål som du vill överföra en fil till.</p> 
    <ul> 
     <li>[!DNL My Drive]</li> 
     <li>[!DNL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>Markera mappen som du vill överföra en fil till. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Title]</td> 
   <td>Ange en rubrik för den nya filen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Convert a file]</td> 
   <td>Om du aktiverar det här alternativet kan modulen konvertera filer till motsvarande [!DNL Google]-format.</td> 
  </tr> 
 </tbody> 
</table>

## Felsökning

### Det går inte att överföra eller uppdatera en fil

Det finns flera orsaker till att det inte går att överföra eller uppdatera en fil:

* Den överförda filen är för stor och överskrider maxgränsen för filstorlek som tillåts för din [!DNL Google Drive]-plan, eller så har du överskridit lagringsgränsen för [!DNL Google Drive]. Du kan antingen uppgradera din lagringsplan eller ta bort befintliga filer från tjänsten [!DNL Google Drive].
* Den valda mappen som filen skulle överföras till finns inte längre. I det här fallet upphör scenariot och du måste välja en annan målmapp i modulen.

<!-- Not present February 2025

## Search for files

In the module List files in a folder you can use your own query which consists of these parts:

* **[!UICONTROL Field]** - Attribute of the file that is being searched, for example, the attribute `name` of the file.

* **[!UICONTROL Operator]** - Test that is performed on the data to provide a match, for example, `contains`.

* **[!UICONTROL Value]** - The content of the attribute that is tested, for example, the name of the file `My cool document`.

Combine clauses with the conjunctions `and` or `or`, and negate the query with `not`.

* [Fields](#fields)
* [Value types](#value-types)
* [Operators](#operators)
* [Examples](#examples)

### Fields 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Field </th> 
   <th>Value Type </th> 
   <th>Operators</th> 
   <th> <p> Description</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>string</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Name of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>string </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Full text of the file including name, description, content, and indexable text.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> string</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> MIME type of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date of the last modification to the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date that the user last viewed a file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Whether the file is in the trash or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Whether the file is starred or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Whether the [!UICONTROL parents] collection contains the specified ID.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who own the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to modify the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to read the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Files that are in the user's "Shared with me" collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>collection</td> 
   <td><code>has </code> </td> 
   <td> <p> Public custom file properties.</p> </td> 
  </tr> 
 </tbody> 
</table>

Consider the following about operators in these fields:

* The `contains` operator only performs prefix matching for a `title`.

   For example, the title "HelloWorld" matches for `title contains 'Hello'` but not for `title contains 'World'`.

* The `contains` operator only performs matching on entire string tokens for `fullText`.

   For example, if the full text of a doc contains the string "HelloWorld" only the query `fullText contains 'HelloWorld'` returns a result. Queries such as `fullText contains 'Hello'` would not return results in this scenario.

* The `contains` operator matches on an exact alphanumeric phrase if it is surrounded by double quotes.

   For example, if the `fullText` of a doc contains the string "Hello there world", then the query `fullText contains '"Hello there"'` returns a result, but the query `fullText contains '"Hello world"'` does not.

   Furthermore, because the search is alphanumeric, if the `fullText` of a doc contains the string "Hello_world", then the query `fullText contains '"Hello world"'` returns a result.

* Fields of `type` date are currently not comparable to each other, only to constant dates.

### Value types

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Value Type</th> 
   <th> <p> Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>String </td> 
   <td> <p>Surround with single quotes '. Escape single quotes in queries with <code>\'</code>, e.g.,<code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Boolean </td> 
   <td> <p><code>true </code>or <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Date </td> 
   <td> <p>RFC 3339 format, default timezone is UTC, e.g., <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operators

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operator </th> 
   <th> <p>Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>The content of one string is present in the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> The content of a string or boolean is equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> The content of a string or boolean is not equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> A date is earlier than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> A date is earlier than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> A date is later than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> A date is later than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>An element is contained within a collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Return files that match both clauses.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Return files that match either clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Negates a search clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>A collection contains an element matching the parameters.</p> </td> 
  </tr> 
 </tbody> 
</table>

For compound clauses, you can use parentheses to group clauses together. For example:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` This search returns all files with an image or video MIME type that their last modification was after June 4, 2012. Because `and` and `or` operators are evaluated from left to right, without parentheses, the above example would return only images modified after June 4, 2012, but would return all videos, even those before June 4, 2012.

### Examples 

All examples on this page show the unencoded `<q>q</q>` parameter, where `title = 'hello'` is encoded as `title+%3d+%27hello%27`. Client libraries handle this encoding automatically.

* Search for files with the name "hello"
   <pre>title = 'hello'</pre>
* Search for folders using the folder-specific MIME type
   <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Search for files that are not folders
   <pre>mimeType != 'application/vnd.google-apps.folder'</pre>
* Search for files with a name containing the words "hello" and "goodbye"
   <pre>title contains 'hello' and [!UICONTROL name] contains 'goodbye'</pre>
* Search for files with a name that does not contain the word "hello"
   <pre>not title contains 'hello'</pre>
* Search for files containing the word "hello" in the content
   <pre>fullText contains 'hello'</pre>
* Search for files not containing the word "hello" in the content
   <pre>not fullText contains 'hello'</pre>
* Search for files containing the exact phrase "hello world" in the content
   <pre>fullText contains '"hello world"'fullText contains '"hello_world"'</pre>
* Search for files with a query containing the "\" character (e.g., "\authors")
   <pre>fullText contains '\\authors'</pre>
* Search for files writeable by the user `test@example.org`
   <pre>'test@example.org' in [!DNL writers]</pre>
* Search for the ID `1234567` in the `parents` collection. This finds all files and folders located directly in the folder whose ID is `1234567`.
   <pre>'1234567' in [!UICONTROL parents]</pre>
* Search for the alias ID `appDataFolder` in the `parents` collection. This finds all files and folders located directly under the [Application Data folder](https://developers.google.com/drive/api/v2/appdata).
   <pre>'appDataFolder' in parents</pre>
* Search for files writeable by the users `test@example.org` and `test2@example.org`
   <pre>'test@example.org' in writers and 'test2@example.org' in writers</pre>
* Search for files containing the text "important" which are in the trash
   <pre>fullText contains 'important' and trashed = true</pre>
* Search for files modified after June 4th 2012
   <pre>modifiedDate > '2012-06-04T12:00:00' // default time zone is UTC</pre><pre>modifiedDate > '2012-06-04T12:00:00-08:00'</pre>
* Search for files shared with the authorized user with "hello" in the name
   <pre>sharedWithMe and title contains 'hello'</pre>
* Search for files with a [custom file property](https://developers.google.com/drive/api/v2/properties) named `additionalID` with the value `8e8aceg2af2ge72e78`.
   <pre>properties has { key='additionalID' and value='8e8aceg2af2ge72e78' and visibility='PRIVATE' }</pre>

Source of this guide is [[!DNL Google Drive] documentation](https://developers.google.com/drive/api/v2/search-shareddrives).

-->
