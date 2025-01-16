---
title: Allmänna funktioner
description: Följande allmänna funktioner är tillgängliga på panelen för mappning av Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 6d4b8801-aa7e-47d4-80b3-aceac10c073f
source-git-commit: 2c732659f3f3e81e13b7b12a5df5bde19c0e0928
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Allmänna funktioner

## [!UICONTROL get (object or array; path)]

Returnerar värdesökvägen för ett objekt eller en array. Använd punktnotation om du vill komma åt kapslade objekt. Det första objektet i en array är index 1.

>[!BEGINSHADEBOX]

**Exempel:**

* `get( array ; 1 + 1 )`
* `get( array ; 5.raw_name )`
* `get( object ; raw_name )`
* `get( object ; raw_name.sub_raw_name )`

>[!ENDSHADEBOX]

## [!UICONTROL if (expression; value1; value2)]

Returnerar `value1` om uttrycket utvärderas till true, annars returneras `value2`.

Om du vill skapa en if-programsats som bara returnerar ett värde om två eller flera uttryck utvärderas till true använder du nyckelordet `and`.

Använd operatorerna `and` och `or` om du vill kombinera `if`-satser.

![och operator](assets/and-in-if-statement.png)

>[!BEGINSHADEBOX]

**Exempel:**

* `if( 1 = 1 ; A ; B )`

  Returnerar A

* `if( 1 = 2 ; A ; B )`

  Returnerar B

* `if( 1 = 2 and 1 = 2 ; A ; B )`

  Returnerar B

>[!ENDSHADEBOX]

## [!UICONTROL ifempty (value1; value2)]

Returnerar `value1` om det här värdet inte är tomt, annars returneras `value2`.

>[!BEGINSHADEBOX]

**Exempel:**

* `ifempty(` `A` `;` `B` )

  Returnerar A

* `ifempty(` `unknown` `;` `B` )

  Returnerar B

* `ifempty(` `""` `;` `B` )

  Returnerar B

>[!ENDSHADEBOX]

## [!UICONTROL switch (expression; value1; result1; [value2; result2; ...]; [else])]

Utvärderar ett värde (kallas uttryck) mot en lista med värden. Returnerar resultatet som motsvarar det första matchande värdet. Om du vill ta med ett `else`-värde lägger du till det efter det sista uttrycket eller värdet.

>[!BEGINSHADEBOX]

**Exempel:**

* `switch( B ; A ; 1 ; B ; 2 ; C ; 3 )`

  Returnerar 2

* `switch( C ; A ; 1 ; B ; 2 ; C ; 3 )`

  Returnerar 3

* `switch( X ; A ; 1 ; B ; 2 ; C ; 3 ; 4 )`

  Returnerar 4

  I den här funktionen är 4 det värde som ska returneras om inga uttryck används (värdet `else`).

>[!ENDSHADEBOX]

## [!UICONTROL omit(object; key1; [key2; ...])]

Utelämnar de angivna tangenterna för objektet och returnerar resten.

>[!BEGINSHADEBOX]

**Exempel:**

`omit(` Användare `;` lösenord `)`

Returnerar en samling med användarens information, exklusive lösenordet.

>[!ENDSHADEBOX]

## [!UICONTROL pick(object; key1; [key2; ...])]

Hämtar endast de angivna nycklarna från objektet.

>[!BEGINSHADEBOX]

**Exempel:**

`pick(` Användare `;` lösenord `;` e-postadress `)`

Returnerar en samling med endast användarens lösenord och e-postadress.

>[!ENDSHADEBOX]

## mergeCollections(collection1; collection2)

Sammanfogar två samlingar genom att kombinera deras nyckelvärdepar. Om båda samlingarna innehåller samma nyckel skrivs värdet från den andra samlingen över från den första samlingen.
