---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Lägga till användare i Adobe Workfront Fusion via Adobe Admin Console
description: Du kan lägga till en användare i Adobe Admin Console och tilldela dem till Adobe Workfront Fusion, eller tilldela en befintlig användare i Adobe Admin Console till Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 7cb1c1a7-3c7a-459a-818f-d9cefcb9988b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 0%

---

# Lägga till användare i Adobe Workfront Fusion via Adobe Admin Console

Du kan lägga till en användare i [!DNL Adobe Admin Console] och tilldela dem till Adobe Workfront Fusion, eller tilldela en befintlig användare i [!DNL Adobe Admin Console] till Workfront Fusion.

En demonstrationsvideo om hur du beskriver Workfront Fusion i [!DNL Adobe Admin Console], inklusive hur du lägger till användare, finns i [[!DNL Fusion]  på Adobe IMS &#x200B;](https://video.tv.adobe.com/v/3412464/){target=_blank}.



Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront-plan*</td> 
   <td> <p>[!UICONTROL Pro] eller högre</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens*</td> 
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inga Workfront Fusion-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] Adobe Workfront måste din organisation köpa Adobe Workfront Fusion samt Adobe Workfront för att kunna använda de funktioner som beskrivs i den här artikeln. Workfront Fusion ingår i Workfront-planen för [!UICONTROL Ultimate].</p>
   <p>eller</p>
   <p>Krav för äldre produkter: Din organisation måste köpa Adobe Workfront Fusion och Adobe Workfront för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr>
   <tr> 
   <td role="rowheader">[!DNL Adobe] administratörsrättigheter</td> 
   <td>Du måste vara en [!UICONTROL Product Configuration Administrator] av [!DNL Adobe] produkter för din organisation.</td> 
  </tr>
  </tbody> 
</table>

&#42;Kontakta Workfront-administratören om du vill veta vilken plan, licenstyp eller åtkomst du har.

&#42;&#42;Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).



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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
     <p>Du måste vara Workfront Fusion-administratör för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++


## Förutsättningar

Innan du använder [!DNL Admin Console] för Workfront bör du få ett e-postmeddelande med en inbjudan till konsolen.

1. Om du inte har använt [!DNL Adobe] tidigare och du har fått ett e-postmeddelande om att du nu har administratörsbehörighet för att hantera [!DNL Adobe]-programvara och tjänster för din organisation klickar du på knappen i e-postmeddelandet för att skapa ett [!DNL Adobe]-konto och öppna [!DNL Admin Console].

   eller

   Om du redan har ett Adobe-konto går du till [[!DNL Adobe Admin Console] sidan](https://adminconsole.adobe.com).


## Lägg till en ny användare i [!DNL Adobe Admin Console] och Workfront Fusion

1. På [[!DNL Adobe Admin Console] sidan](https://adminconsole.adobe.com/) väljer du fliken **[!UICONTROL Products]** i det övre navigeringsfältet och väljer sedan produktpanelen **Workfront Fusion** .

   ![Fusion i Admin Console](assets/fusion-product-admin-console.png)

1. I listan som visas väljer du den organisation där du vill lägga till en användare.

   ![Fusion-instans i Admin Console](assets/fusion-instances-admin-console.png)

1. Klicka på länken Workfront Fusion **[!UICONTROL Product Profiles]** i den lista som visas med fliken [!UICONTROL Product Profile] markerad.

   >[!IMPORTANT]
   >
   > Gör inga ändringar i själva [!UICONTROL Product Profile].

1. Klicka på **[!UICONTROL Users]** med fliken **[!UICONTROL Add User]** markerad ovanför listan.

1. I rutan **[!UICONTROL Add users to this product profile]** anger du e-postadressen eller namnet på en användare som du vill lägga till och markerar sedan användaren i listan som visas.

1. Klicka på **[!UICONTROL Save]**.

   Användaren skapas i Workfront Fusion.

1. (Valfritt) Fortsätt till [Ändra en användares åtkomstnivå i Workfront Fusion](#change-a-users-access-level-in-workfront-fusion)

## Ändra en användares åtkomstnivå i Workfront Fusion

* [Ändra en användares roll till Admin](#change-a-users-role-to-admin)
* [Ändra en användares roll till Medlem, Kontant eller Apputvecklare](#change-a-users-role-to-member-accountant-or-app-developer)

### Ändra en användares roll till Admin

En användare måste ha en administratörsroll i [!DNL Adobe Admin Console].

1. På sidan Workfront Fusion [!UICONTROL Product Profile] där du lade till användaren väljer du fliken **[!UICONTROL Admins]**.

1. Klicka på **[!UICONTROL Add Admin]**.

1. I rutan **[!UICONTROL Add product profile administrators]** anger du e-postadressen eller namnet på den användare som du vill ska bli administratör och markerar sedan användaren i listan som visas.

1. Klicka på **[!UICONTROL Save]**.

   Användaren är nu administratör i Workfront Fusion.

### Ändra en användares roll till Medlem, Kontant eller Apputvecklare

Medlems-, Accountant- och App Developer-roller hanteras i Workfront Fusion.

Instruktioner finns i [Visa eller redigera användarroller](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md).

## Tilldela en befintlig användare i [!DNL Adobe Admin Console] till Workfront Fusion

Du kan lägga till en befintlig användare i ett team i Fusion. Detta hanteras inuti Fusion.

Instruktioner finns i [Lägga till en användare i ett team](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md).
