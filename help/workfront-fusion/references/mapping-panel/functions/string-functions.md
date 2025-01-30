---
title: Strängfunktioner
description: Följande strängfunktioner är tillgängliga på panelen för mappning av Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: d3e49fce-85bc-4ee6-9a94-497a306e0c74
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# Strängfunktioner

## [!UICONTROL length (text or buffer)]

Returnerar längden på textsträngen (antal tecken) eller binär buffert (buffertstorlek i byte).

>[!BEGINSHADEBOX]

**Exempel:**

`length( hello )`

Returer: 5

>[!ENDSHADEBOX]

## [!UICONTROL lower (text)]

Konverterar alla alfabetiska tecken i en textsträng till gemener.

>[!BEGINSHADEBOX]

**Exempel:**

`lower( Hello )`

Returnerar: hej

>[!ENDSHADEBOX]

## [!UICONTROL capitalize (text)]

Konverterar det första tecknet i en textsträng till versaler.

>[!BEGINSHADEBOX]

**Exempel:**

`capitalize( workfront )`

Returnerar: [!DNL Workfront]

>[!ENDSHADEBOX]

## [!UICONTROL startcase (text)]

Ändrar den första bokstaven i varje ord till versaler och gemener i alla andra bokstäver.

>[!BEGINSHADEBOX]

**Exempel:**
`startcase( hello WORLD )`

Returnerar: [!UICONTROL Hello World]

>[!ENDSHADEBOX]

## [!UICONTROL ascii (text; [remove diacritics])]

Tar bort alla icke-ASCII-tecken från en textsträng.

>[!BEGINSHADEBOX]

**Exempel:**

* `ascii(` `Wěošrčkřfžrýoáníté` `)`

Returnerar: [!DNL Workfront]

* `ascii(` `ěščřž` `;` `true` `)`

Returnerar: [!UICONTROL escrz]

>[!ENDSHADEBOX]

## [!UICONTROL replace (text;search string; replacement string)]

Ersätter söksträngen med den nya strängen.

>[!BEGINSHADEBOX]

**Exempel:**

`replace( Hello World ; Hello ; Hi )`

Returnerar: [!UICONTROL Hi World]

>[!ENDSHADEBOX]

Reguljära uttryck (omslutna av `/.../`) kan användas som söksträng med en kombination av flaggor (till exempel `g`, `i`, `m`) tillagda:

>[!BEGINSHADEBOX]

**Exempel:**

![Ersätt](assets/replace---1-350x31.png)

Alla dessa siffror X X X X X ersätts med X

>[!ENDSHADEBOX]

Ersättningssträngen kan innehålla följande speciella ersättningsmönster:

* `$&` Infogar den matchande delsträngen.
* `$n` Där n är ett positivt heltal mindre än 100 infogar den n:te parentesala delmatchningssträngen. Detta är 1-indexerat.

>[!BEGINSHADEBOX]

**Exempel:**

![Variabelvärde](assets/variable-value-350x63.png)

Returnerar: Telefonnummer `+420777111222`

![Variabelretur](assets/variable-value---2-350x55.png)

Returnerar: Telefonnummer: `+420777111222`

>[!CAUTION]
>
>Använd inte namngivna hämtningsgrupper som `/ is (?<number>\d+)/` i ersättningssträngargumentet. Om du gör det uppstår ett fel.


>[!ENDSHADEBOX]

Mer information om reguljära uttryck finns i [Textparser](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/text-parser.md).

## [!UICONTROL trim (text)]

Tar bort blankstegstecken i början eller slutet av texten.

## [!UICONTROL upper (text)]

Konverterar alla bokstäver i en textsträng till versaler.

>[!BEGINSHADEBOX]

**Exempel:**

`upper( Hello )`

Returnerar: [!UICONTROL HELLO]

>[!ENDSHADEBOX]

## [!UICONTROL substring (text; start;end)]

Returnerar en del av en textsträng mellan start- och slutpositionen.

>[!BEGINSHADEBOX]

**Exempel:**

* `substring( Hello ; 0 ; 3)`

  Returnerar: Hel

* `substring( Hello ; 1 ; 3 )`

  Returnerar: el

>[!ENDSHADEBOX]

## [!DNL indexOf (string; value; [start])]

Returnerar positionen för den första förekomsten av ett angivet värde i en sträng. Den här metoden returnerar &#39;-1&#39; om det värde som söks efter inte finns där. Startvärdet anger var i strängen sökningen ska börja.

>[!BEGINSHADEBOX]

**Exempel:**

* `indexOf( Workfront ; o )`

  Returnerar: 1

* `indexOf( Workfront ; x )`

  Returnerar: -1

* `indexOf( Workfront ; o ; 3 )`

  Returer: 6

>[!ENDSHADEBOX]

## [!UICONTROL toBinary (value)]

Konverterar alla värden till binära data.

Du kan också ange kodning som ett andra argument för att tillämpa binära konverteringar från hex eller base64 på binära data.

>[!BEGINSHADEBOX]

**Exempel:**

* `toBinary( Workfront )`

  Returnerar: 57 6f 72 6b 66 72 6f 6e 74

* `toBinary( V29ya2Zyb250 ; base64 )`

  Returnerar: 57 6f 72 6b 66 72 6f 6e 74

>[!ENDSHADEBOX]

## [!UICONTROL toString (value)]

Konverterar alla värden till en sträng.

## [!UICONTROL encodeURL (text)]

Kodar specialtecken i text till en giltig URL-adress.

## [!UICONTROL decodeURL (text)]

Avkodar specialtecken i en URL till text.

>[!BEGINSHADEBOX]

**Exempel:**
`decodeURL( Automate%20your%20workflow )`

Returnerar: [!UICONTROL Automate your workflow]

>[!ENDSHADEBOX]

## [!UICONTROL escapeHTML (text)]

Ignorerar alla HTML-taggar i text.

>[!BEGINSHADEBOX]

**Exempel:**

`escapeHTML( <b>Hello</b> )`

Returnerar: `&lt;b&gt;Hello&lt;/b&gt;`

>[!ENDSHADEBOX]

## [!UICONTROL escapeMarkdown(text)]

Ignorerar alla markeringstaggar i text.

>[!BEGINSHADEBOX]

**Exempel:**

`escapeMarkdown( # Header )`

Returnerar: `&#35; Header`

>[!ENDSHADEBOX]

## [!UICONTROL stripHTML (text)]

Tar bort alla HTML-taggar från text.

>[!BEGINSHADEBOX]

**Exempel:**

`stripHTML( <b>Hello</b> )`

Returnerar: Hej

>[!ENDSHADEBOX]

## contains (text; söksträng)

Verifierar om texten innehåller söksträngen.

>[!BEGINSHADEBOX]

**Exempel:**

* `contains( Hello World ; Hello )`

  Returnerar: [!UICONTROL true]

* `contains( Hello World ; Bye )`

  Returnerar: [!UICONTROL false]

>[!ENDSHADEBOX]

## [!UICONTROL split (text; separator)]

Delar en sträng i en array med strängar genom att dela strängen i delsträngar.

>[!BEGINSHADEBOX]

**Exempel:**

`split( John, George, Paul ; , )`

>[!ENDSHADEBOX]

## [!UICONTROL md5 (text)]

Beräknar md5-hash för en sträng.

>[!BEGINSHADEBOX]

**Exempel:**

`md5( Workfront )`

Returnerar: `1448bbbeaa7a9b8091d426999f1f666b`

>[!ENDSHADEBOX]

## [!UICONTROL sha1 (text; [encoding]; [key])]

Beräknar sha1-hash för en sträng. Om nyckelargumentet anges returneras sha1 HMAC-hash i stället. Kodningar som stöds: &quot;hex&quot; (standard), &quot;base64&quot; eller &quot;latin1&quot;.

>[!BEGINSHADEBOX]

**Exempel:**

`sha1( workfront )`

Returnerar: b2b30b8ae1f9e5b40fbb0696eaabdbfd8d0c087f

>[!ENDSHADEBOX]

## [!UICONTROL sha256 (text; [encoding]; [key])]

Beräknar sha256-hash för en sträng. Om nyckelargumentet anges returneras sha256 HMAC-hash i stället. Kodningar som stöds: &quot;hex&quot; (standard), &quot;base64&quot; eller &quot;latin1&quot;.>

>[!BEGINSHADEBOX]

**Exempel:**

`sha256( workfront )`

Returnerar: ed3d7397eec7b94453035b67ba4468c883ee3bedeb57137f7371f2e0cf5e2bbc

>[!ENDSHADEBOX]

## [!UICONTROL sha512 (text; [output encoding]; [key]; [key encoding])]

Beräknar sha512-hash för en sträng. Om nyckelargumentet anges returneras sha512 HMAC-hash i stället.

Kodningar som stöds:

* &quot;[!UICONTROL hex]&quot; (standard)
* [!UICONTROL base64]
* [!UICONTROL latin1]

Nyckelkodningar som stöds:

* &quot;[!UICONTROL text]&quot; (standard)
* [!UICONTROL hex]
* [!UICONTROL base64] eller [!UICONTROL binary]

När [!UICONTROL binary]-tangentkodning används måste en nyckel vara en buffert, inte en sträng.

>[!BEGINSHADEBOX]

**Exempel:**

`sha512(workfront)`

Returnerar: 789ae41b9456357e4f27c6a09956a767abbb8d80b206003ffdd1e94dbc687cd119 b85e1e19db58bb44b234493af35fd431639c0345adf2cf7ec26e9f4a7fb19

>[!ENDSHADEBOX]

## [!UICONTROL base64 (text)]

Omformar text till base64.

>[!BEGINSHADEBOX]

**Exempel:**

`base64( workfront )`

Returnerar: d29ya2Zyb250===

>[!ENDSHADEBOX]
