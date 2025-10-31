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
source-git-commit: f7c1d5b1de74cc0c59e3a00938bed14b489500db
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---

# Lägga till användare i Adobe Workfront Fusion via Adobe Admin Console

Du kan lägga till en användare i [!DNL Adobe Admin Console] och tilldela dem till Adobe Workfront Fusion, eller tilldela en befintlig användare i [!DNL Adobe Admin Console] till Workfront Fusion.

En demonstrationsvideo om hur du beskriver Workfront Fusion i [!DNL Adobe Admin Console], inklusive hur du lägger till användare, finns i [[!DNL Fusion]  på Adobe IMS ](https://video.tv.adobe.com/v/3412464/){target=_blank}.

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
     <p>Du måste vara Workfront Fusion-administratör för ditt team.</p>
   </td> 
  </tr> 
  </tr>
   <tr> 
   <td role="rowheader">Konfigurationer på åtkomstnivå</td> 
   <td>Du måste vara produktkonfigurationsadministratör för Adobe-produkter för din organisation.</td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

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
