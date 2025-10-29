---
title: Array-funktioner
description: Följande arrayfunktioner är tillgängliga i panelen för mappning av Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 16c3915c-add1-4aab-a0e1-75fc590c42a6
source-git-commit: 9b61a3b18df1f755cc7ccc28889564e4bcb6cda0
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---

# Array-funktioner

## [!UICONTROL join (array; separator)]

Sammanfogar alla objekt i en array till en sträng med den angivna avgränsaren mellan varje objekt.

## [!UICONTROL length (array)]

Returnerar antalet objekt i en array.

## [!UICONTROL keys (object)]

Returnerar en array med egenskaperna för ett givet objekt eller en angiven array.

## [!UICONTROL slice (array; start; [end])]

Returnerar en ny array som endast innehåller markerade objekt.

## [!UICONTROL merge (array1; array2; ...)]

Sammanfogar en eller flera arrayer till en array.

## [!UICONTROL contains (array; value)]

Verifierar om en array innehåller värdet.

## [!UICONTROL remove (array; value1; value2; ...)]

Tar bort värden som anges i parametrarna för en array. Den här funktionen gäller bara för primitiva arrayer med text eller siffror.

## [!UICONTROL add (array; value1; value2; ...)]

Lägger till värden som anges i parametrar till en array och returnerar den arrayen.

## [!UICONTROL map (complex array; key;[key for filtering];[possible values for filtering])]

Returnerar en primitiv array som innehåller värden för en komplex array. Den här funktionen tillåter filtrering av värden. Använd råa variabelnamn för nycklar.

>[!BEGINSHADEBOX]

**Exempel:**

* `map(Emails[];email)`

  Returnerar en primitiv array med e-post

* `map(Emails[];email;label;work)`

  Returnerar en primitiv array med e-postmeddelanden som har en etikett som är lika med arbetet

>[!ENDSHADEBOX]

Mer information finns i [Mappa en array eller ett arrayelement](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md).

## blanda

## [!UICONTROL sort (array; [order]; [key])]

Sorterar värden i en array. Giltiga värden för parametern `order` är:

* `asc`

  (standard) - stigande ordning: 1, 2, 3, ... för typen Number. A, B, C, a, b, c, ... för text

* `desc`

  fallande ordning: ..., 3, 2, 1 för typen Number. ..., c, b, a, C, B, A för typen Text.

* `asc ci`

  skiftlägesokänslig stigande ordning: A, a, B, b, C, c, ... för text.

* `desc ci`

  skiftlägesokänslig fallande ordning: ..., C, c, B, b, A, a för text.

Använd parametern `key` för att komma åt egenskaper i komplexa objekt.

Använd råa variabelnamn för nycklar.

Använd punktnotation om du vill komma åt kapslade egenskaper.

Det första objektet i en array är index 1.

>[!BEGINSHADEBOX]

**Exempel:**

* `sort(Contacts[];name)`

  Sorterar en array med kontakter efter egenskapen &quot;name&quot; i standardstigande ordning

* `sort(Contacts[];desc;name)`

  Sorterar en array med kontakter efter egenskapen &quot;name&quot; i fallande ordning

* `sort(Contacts[];asc ci;name)`

  Sorterar en array med kontakter efter egenskapen &quot;name&quot; i fallokänslig stigande ordning

* `sort(Emails[];sender.name)`

  Sorterar en matris med e-postmeddelanden efter egenskapen &quot;sender.name&quot;

>[!ENDSHADEBOX]

## [!UICONTROL reverse (array)]

Det första elementet i arrayen blir det sista elementet, det andra blir det näst sista och så vidare.

## [!UICONTROL flatten (array)]

Skapar en ny array med alla underarrayelement sammanfogade rekursivt, upp till det angivna djupet.

## [!UICONTROL distinct (array; [key])]

Tar bort dubbletter inuti en array. Använd argumentet [!UICONTROL key] för att komma åt egenskaper i komplexa objekt. Använd punktnotation om du vill komma åt kapslade egenskaper. Det första objektet i en array är index 1.

>[!BEGINSHADEBOX]

**Exempel:** `distinct(Contacts[];name)`

Tar bort dubbletter i en array med kontakter genom att jämföra egenskapen name

>[!ENDSHADEBOX]

## toCollection

* Den här funktionen tar en array som innehåller nyckelvärdepar och konverterar den till en samling. Funktionen har tre argument:

* (array) som innehåller nyckelvärdepar
* (sträng) namnet på fältet som ska användas som nyckel
* (sträng) namnet på fältet som ska användas som värde

>[!BEGINSHADEBOX]

Exempel:

En matris:

```
[{"name":"Bob", "age":22}, {"name":"Tim", "age":23}]
```

och argument

```
{{toCollection(6.array; "name"; "age")}}
```

funktionen returnerar

```
{
    "Bob": 22,
    "Tim": 23
}
```

>[!ENDSHADEBOX]

## toArray

Den här funktionen konverterar en samling till en array med nyckelvärdepar.

>[!BEGINSHADEBOX]

**Exempel:**

Utgående från samlingen

`{ key1: "value1", key2: "value2:}`

Funktionen

`toArray({ key1: "value1", key2: "value2:})`

Returnerar arrayen med nyckelvärdepar

`[{ key1: "value1"}, { key2: "value2"}]`

>[!ENDSHADEBOX]

## [!UICONTROL arrayDifference [array1, array2, mode]]

Returnerar skillnaden mellan två arrayer.

Ange ett av följande värden för parametern `mode`.

* `classic`: Returnerar en ny array som innehåller alla element i `array1` som inte finns i `array2`.

* `symmetric`: Returnerar en array med element som inte är gemensamma för båda arrayerna.

  Funktionen returnerar med andra ord en array som innehåller alla element i `array1` som inte finns i `array2` och alla element i `array2` som inte finns i `array1`.

>[!BEGINSHADEBOX]

**Exempel:**

Följande arrayer:

```
myArray = [1,2,3,4,5]
```

```
yourArray = [3,4,5,6,7]
```

* `arrayDifference [myArray, yourArray, classic]`

  Returnerar `[1,2]`

* `arrayDifference [yourArray, myArray, classic]`

  Returnerar `[6,7]`

* `arrayDifference [myArray, yourArray, symmetric]`

  Returnerar `[1,2,6,7]`

>[!ENDSHADEBOX]

## deDuplicate

## Nyckelord

## emptyarray
