---
title: Operationer
description: En åtgärd i Adobe Workfront Fusion är en uppgift som utförs av en modul. För spårningsändamål är en lyckad åtgärd som utförs av en modul en åtgärd.
author: Becky
feature: Workfront Fusion
exl-id: c14e2bb2-1cce-48ff-8bea-acc9829d3cf2
source-git-commit: 3470f7a9658ac4e6214c27f94f5b41821f2f8665
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# Operationer

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

Din organisation kan ha en månatlig driftgräns. Detta baseras på den [!DNL Workfront]-plan som din organisation har köpt. Planen [!UICONTROL Ultimate] [!DNL Workfront] erbjuder ett obegränsat antal åtgärder.

Om din organisation har en månadsgräns meddelas du när din organisation har nått gränsen. Om din organisation överskrider gränsen kontaktar [!DNL Workfront] din organisation för att säkerställa att din plan uppfyller dina behov.

Workfront Fusion skickar ett meddelande när din organisation når följande procentandelar av organisationens månadsgräns:

* 50 %
* 75 %
* 90 %
* 100 %

## Visa antalet åtgärder som har utförts under de senaste 30 dagarna

Du kan se ett diagram som visar hur många åtgärder som har utförts. Dessa diagram är tillgängliga på följande platser:

* **Organisationens kontrollpanel**: Åtgärder som används av hela organisationen
* **Teaminstrumentpanel**: Åtgärder som används av scenarier som ägs av det här teamet
* **Sidan med scenarioinformation**: Åtgärder som används i det här scenariot
