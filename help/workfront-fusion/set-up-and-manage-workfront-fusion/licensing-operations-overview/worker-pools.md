---
title: Arbetsgrupper
description: En arbetarpool är en mängd Workfront Fusion-bearbetningsresurser som är avsedda för en eller flera specifika organisationer. Alla Fusion-åtgärder och -bearbetning utförs inom ramen för en organisations tilldelade arbetspool.
author: Becky
feature: Workfront Fusion
source-git-commit: bb94083eb9f58dc3ae9f94a59288da43317b567b
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Arbetarpooler

En arbetarpool är en mängd Workfront Fusion-bearbetningsresurser som är dedikerade till en viss organisation. Alla Fusion-åtgärder och -bearbetning utförs inom ramen för en organisations tilldelade arbetspool.

Med Worker-pooler kan dina scenarier köras mer effektivt och eliminerar riskerna för att konkurrera med andra organisationer om fusionskapaciteten.

## Översikt över arbetarpool

En arbetarpool är ett sätt att bearbeta scenariokörningar parallellt. Varje arbetarpool är associerad med:

* Ett antal arbetare.
* En körningskö.

När ett scenario körs skickas det till arbetspoolens körningskö. Arbetare i poolen hämtar kontinuerligt uppgifter från körningspoolen och bearbetar dem parallellt.

Om ködjupet för körningen ökar och alla befintliga arbetare används, skalas poolen automatiskt i Workfront Fusion genom att fler arbetare läggs till. Den här skalningen är dynamisk och händelsestyrd, vilket innebär att kapacitet extraherar eller kontrakteras baserat på realtidsbelastningen utan åtgärder från din eller din organisation.

Workfront Fusion-teamet övervakar kontinuerligt poolernas användnings- och skalningsbeteende och kan granska tröskelvärden eller mönster för att säkerställa enhetliga prestanda i takt med att användningen ökar.
