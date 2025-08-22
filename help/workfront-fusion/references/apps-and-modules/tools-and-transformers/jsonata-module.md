---
title: JSONata-moduler
description: Adobe Workfront Fusion JSONata-kontakten innehåller en modul som bearbetar data i JSON-format så att Adobe Workfront Fusion kan arbeta vidare med datainnehållet.
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# [!UICONTROL JSONata] moduler

Med Adobe Workfront Fusion [!UICONTROL JSONata]-kopplingen kan du fråga JSON-objekt. Den här modulen kräver ingen anslutning.

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
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>[!UICONTROL Ultimate] Workfront: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
