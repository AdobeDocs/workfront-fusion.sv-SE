---
title: Matematiska funktioner
description: Följande matematiska funktioner är tillgängliga i panelen för mappning av Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Matematiska funktioner

## [!UICONTROL average ([array of values]) average(value1; [value2], ...)]

Returnerar det genomsnittliga värdet för de numeriska värdena i en viss array, eller det genomsnittliga värdet för numeriska värden som anges individuellt.

## [!UICONTROL ceil (number)]

Returnerar det minsta heltalet som är större än eller lika med ett angivet tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `ceil(` `1.2` `)`

  Returnerar 2

* `ceil(` `4` `)`

  Returnerar 4

>[!ENDSHADEBOX]

## [!UICONTROL floor (number)]

Returnerar det största heltalet mindre än eller lika med ett angivet tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `floor(` `1.2` `)`

  Returnerar 1

* `floor(` `1.9` `)`

  Returnerar 1

* `floor(` `4` `)`

  Returnerar 4

>[!ENDSHADEBOX]

## [!UICONTROL max ([array of values]), max(value1;value2; ...)]

Returnerar det största talet i en angiven array eller det största talet bland tal som anges individuellt.

## [!UICONTROL min ([array of values]), min(value1; value2; ...)]

Returnerar det minsta talet i en angiven array eller det minsta talet bland tal som anges individuellt.

## [!UICONTROL round (number)]

Avrundar ett numeriskt värde till närmaste heltal.

>[!BEGINSHADEBOX]

**Exempel:**

* `round(` `1.2` `)`

  Returnerar 1

* `round(` `1.5` `)`

  Returnerar 2

* `round(` `1.7` `)`

  Returnerar 2

* `round(` `2` `)`

  Returnerar 2

>[!ENDSHADEBOX]

## [!UICONTROL sum ([array of values]), sum(value1; value2; ...)]

Returnerar summan av värdena i en angiven array eller summan av talen som anges individuellt.

## [!UICONTROL parseNumber (number; decimal separator)]

Tolkar en sträng med ett tal och returnerar talet. parseNumber(1 756,456;,)

## [!UICONTROL formatNumber (number; decimalPOINTS; [decimalSeparator]; [thousandsSeparator])]

Returnerar ett tal i begärt format. Som standard är decimalkommat ett komma (,) och tusentalsavgränsaren är en punkt (.).

>[!BEGINSHADEBOX]

**Exempel:**

`formatNumber( 123456789 ; 3 ; , ; . )`

Returnerar 123,456,789,000

>[!ENDSHADEBOX]
