---
title: Konfigurera en webkrok för en webbtjänst utan anslutning
description: Om en webbtjänst för närvarande inte har någon dedikerad anslutning i Workfront Fusion, men har stöd för att skicka webhooks, kan du lägga till tjänsten i ett scenario med hjälp av den anpassade webkrokmodulen som en direktutlösare.
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Konfigurera en webkrok för en webbtjänst utan anslutning

Om en webbtjänst för närvarande inte har någon dedikerad anslutning i Workfront Fusion, men har stöd för att skicka webhooks, kan du lägga till tjänsten i ett scenario med hjälp av den anpassade webkrokmodulen som en direktutlösare. Den här processen kallas för att ta emot en webkrok och den kräver en viss konfiguration på sidan av programmet som du ansluter till.

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
