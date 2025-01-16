---
title: HTTP-begärandemetoder
description: När du konfigurerar ett API-anrop i en modul måste du välja metoden för HTTP-begäran. I den här artikeln beskrivs de tillgängliga metoderna och varför du bör välja var och en av dem.
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# HTTP-begärandemetoder

När du konfigurerar ett API-anrop i en modul måste du välja metoden för HTTP-begäran. I den här artikeln beskrivs de tillgängliga metoderna och varför du bör välja var och en av dem.

## HTTP-metoder

Använd någon av följande HTTP-metoder.

* **[!UICONTROL GET]**: Hämtar data från en webbserver baserat på dina parametrar. [!UICONTROL GET] begär en representation av den angivna resursen och tar emot ett [!UICONTROL 200 OK]-svarsmeddelande med det begärda innehållet om det lyckas.
* **[!UICONTROL POST]**: Skickar data till en webbserver baserat på dina parametrar. [!UICONTROL POST] begäranden innehåller åtgärder som att överföra en fil. Flera [!UICONTROL POST] kan resultera i ett annat resultat än en enskild [!UICONTROL POST], så var försiktig med att oavsiktligt skicka flera [!UICONTROL POST]. Om [!UICONTROL POST] lyckas får du ett [!UICONTROL 200 OK] -svarsmeddelande.
* **[!UICONTROL PUT]**: Skickar data till en plats på webbservern baserat på dina parametrar. [!UICONTROL PUT] begäranden innehåller åtgärder som att överföra en fil. Skillnaden mellan [!UICONTROL PUT] och [!UICONTROL POST] är att PUT är idempotent, vilket innebär att resultatet av en [!UICONTROL PUT] som lyckades är detsamma som många identiska [!UICONTROL PUT]. Om PUT lyckas får du ett svarsmeddelande från 200 (vanligen 201 eller 204).
* **[!UICONTROL PATCH]**: (Inte tillgängligt för vissa API-anropsmoduler) Tillämpar partiella ändringar på en resurs på en webbserver baserat på dina parametrar. [!UICONTROL PATCH] är inte idempotent, vilket innebär att resultatet av flera [!UICONTROL PATCH]-objekt kan få oönskade konsekvenser. Om [!UICONTROL PATCH] lyckas får du ett 200-svarsmeddelande (vanligen 204).
* **[!UICONTROL DELETE]**: Tar bort den angivna resursen från webbservern baserat på dina parametrar (om resursen finns). Om [!UICONTROL DELETE] lyckas får du ett 200 OK-svarsmeddelande.
