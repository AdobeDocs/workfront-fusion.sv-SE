---
title: Publish och gemensamma mallar
description: När du skapar en mall blir mallen tillgänglig för alla dina teammedlemmar. Om du vill dela mallen med någon utanför ditt team måste du först publicera den.
author: Becky
feature: Workfront Fusion
exl-id: 99a1227d-bff9-479f-b8b9-efcf7cea3708
source-git-commit: 7acc27ab2ce80b964b7f9fbb302816aa75964ab5
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Publish och gemensamma mallar

När du skapar en mall blir mallen tillgänglig för alla dina teammedlemmar. Om du vill dela mallen med någon utanför ditt team måste du först publicera den.

Mer information om hur du skapar en mall finns i [Skapa en ny mall](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md).

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

## Förutsättningar

En mall måste skapas innan den kan publiceras eller delas.

## Publish an template

1. Klicka på **[!UICONTROL Templates]** i den vänstra navigeringspanelen.
1. Klicka på fliken **[!UICONTROL Team templates]**.
1. Klicka på **Publish** på mallraden som du vill publicera.

   eller


   Klicka på namnet på mallen som du vill publicera och klicka sedan på knappen **[!UICONTROL Publish]** i skärmens övre högra hörn.

## Dela en [!DNL Workfront Fusion]-mall

När du har publicerat en mall kan du dela den.

1. Klicka på **[!UICONTROL Templates]** i den vänstra navigeringspanelen.
1. Klicka på fliken **[!UICONTROL Team templates]**.
1. Klicka på namnet på mallen som du vill dela för att öppna mallen.
1. Klicka på fliken **Publicerad** för att öppna den versionen av mallen.
1. (Villkorligt) Om du vill ha en delbar länk klickar du på **[!UICONTROL Share public link]**.

   >[!NOTE]
   >
   >Även om du kan dela den här länken finns själva mallen kvar på fliken [!UICONTROL Team templates] och är inte offentlig.

1. (Villkorligt) Om du vill att mallen ska vara offentlig skickar du den till administratören för godkännande genom att klicka på **[!UICONTROL Request Approval]**.

   >[!NOTE]
   >
   >* När mallen har godkänts blir den offentlig. [!UICONTROL Public templates] visas på fliken [!UICONTROL Public templates] för alla [!DNL Workfront Fusion]-användare, oavsett organisation eller team.
   >* Din administratör har inte informerats om att han eller hon får mallen för granskning via e-post. Kontakta administratören direkt om godkännandet är brådskande.


## Mallstatus

Fusion sparar de olika versionerna (privat, publicerad och godkänd) på olika flikar på mallsidan.

Följande statusar är tillgängliga:

* **[!UICONTROL Private]**: Den här mallen visas bara för mallskaparen och deras team.
* **[!UICONTROL Published]**: Den här mallen visas bara för mallskaparen och deras team. Du kan skicka publicerade mallar för godkännande och kopiera en delbar länk.
* **[!UICONTROL Approved]**: Den här mallen visas för alla Workfront Fusion-användare på fliken [!UICONTROL Public templates]. Du kan kopiera en delbar länk genom att klicka på [!UICONTROL Options] i skärmens övre högra hörn.

<!--You can also check the status from the [!UICONTROL Team templates] tab. If a template is published, it will have an icon to the right of the template name.

* **Eye icon**: The template is published, it is visible only for the team, and the approval request was not sent.
* **Yellow checkmark icon**: The template is published, it is visible only for the team, and the approval request was sent.
* **Green checkmark icon**: The template is published and public. It is visible for any Workfront Fusion user in the [!UICONTROL Public templates] tab. It is also still visible in the [!UICONTROL Team templates] tab, and the template author or their team member can still edit it.

Templates without icons have [!UICONTROL Private] status. They are not published and are visible only to the team.
-->
