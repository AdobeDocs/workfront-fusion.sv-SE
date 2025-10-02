---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: connections-annd-webhooks
title: Hantera anslutningar
description: För de flesta program är det nödvändigt att skapa en anslutning genom vilken Adobe Workfront Fusion kan kommunicera med den angivna tredjepartstjänsten enligt inställningarna för det specifika scenariot.
author: Becky
feature: Workfront Fusion
exl-id: 26d7caad-8e12-4f04-ac7c-f71686c90ee6
source-git-commit: bc1b025af534addf032519142148f6285f481784
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---

# Hantera anslutningar

En anslutning representerar den behörighet och de behörigheter som Fusion använder för att komma åt programmet. Du kan skapa en eller flera anslutningar för varje program och använda samma anslutning i flera moduler eller scenarier.

Du kan hantera de här anslutningarna i området Anslutningar.

Mer information om anslutningar finns i [Anslutningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md).

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

## Visa och hantera anslutningar

Du kan hantera alla anslutningar från området Anslutningar.

>[!NOTE]
>
>Anslutningarna ägs av team. Om du inte kan hitta den anslutning du letar efter kontrollerar du att du visar rätt team.
>
>Om du vill välja ett nytt team klickar du på teamnamnet i den vänstra navigeringen och väljer ett nytt team.

1. Du öppnar området Anslutningar genom att klicka på ikonen **Anslutningar** ![Anslutningar](assets/connections-icon.png) i den vänstra navigeringen.
1. Leta reda på anslutningen som du vill hantera och utför sedan ett eller flera av följande steg på raden för anslutningen.
1. (Valfritt) Tilldela en miljö och anslutningstyp genom att klicka på listrutorna **Miljö** och **Typ** och välja ett alternativ.
1. (Valfritt) Om du vill visa vilka behörigheter som har tilldelats Workfront Fusion för anslutningen klickar du på ikonen Visa ![Visa anslutningsbehörigheter](assets/view-connection-permissions.png) för anslutningen.
1. (Valfritt) Om du vill byta namn på en anslutning markerar du anslutningsnamnet och skriver det nya namnet.
1. (Valfritt) Om du vill återauktorisera en anslutning markerar du kryssrutan bredvid anslutningen och klickar sedan på **Återauktorisera** längst ned på skärmen.
1. (Valfritt) Om du vill ta bort en anslutning markerar du kryssrutan bredvid anslutningen, klickar på **Ta bort** längst ned på skärmen och sedan på **Verkligt?**.
1. (Valfritt) Om du vill verifiera att anslutningen till tjänsten har upprättats markerar du kryssrutan intill anslutningen och klickar sedan på **Verifiera** längst ned på skärmen.
1. (Valfritt) Om du vill visa aktiva scenarier som använder den här anslutningen markerar du kryssrutan intill anslutningen och klickar sedan på **Hämta aktiva scenarier**. Du kan sedan klicka på ett scenario i listan Aktiva scenarier för att gå till det scenariot.

## Förnya en anslutning

Workfront Fusion får vanligtvis åtkomsträttigheter till en viss tjänst under en obegränsad tidsperiod. För vissa program krävs att åtkomstbehörigheten förnyas efter en viss tidsperiod. I dessa fall meddelar Workfront Fusion dig via e-post kort innan åtkomsträttigheterna upphör att gälla.

Så här förnyar du en anslutning:

1. Du öppnar området Anslutningar genom att klicka på ikonen **Anslutningar** ![Anslutningar](assets/connections-icon.png) i den vänstra navigeringen.
1. Leta reda på anslutningen som du vill förnya.
1. Markera kryssrutan bredvid anslutningen på raden för den anslutningen och klicka sedan på **Återauktorisera** längst ned på skärmen.

## Resurser

* Mer information om anslutningsmetadata, till exempel miljö och typ, finns i [Anslutningsmetadata](/help/workfront-fusion/references/connections/connection-metadata.md).
