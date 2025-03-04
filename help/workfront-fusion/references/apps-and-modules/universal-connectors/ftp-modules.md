---
title: FTP-moduler
description: Med FTP-moduler kan du övervaka filändringar i en vald mapp, överföra nya filer till önskad mapp samt ändra eller ta bort befintliga filer som redan finns i en mapp.
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: c5e9c643c828e5556e386a5f46e1d17680b7d4e9
workflow-type: tm+mt
source-wordcount: '1328'
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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Du måste ha ett FTP-konto för att kunna använda FTP-moduler.

## Skapa en anslutning i en FTP-modul {#create-a-connection}

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutningsnamn]</td> 
   <td> <p> Ange namnet på FTP-anslutningen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-värd] </td> 
   <td> <p>Ange FTP-serverns värdnamn. E.g. <code>myftp123.server.com</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-port] </td> 
   <td> <p>Ange FTP-serverns portnummer. E.g. <code>21</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-användarnamn] </td> 
   <td> <p>Ange ditt användarnamn för FTP-kontot.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-lösenord] </td> 
   <td> <p>Ange ditt lösenord för FTP-kontot.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Använd en säker anslutning (TLS)</p> </td> 
   <td> <p>Välj om du vill använda en säker anslutning.</p> <p style="font-weight: bold;">[!UICONTROL-nr]</p> <p>Anslutningen är inte skyddad.</p> <p style="font-weight: bold;">[!UICONTROL Explicit kryptering eller implicit kryptering]</p> <p>Anslutningen skyddas med SSL.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Avvisa obehöriga certifikat]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill verifiera FTP-servercertifikatet. Om verifieringen misslyckas skapas inte anslutningen. Certifikatet måste uppfylla ett av följande kriterier för att kunna godkännas:</p> 
    <ul> 
     <li>signeras av en rotcertifikatutfärdare (<a href="https://en.wikipedia.org/wiki/Certificate_authority">Certificate Authority</a>)</li> 
     <li>signeras av en mellanliggande certifikatutfärdare (mer information finns i <a href="https://knowledge.digicert.com/solution/SO16297.html">Hur certifikatkedjor fungerar</a>). I det här fallet ska alla mellanliggande certifikat installeras på FTP-servern.</li> 
     <li>vara ett självsignerat certifikat som anges i fältet [!UICONTROL Self-signed certificate] (se nedan)</li> </ul>

Om det här alternativet är inaktiverat verifieras inte FTP-servercertifikatet. Vi rekommenderar starkt att du inte inaktiverar alternativet eftersom det gör anslutningen osäker och utgör en allvarlig säkerhetsrisk.</td>
</tr> 
  <tr> 
   <td> <p>[!UICONTROL Self-signed certificate]</p> </td> 
   <td> <p>Klicka på knappen <b>[!UICONTROL Extract]</b> för att öppna dialogrutan för överföring.</p> <p>Överför certifikatet för att använda TLS med ditt självsignerade certifikat. [!DNL Workfront Fusion] sparar eller lagrar inte data som du anger, t.ex. filer och lösenord. Fil och lösenord används endast för att extrahera certifikatet.</p> </td> 
  </tr> 
 </tbody> 
</table>

## FTP-moduler och deras fält

* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

#### [!UICONTROL Bevakade filer]

[!UICONTROL Bevakade filer] är den enda utlösarmodulen för FTP. Den övervakar filinnehållet i den valda mappen. Utlösaren körs när en ny fil infogas i den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutning] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#create-a-connection" class="MCXref xref">[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL-mapp]</p> </td> 
   <td> <p>Markera den mapp som du vill bevaka.</p> <p><b>Obs!</b> Endast en mapp per scenario tillåts. Undermappar ignoreras.</p> <p><b>Tips!</b> Om du vill hålla reda på flera mappar skapar du ett oberoende scenario för var och en av dem.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximalt antal returnerade filer] </td> 
   <td> <p>Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska arbeta med under en cykel. Om värdet är för högt kan anslutningen avbrytas på sidan om den angivna tredjepartstjänsten (timeout). [!DNL Workfront Fusion] har ingen påverkan på detta. Vi rekommenderar att du anger ett lägre värde och antingen definierar ett högre värde för det maximala antalet cykler eller kör scenariot oftare.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Ändra behörigheter]](#change-permissions)
* [[!UICONTROL Skapa en mapp]](#create-a-folder)
* [[!UICONTROL Ta bort en fil]](#delete-a-file)
* [[!UICONTROL Ta bort en mapp]](#delete-a-folder)
* [[!UICONTROL Hämta en fil]](#get-a-file)
* [[!UICONTROL Lista över filer i en mapp]](#list-of-files-in-a-folder)
* [[!UICONTROL Flytta en fil eller mapp]](#move-a-file-or-folder)
* [[!UICONTROL Överför] en fil](#upload-a-file)

#### [!UICONTROL Ändra behörigheter]

Den här åtgärdsmodulen ändrar behörighetsinställningarna för en fil eller mapp.

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL-anslutning]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL Ändra behörighetsinställningar för]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">
               <p>Välj om du vill ändra inställningarna för en fil eller mapp.</p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL-filsökväg]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">Ange eller mappa filsökvägen till mappen eller filen.</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-MediumGray" role="rowheader">[!UICONTROL-behörigheter]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-MediumGray">
               <p>Ange önskade fil- eller mappbehörigheter. Använd chmod-parametrarna. Till exempel: <code>777 </code> eller <code>-rwxrwxrwx</code>.</p>
               <p>Behörigheterna måste matcha mönstret <code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code>.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Skapa en mapp]

Den här åtgärdsmodulen skapar en ny mapp.

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL-anslutning]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL-mappsökväg]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">Ange eller mappa filsökvägen till den nya mappen.</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-LightGray" role="rowheader">[!UICONTROL Nytt mappnamn]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-LightGray">
               <p>Ange eller mappa ett namn för den nya mappen.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Ta bort en fil]

Tar bort en fil från den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutning] </td> 
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL-mapp] </td> 
   <td> <p>Markera den FTP-mapp som du vill ta bort en fil från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-filnamn]</td> 
   <td> <p> Ange filnamnet, inklusive filnamnstillägget. Exempel: <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Ta bort en mapp]

Den här åtgärdsmodulen tar bort den angivna mappen permanent.

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL-anslutning]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL-mapp]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-MediumGray">
               <p>Markera den FTP-mapp som du vill ta bort en fil från.</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Hämta en fil]

Hämtar en fil från FTP-servern som kan bearbetas ytterligare, t.ex. överföras till [!DNL Dropbox].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutning] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-filsökväg]</td> 
   <td> <p> Ange sökvägen till filen som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Lista över filer i en mapp]

Hämtar fil- och/eller mappinformation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutning] </td> 
   <td> <p>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-mapp] </td> 
   <td> <p>Markera den FTP-mapp som du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>Välj om du vill hämta information om filer eller mappar, eller båda.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-sökning] </td> 
   <td> <p>Ange söktermen. Om ingen sökterm anges hämtas alla filer och mappar från den angivna mappen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximalt antal returnerade filer]</td> 
   <td> <p> Ange det maximala antalet hämtade filer i den här modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Flytta en fil eller mapp]

Den här åtgärdsmodulen flyttar en fil eller mapp till en annan plats.

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL-anslutning]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#Create" class="MCXref xref" >[!UICONTROL Skapa en anslutning] i en FTP-modul</a> i den här artikeln.</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL Old file path]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-MediumGray">
               <p>Ange sökvägen som du vill flytta filen från. Exempel: <code>/folder1/document.txt</code>.</p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-LightGray" style="font-weight: bold;">[!UICONTROL Ny filsökväg]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-LightGray">
               <p>Ange sökvägen som du vill flytta filen till. Exempel: <code>/folder2/document.txt</code>.</p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL Överför en fil]

Överför en fil till FTP-servern.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL-anslutning] </td> 
   <td>Instruktioner om hur du upprättar en anslutning till FTP-kontot finns i <a href="#creating-the-ftp-connection" class="MCXref xref">Skapa FTP-anslutningen</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL-mapp] </td> 
   <td> <p>Markera den FTP-mapp som du vill överföra filen till.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source-fil] </td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Lägg till i en befintlig fil]</td> 
   <td> <p>Om det här alternativet är aktiverat och filen redan finns på FTP-servern, läggs filens innehåll till i den befintliga filen. Om det här alternativet inte är aktiverat skrivs innehållet i filen över.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Skapa mappar om det inte finns] </td> 
   <td> <p>Om det här alternativet är aktiverat och mappen som du har angett i fältet Mapp inte finns på FTP-servern, skapas mappen i modulen</p> </td> 
  </tr> 
 </tbody> 
</table>

## Felsökning {#troubleshooting}

Om du får problem med FTP-programmet antingen när anslutningen skapas eller när en modul används, kan du försöka använda någon av de populära FTP-klienterna och försöka utföra samma åtgärd (till exempel skapa en anslutning eller lista med filer i en mapp). med FTP-klienten. Om du får samma problem även med FTP-klienten kan det bero på en felkonfiguration av FTP-servern.
