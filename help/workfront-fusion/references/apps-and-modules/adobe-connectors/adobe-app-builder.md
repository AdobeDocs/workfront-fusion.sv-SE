---
title: Modulen Adobe App Builder
description: Med Adobe App Builder Connector kan du använda anpassade funktioner i dina scenarier.
author: Becky
feature: Workfront Fusion
source-git-commit: 8250d4fdad8ed7ffe63cd003f6e0cb325cbbfa8d
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Modulen Adobe App Builder

Du kan skapa anpassade funktioner under Funktioner i Fusion. Sedan lägger du till dessa funktioner i dina scenarier i form av en Adobe App Builder-modul.

Eftersom anpassade funktioner fungerar i Adobe App Builder måste ni ha en Adobe App Builder-licens för att använda dem.

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
   <p><ul><li>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li><li>Du måste ha en licens för Adobe App Builder för att kunna använda anpassade funktioner.</ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Modulen Adobe App Builder

Den enda Adobe App Builder-modulen som är tillgänglig för närvarande är Kör en åtgärd som gör att du kan använda en tidigare konfigurerad anpassad JavaScript-funktion.

Instruktioner om hur du konfigurerar en anpassad funktion finns i [Mappa data med anpassade funktioner](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md).

### Utföra en åtgärd

Denna modul kör en tidigare konfigurerad anpassad funktion.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Markera anslutningen som innehåller den anpassade funktion som du vill köra. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>Välj den anpassade funktion som du vill köra.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parameters] </td> 
   <td>Ange värden för funktionsparametrarna. Tillgängliga parametrar baseras på de parametrar som konfigurerades när funktionen skapades.<p>Om en parameter har ett standardvärde visas det inte i fältet, men du kan åsidosätta den genom att ange eller mappa ett värde till fältet.</p></td> 
  </tr> 
   </tbody> 
</table>


