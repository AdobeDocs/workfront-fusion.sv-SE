---
title: MCP-moduler (Model Context Protocol)
description: Med modulen Model Context Protocol (MCP) kan du bearbeta en användarfråga med MCP.
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 748055ad-d305-4513-9a5c-9c970b74a96e
source-git-commit: 97abe6bf0ff7b10a139268f02f8a1a24f3e31b47
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# MCP Agent-modul

<!--SET UP REDIRECTS-->

MCP (Model Context Protocol) är ett sätt att på ett säkert sätt ansluta AI-språkmodeller till andra program. Du konfigurerar MCP-servrar som tillåter AI-modellen att komma åt programmet. Du kan sedan skicka ett meddelande till AI-modellen och den kan returnera information från programmet.

Du kan till exempel konfigurera en MCP-server så att den ansluter en AI-modell med Gmail. När du skickar meddelandet&quot;Ge mig mina fem sista e-postmeddelanden från Gmail&quot; kan den komma åt din Gmail och returnera e-postmeddelandena.

Med modulen Model Context Protocol (MCP) kan du bearbeta en användarfråga med hjälp av en språkmodell och MCP-servrar.

Mer information om MCP i Fusion-scenarier finns i [Lägg till en AI-fråga i ditt scenario](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md).

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
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Förutsättningar

* Du måste ha konfigurerat alla MCP-servrar som du vill ansluta till.
* Du måste ha en LLM-nyckel för det valda LLM-formatet (Large Language Model).

## Modellkontextprotokollmodulen och dess fält

### Fråga om processanvändare

Den här åtgärdsmodulen bearbetar en fråga med språkmodellen och de MCP-servrar du anger.

>[!NOTE]
>
>Modulen måste returnera ett objekt. Den returnerar inte utdata som strängar eller tal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>LLM-nyckel</td> 
   <td> Välj en befintlig LLM-nyckel eller skapa en ny genom att klicka på <b>Lägg till</b> och ange följande information: 
     <ul>
       <li><b>Nyckelnamn</b>: Ange ett namn för den nya nyckeln.</li>
       <li><b>LLM</b>: Välj den stora språkmodell som den här nyckeln är associerad med.</li>
       <li><b>Nyckel</b>: Ange eller mappa API-nyckeln för den valda modellen.</li>
       <li><b>Modell</b>: Välj den LLM-modell som nyckeln ska använda.</li>
       <li><b>Max antal token</b>: Ange eller mappa det maximala antalet token som LLM kan generera i sitt svar.<p>En variabel är vanligtvis lika med fyra tecken, eller 0,75 tecken i ett ord på engelska. "Hello world" skulle vara lika med två tokens, och "Authentication" skulle vara lika med två tokens.</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>MCP-servrar</td> 
   <td> <p>För varje MCP-server som du vill ansluta till klickar du på <b>Lägg till</b> och anger följande information: </p> 
     <ul>
       <li><b>Anslutning</b>: Välj den anslutning som Fusion ska använda för att ansluta till MCP-servern.</li>
       <li><b>MCP-servervärd</b>: Ange URL:en för MCP-servern.</li>
       <li><b>MCP-servernamn</b>: Ange eller mappa ett namn för den här MCP-servern.</li>
       <li><b>Huvuden</b>: Lägg till tillämpliga huvuden.</li>
       <li><b>MCP-servertyp</b>: Välj servertyp.</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>Ange din fråga </td> 
   <td> <p>Ange eller mappa den fråga som du vill bearbeta.</p> </td> 
  </tr> 
 </tbody> 
</table>


