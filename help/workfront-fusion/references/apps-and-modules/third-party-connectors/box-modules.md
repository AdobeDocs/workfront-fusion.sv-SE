---
title: Box-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Box samt ansluta det till flera tredjepartsprogram och -tjänster. Övervakar en angiven mapp för att söka efter filändringar, för att ändra och ta bort befintliga filer eller för att överföra nya filer till en mapp.
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 0%

---

# Box-moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Box] samt ansluta det till flera tredjepartsprogram och -tjänster. Övervakar en angiven mapp för att söka efter filändringar, för att ändra och ta bort befintliga filer eller för att överföra nya filer till en mapp.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla Adobe Workfront Workflow-paket och alla Adobe Workfront Automation and Integration-paket</p><p>Workfront Ultimate</p><p>Workfront Prime- och Select-paket med ytterligare köp av Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licenser</td> 
   <td> <p>Standard</p><p>Arbeta eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL Box]-konto för att kunna använda [!DNL Box]-moduler.

## API-information för Box

Box-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Box]-moduler och deras fält

När du konfigurerar [!DNL Box]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Box] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

* [[!UICONTROL New File Event]](#new-file-event)
* [Ny mapphändelse](#new-folder-event)
* [[!UICONTROL Watch Files]](#watch-files)

#### [!UICONTROL New File Event]

Denna snabbutlösarmodul startar ett scenario när en vald åtgärd inträffar för en fil.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj den webkrok som du vill använda för att se utgående meddelanden, eller lägg till en webkrok. </p><p>Om du vill lägga till en webkrok klickar du på <strong>[!UICONTROL Add]</strong> och anger webkrokens namn och anslutning, filen som du vill titta på och de utlösare som du vill titta på.</p> <p> Instruktioner om hur du ansluter ditt [!UICONTROL Box]-konto till [!UICONTROL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Ansluta till en tjänst - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ny mapphändelse

Den här snabbutlösarmodulen startar ett scenario när markeringsåtgärden inträffar i mappen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj den webkrok som du vill använda för att se utgående meddelanden, eller lägg till en webkrok. </p><p>Om du vill lägga till en webkrok klickar du på <strong>[!UICONTROL Add]</strong> och anger webkrokens namn och anslutning, mappen som du vill titta på och utlösarna som du vill titta på.</p> <p> Instruktioner om hur du ansluter ditt [!UICONTROL Box]-konto till [!UICONTROL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Ansluta till en tjänst - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Files]

Den här utlösarmodulen startar ett scenario när en ny fil läggs till eller en befintlig fil uppdateras i en mapp som bevakas.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  <tr> 
   <td role="rowheader">Bevaka i mapp</td> 
   <td> <p>Markera den mapp som du vill bevaka. Ett scenario kan bevaka en enda mapp.</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Titta</td> 
   <td> <p>Välj vilken typ av filer du vill bevaka.</p> 
    <ul> 
     <li> <p><strong>Endast nya filer</strong> </p> <p>Scenariot startar när en ny fil läggs till.</p> </li> 
     <li> <p><strong>Nya filer och alla ändringar</strong> </p> <p>Scenariot startar när en fil läggs till eller när filinnehåll eller ett filattribut (till exempel dess namn) ändras.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Maximalt antal hämtade filer</p> </td> 
   <td> <p>Ange det högsta antal filer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

<!--* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Update a file]](#update-a-file)
* [[!UICONTROL Upload] a file](#upload-a-file)-->
* [Skapa en mapp](#create-a-folder)
* [Hämta en mapp](#get-a-folder)
* [Hämta mappmetadata](#get-folder-metadata)
* [Göra ett API-anrop](#make-an-api-call)
* [Uppdatera mappmetadata](#update-folder-metadata)

<!--#### [!UICONTROL Delete a file] 

This action module deletes a file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to delete.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

This action module downloads a file.

You specify the ID of the file.

>[!NOTE]
>
>This module is useful for providing files to subsequent modules.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to retrieve.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a file] 

This action module updates a file.

You specify the ID of the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to update.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file] 

This action module uploads a file.

You specify the file. You can also provide a new filename for the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Select the folder where you want to upload the file.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If this module is not successful, consider the following:
>
>* The size of the file might exceed the maximum file size limit for your [!DNL Box] plan, or you may have used all of your [!DNL Box] account's storage quota. To get more storage space, delete existing files from [!DNL Box] or upgrade your [!DNL Box] account.
>* [!DNL Box] does not upload more than one files with the same name to a single folder. If the destination folder contains a file with the same name as the file being uploaded, the scenario run terminates with an error. To avoid this, rename the file. If you want to update the file, use the **[!UICONTROL Update a file]** module.-->

#### Skapa en mapp

Den här åtgärdsmodulen skapar en ny tom mapp i den angivna överordnade mappen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td> <p>Ange eller mappa ett namn för den nya mappen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder]</td> 
   <td> <p>Välj den mapp där du vill skapa den nya mappen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder Upload Email Access]</td> 
   <td> <p>När den här parametern har angetts kan användare skicka e-postfiler till den e-postadress som har skapats automatiskt för den här mappen. Medarbetarnas alternativ tillåter endast registrerade e-postmeddelanden för medarbetare.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Synchronization State]</td> 
   <td> <p>Anger om en mapp ska synkroniseras till en användares enhet eller inte. Detta används av Box Sync (upphör) och används inte av Box Drive.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en mapp

Den här åtgärdsmodulen hämtar information om en mapp, inklusive de första 100 posterna i mappen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Markera mappen som du vill hämta information för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta mappmetadata

Den här åtgärdsmodulen hämtar mappmetadata efter mapp-ID.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Välj det omfång som du vill använda för denna metadatahämtning.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Markera mappen som du vill hämta metadata för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Göra ett API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Box API.



<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Bynder]-konto till Workfront Fusion finns i <a href="#connect-bynder-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Bynder] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Ange en relativ sökväg till <code>https://api.box.com</code>. <p>Exempel: <code>/2.0/users/me</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
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

#### Uppdatera mappmetadata

Den här åtgärdsmodulen skapar eller uppdaterar metadata för en mapp.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Välj det omfång som du vill använda för den här metadatauppdateringen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Markera mappen som du vill uppdatera metadata för.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Sökningar

#### Sök efter innehåll

Den här sökmodulen söker efter objekt som är tillgängliga för användaren eller för hela företaget.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Box]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Ange eller mappa strängen som du vill söka efter. Frågan matchas mot objektnamn, beskrivningar, textinnehåll i filer och olika andra fält i de olika objekttyperna.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> <p>Välj om du söker efter innehåll som är associerat med den användare vars inloggningsuppgifter används för anslutningen som används i den här modulen eller om du söker efter innehåll som är associerat med hela företaget.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>Välj om du söker efter filer, mappar eller webblänkar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>Välj om du vill sortera efter relevans eller efter ändringsdatum.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Trash Content]</td> 
   <td> <p>Välj om du vill söka efter innehåll som inte har blivit genomstruket eller innehåll som inte är genomstruket.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder IDs]</td> 
   <td> <p>Om du vill söka i en specifik mapp klickar du på <b>Lägg till objekt</b> för varje mapp som du vill söka i och anger ID:t för mappen. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created From]</td> 
   <td> <p>Om du vill söka efter resurser som skapats i ett visst datumintervall anger du det tidigaste datumet i intervallet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created to]</td> 
   <td> <p>Om du vill söka efter resurser som skapats i ett visst datumintervall anger du det senaste datumet i intervallet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Updated From]</td> 
   <td> <p>Om du vill söka efter resurser som har uppdaterats i ett visst datumintervall anger du det tidigaste datumet i intervallet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Updated to]</td> 
   <td> <p>Om du vill söka efter resurser som har uppdaterats i ett visst datumintervall anger du det senaste datumet i intervallet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>För varje attribut som du vill returnera i modulens svar klickar du på <b>Lägg till objekt</b> och anger fältet.</p><p>Detta kan användas för att begära fält som normalt inte returneras i ett standardsvar. Observera att om du anger den här parametern kommer ingen av standardfälten att returneras i svaret om de inte uttryckligen anges. </p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File Extensions]</td> 
   <td> <p>Om du vill begränsa sökningen till specifika filtillägg anger du en kommaavgränsad lista med filtillägg.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size From]</td> 
   <td> <p>Om du vill söka efter resurser i ett visst storleksintervall anger du den lilla änden av intervallet i byte.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Size To]</td> 
   <td> <p>Om du vill söka efter resurser i ett visst storleksintervall anger du intervallets stora slut i byte.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Owner User ID]</td> 
   <td> <p>Om du vill söka efter resurser som ägs av specifika användare anger du en kommaavgränsad lista med ägar-ID:n.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal resultat som du vill att modulen ska returnera i varje körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>


