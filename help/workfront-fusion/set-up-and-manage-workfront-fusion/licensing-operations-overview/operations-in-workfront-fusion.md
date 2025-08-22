---
title: Användning
description: En åtgärd i Adobe Workfront Fusion är en uppgift som utförs av en modul. För spårningsändamål är en lyckad åtgärd som utförs av en modul en åtgärd.
author: Becky
feature: Workfront Fusion
exl-id: c14e2bb2-1cce-48ff-8bea-acc9829d3cf2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 1%

---

# Användning

En åtgärd i Adobe Workfront Fusion är en uppgift som utförs av en modul. För spårningsändamål är en lyckad åtgärd som utförs av en modul en åtgärd.

## Att tänka på vid inventering av antalet operationer

* I allmänhet betraktas varje lyckad åtgärd som en åtgärd.
* Den första modulen i ett scenario körs bara en gång och räknas alltid som en åtgärd, även om den inte returnerar ett paket.
* Hur många gånger resten av modulerna körs beror på hur många paket de måste behandla.  En serie av en modul för ett paket är en åtgärd. Ett undantag är aggregeringsmodulen, som räknas som en åtgärd per uppsättning paket som bearbetas.
* Åtgärder räknas vid [!UICONTROL Finalization]-steget i en scenariokörning.
* Följande räknas **inte** som åtgärder:
   * Alla filtersteg.
   * Alla åtgärder som innehåller fel eller stopp.
   * Alla vägar som inte körs eftersom ruttens regler inte uppfylls, till exempel återgångsvägar eller inaktiverade rutter.
   * Alla åtgärder som inte körs, antingen på grund av att ett filter inte tillåter data genom eller på grund av att scenariot stoppades på grund av ett fel.

## Operationsbegränsningar

Din organisation kan ha en månatlig driftgräns. Detta baseras på den Workfront-plan som din organisation har köpt. Workfront-planen [!UICONTROL Ultimate] erbjuder ett obegränsat antal åtgärder.

Om din organisation har en månadsgräns meddelas du när din organisation har nått gränsen. Om ni överskrider gränsen kontaktar Workfront er organisation för att säkerställa att er plan uppfyller era behov.

Workfront Fusion skickar ett meddelande när din organisation når följande procentandelar av organisationens månadsgräns:

* 50 %
* 75 %
* 90%
* 100 %

## Visa antalet åtgärder som har utförts under de senaste 30 dagarna

Du kan se ett diagram som visar hur många åtgärder som har utförts. Dessa diagram är tillgängliga på följande platser:

* **Organisationens kontrollpanel**: Åtgärder som används av hela organisationen
* **Teaminstrumentpanel**: Åtgärder som används av scenarier som ägs av det här teamet
* **Sidan med scenarioinformation**: Åtgärder som används i det här scenariot
