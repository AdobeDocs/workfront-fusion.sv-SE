---
title: Adobe Workfront Fusion Glossary
description: I följande ordlista förklaras några vanliga termer i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 7f098ec2-8594-4e5d-9ce7-d1738a05f9a6
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---

# Adobe Workfront Fusion-ordlista

I följande ordlista förklaras några vanliga termer i Adobe Workfront Fusion.


<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Åtgärd</p> </td> 
   <td>En modul som gör att du kan utföra en åtgärd, till exempel läsa eller skriva data från eller till en vald app eller tjänst.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Aggregator</p> </td> 
   <td> <p>En typ av modul som sammanfogar flera paket (flera samlingar av data) till ett enda paket. </p><p>Mer information finns i <a href="/help/workfront-fusion/references/modules/aggregator-module.md" class="MCXref xref">Aggregatormodulen</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API</td> 
   <td>API:er är ett sätt för program och tjänster att kommunicera med varandra. Fusion använder API:er för att kommunicera med det program du ansluter till. Varje program har ett separat API. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-nyckel</td> 
   <td>En unik kod som identifierar användaren, utvecklaren eller programmet som anropar en programvaras API, som används för autentisering. Eftersom Fusion-moduler fungerar genom att ansluta API:er är API-nycklar ibland nödvändiga. API-nycklar distribueras av det program som kräver dem. Om du till exempel behöver en API-nyckel för att ansluta Fusion till Adobe Lightroom, begär du det via ditt Adobe Lightroom-konto.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Program eller tjänst</td> 
   <td> <p>Ett program. Fusion kan ansluta till de flesta program, även om det inte har någon dedikerad anslutning för det programmet.</p> <p>En app kan också vara en specialfunktion som hanterar data, till exempel en iterator eller en aggregator. </p> <p>En tjänst är en datakälla som kan innehålla ett webb-API, en webbsida, olika typer av servrar (FTP, SMTP, IMAP) och så vidare. </p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Paket</p> </td> 
   <td> <p>Ett paket är en grundläggande dataenhet som returneras eller tas emot av moduler. En sökmodul som returnerar tre poster ger till exempel tre datapaket, ett för varje post. Ett paket består av artiklar.</p> </td> 
  </tr> 
  <tr>
   <td role="rowheader"> <p>Anslutning</p> </td> 
   <td> <p>En anslutning representerar en uppsättning autentiseringsuppgifter för att ansluta till en viss tjänst. Du kan konfigurera anslutningar inuti en modul och sedan använda anslutningen i vilken modul som helst. Alla moduler måste ha en anslutning markerad, så att Fusion kan använda dessa autentiseringsuppgifter för att komma åt den information som modulen kräver. </p><p>Mer information finns i <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md" class="MCXref xref">Anslutningsöversikt</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Koppling</td> 
   <td>En koppling är en uppsättning moduler för ett visst program. Workfront Fusion har kopplingar till många vanliga arbetsapplikationer, som Workfront, Salesforce och Jira.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Cykel</p> </td> 
   <td> <p>En cykel består av två faser av scenariokörningen: operation och commit. Scenariot kan bestå av en eller flera cykler. Mer detaljerad information finns i <a href="/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md" class="MCXref xref">Scenariokörning, cykler och faser</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Datalager</p> </td> 
   <td> <p>I ett datalager lagras data från scenarier eller så kan du överföra data mellan enskilda scenarier eller scenariokörningar. </p><p>Mer information finns i <a href="/help/workfront-fusion/create-scenarios/map-data/data-stores.md" class="MCXref xref">Datalager</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Filter</p> </td> 
   <td> <p> Ett filter kan användas mellan två moduler och gör att du bara kan arbeta med paket som uppfyller vissa villkor. Det finns ett antal olika filter som du kan använda. </p><p>Mer information finns i <a href="/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md" class="MCXref xref">Lägga till ett filter i ett scenario</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID </p> </td> 
   <td> <p>Ett namn som används för att unikt identifiera ett paket. Ett ID används vanligtvis för att särskilja ett paket som ska uppdateras eller tas bort från en viss tjänst. ID:n kan mappas från utdata från en tidigare modul.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Objekt</p> </td> 
   <td> <p>En del av ett paket. Paket kan bestå av flera objekt. Det finns flera olika typer av alternativ: text, tal, booleskt (ja/nej), datum, tid, buffert (binära data), samlingar, markeringsmeny, matris och validering.</p><p> Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Objektdatatyper</a>.</p> </td> 
  </tr>
  <tr> 
   <td role="rowheader"> <p>Iterator</p> </td> 
   <td> <p>En typ av modul som gör att du kan ta ett datapaket (en samling data) och dela upp det i separata paket. Dessa paket kan sedan bearbetas individuellt av senare moduler. </p><p>Mer information finns i <a href="/help/workfront-fusion/references/modules/iterator-module.md" class="MCXref xref">[!UICONTROL Iterator] modul</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Modul</p> </td> 
   <td> <p>Ett enskilt steg i ett scenario som utför en funktion, till exempel att skapa en post, i det tillhörande programmet eller tjänsten.</p> <p>Varje program eller tjänst har olika moduler som definierar hur den svarar på en begäran.</p>  <p> <img src="assets/module.png"> </p> <p>Mer information finns i <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">Modulöversikt</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Åtgärd</p> </td> 
   <td> <p>En åtgärd som utförs av en modul, till exempel hämtning av en post eller överföring av en fil.</p><p>Mer information finns i <a href="/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md" class="MCXref xref">Åtgärder</a>.</p>
  </tr> 
  <tr> 
   <td role="rowheader">Offentliga/privata nycklar</td> 
   <td>Offentliga och privata nycklar används för att kryptera och dekryptera data. Den offentliga nyckeln kan distribueras och alla som har den offentliga nyckeln kan kryptera data, men bara den privata nyckeln kan dekryptera den. På samma sätt kan en användare med en privat nyckel kryptera data som alla med den offentliga nyckeln kan dekryptera. Krypteringen av den privata nyckeln garanterar att data kommer från den privata nyckelns ägare och fungerar som validering av datakällan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Router</p> </td> 
   <td>Med en router kan du duplicera data eller lägga till nya vägar till ett scenario, så att du kan omdirigera data och hantera olika grupper av data separat.</p><p> Mer information finns i <a href="/help/workfront-fusion/create-scenarios/add-modules/router-module.md" class="MCXref xref">[!UICONTROL Router] modul</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Scenario</p> </td> 
   <td> <p>En serie automatiserade steg som skapats av användare, där varje steg representeras och utförs av en modul. Syftet med ett scenario är att flytta och hantera data.</p> <p> <img src="assets/entire-scenario-blank.png" style="width: 350;height: 178;"> </p> <p> Mer information finns i <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md" class="MCXref xref">Scenarioöversikt</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Scenariosegment</p> </td> 
   <td> <p> Ett scenariosegment är en del av ett scenario som består av en serie moduler som alla ansluter till samma program. Scenariosegment representerar ofta ett kort arbetsflöde i programmet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Utlösare</p> </td> 
   <td> <p>En utlösare är en sorts modul som söker efter nya och uppdaterade data och startar scenariot när vissa villkor som har konfigurerats i modulen gäller. Utlösare kan konfigureras för att starta ett scenario enligt ett schema (avsökning) eller när dataändringar sker (direktutlösare eller webkrok).</p> <p>Mer information finns i <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">Utlösare</a> i artikeln om modulöversikt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Webkrok</p> </td> 
   <td> <p>En särskild typ av utlösare som gör att du kan köra ett scenario omedelbart efter det att ett nytt paket är tillgängligt. </p><p>Mer information finns i <a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref">Direktutlösare (webhooks)</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
