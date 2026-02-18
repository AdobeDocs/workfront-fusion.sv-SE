---
title: Lägg till en AI-fråga i ditt scenario
description: Du kan inkludera en AI-prompt i ditt scenario som ansluter till din
author: Becky
feature: Workfront Fusion
source-git-commit: 09e8ca28c12990a699816671d07f85288d973bc7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Lägg till en AI-fråga i ditt scenario

Du kan inkludera en AI-prompt i ditt scenario med hjälp av Model Context Protocol (MCP) kombinerat med stora språkmodeller (LLM). Genom att konfigurera dessa i modulen MCP Agent kan du använda artificiell intelligens för att skapa arbetsflöden som är effektiva, säkra och flexibla.

>[!NOTE]
>
>Den här funktionaliteten skiljer sig från möjligheten att lägga till moduler i ett scenario med hjälp av AI.
>
>Mer information om hur du lägger till moduler med AI finns i [Generera ett scenariosegment med hjälp av AI](/help/workfront-fusion/create-scenarios/add-modules/add-a-module-with-ai.md).

## Översikt över modellkontextprotokollet

MCP (Model Context Protocol) är ett sätt att på ett säkert sätt ansluta AI-språkmodeller till andra program. Du konfigurerar MCP-servrar som tillåter AI-modellen att komma åt programmet. Du kan sedan skicka ett meddelande till AI-modellen och den kan returnera information från programmet.

Du kan till exempel konfigurera en MCP-server så att den ansluter en AI-modell med Gmail. När du skickar meddelandet&quot;Ge mig mina fem sista e-postmeddelanden från Gmail&quot; till den stora språkmodellen tolkas meddelandet och skickas till Gmail MPC-servern som sedan kan komma åt din Gmail och returnera e-postmeddelandet.

Med MCP Agent-modulen kan du bearbeta en användarfråga med hjälp av en språkmodell och MCP-servrar.

## Fördelar med att använda MCP i dina Fusion-scenarier

Att använda MCP i dina scenarier ger följande fördelar:

* Om du använder MCP i ditt scenario behöver du inte tänka igenom alla situationer och möjliga varianter av en åtgärd. Genom att använda en prompt eliminerar du behovet av att använda regex- eller parsningsdata för att ta hänsyn till dessa variationer.
* Du kan ge frågan kontext genom att använda element som mappats från tidigare moduler eller andra funktioner på mappningspanelen.
* Det kan vara mer effektivt och flexibelt att använda en prompt än att skapa ett scenario med specifika moduler, eftersom det kan använda en motivering i frågan och välja den bästa åtgärden i det tillgängliga sammanhanget.
* Eftersom du konfigurerar de MCP-servrar som modulen kan ansluta till, kontrollerar du serverns säkerhet och kan vara säker på att säkerheten passar organisationens behov.

>[!NOTE]
>
>Vilka funktioner som är tillgängliga beror på vilka verktyg som finns på MCP-servern och styrs inte av Fusion.

## Lägg till en AI-fråga i ditt scenario

Du kan lägga till en AI-fråga i ditt scenario med hjälp av modulen MCP Agent.

Instruktioner finns i [MCP Agent-modulen](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md).
