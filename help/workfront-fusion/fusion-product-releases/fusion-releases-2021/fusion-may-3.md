---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Versionsaktivitet för Workfront Fusion: 3 maj 2021'
description: Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 3 maj 2021.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 8858fc79-5eda-4938-9bb5-c05be38f02bc
source-git-commit: bc4c5c047f4847b929c4b047be1897d8872709e9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Versionsaktivitet för Workfront Fusion: 3 maj 2021

Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 3 maj 2021.

En lista med alla senaste ändringar finns i [Adobe Workfront Fusion-versionsaktivitet](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

En lista med de senaste felkorrigeringarna i Workfront Fusion finns på sidan [Workfront Maintenance Updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html) och sök efter uppdateringar med namnet Workfront Fusion Maintenance Update.

## Salesforce Connector kan nu söka med SOQL

I modulen Salesforce > Sök efter poster finns nu ett alternativ för att söka med hjälp av SOQL (Salesforce Object Query Language). Du kan också söka med de tidigare tillgängliga alternativen (SOSL och enkla sökningar).

## Den nya anslutningstypen i Azure DevOps-anslutningen kräver färre omfång

För att förbättra säkerheten har vi lagt till en ny anslutningstyp i Workfront Fusion Azure DevOps Connector. När du nu skapar en anslutning i en Azure DevOps-modul kan du välja mellan två typer av anslutningar:

* Azure DevOps

  Den nya anslutningstypen begränsar omfattningen till de som specifikt behövs av Workfront Fusion.

* Azure DevOps (begär alla scope)

  Det här är den äldre anslutningstypen, som begär alla omfattningar som är tillgängliga i en anslutning till Azure DevOps.

Vi rekommenderar att du använder anslutningstypen Azure DevOps i alla nya scenarier där Azure DevOps används. Vi rekommenderar även att du ändrar några Azure DevOps-moduler i dina befintliga scenarier så att de använder den nya anslutningstypen. Den gamla anslutningstypen Azure DevOps (Request all scopes) kommer inom kort att bli inaktuell.
