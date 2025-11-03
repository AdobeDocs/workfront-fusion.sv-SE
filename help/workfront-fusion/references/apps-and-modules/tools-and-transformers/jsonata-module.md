---
title: JSONata-moduler
description: Adobe Workfront Fusion JSONata-kontakten innehåller en modul som bearbetar data i JSON-format så att Adobe Workfront Fusion kan arbeta vidare med datainnehållet.
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# [!UICONTROL JSONata] moduler

Med Adobe Workfront Fusion [!UICONTROL JSONata]-kopplingen kan du fråga JSON-objekt. Den här modulen kräver ingen anslutning.

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



## JSONata-moduler och deras fält

### Utvärdera

Den här åtgärdsmodulen frågar efter ett JSON-objekt och returnerar en array.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expression]</td> 
   <td>Ange det uttryck som du vill använda för att utvärdera JSON-objektet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data] </td> 
   <td> Ange det JSON-objekt som ska utvärderas.  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stringify output] </td> 
   <td> Aktivera det här alternativet om du vill konvertera utdata till en sträng.  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**Exempel**:

Målet är att returnera en array med namn från följande JSON-objekt:

```JSON
{
  "people": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 },
    { "name": "Charlie", "age": 35 }
  ]
}
```

1. Ange `people.name` i uttrycksfältet.
1. Ange JSON-objektet i datafältet.

Modulen returnerar en array med namn som hämtats från JSON-objektet.

>[!ENDSHADEBOX]



### JSONata MCP

Den här åtgärdsmodulen genererar JSONata-uttryck genom att analysera de angivna in- och utdatamodellerna. Du anger scheman som används av MCP (Model Context Protocol) för att generera uttrycket som omformar indata till utdata.




<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Markera anslutningen som du använder för att ansluta till den stora språkmodellen (LLM) som du vill använda för den här modulen.</p> <p>För närvarande stöds bara den Antropiska API-nyckeln.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input schema]</td> 
   <td> <p>Ange eller mappa det indatarema som ska användas för det här uttrycket.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output schema]</td> 
   <td> <p>Ange eller mappa det utdatarema som ska användas för det här uttrycket.</p> </td> 
  </tr> 
 </tbody> 
</table>
