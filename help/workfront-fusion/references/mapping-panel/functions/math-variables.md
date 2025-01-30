---
title: Matematiska variabler
description: Följande matematiska variabler är tillgängliga på  [!DNL Adobe Workfront Fusion mapping] panelen.
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 0%

---

# Matematiska variabler

## pi

Representerar den matematiska symbolen $\pi$.

## [!UICONTROL random]

Returnerar ett pseudoslumpmässigt flyttal i intervallet [`0`,`1`] (inklusive `0`, men inte `1`).

Använd följande formel för att generera ett pseudoslumpmässigt heltal i intervallet [`min`,`max`] (inklusive både `min` och `max`):

![Slumpmässigt](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```
