---
title: Google Drive-moduler
description: Modulerna  [!DNL Adobe Workfront Fusion Google Drive] gör att du kan övervaka, söka, skapa, uppdatera, ta bort och hantera filer, mappar och delade enheter i din [!DNL Google Drive].
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2489'
ht-degree: 0%

---

# [!DNL Google Drive] moduler

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Google Drive] kan du övervaka, söka, skapa, uppdatera, ta bort och hantera filer, mappar eller delade enheter i [!DNL Google Drive].

I ett [!DNL Adobe Workfront Fusion]-scenario kan du ansluta ditt [!DNL Google Drive]-konto till flera tredjepartsprogram och -tjänster.

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



## Ansluter [!DNL Google Drive] till [!DNL Workfront Fusion]

Om du är [!DNL @gmail.com] eller [!DNL @googlemail.com] användare måste du skapa en OAuth-klient på [ [!DNL Google Cloud Platform]](https://console.developers.google.com/projectselector2/apis/dashboard?supportedpurview=project) för att få [!UICONTROL Client ID] och [!UICONTROL Client Secret].

Stegvisa instruktioner om hur du skapar OAuth-klienten (och hämtar [!UICONTROL Client ID] och [!UICONTROL Client Secret]) finns i [Anslut [!DNL Adobe Workfront Fusion] till [!DNL Google Services] med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## [!DNL Google Drive]-moduler och deras fält

När du konfigurerar [!DNL Google Drive] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Google Drive] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

* [[!UICONTROL Watch Files In Folder]](#watch-files-in-folder)
* [[!UICONTROL Watch All Files]](#watch-all-files)
* [[!UICONTROL Watch shared files]](#watch-shared-files)
* [[!UICONTROL Watch Comments]](#watch-comments)

#### [!UICONTROL Watch Files In Folder]

Hämtar filinformation när en fil läggs till eller ändras i den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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
    <td>Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska hämta under en cykel (antalet upprepningar per scenariokörning).</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch All Files]

Hämtar filinformation när en fil i [!DNL Google Drive] läggs till eller ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska hämta under en cykel (antalet upprepningar per scenariokörning).</td> 
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
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska hämta under en cykel (antalet upprepningar per scenariokörning).</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Comments]

Startar när en kommentar läggs till eller ändras i den markerade filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>Ange det maximala antalet kommentarer som [!DNL Workfront Fusion] ska returnera under en cykel (antalet upprepningar per scenario-körning).</td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Upload a File]](#upload-a-file)
* [[!UICONTROL Update a File]](#update-a-file)
* [[!UICONTROL Copy a File]](#copy-a-file)
* [[!UICONTROL Delete a File]](#delete-a-file)
* [[!UICONTROL Move a File/Folder to Trash]](#move-a-filefolder-to-trash)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Search for Files/Folders]](#search-for-filesfolders)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Get a share link]](#get-a-share-link)

#### [!UICONTROL Upload a File]

Överför en fil till din [!DNL Google Drive].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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
   <td>Välj om du vill använda en fil som har skickats från en tidigare modul eller om du vill mappa filen manuellt.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td>Markera filnamnet. Det här alternativet är tillgängligt om du väljer [!UICONTROL Map] i fältet [!UICONTROL source file].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Data]</td> 
   <td>Markera den datafil som du vill överföra. Det här alternativet är tillgängligt om du väljer [!UICONTROL Map] i fältet [!UICONTROL source file].</td> 
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

#### [!UICONTROL Update a File]

Uppdaterar metadata eller innehåll för en fil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som du vill överföra en fil till.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Move to a folder]</td> 
   <td>Om du vill flytta filen till en annan mapp markerar du mappen som du vill flytta filen till.</td> 
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
   <td>Välj om du vill använda en fil som har skickats från en tidigare modul eller om du vill mappa filen manuellt. Det här fältet är tillgängligt om du valde att ändra filens innehåll i det föregående fältet.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td>Markera filnamnet. Det här alternativet är tillgängligt om du väljer [!UICONTROL Map] i fältet [!UICONTROL source file].</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Data]</td> 
   <td>Markera den datafil som du vill överföra. Det här alternativet är tillgängligt om du väljer [!UICONTROL Map] i fältet [!UICONTROL source file].</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy a File]

Kopierar en fil till den nya platsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som du vill överföra en fil till.</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Target folder]</td> 
   <td>Välj den mapp där filen du vill kopiera finns/</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL The name of the copy]</td> 
   <td>Ange en rubrik för den nya filen. Lämna fältet tomt om du inte vill ändra det ursprungliga filnamnet.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File]

Tar bort en fil eller mapp permanent.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder to Trash]

Flyttar en fil eller mapp till papperskorgen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill flytta till papperskorgen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

Hämtar filen med angivet ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
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

#### [!UICONTROL Search for Files/Folders]

Söker efter filer eller mappar baserat på sökvillkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som du vill söka efter.</p> 
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
   <td>Ange det maximala antalet filer eller mappar som [!DNL Workfront Fusion] returnerar under en körningscykel.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td>Aktivera det här alternativet för att säkerställa att scenariot inte stoppas om modulen inte returnerar några resultat.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

Skapar en mapp på den angivna platsen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination]</td> 
   <td> <p>Välj det mål som du vill överföra en fil till.</p> 
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

#### [!UICONTROL Get a share link]

Hämtar delningslänken för en fil i Google Drive.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Google Drive]-konto till [!DNL Workfront Fusion] finns i <a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">Ansluter [!DNL Google Drive] till [!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File ID]</td> 
   <td>Mappa ID:t för filen som du vill hämta delningslänken för.</td> 
  </tr> 
 </tbody> 
</table>

## Felsökning

### Det går inte att överföra eller uppdatera en fil

Det finns flera situationer när det inte går att överföra eller uppdatera en fil:

* Den överförda filen är för stor och överskrider maxgränsen för filstorlek som tillåts för din [!DNL Google Drive]-plan, eller så har du överskridit lagringsgränsen för [!DNL Google Drive]. Du kan antingen uppgradera din lagringsplan eller ta bort befintliga filer från tjänsten [!DNL Google Drive].
* Den valda mappen som filen skulle överföras till finns inte längre. Scenariot stoppas och du måste sedan välja en målmapp igen.

## Sök efter filer

I modullistfilerna i en mapp kan du använda en egen fråga som består av följande delar:

* **[!UICONTROL Field]** - Attribut för filen som söks igenom, till exempel filens attribut `name`.

* **[!UICONTROL Operator]** - Testa data för att ge en matchning, till exempel `contains`.

* **[!UICONTROL Value]** - Innehållet i attributet som testas, till exempel namnet på filen `My cool document`.

Kombinera satser med kopplingarna `and` eller `or` och negera frågan med `not`.

* [Fält](#fields)
* [Värdetyper](#value-types)
* [Operatorer](#operators)
* [Exempel](#examples)

### Fält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Fält </th> 
   <th>Värdetyp </th> 
   <th>Operatorer</th> 
   <th> <p> Beskrivning</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>string</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Filens namn.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>string </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Fullständig text i filen, inklusive namn, beskrivning, innehåll och indexerbar text.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> string</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Filens MIME-typ.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Datum för den senaste ändringen av filen.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Det datum då användaren senast visade en fil.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>boolesk </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Anger om filen finns i papperskorgen eller inte.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>boolesk </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Anger om filen är stjärnmarkerad eller inte.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>samling </td> 
   <td><code>in </code> </td> 
   <td> <p>Anger om [!UICONTROL parents]-samlingen innehåller det angivna ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>samling </td> 
   <td><code>in </code> </td> 
   <td> <p>Användare som äger filen.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>samling </td> 
   <td><code>in </code> </td> 
   <td> <p>Användare som har behörighet att ändra filen.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>samling </td> 
   <td><code>in </code> </td> 
   <td> <p>Användare som har behörighet att läsa filen.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>boolesk </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Filer som finns i användarens"Delade med mig"-samling.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>samling</td> 
   <td><code>has </code> </td> 
   <td> <p> Publika anpassade filegenskaper.</p> </td> 
  </tr> 
 </tbody> 
</table>

Tänk på följande om operatorer i dessa fält:

* Operatorn `contains` utför bara prefixmatchning för en `title`.

  Titeln&quot;HelloWorld&quot; matchar till exempel för `title contains 'Hello'` men inte för `title contains 'World'`.

* Operatorn `contains` utför bara matchning för hela strängtoken för `fullText`.

  Om den fullständiga texten i ett dokument till exempel innehåller strängen &quot;HelloWorld&quot; returnerar bara frågan `fullText contains 'HelloWorld'` ett resultat. Frågor som `fullText contains 'Hello'` returnerar inte resultat i det här scenariot.

* Operatorn `contains` matchar en exakt alfanumerisk fras om den omges av dubbla citattecken.

  Om till exempel `fullText` för ett dokument innehåller strängen &quot;Hello where world&quot; returnerar frågan `fullText contains '"Hello there"'` ett resultat, men frågan `fullText contains '"Hello world"'` gör det inte.

  Eftersom sökningen är alfanumerisk returnerar frågan `fullText contains '"Hello world"'` ett resultat om `fullText` i ett dokument innehåller strängen Hello_world.

* Fält med datumet `type` kan för närvarande inte jämföras med varandra, bara med konstanta datum.

### Värdetyper

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Värdetyp</th> 
   <th> <p> Anteckningar</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Sträng </td> 
   <td> <p>Omge med enkla citattecken '. Escape-enkla citattecken i frågor med <code>\'</code>, t.ex. <code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Boolean </td> 
   <td> <p><code>true </code>eller <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Datum </td> 
   <td> <p>RFC 3339-format, standardtidszonen är UTC, t.ex. <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operatorer

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operator </th> 
   <th> <p>Anteckningar</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>Innehållet i en sträng finns i den andra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> Innehållet i en sträng eller ett booleskt värde är lika med det andra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> Innehållet i en sträng eller ett booleskt värde är inte lika med det andra.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> Ett datum är tidigare än ett annat.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> Ett datum är tidigare än eller lika med ett annat.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> Ett datum är senare än ett annat.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> Ett datum är senare än eller lika med ett annat.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>Ett element finns i en samling.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Returnera filer som matchar båda satserna.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Returnera filer som matchar någon av satserna.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Negerar en söksats.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>En samling innehåller ett element som matchar parametrarna.</p> </td> 
  </tr> 
 </tbody> 
</table>

För sammansatta satser kan du använda parenteser för att gruppera satser. Till exempel:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` Den här sökningen returnerar alla filer med en MIME-typ för bild eller video som senast ändrades efter 4 juni 2012. Eftersom operatorerna `and` och `or` utvärderas från vänster till höger, utan parenteser, returnerar exemplet ovan endast bilder som ändrats efter 4 juni 2012, men alla videor returneras, även de som har ändrats före 4 juni 2012.

### Exempel

Alla exempel på den här sidan visar den okodade parametern `<q>q</q>`, där `title = 'hello'` är kodad som `title+%3d+%27hello%27`. Klientbibliotek hanterar den här kodningen automatiskt.

* Sök efter filer med namnet &quot;hello&quot;
  <pre>title = 'hello'</pre>
* Sök efter mappar med den mappspecifika MIME-typen
  <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Sök efter filer som inte är mappar
  <pre>mimeType != 'application/vnd.google-apps.folder'</pre>
* Sök efter filer med ett namn som innehåller orden &quot;hello&quot; och &quot;hejdå&quot;
  <pre>titeln innehåller "hello" och [!UICONTROL name] innehåller 'hejdå'</pre>
* Sök efter filer med ett namn som inte innehåller ordet &quot;hello&quot;
  <pre>inte titeln innehåller 'hello'</pre>
* Sök efter filer som innehåller ordet &quot;hello&quot; i innehållet
  <pre>fullText innehåller 'hello'</pre>
* Sök efter filer som inte innehåller ordet &quot;hello&quot; i innehållet
  <pre>not fullText contains 'hello'</pre>
* Sök efter filer som innehåller den exakta frasen&quot;hello world&quot; i innehållet
  <pre>fullText innehåller '"hello world"'fullText innehåller '"hello_world"'</pre>
* Sök efter filer med en fråga som innehåller tecknet &quot;\&quot; (t.ex. &quot;\authors&quot;)
  <pre>fullText innehåller \\authors</pre>
* Sök efter filer som kan skrivas av användaren `test@example.org`
  <pre>test@example.org i [!DNL writers]</pre>
* Sök efter ID `1234567` i samlingen `parents`. Detta söker efter alla filer och mappar som finns direkt i den mapp vars ID är `1234567`.
  <pre>1234567 tum [!UICONTROL parents]</pre>
* Sök efter alias-ID:t `appDataFolder` i samlingen `parents`. Detta söker efter alla filer och mappar som finns direkt under mappen [Application Data](https://developers.google.com/drive/api/v2/appdata).
  <pre>appDataFolder i parent</pre>
* Sök efter filer som kan skrivas av användarna `test@example.org` och `test2@example.org`
  <pre>test@example.org i skribenter och test2@example.org i skribenter</pre>
* Sök efter filer som innehåller texten &quot;important&quot; och som finns i papperskorgen
  <pre>fullText innehåller 'important' och trashed = true</pre>
* Sök efter filer som ändrats efter 4 juni 2012
  <pre>modifiedDate &gt; '2012-06-04T12:00:00' // standardtidszonen är UTC</pre><pre>modifiedDate &gt; '2012-06-04T12:00:00-08:00'</pre>
* Sök efter filer som delas med den behöriga användaren med &quot;hello&quot; i namnet
  <pre>sharedWithMe och title innehåller "hello"</pre>
* Sök efter filer med en [anpassad filegenskap](https://developers.google.com/drive/api/v2/properties) med namnet `additionalID` och värdet `8e8aceg2af2ge72e78`.
  <pre>har { key='additionalID' och value='8e8aceg2af2ge72e78' och visibility='PRIVATE' }</pre>

Source i den här handboken är [[!DNL Google Drive] dokumentation](https://developers.google.com/drive/api/v2/search-shareddrives).
