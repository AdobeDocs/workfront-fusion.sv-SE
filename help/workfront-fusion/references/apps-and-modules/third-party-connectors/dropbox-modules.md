---
title: Dropbox moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Dropbox och ansluta det till flera tredjepartsprogram och -tjänster. På så sätt kan du automatisera aktiviteter som övervakning, sökning, hämtning, listning, skapande och redigering av filer och mappar i din Dropbox.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 29ce5940-4d71-4719-ab5e-f03c44b28c8c
source-git-commit: 2ed8e4e956bacc18a43947c4c55482cf32533054
workflow-type: tm+mt
source-wordcount: '2908'
ht-degree: 0%

---

# [!DNL Dropbox] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!UICONTROL Dropbox] eller [!DNL Dropbox Business], samt ansluta det till flera tredjepartsprogram och -tjänster. På så sätt kan du automatisera aktiviteter som övervakning, sökning, hämtning, listning, skapande och redigering av filer och mappar i [!UICONTROL Dropbox].

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

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

* Du måste ha ett [!DNL Dropbox]-konto för att kunna använda [!DNL Dropbox]-moduler.

>[!IMPORTANT]
>
>* Om du vill använda Dropbox-anslutningen måste du först skapa ett program i Dropbox.
>   Om du vill ha mer information kan du söka efter&quot;Skapa ett program&quot; i utvecklarhandboken för Dropbox.
>* Använd följande omdirigerings-URI när du skapar programmet: `https://app.workfrontfusion.com/oauth/cb/dropbox`
>* Dropbox måste godkänna program med fler än 50 användare.
>   Mer information finns i&quot;Produktionsgodkännande&quot; i utvecklarhandboken för Dropbox.

## Dropbox API-information

Dropbox Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://api.dropboxapi.com/2    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td><ul><li><p>Dropbox</p><p>v5.3.9</p></li><li><p>Dropbox Business</p><p>v1.0.12</p></li></ul></td> 
  </tr>
 </tbody> 
 </table>


## Skapa en anslutning till [!DNL Dropbox]

Så här skapar du en anslutning för dina [!DNL Dropbox]-moduler:

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
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om den här anslutningen är avsedd för en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Dropbox] [!UICONTROL Client ID]. </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Dropbox] [!UICONTROL Client Secret]. </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Account Type]</td>
        <td>Ange om du ansluter till ett personligt Dropbox-konto eller ett företagskonto (Dropbox Business).</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Exclude dropbox-api-path-root header]</td>
        <td>Aktivera det här alternativet om du vill exkludera dropbox-api-path-root header för Dropbox-appar med appmappåtkomst</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.## [!DNL Dropbox] moduler och deras fält

## [!DNL Dropbox]-moduler och deras fält

När du konfigurerar [!DNL Dropbox] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Dropbox] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösarmoduler](#trigger-modules)
* [Moduler för att hämta [!DNL Dropbox] filer och mappar](#modules-for-getting-dropbox-files-and-folders)
* [Moduler för att skapa och redigera [!DNL Dropbox] filer och mappar](#modules-for-creating-and-editing-dropbox-files-and-folders)
* [Andra moduler](#other-modules)

### Utlösarmoduler

#### [!UICONTROL Watch Files]

Den här modulen för utlösare returnerar filinformation när filen i en angiven mapp ändras.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen som du vill bevaka ändringar i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch also subfolders]</td> 
   <td> <p> Aktivera det här alternativet om du även vill övervaka undermappar i den valda mappen för ändrade filer.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit] </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Moduler för att hämta [!DNL Dropbox] filer och mappar

* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL Get a Folder Metadata]](#get-a-folder-metadata)
* [[!UICONTROL List All Files/Subfolders in a Folder]](#list-all-filessubfolders-in-a-folder)
* [[!UICONTROL List File Revisions]](#list-file-revisions)
* [[!UICONTROL Search Files/Folders]](#search-filesfolders)

#### [!UICONTROL Download a File]

Den här åtgärdsmodulen hämtar en fil från en mapp.

Du anger filen och dess plats.

Modulen returnerar filens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

>[!NOTE]
>
>Den här modulen är användbar när du vill skicka filer till efterföljande moduler.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Olika sätt att välja filer</td> 
   <td> <p> Välj om du vill mappa filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Filsökväg/fil</p> </td> 
   <td> <p style="font-weight: bold;">Filsökväg</p> <p>Ange eller mappa målsökvägen till filen.</p> <p style="font-weight: bold;">Fil</p> <p>Välj filen på menyn.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Folder Metadata]

Den här åtgärdsmodulen hämtar information om delade mappar.

Du anger mappens ID.

Modulen returnerar ID:t för mappen och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>ID för delad mapp</td> 
   <td> <p> Ange eller mappa ID:t för mappen som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List All Files/Subfolders in a Folder]

Den här åtgärdsmodulen visar filer eller mappar i en viss mapp.

Du anger mappens ID.

Modulen returnerar ID:n för filerna eller mapparna och eventuella associerade fält, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Lista </td> 
   <td> <p>Välj om du vill hämta filer eller mappar.</p> </td> 
  </tr> 
  <tr> 
   <td>Visa endast hämtningsbara filer</td> 
   <td> <p> Aktivera det här alternativet om du bara vill returnera hämtningsbara filer. Det går inte att hämta vissa filtyper, till exempel Google Docs.</p> </td> 
  </tr> 
  <tr> 
   <td>Mapp </td> 
   <td> <p>Ange eller mappa mappen som du vill hämta filer eller mappar från.</p> </td> 
  </tr> 
  <tr> 
   <td>Gräns </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska visa under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List File Revisions]

Den här åtgärdsmodulen hämtar alla filversioner (en versionshistorik) av en viss fil.\
Du anger filens ID.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Olika sätt att välja filer</td> 
   <td> <p> Välj om du vill mappa filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Filsökväg/fil</p> </td> 
   <td> <p><b>Filsökväg</b></p> <p>Ange eller mappa målsökvägen till filen.</p> <p><b>Fil</b></p> <p>Välj filen på menyn.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Gräns</p> </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska visa under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Files/Folders]

Den här sökmodulen söker efter poster i ett objekt i [!DNL Dropbox] som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Ange söktermen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen som du vill söka i. Den här modulen söker igenom hela [!DNL Dropbox]kontot om du inte väljer någon mapp.</p> </td> 
  </tr> 
  <tr> 
   <td>Filstatus</td> 
   <td> <p> Välj den filstatus som du vill ta med i sökningen.</p> </td> 
  </tr> 
  <tr> 
   <td>Filkategorier</td> 
   <td> <p> Markera de filkategorier som du vill ta med i sökningen.</p> </td> 
  </tr> 
  <tr> 
   <td>Filtillägg</td> 
   <td> <p>För varje filtillägg som du vill inkludera i sökningen klickar du på <b>Lägg till objekt</b> och anger eller mappar filtillägget.</p> </td> 
  </tr> 
  <tr> 
   <td>Gräns </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Moduler för att skapa och redigera [!DNL Dropbox] filer och mappar

* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Create/Overwrite a Text File]](#createoverwrite-a-text-file)
* [[!UICONTROL Create/Update a Share Link]](#createupdate-a-share-link)
* [[!UICONTROL Delete a File/Folder]](#delete-a-filefolder)
* [[!UICONTROL Move a File/Folder]](#move-a-filefolder)
* [[!UICONTROL Rename a File/Folder]](#rename-a-filefolder)
* [[!UICONTROL Restore a File]](#restore-a-file)
* [[!UICONTROL Upload] en fil](#upload-a-file)

#### [!UICONTROL Create a Folder]

Den här åtgärdsmodulen skapar en ny mapp.

Du anger sökvägen och ett namn för mappen.

Modulen returnerar ID:t för mappen och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name] </td> 
   <td> <p>Ange namnet på den nya mappen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>Ange eller mappa sökvägen där du vill skapa en ny mapp.</p> <p>Obs!   <p>Om du använder ett [!DNL Dropbox Business]-konto (med grupputrymmen) måste du ta bort snedstrecket <code>/</code> eller inte klicka <strong>Klicka här om du vill välja mappen</strong> och skapa en gruppmapp i roten.</p> <p>Om snedstrecket inte tas bort returneras felet <code>[409] path/malformed_path/..</code>.</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Auto rename]</td> 
   <td> <p> Aktivera det här alternativet om du vill byta namn på den nya mappen, om det redan finns en mapp med samma namn på målplatsen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Overwrite a Text File]

Den här åtgärdsmodulen skapar en DOC-fil eller skriver över innehållet i en befintlig.

Du anger källfilen och mappen.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select to]</td> 
   <td> <p> Välj om du vill skapa eller skriva över en DOC-fil.</p><ul><li><b>Skapa</b></p>Välj den mapp där du vill skapa en fil.</li><li><b>Skriv över</b><p>Välj hur du vill välja vilken fil som ska skrivas över och mappa sedan filsökvägen eller markera filen. </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens innehåll. </p> <p>Om du skapar en fil väljer du <b>Tom</b>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Update a Share Link]

Den här åtgärdsmodulen skapar en offentlig länk till en fil.

Du anger filen och information om länken.

Modulen returnerar länkens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Välj om du vill mappa eller ange filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path / File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>Ange eller mappa sökvägen till målfilen.</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>Markera målfilen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Requested Visibility]</p> </td> 
   <td> <p>Ange om länken är offentlig, för team eller om lösenordet är begränsat.</p> <p><b>Obs!</b></p><p> [!UICONTROL Team only] är bara tillgängligt för Dropbox Business-konton. [!UICONTROL Access with password] är bara tillgängligt för [!DNL Dropbox Pro]- eller Dropbox Business-konton.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Link's Expiration Date]</td> 
   <td> <p> Ange det datum och den tidpunkt då länken upphör att gälla och inte längre är tillgänglig. Om fältet lämnas tomt upphör länken inte att gälla. En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Typtvång</a>.</p>  </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Link's Access Level]</p> </td> 
   <td> <p>Ange behörighet för länkmottagaren.</p> <ul><li><strong>[!UICONTROL Viewer]</strong> <p>Användare som använder länken kan visa och kommentera innehållet.</p> </li><li><strong>[!UICONTROL Editor]</strong><p> Användare som använder länken kan redigera, visa och kommentera innehållet. Den här åtkomstnivån är endast tillgänglig för molnbaserade dokument.</p> </li><li><strong>[!UICONTROL Max]</strong> <p>Användare som använder länken får den maximala åtkomstnivå som du kan ange länken till.</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Delete a File/Folder]

Den här åtgärdsmodulen tar bort en fil eller mapp.

Du anger filen eller mappen.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Välj om du vill mappa eller ange filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File or Folder Path] / [!UICONTROL File or Folder]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>Ange eller mappa målsökvägen till filen eller mappen.</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>Markera filen eller mappen på menyn.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder]

Den här åtgärdsmodulen flyttar en fil eller mapp till en annan plats.

Du anger filen eller mappen och hur och var du vill flytta den.

Modulen returnerar ID:t för filen eller mappen och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files / folders] </td> 
   <td> <p>Välj om du vill mappa eller ange fil- eller mappsökvägen, eller markera filen eller mappen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File / Folder Path] /</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>Ange eller mappa målsökvägen till filen eller mappen.</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>Ange om du flyttar en fil eller mapp, sedan filen eller mappen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL To Folder]</p> </td> 
   <td> <p>Ange eller mappa målplatsen för filen eller mappen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL New Name]</p> </td> 
   <td> <p>Ange det nya namnet på filen eller mappen på den nya platsen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Auto Rename]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill försäkra dig om att om det finns en fil eller mapp med samma namn så byter modulen namn på den nya filen eller mappen genom att lägga till ([!UICONTROL NUMBER]) efter fil- eller mappnamnet. Annars skrivs filen eller mappen på målplatsen över.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Allow ownership transfer]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta flyttning efter ägare, även om det skulle leda till en ägaröverföring för innehållet som flyttas.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File/Folder]

Den här åtgärdsmodulen byter namn på en fil eller mapp.

Du anger filen eller mappen och det nya namnet.

Modulen returnerar ID:t för filen eller mappen och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Olika sätt att välja filer</td> 
   <td> <p> Välj om du vill mappa eller ange filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Fil-/mappsökväg / Fil/Mapp</p> </td> 
   <td> <p style="font-weight: bold;">Fil-/mappsökväg</p> <p>Ange eller mappa målsökvägen till filen eller mappen.</p> <p style="font-weight: bold;">Fil/mapp</p> <p>Ange om du flyttar en fil eller mapp, sedan filen eller mappen.</p> </td> 
  </tr> 
  <tr> 
   <td>Byt namn </td> 
   <td> <p>Ange det nya namnet för filen, inklusive filtillägget.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Restore a File]

Den här åtgärdsmodulen återställer en tidigare version av en fil.

Du anger filen och numret på den revision du vill ha.

Modulen returnerar ID:t för versionen och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> Välj om du vill mappa eller ange filsökvägen eller markera filen manuellt.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p><strong>[!UICONTROL File Path]</strong> </p> <p>Ange eller mappa målsökvägen till filen.</p> <p><strong>[!UICONTROL File]</strong> </p> <p>Välj filen på menyn.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Revision]</p> </td> 
   <td> <p>Ange eller mappa revisionsnumret för den revision som du vill återställa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

Den här åtgärdsmodulen överför en fil till en mapp.

Du kan ange information om till exempel filens plats, vilken fil du vill överföra och ett valfritt nytt namn för filen.

Modulen returnerar filens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder]</td> 
   <td> <p> Markera mappen för den [!DNL Dropbox] som du vill överföra filen till.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> <p><b>Obs!</b></p><p> Den överförda filens största storlek är 150 MB.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing file]</td> 
   <td> <p> Aktivera det här alternativet om du vill ersätta den befintliga filen med den nya filen. Om det här alternativet är inaktiverat byter den överförda filen namn.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Andra moduler

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Dropbox]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Dropbox]-modulerna.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Dropbox]-konto till [!DNL Workfront Fusion] finns i <a href="#create-a-connection-to-dropbox" class="MCXref xref">Skapa en anslutning till [!DNL Dropbox]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till Ange en relativ sökväg till <code>https://api.dropboxapi.com</code>. Exempel: <code>/2/files/list_folder</code></p>  </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers] </td> 
   <td> <p>Ange önskade begäranderubriker. [!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p> Ange frågesträngen för begäran.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body] </td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!   <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:**

Följande API-anrop returnerar de första 10 filerna från mappen [!DNL /Text files] i ditt [!DNL Dropbox]-konto:

URL: `/2/files/list_folder`

Brödtext:

```
{
"path": "/Text files",
"limit": 10,
"recursive": false,
"include_deleted": false
}
```

Det går att hitta matchningar av sökningen i modulens utdata under [!UICONTROL Bundle] > [!UICONTROL Body] > poster.

I vårt exempel returnerades 10 biljetter.

>[!ENDSHADEBOX]

## Vanliga problem

* [Det går inte att överföra eller uppdatera en fil](#unable-to-upload-or-update-a-file)
* [Bild som refereras via en delad länk återges inte](#image-referenced-via-a-shared-link-does-not-render)

### Det går inte att överföra eller uppdatera en fil

Följande kan bero på att det inte går att överföra eller uppdatera en fil:

* Den överförda filen är för stor och överskrider den största tillåtna filstorleken för din [!DNL Dropbox]-plan, eller så har du använt hela lagringskvoten för ditt [!DNL Dropbox]-konto. Du måste ta bort befintliga filer från ditt [!DNL Dropbox]-konto eller uppgradera din plan.
* Den tidigare markerade mappen, som filen överförs till, finns inte längre. Scenariot stoppas och du måste välja målmappen igen.

### Bild som refereras via en delad länk återges inte

Den URL som returneras av [!UICONTROL Dropbox] >[!UICONTROL Create a shared link] länkar inte direkt till en bild, utan till en [!DNL Dropbox]-sida. Ersätt efterföljande `?dl=0` med `?dl=1` om du vill tvinga bilden att hämtas. Om du vill tvinga bilden att återges (till exempel i en webbläsare eller i Facebook Messenger) lägger du till `&raw=1` i URL:en.

Om du behöver hämta den direkta eller råa länken till bilden för webbplatsen eller för andra [!DNL Workfront Fusion]-moduler måste du ändra den ursprungliga delade URL:en på följande sätt:

Ursprunglig URL:

`https://www.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png?dl=0`

1. Ersätt `www` med `dl`.
1. Ta bort `?dl=0`.

Slutlig URL:

`https://dl.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png`

Om du vill ändra URL-adressen automatiskt kan du använda funktionen `replace()` två gånger:

* Ersätt www med dl

  ![Ersätt www med dl](/help/workfront-fusion/references/apps-and-modules/assets/www-to-dl-350x32.png)

* Och ta bort ?dl=0

  ![Ta bort DL](/help/workfront-fusion/references/apps-and-modules/assets/remove-dl0-350x33.png)

Om du vill göra det i ett enda steg kombinerar du dessa funktioner:

![Ersätt båda](/help/workfront-fusion/references/apps-and-modules/assets/replace-both-350x47.png)

Du kan också kopiera den och klistra in den i fältet. Ersätt `1.url` med URL:en.

```
{{replace(replace(1.url; "?dl=0"; ""); "www"; "dl")}}
```
