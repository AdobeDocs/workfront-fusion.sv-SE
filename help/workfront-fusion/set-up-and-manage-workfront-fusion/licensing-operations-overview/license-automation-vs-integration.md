---
title: Adobe Workfront Fusion-licenser
description: Adobe Workfront Fusion har två olika licenser som avgör vilken funktionalitet du har tillgång till. Din organisation valde en av dessa licenser när den köpte Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6e2df1a0-c1f9-4833-b1c2-65efb3be9657
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Adobe Workfront Fusion-licenser

Workfront Fusion har två licensieringsmodeller, en ny driftbaserad modell och en äldre anslutningsbaserad modell.

## Driftbaserad licensieringsmodell (ny)

Den nya licensieringsmodellen i Workfront Fusion baseras på antalet operationer som din organisation använder. I den här modellen har alla organisationer tillgång till samma funktioner.

Om din organisation har en Workfront Ultimate-plan ingår din Fusion-instans i din plan och du kan använda ett obegränsat antal Fusion-operationer per månad. Om din organisation har en Workfront Prime- eller Select-plan kan Fusion köpas och priset baseras på antalet åtgärder som utförs under en månad.

Information om vad som räknas som en åtgärd under den nya licensieringsmodellen finns i [Åtgärder](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md).

## Kopplingsbaserad licensieringsmodell (äldre)

I den äldre licensmodellen för Adobe Workfront Fusion erbjuder Fusion två olika licenser som avgör vilken funktionalitet du har tillgång till. Din organisation valde en av dessa licenser när den köpte Workfront Fusion.

* [Workfront Fusion for Work Automation](#workfront-fusion-for-work-automation)
* [Workfront Fusion for Work Automation and Integration](#workfront-fusion-for-work-automation-and-integration)

Kontakta din Workfront Fusion-administratör för att ta reda på vilken typ av Workfront Fusion-licens din organisation har.

### Workfront Fusion for Work Automation

* [Fördelar med Workfront Fusion for Work Automation](#benefits-of-workfront-fusion-for-work-automation)
* [Kopplingar och moduler för Workfront Fusion for Work Automation](#connectors-and-modules-available-for-workfront-fusion-for-work-automation)
* [Exempel på Workfront Fusion for Work Automation](#example-of-workfront-fusion-for-work-automation)

#### Fördelar med Workfront Fusion for Work Automation

Med en Workfront Fusion for Work Automation-licens kan du automatisera dina [!DNL Workfront]-arbetsflöden. Genom att använda Workfront Fusion for Work Automation kan ni skapa scenarier för att automatisera organisationens unika arbetsprocesser.

Fördelarna med att automatisera dina [!DNL Workfront]-processer är bland annat följande:

* Automatisering går snabbare och mindre felbenägen.
* Arbetsflöden som inte kräver några beslut eller som har beslut är baserade på enkel logik, som if/then, är bra kandidater för automatisering.
* Automatisering kan tillgodose specifika behov i arbetsflöden som används av organisationen och som inte behandlas direkt i Workfront.

#### Kopplingar och moduler för Workfront Fusion for Work Automation

Med Workfront Fusion for Work Automation-licensen får du tillgång till följande:

* Adobe Workfront
* Workfront Proof
* Webhooks
* Verktyg och transformatormoduler som:

   * Arkiv
   * CSV
   * Datalager
   * Bild
   * JSON
   * Matematik
   * MIME
   * XML

#### Exempel på Workfront Fusion for Work Automation

I följande exempel visas ett arbetsflöde som:

1. Söker efter en fältändring
1. Hämtar information om objektet som fältet är kopplat till, inklusive vem som objektet är kopplat till
1. Skickar ett meddelande om fältändringen till användaren som objektet är tilldelat till

![Exempel på automatisering](assets/fusion-template-example.png)

### Workfront Fusion for Work Automation and Integration

* [Fördelar med Workfront Fusion for Work Automation and Integration](#benefits-of-workfront-fusion-for-work-automation-and-integration)
* [Kopplingar och moduler för Workfront Fusion for Work Automation and Integration](#connectors-and-modules-available-for-workfront-fusion-for-work-automation-and-integration)
* [Exempel på Workfront Fusion for Work Automation and Integration](#example-of-workfront-fusion-for-work-automation-and-integration)

#### Fördelar med Workfront Fusion for Work Automation and Integration {#benefits-of-workfront-fusion-for-work-automation-and-integration}

En Workfront Fusion for Work Automation and Integration-licens ger dig tillgång till alla funktioner i Workfront Fusion for Work Automation-licensen. Dessutom kan du med den här licensen använda andra program och tjänster i dina scenarier. Du kan till exempel använda Workfront Fusion för att automatisera en process som importerar Jira-biljetter och sedan omvandla dem till uppgifter i Workfront. Du kan också använda HTTP- eller SFTP-anslutningarna för att ansluta till nästan alla webbtjänster, även om Workfront Fusion inte har någon dedikerad anslutning.

Fördelarna med en Workfront Fusion for Work Automation och Integration-licens är bland annat följande:

* Workfront Fusion for Work Automation and Integration innehåller alla fördelar som är förknippade med Workfront Fusion for Work Automation
* Integreringen minskar behovet av att hoppa in i och ut ur olika program när du slutför ett arbetsflöde.
* Automatisering av dataöverföring mellan program är snabbare och mindre felbenägen än manuell överföring av data

#### Kopplingar och moduler för Workfront Fusion for Work Automation and Integration

En lista över tillgängliga dedikerade anslutningar finns i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!IMPORTANT]
>
>Workfront Fusion kan ansluta till nästan alla webbtjänster. Om appen du vill arbeta med inte har någon dedikerad anslutning kan du använda [!UICONTROL HTTP]-, [!UICONTROL SFTP]- eller [!UICONTROL JSON]-anslutningarna för att ansluta direkt till webbtjänsten.

#### Exempel på Workfront Fusion for Work Automation and Integration

I följande exempel visas ett arbetsflöde som:

1. Tittar på ett kalkylblad för nya användare
1. Kontrollerar om användaren finns i [!DNL Workfront]
1. Skapar användaren i [!DNL Workfront] om användaren inte finns
1. Överför användar-ID:t [!DNL Workfront] tillbaka till kalkylbladet.

![Exempel på automatiseringsscenario](assets/fusion-integration-example.png)
