---
title: SFTP-moduler
description: Med modulerna  [!DNL Adobe Workfront Fusion SFTP] kan du övervaka filändringar i en vald mapp/undermapp, överföra nya filer till önskad mapp, ändra eller ta bort befintliga filer som redan finns i en mapp eller ändra filbehörigheter.
author: Becky
feature: Workfront Fusion
exl-id: bde3cbda-8a19-4d9f-b970-f56d73a1f8dd
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 0%

---

# SFTP-moduler

Med modulerna [!DNL Adobe Workfront Fusion] SFTP kan du övervaka filändringar i en vald mapp/undermapp, överföra nya filer till önskad mapp, ändra eller ta bort befintliga filer som redan finns i en mapp eller ändra filbehörigheter.

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

Om du vill använda SFTP med [!DNL Workfront Fusion] måste du ha ett SFTP-konto (till exempel [!DNL GoDaddy] webbhosting).

## Anslut SFTP till [!DNL Workfront Fusion] {#connect-sftp-to-workfront-fusion}

Om du vill ansluta ditt SFTP-konto till [!DNL Workfront Fusion] måste du skapa en anslutning som anger målvärden och SFTP-autentiseringsuppgifter (användarnamn och lösenord eller användarnamn och nyckel).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection name]</td> 
   <td> <p> Ange namnet på SFTP-anslutningen.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Environment]</td>
    <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL Type]</td>
    <td>Välj om du vill ansluta till ett tjänstkonto eller ett personligt konto.</td>
  </tr>
  <tr>
   <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
   <td> <p>Ange värdnamnet för den SFTP-server som du vill ansluta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Port] </td> 
   <td> <p>Ange SFTP-serverporten. Exempel: 22.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Auth type]</p> </td> 
   <td> <p>Välj den auktoriseringsmetod som du vill använda för att ansluta till SFTP-servern.</p> 
    <ul> 
     <li><strong>[!UICONTROL User name and password]</strong>: Ange dina autentiseringsuppgifter.</li> 
     <li> <p><strong>[!UICONTROL User name and key]</strong>: Ange ditt användarnamn och den privata nyckeln/certifikatet</p> <p>Överför den privata nyckeln för att använda auktoriseringen på klientsidan eller överför certifikatet (P12- eller PFX-fil) om du vill använda TLS med ditt självsignerade certifikat. Om du använder certifikatauktorisering på klientsidan kan du ange ditt certifikatutfärdarcertifikat här.</p> <p>[!DNL Workfront Fusion] sparar eller lagrar inte data (filer, lösenord) som du anger här. Fil och lösenord används bara för att extrahera en privat nyckel/certifikat.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Key exchange algorithms] </td> 
   <td> <p>Du kan ange en uppsättning algoritmer för nyckelutbyte. Modulen prioriterar algoritmer baserat på den ordning som de lades till. För varje algoritm som du vill lägga till klickar du på <b>Lägg till objekt</b> och väljer algoritmen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Ciphers] </td> 
   <td> <p>Du kan ange en uppsättning ciphers för nyckelutbyte. Modulen prioriterar ciphers baserat på den ordning de lagts till. Klicka på <b>Lägg till objekt</b> för varje klipp som du vill lägga till och markera chiffret.</p> </td> 
  </tr> 
 </tbody> 
</table>

När du har angett anslutningsinformationen klickar du på **[!UICONTROL Continue]** för att upprätta en anslutning.

## [!UICONTROL SFTP]-moduler och deras fält

När du konfigurerar [!UICONTROL SFTP] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!UICONTROL SFTP] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Utlösare

* [Bevakade filer i en mapp](#watch-files-in-a-folder)
* [Bevaka undermappar i en mapp](#watch-subfolders-in-a-folder)

#### [!UICONTROL Watch Files in a Folder]

Returnerar filer med information när en fil skapas eller ändras i en angiven mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange den mapp som du vill bevaka. Du kan ange en absolut sökväg, till exempel <code>/home/user/</code>, eller ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>Buffertstorlek [B]</td> 
   <td> <p> Ange buffertstorleken i byte. Värdet definierar storleken på överförda segment från servern. Vissa servrar kan orsaka problem eller skadade filer när värdet är för högt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Subfolders in a Folder]

Returnerar mappar med information när en mapp skapas eller ändras i en angiven mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange eller mappa mappen som du vill bevaka. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [Skapa en mapp](#create-a-folderr)
* [Ta bort en fil](#delete-a-file)
* [Ta bort en mapp](#delete-a-folder)
* [Hämta en fil](#get-a-file)
* [Hämta filer](#get-files)
* [Visa innehållet i en mapp](#list-a-folders-content)
* [Flytta en fil](#move-a-file)
* [Byta namn på en fil](#rename-a-file)
* [Uppdatera filbehörigheter](#update-file-permissions)
* [Överföra en fil](#upload-a-file)

#### [!UICONTROL Create a folder]

Skapar en ny mapp på den angivna platsen.

>[!NOTE]
>
>Om mappen redan finns genereras ett fel. Om du vill fortsätta flödet utan avbrott kopplar du en felhanterarväg till modulen för att fånga upp felet och använder direktivet [!UICONTROL Resume] för att fortsätta flödet. Mer information om hur du kopplar en felhanterarväg finns i [Felhantering i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md). Mer information om felhanterarvägen finns i [Direktiv om felhantering i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange en befintlig mapp som lagringsplats för den nya mappen. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name]</td> 
   <td> <p> Ange mappnamnet.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Ange önskade mappbehörigheter. Använd chmod-parametrar. Till exempel <code>777</code> eller <code>-rwxrwxrwx</code>.</p> <p>Dessa behörigheter måste matcha mönstret <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Mer information om chmod finns i <a href="https://ss64.com/bash/chmod.html">chmod-dokumentationen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a file]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Ange sökvägen till filen som du vill ta bort. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./file.txt</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a folder]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Folder Path]</td> 
   <td> <p> Ange sökvägen till mappen som du vill ta bort. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

Den här modulen hämtar filinformation, inklusive fildata.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> Ange buffertstorleken i byte. Värdet definierar storleken på överförda segment från servern. Vissa servrar kan orsaka problem eller skadade filer när värdet är för högt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path] </td> 
   <td> <p>Ange sökvägen till filen. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./file.txt</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get files]

Denna modul returnerar filer från en angiven mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> Ange buffertstorleken i byte. Värdet definierar storleken på överförda segment från servern. Vissa servrar kan orsaka problem eller skadade filer när värdet är för högt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange eller mappa den mapp som innehåller de filer eller mappar som du vill visa. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Ange eller mappa söktermen. Om du till exempel vill söka efter filer med filtillägget .txt anger du <code>.txt</code>. Du kan också ange eller mappa namnet på filen som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> Välj om du vill sortera resultaten efter filnamn, storlek, senaste åtkomstdatum eller senaste ändringsdatum.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order]</td> 
   <td> <p> Välj om resultatet ska returneras i stigande eller fallande ordning.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>Aktivera det här alternativet för att se till att den här modulen inte stoppar scenariot om den inte returnerar några resultat.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List a folder's content]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>Välj om du vill hämta filer, mappar eller både och.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange eller mappa den mapp som innehåller de filer eller mappar som du vill visa. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>Ange eller mappa söktermen. Om du till exempel vill söka efter filer med filtillägget .txt anger du <code>.txt</code>. Du kan också ange eller mappa namnet på filen som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> Välj om du vill sortera resultaten efter filnamn, storlek, senaste åtkomstdatum eller senaste ändringsdatum.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order] </td> 
   <td> <p>Välj om resultatet ska returneras i stigande eller fallande ordning.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>Aktivera det här alternativet för att se till att den här modulen inte stoppar scenariot om den inte returnerar några resultat.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Ange sökvägen till filen som du vill flytta. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New Folder]</td> 
   <td> <p> Ange sökvägen till filens nya plats. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File]

Byter namn på en fil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Ange sökvägen till filen som du vill byta namn på. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New file name]</td> 
   <td> <p> Ange det nya namnet för filen, inklusive filtillägget.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update file permissions]

Gör att du kan ändra behörigheter för filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> Ange sökvägen till filen som du vill flytta. Du kan ange en absolut sökväg som <code>/home/user/file.txt</code>. Du kan också ange en relativ sökväg som pekar på en viss mapp för den inloggade användaren, till exempel <code>./file.txt</code>.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Ange önskade filbehörigheter. Använd chmod-parametrar. Till exempel <code>777</code> eller <code>-rwxrwxrwx</code>.</p> <p>Dessa behörigheter måste matcha mönstret <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Mer information om chmod finns i <a href="https://ss64.com/bash/chmod.html">chmod-dokumentationen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

Med den här modulen kan du överföra en fil till SFTP-servern.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>Instruktioner om hur du ansluter ditt SFTP-konto till [!DNL Workfront Fusion] finns i <a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">Ansluta SFTP till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Ange en befintlig mapp som lagringsplats för filen. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source File]</td> 
   <td> <p> Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Ange önskade behörigheter för filen eller mappen. Använd chmod-parametrar. Till exempel <code>777</code> eller <code>-rwxrwxrwx</code>.</p> <p>Dessa behörigheter måste matcha mönstret <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Mer information om chmod finns i <a href="https://ss64.com/bash/chmod.html">chmod-dokumentationen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
