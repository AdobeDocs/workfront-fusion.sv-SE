---
title: Hantera Adobe Workfront Fusion-användare i organisationen
description: Hantera Adobe Workfront Fusion-användare i organisationen
author: Becky
feature: Workfront Fusion
exl-id: 32c221fa-856b-4921-9fa6-5e60f2aa08cd
source-git-commit: 3f9390d8947ef2666336c1a4cc6eab8d174849d5
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Visa eller redigera användarroller

Adobe Workfront Fusion-administratörer kan hantera användarroller inifrån Workfront Fusion.


>[!NOTE]
>
>Om din organisation håller på att övergå till Adobe Admin Console kan du inte hantera användare i Workfront (lägga till eller ta bort användare). Du kan utföra dessa åtgärder i Adobe Admin Console när migreringen är klar.

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
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Visa eller redigera användarroller för en organisation

Adobe Workfront Fusion-administratörer kan visa och uppdatera användarroller för en organisation.

1. När du är inloggad som Workfront Fusion-administratör väljer du **[!UICONTROL All users]** i den vänstra navigeringen.
1. Klicka på **[!UICONTROL Details]** på raden för den användare som du vill visa.
1. (Valfritt) Om du vill uppdatera användarens roll i en organisation klickar du på listrutan i kolumnen **[!DNL Role]** på raden i organisationen där du vill ändra användarens roll och väljer sedan den nya rollen.

### Att tänka på när du lägger till eller ändrar organisationsägare

Din organisation kan ha fler än en ägare.

När du tilldelar en användare till eller från en ägarroll bör du tänka på följande.

* Endast en ägare kan tilldela rollen Ägare eller tilldela en annan roll till en aktuell ägare.
* Endast administratörer kan uppgraderas till Ägare.
* Om det bara finns en ägare går det inte att ändra eller ta bort ägarrollen.
* Om det bara finns en ägare kan den ägaren inte tas bort om det finns andra användare i organisationen.
* När en administratör tilldelas en ägarroll blir de automatiskt administratörer i alla team i organisationen.
* När en ägare tilldelas en annan roll blir den användaren automatiskt en teammedlem i alla team.
* När ett nytt team skapas tilldelas alla ägare automatiskt till teamadministratörer.

## Visa eller redigera användarroller för ett team

Adobe Workfront Fusion-administratörer och teamadministratörer kan visa och uppdatera användarroller.

1. När du är inloggad som Workfront Fusion-administratör väljer du **[!UICONTROL All users]** i den vänstra navigeringen.
1. Klicka på **[!UICONTROL Details]** på raden för den användare som du vill visa.
1. Klicka på Teams-ikonen i kolumnen **[!DNL Role]** på raden i organisationen som innehåller det team där du vill visa eller redigera användarens roll.
1. (Valfritt) Om du vill uppdatera rollen för användaren i ett team klickar du på listrutan i kolumnen **[!DNL Role]** på den rad i teamet där du vill ändra användarens roll och väljer sedan den nya rollen.
