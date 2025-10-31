---
title: Skapa en anslutning - grundläggande instruktioner
description: Många Adobe Workfront Fusion-anslutningar kräver ingen anpassad konfiguration när en anslutning skapas. I den här artikeln beskrivs standardprocessen för att skapa anslutningar.
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Skapa en anslutning - grundläggande instruktioner

Många Adobe Workfront Fusion-anslutningar kräver ingen anpassad konfiguration när en anslutning skapas. I den här artikeln beskrivs standardprocessen för att skapa anslutningar.

>[!NOTE]
>
>
>Om Adobe Workfront Fusion inte innehåller någon app för den webbtjänst som du vill använda i ditt scenario kan du ansluta till webbtjänsten med Workfront Fusion HTTP- och Webhooks-modulerna, vilket förklaras i följande artiklar:
>
>* [Anslut Adobe Workfront Fusion till en webbtjänst som använder API-tokenauktorisering](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [Konfigurera en webkrok för en webbtjänst utan anslutning](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

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
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Om du vill ansluta till program utanför Workfront produktfamilj måste du ha Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Skapa en anslutning

Om du vill skapa en anslutning till ett visst program måste du finnas i en modul för det programmet. Om du till exempel vill skapa en anslutning till Workfront måste du vara i en Workfront-modul.

Så här skapar du en anslutning inuti en Workfront Fusion-modul:

1. Klicka på **[!UICONTROL Add]** bredvid rutan [!UICONTROL Connection] i en modul för det angivna programmet för att öppna panelen **[!UICONTROL Create a connection]**.
1. (Valfritt) Ändra standardvärdet **[!UICONTROL Connection name]**.
1. I fältet Miljö väljer du om detta är en produktionsmiljö eller icke-produktionsmiljö.
1. I fältet Typ väljer du om det här är en tjänst eller ett personligt konto.
1. (Villkorligt) Om programmet kräver avancerade anslutningsinställningar, till exempel ett ID, en nyckel eller [!UICONTROL secret], anger du den informationen.

   Du kan behöva klicka på **[!UICONTROL Show advanced settings]** för att visa fälten där du kan ange den här typen av information.

1. Klicka på **[!UICONTROL Continue]**.
1. I inloggningsfönstret som visas anger du dina inloggningsuppgifter för att logga in på appen om du inte redan har gjort det.
1. (Villkorligt) Om en **[!UICONTROL Allow]**-knapp visas kontrollerar du de åtgärder som anslutningsprogrammet kan vidta och klickar sedan på knappen för att ansluta appen till Workfront Fusion.

   >[!NOTE]
   >
   >* Fälten Miljö och Typ är bara till för information och ändrar inte funktionaliteten för anslutningen. Denna information visas i området Anslutningar i Fusion, där du kan avgöra vilken anslutning som ska användas för ett visst användningsfall i organisationen.
   >* Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
   >
   >   Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.
