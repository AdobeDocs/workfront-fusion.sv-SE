---
title: Azure DevOps-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder  [!DNL Azure DevOps] samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: c0919a9a-ce99-485c-9627-45353741f6d8
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1564'
ht-degree: 0%

---

# [!DNL Azure DevOps] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Azure DevOps] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

## Förutsättningar

Om du vill använda [!DNL Azure DevOps] moduler måste du ha ett [!DNL Azure] DevOps-konto.

## API-information för [!DNL Azure DevOps]

Azure DevOps-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v5.1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.29.33</td> 
  </tr>
 </tbody> 
</table>

## Anslut [!DNL Azure DevOps] till [!DNL Workfront Fusion] {#connect-azure-devops-to-workfront-fusion}

1. Lägg till en [!DNL Azure DevOps]-modul i ditt scenario.
1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection].
1. Välj **[!DNL Azure DevOps]** i fältet [!UICONTROL Connection Type].

   >[!IMPORTANT]
   >
   >Anslutningstypen [!UICONTROL [!DNL Azure DevOps] (Request All Scopes)] kommer att bli inaktuell inom den närmaste framtiden. Därför rekommenderar vi inte att du använder den.

1. Fyll i följande fält:

   <table style="table-layout:auto">
        <tr>
            <td>[!UICONTROL Connection name]</td>
            <td>Ange ett namn för anslutningen som du skapar.</td>
        </tr>
      <tr>
            <td>[!UICONTROL Organization]</td>
            <td>Ange namnet på den organisation som du skapade ditt [!DNL Azure DevOps]-program under.</td>
        </tr>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att slutföra konfigurationen av anslutningen och fortsätta skapa ditt scenario.

## [!UICONTROL Azure DevOps]-moduler och deras fält

När du konfigurerar [!DNL Azure DevOps] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Azure DevOps] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

#### [!UICONTROL Watch for work items]

Denna snabbutlösarmodul kör ett scenario när en post läggs till, uppdateras eller tas bort i [!UICONTROL Azure DevOps].

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj eller lägg till en webkrok för modulen.</p> <p>Mer information om webhooks i utlösarmoduler finns i <!--<a href="For instructions, see [Instant triggers (webhooks) in Adobe Workfront Fusion](/help/workfront-fusion/).-->" class="MCXref xref"&gt;Direktutlösare (webhooks) i [!DNL Adobe Workfront Fusion]</a>.</p> <p>Mer information om hur du skapar en webkrok finns i <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhooks</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [Skapa en post](#create-a-record)
* [Anpassat API-anrop](#custom-api-call)
* [Hämta en bifogad fil](#download-an-attachment)
* [Länka arbetsobjekt](#link-work-items)
* [Läs post](#read-record)
* [Uppdatera en arbetsuppgift](#update-a-work-item)
* [[!UICONTROL Upload an attachment]](#upload-an-attachment)

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Azure DevOps]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Azure DevOps]-modulerna.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Base URL]</td> 
   <td> <p>Välj eller mappa den bas-URL som du använder för att ansluta till ditt [!DNL Azure DevOps]-konto</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Relative URL]</td> 
   <td> <p>Ange den relativa URL som du vill ansluta till för detta API-anrop.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span><code>{organization}/_apis[/{area}]/{resource}</code> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Markera eller mappa den version av [!DNL Azure DevOps]-API:t som du vill ansluta till för det här API-anropet. Om ingen version är markerad ansluter [!DNL Workfront Fusion] till [!DNL Azure DevOps] API version 5.1.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> </td> 
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

#### [!UICONTROL Create a record]

Den här åtgärdsmodulen skapar ett nytt projekt eller en ny arbetsuppgift.

Modulen matar ut objekt-ID:t för det nya arbetsobjektet eller URL:en och statuskoden för ett nyligen skapat projekt.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill skapa en arbetsuppgift eller ett projekt.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Project]</strong> </p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Name]</strong>:Ange eller mappa ett namn för det nya projektet.</p> </li> 
       <li> <p><strong>[!UICONTROL Description]</strong>:Ange eller mappa en beskrivning för det nya projektet. </p> </li> 
       <li> <p><strong>[!UICONTROL Visibility]</strong>: Välj om du vill att projektet ska vara offentligt eller privat. Användarna måste vara inloggade i organisationen och ha beviljats åtkomst till projektet för att kunna interagera med ett privat projekt. Offentliga projekt är synliga för användare som inte är inloggade på din organisation.</p> </li> 
       <li> <p><strong>[!UICONTROL Version control]</strong>: Välj om du vill att projektet ska använda [!DNL Git] eller [!UICONTROL Team Foundation Version Control (TFCV)] för versionskontroll.</p> </li> 
       <li> <p><strong>[!UICONTROL Work item process]</strong>: Välj den arbetsprocess som du vill använda för projektet. Alternativen är [!UICONTROL Basic], [!UICONTROL Scrum], [!UICONTROL Capability Maturity Model Integration (CMMI)] och [!UICONTROL Agile].</p> <p>Mer information om [!DNL Azure DevOps]-processer finns i <a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&amp;tabs=basic-process">Välj en process</a> i [!DNL Azure DevOps]-dokumentationen.</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong> </p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Project]</strong>: Välj det projekt där du vill skapa arbetsposten.</p> </li> 
       <li> <p><strong>[!UICONTROL Work item type]</strong>: Välj den typ av arbetsuppgift som du vill skapa.</p> </li> 
       <li> <p><strong>[!UICONTROL Other fields]</strong>:I dessa fält anger du det värde som du vill att arbetsposten ska ha för en viss egenskap. Vilka fält som är tillgängliga beror på arbetsobjekttypen.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download an attachment]

Den här åtgärdsmodulen hämtar en bifogad fil.

Modulen returnerar filinnehållet i den bifogade filen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment URL]</td> 
   <td> <p>Ange eller mappa URL:en för den bifogade fil som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Link work items]

Den här åtgärdsmodulen länkar två arbetsobjekt och definierar relationen mellan dem.

Modulen returnerar ID:t för huvudobjektet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>Ange eller mappa ID:t för det huvudsakliga arbetsobjekt som du vill länka ett annat arbetsobjekt till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Linked work item ID]</td> 
   <td>Ange eller mappa ID:t för arbetsuppgiften som du vill länka till huvudarbetsuppgiften.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Link Type]</td> 
   <td> <p>Definiera relationen mellan arbetsobjekten som du vill länka.</p> <p>Mer information finns i <a href="https://docs.microsoft.com/en-us/azure/devops/boards/queries/link-type-reference?view=azure-devops">Referens för länktyp</a> i [!UICONTROL Azure DevOps] -dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>Ange eller mappa texten i en kommentar. Detta är användbart för att förklara länkens resonemang eller avsikt.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read record]

Den här åtgärdsmodulen läser data från en enskild post i [!DNL Azure DevOps].

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill läsa ett projekt eller en arbetsuppgift</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Project]</strong>: Välj det projekt som du vill läsa.</p> </li> 
     <li> <p><strong>[!UICONTROL Work item]</strong>: Välj det projekt som innehåller det arbetsobjekt som du vill läsa och välj sedan arbetsobjekttyp.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Välj den information som du vill inkludera i utdatapaketet för den här modulen. Vilka fält som är tillgängliga beror på arbetsobjekttypen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för den post som du vill läsa.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a work item]

Den här åtgärdsmodulen uppdaterar ett befintligt arbetsobjekt med dess ID.

Modulen returnerar ID:t för det uppdaterade arbetsobjektet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>Välj det projekt som innehåller den arbetsuppgift som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work Item Type]</td> 
   <td> <p>Välj den typ av arbetsuppgift som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other Fields]</td> 
   <td>I vart och ett av dessa fält anger du det värde som du vill att arbetsposten ska ha för en viss egenskap. Vilka fält som är tillgängliga beror på arbetsobjekttypen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td>Ange eller mappa ID:t för den arbetsuppgift som du vill uppdatera.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload an attachment]

Den här åtgärdsmodulen överför en fil och bifogar den till ett arbetsobjekt.

Modulen returnerar den bifogade filens ID och en hämtnings-URL för den bifogade filen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project] </td> 
   <td> <p>Välj det projekt där du vill överföra en bifogad fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item ID]</td> 
   <td> <p>Ange eller mappa ID:t för arbetsuppgiften där du vill överföra en bifogad fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment]</td> 
   <td>Ange texten för en kommentar som du vill lägga till i den överförda bilagan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file] </td> 
   <td>Välj en källfil från en tidigare modul eller ange eller mappa källfilens namn och innehåll.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

#### [!UICONTROL List work items]

Den här åtgärdsmodulen hämtar alla arbetsobjekt av en viss typ i ett [!DNL Azure DevOps]-projekt.

Modulen returnerar ID:t för huvudobjektet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Azure DevOps]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Azure DevOps] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td>Välj det projekt som du vill hämta arbetsobjekt från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Work item type]</td> 
   <td> <p>Välj den typ av arbetsuppgift som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de egenskaper som du vill ska visas i modulens utdata. Vilka fält som är tillgängliga beror på vilken typ av arbetsobjekt du vill hämta. Du måste välja minst en egenskap.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet arbetsobjekt som [!DNL Workfront Fusion] returnerar under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>
