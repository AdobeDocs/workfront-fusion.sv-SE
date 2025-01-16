---
title: Anslutningsöversikt
description: För de flesta program är det nödvändigt att skapa en anslutning genom vilken  [!DNL Adobe Workfront Fusion] kan kommunicera med den angivna tredjepartstjänsten enligt inställningarna för det specifika scenariot.
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Anslutningsöversikt

Workfront Fusion kräver en anslutning för de flesta program.  Den använder den här anslutningen för att kommunicera med den angivna tredjepartstjänsten.

Om du till exempel vill skapa ett scenario som hämtar information från [!DNL Workfront] måste du ge [!DNL Workfront Fusion] behörighet att komma åt ditt [!DNL Workfront]-konto.

En anslutning representerar den behörighet och de behörigheter som Fusion använder för att komma åt programmet. Du kan skapa en eller flera anslutningar för varje program som används i dina scenarier, och du kan använda samma anslutning i flera moduler eller scenarier.

De flesta anslutningar används endast för ett enda program. En [!DNL Workfront]-anslutning kan till exempel inte användas i en [!UICONTROL Salesforce]-modul. Vissa [!DNL Adobe]-program kan dela anslutningar. Mer information finns i artiklarna för dessa program, som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

Anslutningarna ägs av team. Alla medlemmar i ett team har tillgång till teamets anslutningar, och användare utanför ett team har inte tillgång till teamets anslutningar.

## Åtkomsträttigheter

För varje anslutning kräver [!DNL Workfront Fusion] bara de åtkomsträttigheter som krävs för att slutföra ett visst scenario. Om du t.ex. skapar ett scenario för hämtning av ett dokument från [!DNL Workfront], frågar [!DNL Workfront Fusion] inte efter behörighet att skapa ett nytt projekt. Om du senare upptäcker att du behöver skapa ett projekt kan du uppdatera anslutningen eller skapa en ny som kan skapa projekt.

Du kan inte begränsa åtkomsten till vissa uppgifter med alla tjänster. I dessa fall måste [!DNL Workfront Fusion] kräva fullständig åtkomstbehörighet. Mer information om hur du begränsar [!DNL Workfront Fusion]-åtkomst till ditt konto som är registrerat för dessa tjänster finns i den programspecifika dokumentationen som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
