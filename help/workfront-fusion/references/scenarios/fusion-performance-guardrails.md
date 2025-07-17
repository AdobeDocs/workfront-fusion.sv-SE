---
title: Gardrutor för fusionsprestanda
description: Automatisering av arbete kräver snabb bearbetning, så [!DNL Adobe Workfront Fusion]  är utformad för höga prestanda. Eftersom långvariga scenarier kan göra arbetet långsammare har vi utformat  [!DNL Workfront Fusion] med prestandabevarande säkerhetsdetaljer som begränsar körningstid, datastorlek och andra scenarioparametrar. [!DNL Workfront Fusion] Designers bör vara medvetna om dessa skyddsräcken och införliva dem i sin designpraxis.
author: Becky
feature: Workfront Fusion
exl-id: d142a521-edbc-4d7b-b5cd-872a9d3d2e1c
source-git-commit: e036784fbf241c6d528f2020b7c368249e4f2133
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 0%

---

# Skyddsräcken för Fusion-prestanda

Automatisering av arbete kräver snabb bearbetning, så [!DNL Adobe Workfront Fusion] är utformad för höga prestanda. Eftersom långvariga scenarier kan göra arbetet långsammare har vi utformat [!DNL Workfront Fusion] med prestandabevarande säkerhetsdetaljer som begränsar körningstid, datastorlek och andra scenarioparametrar. [!DNL Workfront Fusion]-designers bör vara medvetna om dessa skyddsräcken och införliva dem i sin designpraxis.

## Webbläsare

* Workfront Fusion stöder endast Chrome-baserade webbläsare.

## Scenarier

* Standardtidsgränsen för scenariokörning är **40 minuter**. När körningen når den här tidsgränsen avbryter [!DNL Workfront Fusion] körningen av scenariot efter nästa cykel eller åtgärd, beroende på scenariot. Detta medför att scenariot avbryts kort efter att gränsen på 40 minuter har nåtts

  Kedningsscenarier räknas inte med i tidsgränsen för scenariokörning. Ett överordnat scenario tar inte lång tid i väntan på att ett underordnat scenario ska köras.
* Den största tillåtna storleken för en scenarioplan är **5 MB**, men vi rekommenderar att du behåller scenariostorleken under **3 MB**.

  Programmoduler som skapar eller uppdaterar data med ett stort antal fält kan orsaka mycket stora utkast.

   * När du använder appen [!DNL Workfront] ska du bara välja fält som behövs för dina användningsfall för att skapa eller uppdatera.
   * När du använder andra program kan du använda anpassade API-moduler för att interagera med valfri posttyp som har ett stort antal fält.

* Även om det inte finns något tak för antalet moduler i ett scenario, påverkar scenarier med fler än 150 moduler prestandan i ditt [!DNL Workfront Fusion]-system negativt. Därför rekommenderar vi inte att du skapar scenarier med fler än 150 moduler.

## Operationer

* Standardåtgärdens timeout är vanligtvis **40 sekunder**.

<!--
* The operation timeout for calls to Adobe Workfront is **120 seconds**.
-->

## Filer

* Fusions totala bearbetningskapacitet för filer är **1 GB**. Gränsen baseras på en total minneskostnad. Alla operationer bidrar till den kostnaden. Om en fil på 400 MB laddas ned och överförs blir den totala kostnaden för filkapaciteten 800 MB.
* Organisationer som har Workfront Ultimate-plan har tillgång till mer än 1 GB filbearbetning. Fusion-plattformen har stöd för enskilda filer upp till 15 GB för en enda åtgärd (t.ex. överföringsfil), men det finns andra faktorer som påverkar dataöverföringen. Storleksgränsen för en åtgärd beror på hur web service Fusion ansluts till. Dataöverföring är den totala bearbetningen för en enskild körning. Detta innebär att flera åtgärder i en enda körning bidrar till den totala dataöverföringen. Fusion bearbetar filer tills körningsgränsen på 40 minuter är nådd.
* Om en fil laddas ned med en modul som stöder stora filer och sedan skickas till en modul som inte stöder stora filer, bearbetas inte filen korrekt i den modulen. Stora filer måste hanteras exklusivt med moduler som stöds i hela arbetsflödet.
* Moduler som inte stöder stora filer kan bearbeta filer som är högst **200 MB**.

Mer information finns i [Arbeta med stora filer](/help/workfront-fusion/references/scenarios/fusion-large-files.md).

## Serverminnesanvändning

* Serverminnesanvändningen för en enskild körning är begränsad till **1 GB**.

  Många faktorer, till exempel stora filer eller komplexa moduler, kan påverka minnesanvändningen på ett sätt som är svårt att förutse eller kontrollera. På grund av detta kan din scenariokörning överskrida minnesgränsen på 1 GB, även om scenariot följer alla andra prestandaskydd. Om du överskrider minnesgränsen misslyckas körningen.

## Webhooks

* Den maximala standardstorleken för en nyttolast är **5 MB**.
* Webbhooks är begränsade till **100 begäranden per sekund**. När den här gränsen har nåtts skickar Workfront Fusion en 429-status ([!UICONTROL Too Many Requests]).
* [!DNL Workfront Fusion] lagrar webkrocknyttolaster i 30 dagar. Om du får åtkomst till en webkrok-nyttolast mer än 30 dagar efter att den togs emot uppstår felet [!UICONTROL Failed to read file from storage.]
* Webhooks inaktiveras automatiskt om något av följande gäller:

   * Webbkroken har inte varit ansluten till något scenario på mer än fem dagar
   * Webkroken används bara i inaktiva scenarier, som har varit inaktiva i mer än 30 dagar.

* Inaktiverade webhooks tas bort och avregistreras automatiskt om de inte är anslutna till några scenarier och har inaktiverats i över 30 dagar.

## Körningshistorik

* Körningshistorikloggarna är begränsade till storleken **100 MB**. Om körningshistoriken överskrider den här storleken visas endast de första 100 MB.
* Om ett scenario har flera samtidiga körningar. Endast 5 körningar visas i området Körningar på sidan med scenarioinformation. Detta gäller även när fler än fem exekveringar körs.

## Ofullständiga körningar

* Ofullständiga körningar är begränsade till en total storlek på **10 MB** per scenario. Om gränsen på 10 MB nås kommer inga fler ofullständiga körningar att lagras för det scenariot.
* Ofullständiga körningar är begränsade till en total storlek på **500 MB** per team. Om gränsen på 500 MB nås kommer inga fler ofullständiga körningar att lagras för det teamet.
* Workfront Fusion tillåter upp till 5 fel per minut.

## Försök igen

* Om ett scenario misslyckas i följd 10 gånger inom en tvåminutersperiod när du använder modulen Bryt och anger direktivet Försök igen inaktiveras scenariot automatiskt.

## Rekursion

Rekursion inträffar när ett scenario utlöser en ny körning av sig själv, som utlöser en ny körning och så vidare i en oändlig slinga.

Ett scenario aktiveras till exempel när en uppgift skapas och det scenariot skapar två uppgifter. De nya uppgifterna utlöser båda scenariot igen, vilket skapar fyra nya uppgifter. Varje gång en uppgift skapas utlöses scenariot och varje gång scenariot körs dubbleras antalet uppgifter. Antalet uppgifter ökar exponentiellt.

Rekursion kan orsaka prestandaproblem både för den organisation som äger det rekursiva scenariot och för andra organisationer.

Tänk på följande när det gäller rekursion:

* **När ett scenario orsakar rekursion inaktiveras det av Fusion Engineering-teamet för att förhindra ytterligare prestandaproblem.**
* Eftersom rekursion är ett resultat av scenariodesign måste du utforma dina scenarier på ett sätt som säkerställer att scenariot inte innehåller åtgärder som utlöser scenariot.

## TLS

* Fusion har för närvarande stöd för TLS version 1.2 som standard.
* Fusion kan använda TLS 1.3 för utgående HTTPS-begäranden om TLS 1.3 är aktiverat för måltjänsten.
* Fusion har stöd för både TLS 1.2 och TLS 1.3 för inkommande HTTPS-begäranden till Webhooks.
* Organisationer kan begära att TLS version 1.3 aktiveras för deras Fusion-instans.

>[!NOTE]
>
> Om du ansluter till Workfront ska du vara medveten om att den här TLS-funktionen är aktiverad i Workfront för anrop till domäner med formatet `https://<domain>.my.workfront.com`.
