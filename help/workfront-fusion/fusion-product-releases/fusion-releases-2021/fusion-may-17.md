---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Versionsaktivitet för Workfront Fusion: 17 maj 2021'
description: Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 17 maj 2021.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 2ea57c69-8db7-4500-9157-e2c2d8c74938
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Versionsaktivitet för Workfront Fusion: 17 maj 2021

Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 17 maj 2021.

En lista med alla senaste ändringar finns i [Adobe Workfront Fusion-versionsaktivitet](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

En lista med de senaste felkorrigeringarna i Workfront Fusion finns på sidan [Workfront Maintenance Updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=sv-SE) och sök efter uppdateringar med namnet Workfront Fusion Maintenance Update.

## Kopiera moduler i Workfront Fusion-scenarier

För att göra dina Workfront Fusion-scenarier enklare att arbeta med har vi gjort det möjligt att kopiera och klistra in moduler. Nu kan du kopiera en modul eller en grupp moduler och klistra in dem i samma eller ett annat scenario. När du kopierar moduler bevaras fältvärdena i den modulen.


## Markera flera moduler i ett Workfront Fusion-scenario

När du redigerar ett scenario kan du nu markera flera moduler i taget. Du kan sedan utföra gruppåtgärder på de valda modulerna.

* Kopiera
* Flytta
* Ta bort

När du kopierar och flyttar moduler behålls modulvärdena och alla linjer som ansluter modulerna.


## Modulerna bevarar nu information som inte har sparats

För att göra det enklare att skapa scenarier har vi gjort det möjligt för moduler att bevara fältvärden när de inte är i fokus. När du klickar bort från en modul utan att spara den och sedan återgår till den visar fälten de värden som du tidigare angett. När modulen stängs visas en indikator på att det finns osparade fält.

## Azure AD Connector hanterar nu nya och uppdaterade poster separat

Nya poster och uppdateringar av befintliga poster hanteras nu av separata moduler.

* Du kan använda utlösarmodulen Bevakade poster för att bevaka nya poster. Den här modulen söker inte längre efter uppdaterade poster.
* Om du vill hämta uppdaterade poster kan du använda den nya modulen Sök användare/grupper (delta). Denna modul returnerar nya, uppdaterade och borttagna poster.
