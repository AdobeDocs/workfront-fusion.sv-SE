---
title: Anslutningsöversikt
description: För de flesta program är det nödvändigt att skapa en anslutning genom vilken Adobe Workfront Fusion kan kommunicera med den angivna tredjepartstjänsten enligt inställningarna för det specifika scenariot.
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Anslutningsöversikt

Workfront Fusion kräver en anslutning för de flesta program.  Den använder den här anslutningen för att kommunicera med den angivna tredjepartstjänsten.

Om du till exempel vill skapa ett scenario som hämtar information från Workfront måste du ge Workfront Fusion behörighet att komma åt ditt Workfront-konto.

En anslutning representerar den behörighet och de behörigheter som Fusion använder för att komma åt programmet. Du kan skapa en eller flera anslutningar för varje program som används i dina scenarier, och du kan använda samma anslutning i flera moduler eller scenarier.

De flesta anslutningar används endast för ett enda program. En Workfront-anslutning kan till exempel inte användas i en [!UICONTROL Salesforce]-modul. Vissa [!DNL Adobe]-program kan dela anslutningar. Mer information finns i artiklarna för dessa program, som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

Anslutningarna ägs av team. Alla medlemmar i ett team har tillgång till teamets anslutningar, och användare utanför ett team har inte tillgång till teamets anslutningar.

## Åtkomsträttigheter

För varje anslutning kräver Workfront Fusion endast de åtkomsträttigheter som är nödvändiga för att slutföra ett visst scenario. Om du till exempel skapar ett scenario för att hämta ett dokument från Workfront, frågar Workfront Fusion inte efter tillstånd att skapa ett nytt projekt. Om du senare upptäcker att du behöver skapa ett projekt kan du uppdatera anslutningen eller skapa en ny som kan skapa projekt.

Du kan inte begränsa åtkomsten till vissa uppgifter med alla tjänster. I dessa fall måste Workfront Fusion kräva fullständig behörighet. Mer information om hur du begränsar Workfront Fusion-åtkomsten till ditt konto som är registrerat för dessa tjänster finns i den programspecifika dokumentationen som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).
