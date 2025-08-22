---
content-type: reference
title: Godkänn eller avslå mallar
description: I den här artikeln beskrivs hur du godkänner eller inte godkänner Fusion-mallar.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: dafecd8b-96e5-46da-9ab6-15f0bc9b52a4
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# Godkänn eller avslå mallar för fliken Offentlig

Adobe Workfront Fusion-mallar är färdiga scenarier som utformats för att automatisera och effektivisera olika arbetsflöden. Mallarna kan hjälpa användarna att snabbt skapa integreringar och automatiseringar utan att behöva bygga allt från scratch.

Om du är administratör kan du välja om vissa mallar ska delas med hela organisationen på fliken Offentliga mallar eller inte.

Användarna kan skicka mallar de skapar för godkännande och sedan dela dem på sidan Offentliga mallar. <!--do the have to be requested or can an admin just choose to approve?-->

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">Adobe Workfront</td>
      <td><p>Alla</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">Adobe Workfront-licens</td>
      <td><p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p></td>
    </tr>
    <tr>
      <td role="rowheader">Adobe Workfront Fusion-licens**</td>
      <td>
        <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
        <p>eller</p>
        <p>Äldre: Alla</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Produkt</td>
      <td>
        <p>Nytt:</p>
        <ul>
          <li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li>
          <li>[!UICONTROL Ultimate] Workfront-plan: Workfront Fusion ingår.</li>
        </ul>
        <p>eller</p>
        <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).-->

+++

## Godkänn eller avslå Workfront Fusion-mallar

Om du godkänner en mall blir den synlig på fliken [!UICONTROL Public templates] och tillgänglig för alla användare.

Om du avvisar en mall tas den bort från fliken [!UICONTROL Public templates] och blir bara tillgänglig för det team som skapade den.

1. Klicka på **[!UICONTROL Administration]** i den vänstra navigeringspanelen för att öppna området [!UICONTROL Administration].
1. Klicka på **[!UICONTROL Templates]** i den vänstra navigeringspanelen.
1. Om du vill godkänna en mall klickar du på **[!UICONTROL Approve]** till höger om mallen.
1. Om du inte vill godkänna en mall klickar du på **[!UICONTROL Disapprove]** till höger om mallen.

>[!NOTE]
>
>Om du godkänner mallen som tidigare godkänts och sedan redigerats, kommer ditt andra godkännande att skriva över den ursprungliga mallen.


## Mallstatus

Du kan kontrollera mallsidans status under mallnamnet.

Följande statusar är tillgängliga:

* **[!UICONTROL Private]**: Den här mallen visas bara för mallskaparen och deras team.
* **[!UICONTROL Published]**: Den här mallen visas bara för mallskaparen och deras team. När mallen har publicerats kan du skicka den för godkännande om du vill. Du kan även kopiera en delbar länk.
* **[!UICONTROL Approved]**: Den här mallen visas för alla Workfront Fusion-användare på fliken [!UICONTROL Public templates]. Du kan också kopiera en delbar länk genom att klicka på [!UICONTROL Options] i skärmens övre högra hörn.

Du kan även kontrollera statusen på fliken [!UICONTROL Team templates]. Om en mall publiceras visas en ikon till höger om mallnamnet.

* **Ögonikon**: Mallen är publicerad, den är bara synlig för gruppen och ingen godkännandebegäran skickades.
* **Gula bockmarkeringsikonen**: Mallen är publicerad, den är bara synlig för teamet och den väntar på godkännande att läggas till på fliken Offentliga mallar.
* **Grön bockmarkeringsikon**: Mallen är tillgänglig på fliken Offentliga mallar och är synlig för alla Workfront Fusion-användare. Den är fortfarande synlig på fliken [!UICONTROL Team templates]. Mallförfattaren eller teammedlemmen kan fortfarande redigera den.

Mallar utan ikoner har statusen [!UICONTROL Private]. De publiceras inte och är bara synliga för teamet.


<!--

## Questions about how this works

Editing

1. If an admin edits a template, do they have to publish again? ... Do they have to approve again?
1. What does publishing actually do?
1. Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
1. What is the admin approving? Does a user have to submit it for approval? 



What does "Publishing" mean?
What does "Approving" mean?
If an admin edits a template, do they have to publish again? ... Do they have to approve again?
Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
What is the admin approving? Does a user have to submit it for approval?

-->
