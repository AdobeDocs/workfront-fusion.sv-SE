---
title: MCP-moduler (Model Context Protocol)
description: Med modulen Model Context Protocol (MCP) kan du bearbeta en användarfråga med MCP.
author: Becky
feature: Workfront Fusion
source-git-commit: d8ae176db714d2b9f041b74a62e8276171745c4b
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# MCP-moduler (Model Context Protocol)

MCP (Model Context Protocol) är ett sätt att på ett säkert sätt ansluta AI-språkmodeller till andra program. Du konfigurerar MCP-servrar som tillåter AI-modellen att komma åt programmet. Du kan sedan skicka ett meddelande till AI-modellen och den kan returnera information från programmet.

Du kan till exempel konfigurera en MCP-server så att den ansluter en AI-modell med Gmail. När du skickar meddelandet&quot;Ge mig mina fem sista e-postmeddelanden från Gmail&quot; kan den komma åt din Gmail och returnera e-postmeddelandena.

Med modulen Model Context Protocol (MCP) kan du bearbeta en användarfråga med hjälp av en språkmodell och MCP-servrar.

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

## Modellkontextprotokollmodulen och dess fält

När du konfigurerar MCP-modulen visar [!DNL Adobe Workfront Fusion] fälten som listas nedan. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

### Fråga om processanvändare

Den här åtgärdsmodulen bearbetar en fråga med språkmodellen och de MCP-servrar du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Large language model (LLM) key]</td> 
   <td> <p>Ange eller mappa API-nyckel för den stora språkmodell som du vill använda för den här uppmaningen. </p> <p>För närvarande stöds bara den Antropiska API-nyckeln.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MCP servers]</td> 
   <td> <p>För varje MCP-server som du vill göra tillgänglig för den här uppmaningen klickar du på <b>Lägg till objekt</b> och anger serverns namn och värddator. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter your prompt]</td> 
   <td> <p>Ange eller mappa uppmaningen för den stora språkmodellen. </p> </td> 
  </tr> 
 </tbody> 
</table>
