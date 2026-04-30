---
title: Redigera webbhotell
description: Du kan redigera befintliga webbböcker för Workfront- och Workfront Planning-anslutningarna.
author: Becky
feature: Workfront Fusion
source-git-commit: 2561c911b9b542a7b143fae745baf4e1de45be38
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Redigera webbhotell

Du kan redigera befintliga webbböcker. Scenarier som använder dessa webhooks använder den nya konfigurationen som går framåt, vilket eliminerar behovet av att skapa en ny webkrok och manuellt tilldela den till alla berörda scenarier.

Webhooks kan bara redigeras för följande anslutningar:

* Workfront
* Workfront Planning

>[!IMPORTANT]
>
>Tänk på följande när du uppdaterar en webkrok:
>
>* Den redigerade webkroken hanteras av Workfront händelseprenumerationer som en ny prenumeration. Händelseprenumerationshistorik bevaras inte för den tidigare webbkrokkonfigurationen, eftersom detta betraktas som en separat händelseprenumeration.
>* Övergången från den gamla till den nya händelseprenumerationen kanske inte är helt synkroniserad. Det är därför möjligt att ta emot en händelse två gånger (om den nya prenumerationen börjar köras innan den gamla stoppas) eller att missa en händelse (om den gamla prenumerationen upphör innan den nya börjar köras).

## Redigera en webkrok

Du kan redigera webbböcker från ett scenario eller från listan Webhooks.

### Redigera en webkrok i ett scenario

>[!NOTE]
>
>Den här funktionen är bara tillgänglig för scenarier som har en Workfront- eller Workfront Planning-utlösarmodul.

1. Gå till scenariot som innehåller den webkrok som du vill redigera.
1. Klicka på listrutan bredvid Webkrok-fältet i scenariots utlösarmodul och välj **Redigera objekt**.

   Webhochens konfigurationsfönster öppnas, ifyllt med den befintliga konfigurationen.

1. Gör de ändringar du vill på webbkroken.
1. Klicka på **Spara** för att spara webkroken och återgå till modulen.

### Redigera en webkrok från listan Webhooks

1. Välj **Webhooks** ![Webhooks-ikon](assets/webhooks-icon.png) i den vänstra navigeringen.
1. Klicka i kryssrutan bredvid den webkrok som du vill redigera.
1. Klicka på **Redigera** i den blå banderollen längst ned på skärmen.
1. Gör de ändringar du vill på webbkroken.
1. Klicka på **Spara** för att spara webkroken och återgå till listan Webhooks.

