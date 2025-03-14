---
title: Konfigurera en webkrok för en webbtjänst utan anslutning
description: Om en webbtjänst för närvarande inte har någon dedikerad anslutning i Workfront Fusion, men har stöd för att skicka webhooks, kan du lägga till tjänsten i ett scenario med hjälp av den anpassade webkrokmodulen som en direktutlösare.
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Konfigurera en webkrok för en webbtjänst utan anslutning

Om en webbtjänst för närvarande inte har någon dedikerad anslutning i Workfront Fusion, men har stöd för att skicka webhooks, kan du lägga till tjänsten i ett scenario med hjälp av den anpassade webkrokmodulen som en direktutlösare. Den här processen kallas för att ta emot en webkrok och den kräver en viss konfiguration på sidan av programmet som du ansluter till.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package 
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
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront Plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>Ultimate Workfront Plan: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ta emot en webkrok

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en webkrok.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Lägg till **Webhooks > Anpassad webkrok** för att starta ditt scenario.
1. Klicka på **Lägg till** bredvid Webkrok-fältet.
1. Ange ett **webbkroknamn** i rutan som visas
1. (Valfritt) konfigurera webkroken.

   Instruktioner finns i [Webbhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md).

1. Klicka på **Spara**.

1. Klicka på **Kopiera adress till Urklipp** och sedan på **OK**.

1. Logga in på webbtjänsten och gör följande:

   1. Skapa en webkrok under Inställningar för webbtjänsten.

      Specifika instruktioner beror på programmet. Vi rekommenderar att du söker efter&quot;Skapa en webkrok&quot; i programmets dokumentation.
   1. Klistra in adressen som du kopierade till Urklipp i steg 3.
   1. Välj den händelse som ska utlösa webkroken.

1. Kör scenariot.

   När händelsen eller händelserna inträffar utlöses den anpassade webbkrokmodulen och scenariot körs.
