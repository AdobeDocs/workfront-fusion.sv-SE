---
title: Datum- och tidsfunktioner
description: Följande datum- och tidsfunktioner är tillgängliga i panelen för mappning av Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 92813dac-4bf0-4681-9b71-7bd2e92a89a4
source-git-commit: 2c732659f3f3e81e13b7b12a5df5bde19c0e0928
workflow-type: tm+mt
source-wordcount: '1773'
ht-degree: 0%

---

# Datum- och tidsfunktioner

## Variabel

### nu

Hämtar aktuell tid i formatet YYYY-MM-DD-hh:mm:ss.

### tidsstämpel

Hämtar den aktuella tiden som en Unix-tidsstämpel.

## Funktioner

### [!UICONTROL addSeconds (date; number)]

Returnerar ett nytt datum som ett resultat av att ett visst antal sekunder har lagts till ett datum. Om du vill subtrahera sekunder anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addSeconds(2016-12-08T15:55:57.536Z;2)`

  Returnerar 2016-12-08T15:55:59.536Z

* `addSeconds(2016-12-08T15:55:57.536Z;-2)`

  Returnerar 2016-12-08T15:55:55.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addMinutes (date; number)] {#addminutes-date-number}

Returnerar ett nytt datum som ett resultat av att ett visst antal minuter har lagts till ett datum. Om du vill subtrahera minuter anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addMinutes(2016-12-08T15:55:57.536Z;2)`

  Returnerar 2016-12-08T15:57:57.536Z

* `addMinutes(2016-12-08T15:55:57.536Z;-2)`

  Returnerar 2016-12-08T15:53:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addHours (date; number)] {#addhours-date-number}

Returnerar ett nytt datum som ett resultat av att ett visst antal timmar har lagts till ett datum. Om du vill subtrahera timmar anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addHours(2016-12-08T15:55:57.536Z; 2)`

  Returnerar 2016-12-08T17:55:57.536Z

* `addHours(2016-12-08T15:55:57.536Z;-2)`

  Returnerar 2016-12-08T13:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addDays (date; number)] {#adddays-date-number}

Returnerar ett nytt datum som ett resultat av att ett visst antal dagar har lagts till ett datum. Om du vill subtrahera dagar anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addDays(2016-12-08T15:55:57.536Z;2)`

  Returnerar 2016-12-10T15:55:57.536Z

* `addDays(2016-12-08T15:55:57.536Z;-2)`

  Returnerar 2016-12-6T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addMonths (date; number)]

Returnerar ett nytt datum som ett resultat av att ett visst antal månader har lagts till ett datum. Om du vill subtrahera månader anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addMonths(2016-08-08T15:55:57.536Z;2)`

  Returnerar 2016-10-08T15:55:57.536Z

* `addMonths(2016-08-08T15:55:57.536Z;-2)`

  Returnerar 2016-06-08T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL addYears (date; number)]

Returnerar ett nytt datum som ett resultat av att ett visst antal år har lagts till ett datum. Om du vill subtrahera år anger du ett negativt tal.

>[!BEGINSHADEBOX]

**Exempel:**

* `addYears(2016-08-08T15:55:57.536Z;2)`

  Returnerar 2018-08-08T15:55:57.536Z

* `addYears(2016-12-08T15:55:57.536Z; -2)`

  Returnerar 2014-08-08T15:55:57.536Z

>[!ENDSHADEBOX]

### [!UICONTROL setSecond (date; number)]

Den här funktionen returnerar ett nytt datum med de sekunder som anges i parametrar.

Ange ett tal mellan 0 och 59. Om talet ligger utanför det intervallet returnerar funktionen en sekund från föregående minut (för ett negativt tal) eller efterföljande minut (för ett positivt tal).

Om du behöver ange ett tal utanför intervallet rekommenderar vi att du använder [!UICONTROL  addSeconds], enligt beskrivningen ovan i avsnittet [addSeconds (date; number)](#addseconds-date-number).

>[!BEGINSHADEBOX]

**Exempel:**

* `setSecond(2015-10-07T11:36:39.138Z;10)`

  Returnerar 2015-10-07T11:36:10.138Z

* `setSecond(2015-10-07T11:36:39.138Z; 6)`

  Returnerar 2015-10-07T11:37:01.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setMinute (date; number)]

Den här funktionen returnerar ett nytt datum med de minuter som anges i parametrarna.

Ange ett tal mellan 0 och 59. Om talet ligger utanför det intervallet returnerar funktionen en minut från föregående timme (för ett negativt tal) eller efterföljande timme (för ett positivt tal).

Om du behöver ange ett tal utanför intervallet rekommenderar vi att du använder addMinutes enligt beskrivningen ovan i [addMinutes (date; number)](#addminutes-date-number).

>[!BEGINSHADEBOX]

**Exempel:**

* `setMinute(2015-10-07T11:36:39.138Z;10)`

  Returnerar 2015-10-07T11:10:39.138Z

* `setMinute(2015-10-07T11:36:39.138Z;61)`

  Returnerar 2015-10-07T12:01:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setHour (date; number)]

Den här funktionen returnerar ett nytt datum med timmen angiven i parametrar.

Ange ett tal mellan 0 och 23. Om talet ligger utanför det här intervallet returnerar funktionen en timme från föregående dag (för ett negativt tal) eller efterföljande dag (för ett positivt tal).

Om du behöver ange ett tal utanför intervallet rekommenderar vi att du använder addHours enligt beskrivningen ovan i [addHours (date; number)](#addhours-date-number).

>[!BEGINSHADEBOX]

**Exempel:**

* `setHour(2015-08-07T11:36:39.138Z;6)`

  Returnerar 2015-08-07T06:36:39.138Z

* `setHour(2015-08-07T11:36:39.138;-6)`

  Returnerar 2015-08-06T18:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDay (date; number/name of the day in English)]

Den här funktionen returnerar ett nytt datum med den dag som anges i parametrar.

Du kan använda den här funktionen för att ange veckodag, med söndag som 1 och lördag som 7. Om du anger ett tal mellan 1 och 7 blir det resulterande datumet inom den aktuella veckan (söndag till lördag). Om talet ligger utanför det intervallet returnerar funktionen en dag från föregående vecka (för ett negativt tal) eller efterföljande vecka (för ett positivt tal).

Om du behöver ange ett tal utanför intervallet rekommenderar vi att du använder addDays enligt beskrivningen ovan i [addDays (date; number)](#adddays-date-number).

>[!BEGINSHADEBOX]

**Exempel:**

* `setDay(2018-06-27T11:36:39.138Z;Monday)`

  Returnerar 2018-06-25T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;1)`

  Returnerar 2018-06-24T11:36:39.138Z

* `setDay(2018-06-27T11:36:39.138Z;7)`

  Returnerar 2018-06-30T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setDate (date; number)]

Den här funktionen returnerar ett nytt datum med den dag i månaden som anges i parametrar.

Ange ett tal mellan 1 och 31. Om talet ligger utanför det här intervallet returnerar funktionen en dag från föregående månad (för ett negativt tal) eller efterföljande månad (för ett positivt tal).

>[!BEGINSHADEBOX]

**Exempel:**

* `setDate(2015-08-07T11:36:39.138Z;5)`

  Returnerar 2015-08-05T11:36:39.138Z

* `setDate(2015-08-07T11:36:39.138Z;32)`

  Returnerar 2015-09-01T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setMonth (date; number/name of the month in English)]

Den här funktionen returnerar ett nytt datum med den månad som anges i parametrar.

Ange ett tal mellan 1 och 12. Om talet ligger utanför det här intervallet returnerar funktionen månaden under föregående år (för ett negativt tal) eller efterföljande år (för ett positivt tal).

>[!BEGINSHADEBOX]

**Exempel:**

* `setMonth(2015-08-07T11:36:39.138Z;5)`

  Returnerar 2015-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;17)`

  Returnerar 2016-05-07T11:36:39.138Z

* `setMonth(2015-08-07T11:36:39.138Z;january)`

  Returnerar 2015-01-07T12:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL setYear (date; number)]

Returnerar ett nytt datum med året angivet i parametrar.

>[!BEGINSHADEBOX]

**Exempel:**

* `setYear(2015-08-07T11:36:39.138Z;2017)`

  Returnerar 2017-08-07T11:36:39.138Z

>[!ENDSHADEBOX]

### [!UICONTROL formatDate (date; format; [timezone])]

Använd den här funktionen när du har ett datumvärde, till exempel `12-10-2021 20:30`, som du vill formatera som ett textvärde, till exempel `Dec 10, 2021 8:30 PM`.

Detta är praktiskt när du till exempel behöver ändra datumformatet för en app eller webbtjänst till datumformatet för en ansluten app eller webbtjänst i samma scenario.

Mer information finns i Datum och text i artikeln [Objektdatatyper](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

#### Parametrar

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Parameter</th> 
   <th>Förväntad datatyp* </th> 
   <th>Vad det gör</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL date] </td> 
   <td>Datum </td> 
   <td> <p>Konverterar ett datumvärde till ett textvärde. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>Text </td> 
   <td> <p>Här kan du ange ett format med hjälp av tokens för datum- och tidsformatering. Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref">Token för datum- och tidsformatering</a>.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>Text </td> 
   <td> <p>(Valfritt) Du kan ange vilken tidszon som ska användas för konverteringen. </p> <p>En lista över godkända tidszoner finns i kolumnen "TZ-databasnamn" i Wikipedia <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">List of tz database time zone</a>. Endast värdena i den här kolumnen tolkas som en giltig tidszon av funktionen. Alla andra värden ignoreras och scenernas tidszon som anges i din profil används i stället. </p> <p>Om du utelämnar den här parametern används den tidszon för scenarier som anges i profilinställningarna. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span><code>Europe/Prague</code>, <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

Om en annan typ anges används typtvång. Mer information finns i [Typtvång](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

#### Returvärde och typ

Funktionen `formatDate` returnerar en textrepresentation av det angivna Date-värdet enligt det angivna formatet och tidszonen. Datatypen är Text.

>[!BEGINSHADEBOX]

**Exempel:** Scenario och Web timezone var båda inställda på `Europe/Prague` i dessa exempel.

![](assets/date&time-functions-examples-350x61.png)

* `formatDate(1. Date created;MM/DD/YYYY)`

  Returer 2018-10-01

* `formatDate(1. Date created; YYYY-MM-DD hh:mm A)`

  Returnerar 2018-10-01 09:32

* `formatDate(1. Date created;DD.MM.YYYY HH:mm;UTC)`

  Returnerar 01.10.2018 07:32

* `formatDate(now;DD.MM.YYYY HH:mm)`

  Returnerar 19.03.2019 15:30

>[!ENDSHADEBOX]

### [!UICONTROL parseDate (text; format; [timezone])]

Använd den här funktionen när du har ett textvärde som representerar ett datum (till exempel `12-10-2019 20:30` eller `Aug 18, 2019 10:00 AM`) och du vill konvertera (parsa) det till ett datumvärde (en binär maskinläsbar representation). Mer information finns i Datum och text i artikeln [Objektdatatyper](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md).

#### Parametrar

Den andra kolumnen anger den förväntade typen. Om en annan typ anges används typtvång. Mer information finns i [Typtvång](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Parameter</th> 
   <th>Förväntad datatyp* </th> 
   <th>Vad det gör</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL text] </td> 
   <td>Text </td> 
   <td> <p>Konverterar ett datumvärde till ett textvärde. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL format] </td> 
   <td>Text </td> 
   <td> <p>Här kan du ange ett format med hjälp av tokens för datum- och tidsformatering. Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md" class="MCXref xref">Token för datum- och tidsformatering</a>.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span><code>DD.MM.YYYY HH:mm</code> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL timezone] </td> 
   <td>Text </td> 
   <td> <p>(Valfritt) Du kan ange vilken tidszon som ska användas för konverteringen. </p> <p>En lista över godkända tidszoner finns i kolumnen "TZ-databasnamn" i Wikipedia <a href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones">List of tz database time zone</a>. Endast värdena i den här kolumnen tolkas som en giltig tidszon av funktionen. Alla andra värden ignoreras och scenernas tidszon som anges i din profil används i stället. </p> <p>Om du utelämnar den här parametern används den tidszon för scenarier som anges i profilinställningarna.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span><code>Europe/Prague</code>, <code>UTC</code></p> </td> 
  </tr> 
 </tbody> 
</table>

Om en annan typ anges används typtvång. Mer information finns i [Typtvång](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

#### Returvärde och typ

Den här funktionen konverterar en textsträng till ett datum enligt det format och den tidszon som du anger. Datatypen för värdet är Date.

>[!BEGINSHADEBOX]

**Exempel:** I följande exempel uttrycks det returnerade Date-värdet enligt ISO 8601, men datatypen för resultatet är Date.

* `parseDate(2016-12-28;YYYY-MM-DD)`

  Returnerar 2016-12-28T00:00:00.000Z

* `parseDate(2016-12-28 16:03;YYYY-MM-DD HH:mm)`

  Returnerar 2016-12-28T16:03:00.000Z

* `parseDate(2016-12-28 04:03 pm; YYYY-MM-DD hh:mm a)`

  Returnerar 2016-12-28T16:03:06.000Z

* `parseDate(1482940986;X)`

  Returnerar 2016-12-28T16:03:06.000Z

>[!ENDSHADEBOX]

### [!UICONTROL dateDifference (Date1; Date2; Unit)]

Returnerar ett tal som representerar skillnaden mellan de två datumen, uttryckt i den angivna enheten.

Datum2 subtraheras från datum1.

Använd ett av följande tidsvärden för parametern `unit`:

* millisekunder
* sekunder
* minuter
* timmar
* dagar
* veckor
* månader

Om ingen enhet anges returnerar funktionen differensen i millisekunder.

>[!BEGINSHADEBOX]

**Exempel:**

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z)`

  Returnerar `600,000`

* `dateDifference(2021-05-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;hours)`

  Returnerar `4`

* `dateDifference2021-06-11T18:10:00.000Z;2021-05-11T18:00:00.000Z;months)`

  Returnerar `1`

>[!ENDSHADEBOX]

### Ytterligare exempel

#### Så här beräknar du den n:e veckodagen i månaden

Det här avsnittet är anpassat för [!DNL Workfront Fusion] från webbsidan [!DNL Exceljet] som förklarar hur du hämtar den nionde veckodagen i en månad.

Om du behöver beräkna ett datum som motsvarar den n:e veckodagen i månaden (till exempel den första tisdagen, den tredje fredagen och så vidare) kan du använda följande formel:

![](assets/date&time-functions-calc-nth-day-350x31.png)

```
{{addDays(setDate(1.date; 1); 1.n * 7 - formatDate(addDays(setDate(1.date; 1); "-" + 1.dow); "E"))}}
```

Formeln innehåller följande artiklar:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><code>1.n</code> </td> 
   <td> <p> N:e dagen:</p> 
    <ul> 
     <li><code>1</code> för 1 tisdag</li> 
     <li><code>2</code> för andra tisdagen</li> 
     <li><code>3</code> för 3 tisdag och så vidare</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>2.dow</code> </td> 
   <td> <p> veckodag:</p> 
    <ul> 
     <li><code>1</code> för måndag</li> 
     <li><code>2</code> för tisdag</li> 
     <li><code>3</code> för onsdag</li> 
     <li><code>4</code> för torsdag</li> 
     <li><code>5</code> i fredag</li> 
     <li><code>6</code> för lördag</li> 
     <li><code>7</code> för söndag</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>1.date</code> </td> 
   <td> <p> Datumet bestämmer månaden. Om du vill beräkna den n:e veckodagen i den aktuella månaden använder du variabeln <code>now</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

Om du bara vill beräkna ett specifikt fall, till exempel varje onsdag, kan du ersätta objekten `1.n` och `2.dow` i formeln med motsvarande tal. För den andra onsdagen i den aktuella månaden använder du följande värden:

* `1.n` = `2`
* `1.dow` = `3`
* `1.date` = `now`

![](assets/nth-day-variable-value-350x33.png)

#### Förklaring:

* `setDate(now;1)` returnerar den första av den aktuella månaden
* `formatDate(....;E)` returnerar veckodag (1, 2, ... 6)

### Beräkna dagar mellan datum

En möjlighet är att använda följande uttryck:

![](assets/calculate-days-between-dates-350x68.png)

```
{{round((2.value - 1.value) / 1000 / 60 / 60 / 24)}}
```

>[!NOTE]
>
>* Värdena för `D1` och `D2` har datatypsvärden. Om de är strängtypsvärden (till exempel 20.10.2018) använder du funktionen `parseDate()` för att konvertera dem till datatypsvärden.
>
>* Funktionen `round()` används för fall när ett av datumen ligger inom sommartidsperioden och det andra inte gör det. I dessa fall är skillnaden i timmar en timme mindre eller mer. Du kan dividera det med 24 för ett resultat som inte är ett heltal. Du förlorar en timmes sommartid. Rund förenklar den så att du inte får en procentandel

#### Så här beräknar du sista dagen/millisekunden i månaden

När du anger ett datumintervall, till exempel i en sökmodul, måste du beräkna den sista dagen i månaden om intervallet sträcker sig över hela föregående månad som ett slutet intervall (det intervall som innehåller båda gränspunkterna).

2019-09-01 ≤ D ≤ 2019-09-30

Formeln nedan visar ett sätt att beräkna den sista dagen i föregående månad:

![](assets/last-day-prev-month.png)

```
{{addDays(setDate(now; 1); -1)}}
```

I vissa fall behöver du inte bara beräkna den sista dagen i månaden, utan bokstavligen dess sista millisekund:

2019-09-01T00:00:00.000Z ≤ D ≤ 2019-09-30T23:59:59.999Z

Den här formeln visar ett sätt att beräkna den sista millisekunddelen i föregående månad:

![](assets/last-millisecond-prev-month-350x45.png)

```
{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD"; "UTC") - 1; "x")}}
```

Om du behöver resultatet för att använda tidszonsinställningen utelämnar du UTC-argumentet:

![](assets/omit-utc-argument-350x45.png)

`{{parseDate(parseDate(formatDate(now; "YYYYMM01"); "YYYYMMDD") - 1; "x")}}`

Det är dock bättre att använda ett halvöppet intervall i stället (det intervall som utesluter en av sina gränspunkter), ange den första dagen i nästa månad i stället och ersätta operatorn &quot;mindre än eller lika med&quot; med &quot;mindre än&quot; enligt följande:

`2019-09-01 ≤ D < 2019-10-01`

`2019-09-01T00:00:00.000Z ≤ D < 2019-10-01T00:00:00.000Z`
