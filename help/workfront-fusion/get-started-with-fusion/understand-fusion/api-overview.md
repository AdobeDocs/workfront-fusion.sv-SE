---
title: API-översikt
description: API:er är ett sätt för program och tjänster att kommunicera med varandra. Fusion använder API:er för att kommunicera med det program du ansluter till. Varje program har ett separat API.
author: Becky
feature: Workfront Fusion
source-git-commit: 1ee32ad1faa8c105142f85e83f1b522548fc7f93
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Översikt över API:er i Fusion

<!--Add me to TOCs-->

API:er är ett sätt för program och tjänster att kommunicera med varandra. Fusion använder API:er för att kommunicera med de program som du ansluter till.

API:er skapas och styrs av programägarna. Workfront API ägs till exempel av Workfront team på Adobe, och Microsoft Graph API ägs av Microsoft. Ägaren till API:t definierar vilka åtgärder som är tillgängliga via API:t.

## Överväganden

Det faktum att API:er definieras av deras ägare och inte av Fusion leder till några viktiga överväganden:

* **Du kan använda Fusion för att ansluta till alla program eller tjänster som har ett offentligt API**, oavsett om Fusion har en dedikerad anslutning till appen eller tjänsten eller inte. Du kan använda Fusions universella anslutningar för att få in dessa appar eller tjänster i dina scenarier.

  En lista över universella anslutningar finns i [Universella anslutningar](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)

* **Ändringar som görs i ett programs API av dess ägare kan påverka Fusion-funktionen.** Om ändringarna är tillräckligt allvarliga kan Fusion behöva uppdatera moduler eller anslutningstyper, eller i extrema fall skapa en ny koppling för programmet.

  Mer information om de här extrema situationerna, som kallas&quot;bryta ändringar&quot;, finns i [Bryta ändringar](#breaking-changes) i den här artikeln.


## Bryta ändringar

En vanlig orsak till att ändringar bryts är borttagning när en API-ägare tar bort delar av eller hela ett API från tillgängligheten. När detta inträffar gör Fusion-teamet allt för att snabbt justera Fusion-funktionerna efter den nya versionen av programmets API. Detta sker vanligtvis i form av nya moduler, anslutningstyper eller kopplingar.

Eftersom dina Fusion-scenarier är konfigurerade med dina specifika data kan du behöva uppdatera dina scenarier.

* Om ändringarna gällde autentisering eller auktorisering kan du behöva uppdatera anslutningarna för det programmet.
* Om ändringarna var relaterade till en viss åtgärd (slutpunkt) i API:t kan du behöva uppdatera moduler som är kopplade till den åtgärden till en ny version av modulen.
* Om hela API-versionen som används av Fusion är inaktuell kan du behöva uppdatera alla moduler i den kopplingen till en ny version av en koppling.

I många fall kan du uppgradera till den nya versionen av en modul utan att behöva konfigurera om den modulen.

Mer information och instruktioner om hur du uppgraderar en modul finns i [Uppgradera en modul till en ny version](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md).
