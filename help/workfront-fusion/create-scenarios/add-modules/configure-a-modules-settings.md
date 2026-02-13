---
title: Konfigurera en modul
description: Du måste konfigurera inställningar för varje modul som du skapar.
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Konfigurera en modul

Du måste konfigurera inställningar för varje modul som du skapar.

I modulen Workfront > Överför dokument måste du till exempel ange den post som du vill överföra ett dokument till.

>[!NOTE]
>
>Förutom modulinställningarna kan du även justera inställningarna för ett scenario. Du kan bland annat byta namn på ditt scenario, ändra dess schema och ange ytterligare inställningar.

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

## Konfigurera en moduls inställningar

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till ett filter.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Lägg till en ny modul i ett scenario.

   eller

   Klicka på modulen som du vill konfigurera.

1. Om det behövs för modulen skapar du ett **[!UICONTROL Connection]** till ditt registrerade användarkonto för den aktuella tjänsten, enligt beskrivningen i [Anslutningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).
1. Skriv lämplig text i varje fält.

   eller

   Mappa utdata från en tidigare modul till fältet.

   Mer information om mappning finns i [Mappningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md).

   Mer information om de olika objekttyperna som Workfront Fusion känner igen (till exempel datum, nummer och text) finns i [Objektdatatyper](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

   >[!NOTE]
   >
   >Folidparametrar krävs.

1. (Villkorligt) Om modulen har avancerade alternativ som du vill visa och använda väljer du **[!UICONTROL Show advanced settings]**.
