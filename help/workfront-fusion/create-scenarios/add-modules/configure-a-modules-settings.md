---
title: Konfigurera en modul
description: Du måste konfigurera inställningar för varje modul som du skapar.
author: Becky
feature: Workfront Fusion
exl-id: ae82d1fe-31e1-424a-9c1a-42dc1a20b749
source-git-commit: 55fe4bc46bc50ad9ccfd1b234e89028cf3cd12d5
workflow-type: tm+mt
source-wordcount: '283'
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

   Mer information om de olika objekttyperna som [!DNL Workfront Fusion] kan identifiera (till exempel datum, nummer och text) finns i [Objektdatatyper](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

   >[!NOTE]
   >
   >Folidparametrar krävs.

1. (Villkorligt) Om modulen har avancerade alternativ som du vill visa och använda väljer du **[!UICONTROL Show advanced settings]**.
