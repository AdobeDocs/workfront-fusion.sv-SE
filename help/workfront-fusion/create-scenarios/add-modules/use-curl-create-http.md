---
title: Använd cURL för att lägga till en HTTP-modul
description: Du kan klistra in en cURL-begäran i ditt scenario, så skapar Fusion en HTTP-modul som konfigurerats från cURL-begäran.
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Använd cURL för att lägga till en HTTP-modul

Du kan klistra in en cURL-begäran i ditt scenario, så skapar Fusion en HTTP-modul som konfigurerats från cURL-begäran.

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

## Skapa en HTTP-modul från en cURL-begäran


Så här skapar du en HTTP-modul med cURL:

1. Skapa texten i cURL-begäran utanför Fusion, till exempel i en textredigerare.
1. Kopiera cURL-begäran till Urklipp.
1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill skapa modulen.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Högerklicka på ett tomt utrymme i scenarioredigeraren och välj **Klistra in**.

   eller

   Tryck på Ctrl + V (Windows) eller Cmd + V (Mac).


   En HTML-modul skapas.
1. Dra modulen för att ansluta den till ditt scenario.

## Felsökning

Om din cURL inte klistras in i ditt scenario kontrollerar du webbläsarinställningarna för att vara säker på att inklistring från Urklipp är aktiverad.
