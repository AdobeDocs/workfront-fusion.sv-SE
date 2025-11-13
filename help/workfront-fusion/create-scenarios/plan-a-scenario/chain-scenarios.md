---
title: Kedja flera scenarier tillsammans
description: Du kan kedja scenarier tillsammans, så att ett scenario kan utlösa ett annat och returnera data från det andra scenariot till det första.
author: Becky
feature: Workfront Fusion
exl-id: def8d4c1-fc20-4b93-b1fd-be2f60300464
source-git-commit: 7f73007e219714c38dd0cf29d2a1e3a4c8f6f3cc
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 0%

---

# Kedja flera scenarier tillsammans

>[!NOTE]
>
>Den här funktionen finns i Beta.

Du kan kedja scenarier tillsammans, så att ett scenario kan utlösa ett annat och returnera data från det andra scenariot till det första. Detta gör det möjligt att skapa ett mer modulärt scenario där du inte behöver duplicera scenarioavsnitt i flera scenarier.

Du kan anropa flera underordnade scenarier från ett överordnat scenario, och du kan anropa ett underordnat scenario från flera överordnade scenarier. Du kan även kapsla underordnade scenarier och anropa ett från ett annat.

När ett överordnat scenario väntar på att ett underordnat scenario ska returnera data räknas den tiden inte mot det överordnade scenariets timeout. Ett överordnat scenario anropar till exempel 5 underordnade scenarier, där vart och ett tar 10 minuter att köra, under totalt 50 minuter. Modulerna i det överordnade scenariot tar 15 minuter att köra. Det överordnade scenariot gör inte timeout, även om totalt 65 minuter har gått, vilket är över tidsgränsen på 40 minuter.

Mer information om Fusions prestandaresäkerhetsskydd, inklusive tidsgränser, finns i [Förberedelser för Fusion-prestanda](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md).

Instruktioner om hur du konfigurerar kedjemoduler finns i [Kedjemoduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md).

## Överordnade och underordnade scenarier

* Scenariot **parent** anropar ett annat scenario med hjälp av modulen **Chain** > **Anropa ett underordnat scenario**. Den tar emot utdata från det underordnade scenariot, som kan bearbetas i senare scenariomoduler.
* Scenariot **child** anropas av det överordnade scenariot. Dess utlösarmodul tar emot data från det överordnade scenariot och returnerar utdata till det överordnade scenariot.

Det överordnade scenariot kräver ett svar från det underordnade scenariot. Underordnade scenarier som inte returnerar data stöds för närvarande inte.

## Datastrukturer i kedjade scenarier

Workfront Fusion använder datastrukturer för att överföra information från det överordnade scenariot till det underordnade scenariot. Datastrukturen är konfigurerad i det underordnade scenariot. När det underordnade scenariot väljs från det överordnade scenariot visas fälten för den datastruktur som används som indata för det underordnade scenariot i det överordnade scenariot. Du kan mappa värden till dessa fält, som skickas till det underordnade scenariot när det aktiveras.

Mer information om vilka moduler som ska konfigureras i det överordnade och underordnade scenariot finns i [Kedjemoduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md).

Mer information om datastrukturer finns i [Datastrukturer](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

## Dataflöde

1. Data flödar genom det överordnade scenariot.
1. Data når modulen Anropa ett underordnat scenario. Data mappas till fälten i modulen Anropa ett underordnat scenario, som matchar fälten i datastrukturen som används i det underordnade scenariots utlösarmodul.
1. Data från Anropa ett underordnat scenario skickas till det underordnade scenariot.
1. Det underordnade scenariot bearbetar data och utför åtgärder.
1. Det underordnade scenariot avslutas med retursvaret till den överordnade modulen.
1. Utdata från retursvaret på den överordnade modulen skickas till det överordnade scenariot.
1. Utdata för scenariot Anropa ett underordnat scenario är utdata från det underordnade scenariot. Utdata kan bearbetas senare i det överordnade scenariot.

## Användningsexempel

Här följer några exempel på hur du använder kedjningsscenarier:

* **Återanvändbar logik**: Du kan kedja scenarier för upprepade åtgärder som används i flera scenarier. Om du till exempel har flera scenarier där innehållet arkiveras kan du skapa ett enda underordnat scenario som kallas&quot;Arkivera innehåll&quot; och sedan använda det som ett underordnat scenario för alla arbetsflöden som arkiverar innehåll.

* **Felhantering**: Det är vanligt att organisationer har samma felhanteringsåtgärder i flera scenarier, till exempel en felhanteringsväg som skickar en fellogg till ett datalager och skapar ett slackmeddelande. Du kan skapa ett underordnat scenario med dessa åtgärder och kedja det scenariot i felhanteringsflöden i flera scenarier.

* **Utökad tid**: Du kan använda kodning för stora gruppåtgärder med åtgärder som körs länge, till exempel när du exporterar och importerar filer. Den här åtgärden tar en stund om det finns många filer. Eftersom underordnade scenarier inte räknas med i det överordnade scenariets timeout kan du överskrida körningstiden genom att använda flera underordnade scenarier för att exportera eller importera filerna.

* **Att ersätta iteratorer** Att ersätta iteratorer med underordnade scenarier kan minska minnesanvändningen, till exempel vid komplexa åtgärder i en iteration som orsakar fel av typen Slut på minne. Du kan skapa ett separat scenario för den komplexa åtgärden och ersätta iteratorn med Anropa en underordnad scenariomodul

* **Sök efter och skapa en post**: Du kan till exempel skapa ett scenario som söker efter en användare. Om de finns läggs de till som godkännare med åtkomst som de behöver för att granska och godkänna. Om de inte finns skapar scenariot en begäran om att administratören ska ta in en ny användare.

## Visa körningshistorik för kedjade scenarier

Du kan visa körningshistorik för kedjade scenarier genom att visa historiken för varje scenario som ingår i kedjan. Det överordnade scenariets körningshistorik innehåller till exempel information om moduler och data som bearbetas direkt i det överordnade scenariot. Om du vill visa körningshistorik för moduler och data som bearbetas i ett underordnat scenario öppnar du det underordnade scenariot och visar körningshistoriken där.

Vi rekommenderar att du använder knappen **Gå till det underordnade scenariot** i modulen Anropa ett underordnat scenario för att snabbt gå till det underordnade scenariot, där du kan visa dess körningshistorik. Det underordnade scenariot öppnas i ett annat webbläsarfönster så att du kan se överordnade och underordnade scenarier samtidigt.

![Gå till knappen för underordnat scenario](assets/go-to-the-child-button.png)

## Fel och ofullständiga körningar

### Felhantering

Om det underordnade scenariot slutar fungera kan det påverka hur data hämtas tillbaka till det överordnade.

Vi rekommenderar att felhantering konfigureras i det underordnade scenariot för att säkerställa att det överordnade scenariot inte fastnar för svar från det underordnade scenariot om något går fel i det underordnade scenariot.

## Bästa praxis

Tänk på följande när du kedjer ett scenario.

### Undvik rekursion vid kedjningsscenarier

Rekursion inträffar när ett scenario utlöser en ny körning av sig själv, som utlöser en ny körning och så vidare i en oändlig slinga.

Rekursion kan orsaka prestandaproblem både för den organisation som äger det rekursiva scenariot och för andra organisationer.

Följ de här stegen för att undvika rekursion när du kedjer scenarier:

* Kontrollera att **underordnade scenarier inte kan utlösa det överordnade scenariot**. Om till exempel ett överordnat scenario aktiveras när en begäran skapas, ska du se till att de underordnade scenarierna inte skapar några begäranden.
* Se till att **underordnade scenarier inte anropar varandra**. Om det underordnade scenariot A till exempel anropar det underordnade scenariot B, ska du se till att det underordnade scenariot B inte anropar det underordnade scenariot A.
* Kontrollera att **ett scenario inte kan anropa sig själv**. Ett scenario aktiveras till exempel när en uppgift skapas och det scenariot skapar två uppgifter. De nya uppgifterna utlöser båda scenariot igen, vilket skapar fyra nya uppgifter. Varje gång en uppgift skapas utlöses scenariot och varje gång scenariot körs dubbleras antalet uppgifter. Antalet uppgifter ökar exponentiellt.

>[!IMPORTANT]
>
>* **När ett scenario orsakar rekursion inaktiveras det av Fusion Engineering-teamet för att förhindra ytterligare prestandaproblem.**
>* Eftersom rekursion är ett resultat av scenariodesign måste du utforma dina scenarier på ett sätt som säkerställer att scenariot inte innehåller åtgärder som utlöser scenariot.

### Använd felhantering för att säkerställa ett svar

Eftersom det överordnade scenariot väntar på ett svar från det underordnade scenariot innan det kan fortsätta måste du se till att det underordnade scenariot skapas så att det ger ett svar även om ett fel påträffas.
