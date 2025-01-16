---
title: Anslutningsmetadata
description: Fusion använder metadata för att identifiera viktiga attribut i en anslutning.
author: Becky
feature: Workfront Fusion
exl-id: b41fbe8c-30fa-49d0-8a24-3535642b97ae
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Anslutningsmetadata

Fusion använder metadata för att identifiera viktiga attribut i en anslutning.

Du kan ange anslutningsmetadata när du skapar en ny anslutning. Attributen finns i samma dialogruta som används för att konfigurera en anslutning:

![Anslutningsmetadata](assets/connection-metadata-setup.png)

Fusion-användare kan visa och redigera anslutningar från området Anslutningar.

![Anslutningsmetadata i området Anslutningar](assets/connections-area-metadata.png)

## Miljötyp

Fusion-anslutningar kan användas både i produktionssystem och icke-produktionssystem. Du kan markera vilken typ av miljö som en anslutning kopplas till, vilket bidrar till att skydda produktionsmiljöer.

Miljötypen, liksom andra anslutningsmetadata, används endast i informationssyfte. Användarna ansvarar för att ställa in attributet korrekt och att använda en anslutning till rätt miljö i ett scenario.

## Autentiseringstyp

Fusion-anslutningar kan användas för både tjänstkonton och personliga konton. Tjänstkonton används för autentisering när ett scenario automatiseras som Fusion. Personkonton är autentisering baserat på en viss person. Vilken autentiseringstyp som används beror på scenariots krav. Personkonton bör användas för automatiska användaråtgärder. Om till exempel ett Fusion-scenario automatiserar godkännande av en viss person, ska autentiseringstypen vara för den personen. Annars fungerar Fusion som Fusion och typen ska vara tjänstkonto.

Autentiseringstypen, liksom andra anslutningsmetadata, används endast i informationssyfte. Användare ansvarar för att ställa in det här attributet korrekt och att använda rätt typ av anslutning i ett scenario.

Mer information om autentiseringstyper finns i [Autentisering](https://developer.adobe.com/developer-console/docs/guides/authentication/) i Adobe autentiseringsguide.

## Resurs

* Instruktioner om hur du hanterar anslutningsmetadata finns i [Hantera anslutningar](/help/workfront-fusion/create-scenarios/connect-to-apps/manage-connections.md).
