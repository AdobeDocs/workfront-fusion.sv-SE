---
title: Översikt över Fusion-organisationer och -team
description: Adobe Workfront Fusions funktioner för organisation och team gör det möjligt för företag att styra åtkomsten till scenarier och andra funktioner i Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Översikt över [!DNL Adobe Workfront Fusion] organisationer och team

Med funktionerna för organisation och team i [!DNL Adobe Workfront Fusion] kan företag styra åtkomsten till scenarier och andra funktioner i Fusion.

En organisation är Adobe Workfront Fusions största bolag. Din Fusion-organisation kan till exempel representera Fusion-kontot för hela företaget.

Team är mindre grupper inom organisationen och delar Fusion-resurser som scenarier, anslutningar och mallar.

## Organisationer

[!DNL Workfront Fusion] användare tillhör en organisation.

Användarna måste läggas till i en organisation innan de kan läggas till i ett team.

### Organisationsroller

En användare har en av följande roller i en organisation:

* **[!UICONTROL Owner]**: Ägaren har alla behörigheter som är tillgängliga i organisationen.
* **[!UICONTROL Admin]**: Administratörer kan skapa och hantera team och användare för organisationen och godkänna mallar.
* **[!UICONTROL Member]**: Medlemmar kan använda [!DNL Workfront Fusion] men kan inte göra organisatoriska ändringar.
* **[!UICONTROL Accountant]**: Kontoansvariga kan se licensinformation på kontrollpanelen för organisationen, men kan inte utföra några åtgärder.
* **[!UICONTROL App Developer]**: Funktionerna för den här rollen är inte tillgängliga just nu och kommer att göras tillgängliga inom den närmaste framtiden. Vi rekommenderar för närvarande inte att du tilldelar användare till den här rollen.

Mer information om specifika åtgärder som är tillgängliga för användare i respektive organisationsroll finns i [Organisations- och teamroller](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).

## Team

Team är grupper av användare som delar åtkomst till särskilda resurser. Resurserna kan omfatta:

* Scenarier
* Anslutningar
* Webhooks
* Tangenter
* Datalager
* Datastrukturer
* Inställningar för e-postmeddelanden

>[!NOTE]
>
>Eftersom team delar resurser kan det vara praktiskt att bara ha en medlem. Användare i utbildning kan till exempel skapa anslutningar till sina enskilda [!DNL Workfront]-konton. Alla teammedlemmar kan också ansluta till det enskilda [!DNL Workfront]-kontot. I det här fallet rekommenderar vi att användaren är den enda medlemmen i ett utbildningsteam.

Organisationer kan ha så många team de behöver, och användarna kan tillhöra ett eller flera team.

Användarna kan välja sitt team i listrutan i den vänstra navigeringspanelen. Användare ser bara team som de är medlemmar i. Om du väljer ett team kan användaren komma åt teamets resurser.

### Teamroller

En användare har en av följande roller i varje team:

* **[!UICONTROL Team Admin]**: Administratörer kan lägga till, ta bort eller ändra en teammedlems roll. De kan även utföra alla åtgärder som är tillgängliga för de andra teamrollerna.
* **[!UICONTROL Team Member]**: Teammedlemsrollen tillåter användare att skapa och köra scenarier.
* **[!UICONTROL Team Monitoring]**: Med rollen [!UICONTROL monitoring] kan användare få åtkomst till körningsinformation för scenarier, men de kan inte utforma scenarier eller ändra statusen Aktiv.
* **[!UICONTROL Team Operator]**: Med rollen [!UICONTROL operator] kan användare se körningsdata och ändra statusen Aktiv för scenarier.
* **[!UICONTROL Team Restricted Member]**: Funktionerna för den här rollen är inte tillgängliga just nu och kommer att göras tillgängliga inom den närmaste framtiden. Vi rekommenderar för närvarande inte att du tilldelar användare till den här rollen.

Mer information om specifika åtgärder som är tillgängliga för användare i varje teamroll finns i [Organisations- och teamroller](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md).
