---
title: Generera ett scenariosegment med AI
description: Du kan använda AI för att ange en textprompt som beskriver vad du behöver ett segment i ditt scenario för att göra. Fusion genererar sedan en eller flera moduler som utför dessa åtgärder, som du kan använda i ditt scenario.
author: Becky
feature: Workfront Fusion
exl-id: d231e33a-6033-4e3c-b1d4-7034797c45a5
source-git-commit: 2bec2607d55e4ba2ffd6ddcae6daa51071b204c4
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Generera ett scenariosegment med AI

<!--DO NOT DELETE - linked through CSH-->

<!--Check if this is in GA before repo goes live. If not, hide this article.-->

<!--Check if they need to have signed the rider and stuff-->

Du kan använda AI för att ange en textprompt som beskriver vad du behöver ett segment i ditt scenario för att göra. Fusion genererar sedan en eller flera moduler som utför dessa åtgärder, som du kan använda i ditt scenario.

Genererade scenariosegment innehåller moduler för en enda koppling. Om du vill generera moduler för en annan koppling skapar du en separat prompt och ansluter sedan scenariosegmenten i ditt scenario.

Precis som för allt som genereras från AI rekommenderar vi att du kontrollerar och testar de genererade modulerna för att se till att de fungerar som de ska.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront-paketet</td> 
   <td> <p>Vilket Adobe Workfront Workflow-paket som helst och vilket Adobe Workfront Automation- och integrationspaket som helst</p><p>Workfront Ultimate</p><p>Workfront Prime och Select-paket, med ett tillägg av Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licenser</td> 
   <td> <p>Standard</p><p>Arbeta eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

För mer detaljer om informationen i denna tabell, se [åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Förkunskapskrav

Din organisation måste uppfylla följande krav för att kunna använda den här funktionen:

* Din organisation måste ha deltagit i Workfront AI Assistant Beta.
* Adobe måste ha ett signerat Adobe Gen AI-avtal till din organisation.

  Mer information om hur du signerar avtalet finns i [Signera Adobe Gen AI-avtalet](https://experienceleague.adobe.com/en/docs/workfront/using/basics/ai-assistant/ai-assistant-overview#sign-the-adobe-gen-ai-agreement) i artikens AI Assistant-översikt i Workfront-dokumentationen.

## AI-modulprogram som stöds för närvarande

Fusion AI kan för närvarande generera moduler som ansluter till följande program:

* Adobe Firefly
* Azure OpenAI
* Microsoft Graph
* Adobe Workfront Planning
* Adobe Analytics
* Adobe PDF-tjänster
* Adobe Marketo
* Adobe Frame.io
* Dropbox
* NetSuite
* Google Calendar
* Atlassian Jira
* GitLab
* Spotify
* Bitbucket
* OpenAI
* Slack

## Generera moduler

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en modul.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på ikonen **AI-assistenten** ![AI-assistenten](assets/ai-assistant-icon.png) i skärmens övre högra hörn.
1. Skriv in en textprompt i AI Assistant-panelen.

   För tips på prompts, se [Tips för att skapa prompts för scenariosegment](#tips-for-creating-prompts-for-scenario-segments) i denna artikel.

   AI Assistant genererar modulen eller uppsättningen av moduler.
1. (Villkorat) Om det behövs, lägg till din API-token för applikationen i modulerna.
1. Kontrollera modulerna för att säkerställa att de är konfigurerade för rätt applikation och åtgärd.
1. (Villkorligt) Om det genererade scenarioavsnittet inte är kopplat till ditt scenario drar du det till rätt plats.

Vi rekommenderar att du testar modulerna för att kontrollera att de fungerar som de ska.

## Tips för att skapa uppmaningar för scenariosegment

Textmeddelanden ska innehålla minst följande information:

* Programmet som du ansluter till
* Den eller de åtgärder som du vill utföra

>[!IMPORTANT]
>
>Du kan generera mer än en modul i taget, men du kan bara generera moduler för ett program i taget.

>[!BEGINSHADEBOX]

**Exempel**:

* `Delete the records 'xyz-123', 'xyz-456', 'xyz-789' from Adobe Workfront Planning`
Detta inkluderar programmet `Workfront Planning` och åtgärden `delete records` . Denna uppmaning skapar tre moduler, en för varje post som ska tas bort.
* `Change campaign summary of the record 'xyz-123' from Adobe Workfront Planning`
Detta inkluderar programmet `Workfront Planning` och åtgärden `change campaign summary` .
* `Get all field details in the record type with ID 'test-record' from Adobe Workfront Planning`
Detta inkluderar programmet `Workfront Planning` och åtgärden `get field details` .

Följande exempel är INTE korrekt:

* `Generate an image in Adobe Firefly and upload it to Dropbox`

  Det här exemplet är felaktigt eftersom det innehåller mer än ett program

>[!ENDSHADEBOX]

Tänk på följande när du skapar textmeddelanden:

* Använd direkt, enkelt språk.
* Kontrollera och testa scenariosegmentet. Om det inte fungerar som förväntat, förfina din prompt och försök igen.
