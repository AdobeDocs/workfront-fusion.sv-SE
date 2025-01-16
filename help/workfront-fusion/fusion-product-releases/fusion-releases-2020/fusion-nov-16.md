---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Versionsaktivitet för Workfront Fusion: 16 november 2020'
description: Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 16 november 2020.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 69e4a458-fd32-4dcd-be43-19a9467cf678
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Versionsaktivitet för Workfront Fusion: 16 november 2020

Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion den 16 november 2020.

En lista med alla senaste ändringar finns i [Adobe Workfront Fusion-versionsaktivitet](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

En lista med de senaste felkorrigeringarna i Workfront Fusion finns på sidan [Workfront Maintenance Updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html) och sök efter uppdateringar med namnet Workfront Fusion Maintenance Update.

## Uppdateringar till Jira Cloud-anslutningen

För att utöka de sätt som du kan använda Jira Cloud-anslutningen har vi lagt till tre nya moduler:

* Lägg till utgåva i utskrift
* Listposter
* Sök efter poster

Vi har även uppdaterat befintliga moduler som stöder objekttypen Sprint. Tidigare gick det bara att komma åt Sprint-objektet via modulen för anpassade API-anrop.

## Körnings-ID är nu tillgängligt för mappning i scenarier

Körnings-ID för ett scenario är nu tillgängligt på mappningspanelen. Detta ID representerar en specifik körning av scenariot och kan användas som metadata. Körnings-ID kan till exempel sparas med en post som skapas i Fusion, så att du senare kan avgöra vilken Fusion-körning som posten skapades i. Du hittar det körnings-ID som finns på mappningspanelen under Allmänna funktioner.

## Kortkommandon för Workfront Fusion 2.0-scenarier

Vi har lagt till några kortkommandon för att göra scenarioskapandet enklare:

* Ctrl/Cmd+Skift+Retur: Kör ett scenario en gång
* Ctrl/Cmd + Skift + S: Spara ett scenario

## Uppdateringar till Office 365 Excel-anslutningsprogrammet

Vi har lagt till några nya moduler för att utöka de sätt som du kan använda Office 365 Excel-anslutningen. Nu kan du:

* Utlösa en modul från ändringar till arbetsböcker
* Söka i eller hämta arbetsböcker
* Visa kalkylblad, kalkylbladsrader, tabeller eller tabellrader
* Uppdatera en tabell eller kalkylbladsrad
* Ta bort en tabell eller kalkylbladsrad
* Hämta metadata för en tabell
* Göra ett anpassat API-anrop

Tidigare tillgängliga moduler finns fortfarande i appen.


## Använd OAuth 2.0 i dina Workfront-appanslutningar

Vi har uppdaterat Workfront Connector så att OAuth 2.0 används. Den här uppdateringen innebär att det är enklare att göra ändringar i dina Workfront-appanslutningar. Om till exempel något om din anslutning ändras (till exempel ett lösenord) behöver du inte längre uppdatera varje enskild anslutning i dina scenarier. OAuth2 har dessutom andra fördelar, som förbättrad säkerhet och möjligheten att använda enkel inloggning (SSO).

Befintliga anslutningar kräver för närvarande inga ändringar. Du kan dock återauktorisera befintliga anslutningar om du vill dra nytta av fördelarna med OAuth 2.0.
