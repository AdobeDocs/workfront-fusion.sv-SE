---
title: GitHub-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder GitHub samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: d9e6c26c-8770-40bc-a83a-8c05f86e4a3f
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1627'
ht-degree: 0%

---

# [!DNL GitHub] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!UICONTROL GitHub] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Om du vill använda [!DNL GitHub] moduler måste du ha ett [!DNL GitHub]-konto.

## Anslut [!DNL GitHub] till Workfront Fusion

Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## [!DNL GitHub]-moduler och deras fält.

När du konfigurerar [!DNL GitHub]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL GitHub] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)

### Utlösare

* [[!UICONTROL Watch Comments]](#watch-comments)
* [[!UICONTROL Watch Forks]](#watch-forks)
* [[!UICONTROL Watch Issues]](#watch-issues)
* [[!UICONTROL Watch Pull Requests]](#watch-pull-requests)
* [[!UICONTROL Watch Repositories]](#watch-repositories)

#### [!UICONTROL Watch Comments]

Den här utlösarmodulen startar ett scenario när en ny kommentar läggs till eller en befintlig kommentar ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue number]</td> 
   <td>Om du vill begränsa sökningen genom att bara söka efter nya kommentarer som har gjorts i en viss fråga anger du numret.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Ange det maximala antalet kommentarer som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Välj om du bara vill bevaka för nya kommentarer, eller för kommentarer och alla ändringar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Forks]

Den här utlösarmodulen startar ett scenario när en ny förgrening skapas.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som du vill bevaka för gafflar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned forks]</td> 
    <td>Ange eller mappa det maximala antal gafflar som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Issues]

Den här utlösarmodulen startar ett scenario när en ny utgåva läggs till eller när en befintlig utgåva ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to watch]</td> 
   <td>Välj om du vill bevaka alla databaser som är associerade med det här kontot eller bara en databas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Om du har valt att endast bevaka problem i en databas väljer du den databas som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Ange det maximala antalet problem som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Välj om du endast vill bevaka nya utgåvor, eller nya utgåvor och alla ändringar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Du kan filtrera de problem som du vill bevaka efter hur du är kopplad till dem.</p> 
    <ul> 
     <li>[!UICONTROL All issues]</li> 
     <li>[!UICONTROL Only issues assigned to me]</li> 
     <li>[!UICONTROL Only issues created by me]</li> 
     <li>[!UICONTROL Only issues mentioning me]</li> 
     <li>[!UICONTROL Only issues I'm subscribed to updates for]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Välj om du bara vill titta på öppna utgåvor eller endast stängda utgåvor. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>För varje tagg som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger taggen. Modulen söker efter problem med de här taggarna.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Pull Requests]

Den här modulen utlöses när en ny pull-begäran läggs till eller en befintlig pull-begäran ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned pull requests]</td> 
   <td> <p> Ange det maximala antalet pull-begäranden som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Välj om du vill bevaka [!UICONTROL only open pull] förfrågningar, [!UICONTROL only closed ones] eller alla pull-förfrågningar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Välj om du endast vill bevaka nya pull-begäranden eller nya pull-begäranden och alla ändringar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Repositories]

Den här utlösarmodulen startar ett scenario när en databas skapas eller ändras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned repositories]</td> 
   <td> <p> Ange det maximala antalet databaser som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch]</td> 
   <td>Välj om du vill bevaka om det finns nya databaser och alla ändringar, eller endast nya databaser.</td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add assignees]](#add-assignees)
* [[!UICONTROL Add labels to an issue]](#add-labels-to-an-issue)
* [[!UICONTROL Create a comment]](#create-a-comment)
* [[!UICONTROL Create an issue]](#create-an-issue)
* [[!UICONTROL Get an issue]](#get-an-issue)
* [[!UICONTROL List comments]](#list-comments)
* [[!UICONTROL Remove a label from an issue]](#remove-a-label-from-an-issue)
* [[!UICONTROL Remove assignees]](#remove-assignees)
* [[!UICONTROL Search for an issue]](#search-for-an-issue)
* [[!UICONTROL Update an issue]](#update-an-issue)

#### [!UICONTROL Add assignees]

Den här modulen lägger till tilldelningar till det angivna problemet

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller problemet som du vill lägga till tilldelningar i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Välj de personer som du vill tilldela till utgåvan. De tillgängliga uppdragen är alla som har skrivbehörighet till databasen och organisationsmedlemmar med läsbehörighet till databasen. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på utgåvan som du vill lägga till tilldelningar till. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add labels to an issue]

Den här modulen lägger till etiketter i en utgåva. Etiketter definieras på databasnivå och kan bara skapas av någon som har skrivåtkomst till databasen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller utgåvan som du vill lägga till etiketter i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Markera etiketterna som du vill lägga till i utgåvan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på utgåvan som du vill lägga till etiketter till.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a comment]

Den här modulen skapar en kommentar om det angivna problemet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller det problem som du vill skapa en kommentar för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på det ärende som du vill skapa en kommentar för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa innehållet i kommentaren.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an issue]

Den här modulen skapar ett nytt problem i den valda databasen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas där du vill skapa en utgåva.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Välj de personer som du vill tilldela till utgåvan. De tillgängliga uppdragen är alla som har skrivbehörighet till databasen och organisationsmedlemmar med läsbehörighet till databasen. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>Välj den milstolpe som du vill associera med den nya utgåvan. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Markera de etiketter som du vill använda för den nya utgåvan. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Ange eller mappa en titel för den nya utgåvan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa problemets innehåll, till exempel en beskrivning eller ytterligare information</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an issue]

Den här modulen hämtar information om det angivna problemet

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller problemet som du vill hämta information om.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på det problem som du vill hämta information om. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List comments]

I den här modulen visas alla kommentarer om det angivna problemet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller det problem som du vill visa kommentarer från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på det problem som du vill visa kommentarer från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since]</td> 
   <td>Modulen returnerar kommentarer som skapats efter detta datum. En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td> 
   <td> <p> Ange det maximala antalet kommentarer som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove a label from an issue]

Den här modulen tar bort en enstaka etikett från ett problem.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller problemet som du vill ta bort en etikett från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Markera den etikett du vill ta bort från utgåvan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på det problem du vill ta bort en etikett från.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assignees]

Den här modulen tar bort tilldelningar från det angivna problemet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som innehåller det problem som du vill ta bort tilldelningar från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Markera de personer som du vill ta bort från utgåvan. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på utgåvan som du vill ta bort tilldelningar från. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search for an issue]

Den här modulen söker efter problem som matchar sökvillkoren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned issues]</td> 
   <td> <p> Ange det maximala antalet problem som Workfront Fusion returnerar under en cykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Välj hur du vill sortera sökresultaten.</p> 
    <ul> 
     <li> <p>[!UICONTROL Best match] </p> </li> 
     <li>[!UICONTROL Date created]</li> 
     <li>[!UICONTROL Date updated]</li> 
     <li>[!UICONTROL Number of comments]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort direction]</td> 
   <td> <p>Välj stigande eller fallande. </p> <p>Om du väljer <strong>[!UICONTROL descending]</strong> för datum returneras det senaste datumet först. </p> <p>Om du väljer [!UICONTROL number of comments] för <strong>[!UICONTROL descending]</strong> returneras problemet med det högsta antalet kommentarer först.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>Ange eller mappa sökfrågan. En detaljerad beskrivning av sökalternativen finns i <a href="https://docs.github.com/en/github/searching-for-information-on-github/searching-issues-and-pull-requests">Söka efter problem och dra in-begäranden</a> på hjälpwebbplatsen för [!DNL GitHub].</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an issue]

Den här modulen uppdaterar ett befintligt [!DNL GitHub]-problem.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL GitHub]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Repository]</td> 
   <td>Välj den databas som du vill uppdatera ett problem i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assignee]</td> 
   <td>Välj de personer som du vill tilldela till utgåvan. De tillgängliga uppdragen är alla som har skrivbehörighet till databasen och organisationsmedlemmar med läsbehörighet till databasen. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Milestone]</td> 
   <td>Välj den milstolpe som du vill associera med utgåvan. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels]</td> 
   <td>Välj de etiketter som du vill använda för utgåvan. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Number]</td> 
   <td>Ange eller mappa numret på det problem du vill uppdatera. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Välj det tillstånd som du vill uppdatera utgåvan till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Ange eller mappa en ny titel för problemet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa en ny text för problemet, till exempel en beskrivning eller ytterligare information</td> 
  </tr> 
 </tbody> 
</table>
