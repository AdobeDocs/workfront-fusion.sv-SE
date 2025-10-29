---
title: Dela.io-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Split.io] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 7d738a96-5424-4c30-831f-82e1d4c6f9d2
source-git-commit: 28de0fbe4fd6dfbcdc8ea4032e1aa95ae3e7c556
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 0%

---

# [!DNL Split.io] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Split.io] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

## Förutsättningar

Du måste ha ett [!DNL Split.io]-konto för att kunna använda [!DNL Split.io]-moduler.

## API-information för Split.io

Kopplingen Split.io använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://api.split.io/internal/api</td>
   </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.34.1</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Split.io] till Workfront Fusion  {#connect-split-io-to-workfront-fusion}

Du kan skapa en anslutning till ditt [!DNL Split.io]-konto direkt inifrån en [!DNL Split.io]-modul.

1. Klicka på [!DNL Split.io] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Fyll i följande fält.

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">[!UICONTROL Connection name]</td> 
       <td> <p>Ange ett namn för anslutningen.</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Välj om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">[!UICONTROL API key]</td> 
       <td>Ange din [!DNL Split.io] API-nyckel.<p>Mer information om [!DNL Split.io] API-nycklar finns i <a href="https://help.split.io/hc/en-us/articles/360019916211-API-keys">API-nycklar</a> i [!DNL Split.io]-dokumentationen.</p></td> 
      </tr> 
     </tbody> 
    </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Split.io]-moduler och deras fält

När du konfigurerar [!DNL split.io]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL split.io] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärder](#actions)
* [Sökningar](#searches)

### Åtgärder

* [[!UICONTROL Associate Tags]](#associate-tags)
* [[!UICONTROL Create Split]](#create-split)
* [[!UICONTROL Create Split Definition in Environment]](#create-split-definition-in-environment)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Delete Split]](#delete-split)
* [[!UICONTROL Get Split]](#get-split)
* [[!UICONTROL Get Split Definition in Environment]](#get-split-definition-in-environment)
* [[!UICONTROL Partial Update Split Definition in Environment]](#partial-update-split-definition-in-environment)
* [[!UICONTROL Remove Split Definition from Environment]](#remove-split-definition-from-environment)

#### [!UICONTROL Associate Tags]

Den här åtgärdsmodulen lägger till taggar i det angivna objektet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill lägga till en tagg.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Name]</td> 
   <td>Ange eller mappa namnet på objektet som du vill lägga till taggar i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type]</td> 
   <td> <p>Ange eller mappa den typ av objekt som du vill lägga till taggar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> <p>För varje tagg som du vill lägga till klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar taggen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split]

Den här åtgärdsmodulen skapar en ny delning i organisationen utifrån en trafiktyp.

>[!NOTE]
>
>API:t konfigurerar inte delningen i någon miljö.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill dela.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Traffic Type ID or Name]</td> 
   <td>Markera eller mappa den trafiktyp som du vill använda för att skapa delningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa ett namn för den delning som du vill skapa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Description]</td> 
   <td>Ange eller mappa en [!UICONTROL split]-beskrivning för delningen som du vill skapa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split Definition in Environment]

Den här åtgärdsmodulen konfigurerar en delad definition för en viss miljö.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill skapa en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Markera eller mappa miljön där du vill skapa en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill skapa en definition för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Ange eller mappa eventuella kommentarer som du vill lägga till i delningsdefinitionen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Rules]</td> 
   <td> <p>För varje målregel som du vill lägga till i definitionen klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar sedan regeln. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default rule]</td> 
   <td> <p>Ange eller mappa regeln som du vill att delningen ska använda för trafiken som inte uppfyller specifikationerna för de andra reglerna.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default treatment]</td> 
   <td> <p>Ange eller mappa den behandling som du vill att delningen ska använda om delningen avbryts eller om kunden inte inkluderas i trafikallokeringen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Treatments]</td> 
   <td> <p>För varje behandling som du vill lägga till i definitionen klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar sedan behandlingen och storleken.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL split.io]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL split.io]-modulerna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code>https://api.split.io/internal/api/v2/</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska arbeta med under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Split]

Den här åtgärdsmodulen tar bort en delning från din organisation. Den delade definitionen avkonfigureras automatiskt från alla miljöer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill ta bort delningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split]

Den här åtgärdsmodulen hämtar delningen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller den delning som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split Definition in Environment]

Den här åtgärdsmodulen hämtar en specifik delad definition från den angivna miljön.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller den delningsdefinition som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Markera eller mappa miljön som innehåller den delningsdefinition som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill hämta delningsdefinitionen för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Partial Update Split Definition in Environment]

Den här åtgärdsmodulen uppdaterar en delad definition för en viss miljö.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill uppdatera en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Markera eller mappa miljön där du vill uppdatera en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill uppdatera en definition för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update content]</td> 
   <td> <p>För varje attribut i delningen som du vill uppdatera klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar ändringarna.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Ange eller mappa eventuella kommentarer som du vill lägga till i delningsdefinitionen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Split Definition from Environment]

Den här åtgärdsmodulen avkonfigurerar en delad definition för en viss miljö.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill ta bort en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Markera eller mappa miljön där du vill ta bort en delad definition.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>Ange eller mappa namnet på den delning som du vill ta bort en definition för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>Ange eller mappa eventuella kommentarer som du vill lägga till i delningsdefinitionen.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Associate Tags]

Den här åtgärdsmodulen lägger till taggar i det angivna objektet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan där du vill lägga till en tagg.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Name]</td> 
   <td>Ange eller mappa namnet på objektet som du vill lägga till taggar i,</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type]</td> 
   <td> <p>Ange eller mappa den typ av objekt som du vill lägga till taggar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> <p>För varje tagg som du vill lägga till klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar taggen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL Get Environments]](#get-environments)
* [[!UICONTROL Get Traffic Types]](#get-traffic-types)
* [[!UICONTROL Get Workspaces]](#get-workspaces)
* [[!UICONTROL List Split Definitions in an Environment]](#list-split-definitions-in-an-environment)
* [[!UICONTROL List Splits]](#list-splits)

#### [!UICONTROL Get Environments]

Den här sökmodulen hämtar en lista över miljöer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller de miljöer du vill visa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Traffic Types]

Den här sökmodulen hämtar en lista med trafiktyper.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller de trafiktyper som du vill visa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Workspaces]

Den här sökmodulen hämtar arbetsytorna för en organisation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet arbetsytor som du vill att modulen ska hämta under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Split Definitions in an Environment]

Den här sökmodulen hämtar en lista med delade definitioner i en viss miljö.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller de delade definitioner som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>Markera eller mappa miljön som innehåller de delade definitioner som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet delningsdefinitioner som du vill att modulen ska hämta under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Splits]

Den här sökmodulen hämtar en lista med delningar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Split.io]-konto till Workfront Fusion finns i <a href="#connect-split-io-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Split.io] till [!UICONTROL Workfront Fusion] </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa arbetsytan som innehåller de uppdelningar som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det högsta antal delningar som du vill att modulen ska hämta under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>
