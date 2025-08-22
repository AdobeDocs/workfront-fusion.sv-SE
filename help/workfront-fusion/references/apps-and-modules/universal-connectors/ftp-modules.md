---
title: FTP-moduler
description: Med FTP-moduler kan du övervaka filändringar i en vald mapp, överföra nya filer till önskad mapp samt ändra eller ta bort befintliga filer som redan finns i en mapp.
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 0%

---

# FTP-moduler

Med FTP-moduler kan du övervaka filändringar i en vald mapp, överföra nya filer till önskad mapp samt ändra eller ta bort befintliga filer som redan finns i en mapp.

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

## Förutsättningar

Om du vill använda FTP-moduler måste du ha ett konto hos en FTP-tjänst.

## Skapa en anslutning i en FTP-modul {#create-a-connection}

1. Klicka på **Lägg till** bredvid anslutningsrutan i en FTP-modul.
1. Fyll i följande fält.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Connection name]</td> 
      <td> <p> Ange namnet på FTP-anslutningen.</p> </td> 
     </tr> 
     <tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td> <p>Välj om du använder en produktionsmiljö eller icke-produktionsmiljö.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Type]</p> </td> 
      <td> <p>Ange om du använder ett tjänstkonto eller ett personligt konto.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Host] </td> 
      <td> <p>Ange FTP-serverns värdnamn. Exempel: <code>myftp123.server.com</code></p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Port] </td> 
      <td> <p>Ange FTP-serverns portnummer. Exempel: <code>21</code></p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL User name] </td> 
      <td> <p>Ange ditt användarnamn för FTP-kontot.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Password] </td> 
      <td> <p>Ange ditt lösenord för FTP-kontot.</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Använd en säker anslutning (TLS)</p> </td> 
      <td> <p>Välj om du vill använda en säker anslutning.</p> <ul><li><p><b>[!UICONTROL No]</b></p> <p>Anslutningen är inte skyddad.</p></li><li> <p><b>Explicit kryptering</b> eller <b>implicit kryptering</b></p> <p>Anslutningen skyddas med SSL.</p> </td> 
     </tr> 
    <tr> 
   <td> <p>[!UICONTROL Reject unauthorized certificates]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill verifiera FTP-servercertifikatet. Om verifieringen misslyckas skapas inte anslutningen. Certifikatet måste uppfylla ett av följande kriterier för att kunna godkännas:</p> 
    <ul> 
     <li>signeras av en rotcertifikatutfärdare</a></li> 
     <li>signeras av en mellanliggande certifikatutfärdare. I det här fallet ska alla mellanliggande certifikat installeras på FTP-servern.</li> 
     <li>vara ett självsignerat certifikat i fältet [!UICONTROL Self-signed certificate] (se nedan)</li> </ul>
     <p>Om det här alternativet är inaktiverat verifieras inte FTP-servercertifikatet. Vi rekommenderar starkt att du inte inaktiverar alternativet eftersom det gör anslutningen osäker och utgör en allvarlig säkerhetsrisk.</p></td>
    </tr> 
    <tr> 
     <td> <p>[!UICONTROL Self-signed certificate]</p> </td> 
     <td> <p>Klicka på knappen <b>[!UICONTROL Extract]</b> för att öppna dialogrutan för överföring.</p> <p>Överför certifikatet för att använda TLS med ditt självsignerade certifikat. Workfront Fusion bevarar eller lagrar inga data som du tillhandahåller, t.ex. filer och lösenord. Fil och lösenord används endast för att extrahera certifikatet.</p> </td> 
    </tr> 
   </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## FTP-moduler och deras fält

* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

#### [!UICONTROL Watch files]

[!UICONTROL Watch files] är den enda utlösarmodulen för FTP. Den övervakar filinnehållet i den valda mappen. Utlösaren körs när en ny fil läggs till i den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#create-a-connection" class="MCXref xref">[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>Markera den mapp som du vill bevaka.</p> <p><b>Obs!</b> Endast en mapp per scenario tillåts. Undermappar ignoreras.</p> <p><b>Tips!</b> Om du vill bevaka flera mappar skapar du ett separat scenario för var och en av dem.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files] </td> 
   <td> <p>Ange det maximala antal resultat som du vill att modulen ska arbeta med under en cykel. Om värdet är för högt kan anslutningen avbrytas på FTP-serversidan. Workfront Fusion har ingen effekt på detta. Vi rekommenderar att du anger ett lägre värde och antingen definierar ett högre värde för det maximala antalet cykler eller kör scenariot oftare.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Change permissions]](#change-permissions)
* [[!UICONTROL Create a folder]](#create-a-folder)
* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Delete a folder]](#delete-a-folder)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL List of files in a folder]](#list-of-files-in-a-folder)
* [[!UICONTROL Move a file or folder]](#move-a-file-or-folder)
* [[!UICONTROL Upload] en fil](#upload-a-file)

#### [!UICONTROL Change permissions]

Den här åtgärdsmodulen ändrar behörighetsinställningarna för en fil eller mapp.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Change permission settings of]</td>
            <td>
               <p>Välj om du vill ändra inställningarna för en fil eller mapp.</p>
            </td>
         </tr>
         <tr>
            <td>[!UICONTROL File path]</td>
            <td>Ange eller mappa filsökvägen till mappen eller filen.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Permissions]</td>
            <td>
               <p>Ange önskade fil- eller mappbehörigheter. Använd chmod-parametrarna. Till exempel: <code>777 </code> eller <code>-rwxrwxrwx</code>.</p>
               <p>Behörigheterna måste matcha mönstret <code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code>.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Create a folder]

Den här åtgärdsmodulen skapar en ny mapp.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Folder path]</td>
            <td>Ange eller mappa filsökvägen till den nya mappen.</td>
         </tr>
         <tr>
            <td>[!UICONTROL New folder name]</td>
            <td>
               <p>Ange eller mappa ett namn för den nya mappen.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Delete a file]

Den här åtgärdsmodulen tar bort en fil från den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
            <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera den FTP-mapp som du vill ta bort en fil från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td> <p> Ange filnamnet, inklusive filnamnstillägget. Exempel: <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a folder]

Den här åtgärdsmodulen tar bort den angivna mappen permanent.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Folder]</td>
            <td>
               <p>Markera den FTP-mapp som du vill ta bort en fil från.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Get a file]

Den här åtgärdsmodulen hämtar en fil från FTP-servern.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File path]</td> 
   <td> <p> Ange sökvägen till filen som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List of files in a folder]

Den här åtgärdsmodulen hämtar fil- och/eller mappinformation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera den FTP-mapp som du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>Välj om du vill hämta information om filer eller mappar, eller båda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Ange söktermen. Om ingen sökterm anges hämtas alla filer eller mappar från den angivna mappen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p>Ange eller mappa det maximala antal resultat som du vill att modulen ska arbeta med under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a file or folder]

Den här åtgärdsmodulen flyttar en fil eller mapp till en annan plats.

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr>
            <td>[!UICONTROL Old file path]</td>
            <td>
               <p>Ange sökvägen som du vill flytta filen från. Exempel: <code>/folder1/document.txt</code>.</p>
            </td>
         </tr>
         <tr>
            <td>[!UICONTROL New file path]</td>
            <td>
               <p>Ange sökvägen som du vill flytta filen till. Exempel: <code>/folder2/document.txt</code>.</p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL Upload a file]

Överför en fil till FTP-servern.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera den FTP-mapp som du vill överföra filen till.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file] </td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Append to an already existing file]</td> 
   <td> <p>Om det här alternativet är aktiverat och filen redan finns på FTP-servern, läggs filens innehåll till i den befintliga filen. Om det här alternativet inte är aktiverat skrivs innehållet i filen över.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create folders if don't exist] </td> 
   <td> <p>Om det här alternativet är aktiverat och mappen som du har angett i fältet Mapp inte finns på FTP-servern, skapas mappen i modulen</p> </td> 
  </tr> 
 </tbody> 
</table>

## Felsökning {#troubleshooting}

Om du får problem med FTP-programmet antingen när anslutningen skapas eller när en modul används, kan du försöka använda någon av de populära FTP-klienterna och försöka utföra samma åtgärd (till exempel skapa en anslutning eller lista med filer i en mapp). med FTP-klienten. Om du får samma problem även med FTP-klienten kan det bero på en felkonfiguration av FTP-servern.
