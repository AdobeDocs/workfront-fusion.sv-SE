---
title: SFTP-moduler
description: Med modulerna  [!DNL Adobe Workfront Fusion SFTP] kan du övervaka filändringar i en vald mapp/undermapp, överföra nya filer till önskad mapp, ändra eller ta bort befintliga filer som redan finns i en mapp eller ändra filbehörigheter.
author: Becky
feature: Workfront Fusion
exl-id: bde3cbda-8a19-4d9f-b970-f56d73a1f8dd
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1688'
ht-degree: 0%

---

# SFTP-moduler

Med modulerna [!DNL Adobe Workfront Fusion] SFTP kan du övervaka filändringar i en vald mapp/undermapp, överföra nya filer till önskad mapp, ändra eller ta bort befintliga filer som redan finns i en mapp eller ändra filbehörigheter.

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

Om du vill använda SFTP med [!DNL Workfront Fusion] måste du ha ett SFTP-konto (till exempel [!DNL GoDaddy] webbhosting).

## Anslut SFTP till [!DNL Workfront Fusion] {#connect-sftp-to-workfront-fusion}

Om du vill ansluta ditt SFTP-konto till [!DNL Workfront Fusion] måste du ange målvärden och SFTP-autentiseringsuppgifter (användarnamn och lösenord eller användarnamn och nyckel) för modulens [!UICONTROL Create a connection]-dialogruta.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection name]</td> 
   <td> <p> Ange namnet på SFTP-anslutningen.</p> </td> 
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
 </tbody> 
</table>

När du har angett anslutningsinformationen klickar du på **[!UICONTROL Continue]** för att upprätta en anslutning.

## [!UICONTROL SFTP]-moduler och deras fält

När du konfigurerar [!UICONTROL SFTP] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!UICONTROL SFTP] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Utlösare

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
   <td> <p>Ange eller mappa mappen som du vill bevaka. Du kan ange en absolut sökväg som <code>/home/user/</code>. Du kan också ange en relativ sökväg som pekar mot en viss mapp för den inloggade användaren, till exempel <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>Buffertstorlek [B]</td> 
   <td> <p> Ange buffertstorleken i byte. Värdet definierar storleken på överförda segment från servern. Vissa servrar kan orsaka problem eller skadade filer när värdet är för högt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> Ange maximalt antal filer som [!DNL Workfront Fusion] ska arbeta med under en cykel</p> </td> 
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
   <td> <p> Ange maximalt antal mappar som [!DNL Workfront Fusion] ska returnera under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

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
   <td> <p> Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska returnera under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Files]

Den här modulen visar filer från en angiven mapp.

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
   <td> <p> Ange det maximala antalet filer som [!DNL Workfront Fusion] ska returnera under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a File]

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
   <td> <p> Mappa källfilen från en tidigare modul, till exempel [!UICONTROL Dropbox] &gt; [!UICONTROL Get File]. Du kan också ange eller mappa filnamnet och fildata.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>Ange önskade behörigheter för filen eller mappen. Använd chmod-parametrar. Till exempel: <code>777 </code> eller <code>-rwxrwxrwx</code>.</p> <p>Mer information om chmod finns i <a href="https://ss64.com/bash/chmod.html">chmod-dokumentationen</a>.</p> </td> 
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

#### [!UICONTROL Delete a File]

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
   <td> <p>Ange önskade filbehörigheter. Använd chmod-parametrarna. Till exempel <code>777 </code> eller <code>-rwxrwxrwx</code>.</p> <p>Matcha mönster <code> /(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Mer information om chmod finns i <a href="https://ss64.com/bash/chmod.html">chmod-dokumentationen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Folder]

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
   <td> <p>Ange önskade mappbehörigheter. Använd chmod-parametrar. Till exempel <code>777 </code> eller <code>-rwxrwxrwx</code>.</p> <p>Matcha mönster <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>Mer information om chmod finns på <a href="https://ss64.com/bash/chmod.html">chmod Man Page</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Folder]

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
