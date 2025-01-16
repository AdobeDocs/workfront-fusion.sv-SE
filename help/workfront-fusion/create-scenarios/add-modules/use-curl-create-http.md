---
title: Använd cURL för att lägga till en HTTP-modul
description: Du kan klistra in en cURL-begäran i ditt scenario, så skapar Fusion en HTTP-modul som konfigurerats från cURL-begäran.
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: 55fe4bc46bc50ad9ccfd1b234e89028cf3cd12d5
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Använd cURL för att lägga till en HTTP-modul

Du kan klistra in en cURL-begäran i ditt scenario, så skapar Fusion en HTTP-modul som konfigurerats från cURL-begäran.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> <p>Nytt: [!UICONTROL Standard]</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront]: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
