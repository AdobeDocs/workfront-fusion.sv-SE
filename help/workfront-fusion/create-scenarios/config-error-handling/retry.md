---
title: Konfigurera tillfällig lösning för felhantering på nytt
description: Ibland kan det vara användbart att köra en felande modul igen om det finns en möjlighet att orsaken till felet snabbt kan lösas.
author: Becky
feature: Workfront Fusion
exl-id: 08e19a1a-7ca9-4c79-a165-f200048a5cda
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 0%

---

# Konfigurera `retry` felhanteringslösning

Ibland kan det vara användbart att köra en felande modul igen om det finns en möjlighet att orsaken till felet snabbt kan lösas.

Adobe Workfront Fusion innehåller för närvarande inte direktivet `retry` för felhantering, men det finns två tillfälliga lösningar för att efterlikna funktionen `retry`.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla Adobe Workfront Workflow-paket och alla Adobe Workfront Automation and Integration-paket</p><p>Workfront Ultimate</p><p>Workfront Prime- och Select-paket med ytterligare köp av Workfront Fusion.</p> </td> 
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

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Tillfälliga lösningar på direktivet [!UICONTROL Retry] för felhantering

Workfront Fusion innehåller för närvarande inte direktivet `retry` för felhantering. Använd någon av följande tillfälliga lösningar för att efterlikna funktionaliteten.

Instruktioner finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

* [Använda direktivet Break](#use-the-break-directive)
* [Använda upprepningsmodulen](#use-the-repeater-module)

### Använda direktivet Break

När direktivet Break körs lagras scenariokörningens tillstånd i kön med ofullständiga körningar. Om detta inträffar kan du lösa den ofullständiga körningen manuellt.

Instruktioner finns i [Åtgärda fel som hanteras av direktivet Break](/help/workfront-fusion/create-scenarios/config-error-handling/resolve-error-from-break-directive.md)

Instruktioner om hur du löser ofullständiga körningar finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

#### Nackdelar

* Det minsta intervallet för återförsök är en minut.
* Om modulen bearbetar flera paket och bearbetningen av ett paket misslyckas, flyttas den partiella körningen (endast det paket som orsakade felet) till den ofullständiga körningsmappen och schemaläggs för nya försök enligt [!UICONTROL Break]-direktivets inställningar. Den aktuella körningen fortsätter dock och modulen fortsätter att bearbeta efterföljande paket.

  Om du vill förhindra att scenariot körs igen tills körningen i mappen Ofullständiga körningar har lösts aktiverar du alternativet [!UICONTROL Sequential processing] i [!UICONTROL Scenario settings].

Mer information om ofullständiga körningar finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

### Använda upprepningsmodulen

Repeatermodulens lösning är mer komplex, men mer anpassningsbar.

#### Konfigurera felhanterarvägen

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en tillfällig lösning.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på ikonen **Flödeskontroll** ![Flödeskontroll](assets/flow-control-icon.png) och välj **Upprepa**.
1. I Repeater-modulen ställer du in fältet **[!UICONTROL Repeats]** till maximalt antal gånger som du vill att scenariot ska försöka igen.
1. Koppla den eventuellt felaktiga modulen efter modulen **[!UICONTROL Repeater]**.
1. Koppla en felhanterarväg till den modul som kan misslyckas.

   Instruktioner finns i [Lägg till felhantering](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md).
1. Lägg till modulen **[!UICONTROL Tools]>[!UICONTROL Sleep]** i felhanterarvägen och ställ in fältet **[!UICONTROL Delay]** på antalet sekunder mellan återförsök.

1. Lägg till direktivet **[!UICONTROL Ignore]** efter modulen **[!UICONTROL Tools]>[!UICONTROL Sleep]**.
1. Fortsätt till [Konfigurera standardvägen](#configure-the-default-route).

#### Konfigurera standardvägen

1. Lägg till modulen **[!UICONTROL Tools]>[!UICONTROL Set variable]** i en separat (icke-felhanterare) väg efter den eventuellt felaktiga modulen och konfigurera den så att modulens resultat lagras i en variabel med namnet `Result`.

1. Lägg till modulen **[!UICONTROL Array aggregator]** efter **[!UICONTROL Tools]>[!UICONTROL Set variable]** och markera modulen **[!DNL Repeater]** i fältet Source-modul.

1. Lägg till modulen **[!UICONTROL Tools]>[!UICONTROL Get variable]** efter modulen **[!UICONTROL Array aggregator]** och mappa värdet för variabeln `Result` till den.

1. Infoga modulen **[!UICONTROL Tools]>[!UICONTROL Get variable]** mellan modulen **[!UICONTROL Repeater]** och den modul som kan misslyckas och mappa värdet för variabeln `Result` till den.

1. Infoga ett filter mellan den här **[!UICONTROL Tools]>[!UICONTROL Get variable]**-modulen och den eventuellt felaktiga modulen så att den bara fortsätter om variabeln `Result` inte finns.

>[!BEGINSHADEBOX]

**Exempel:**

I det här exempelscenariot representerar modulen [!UICONTROL HTTP] > [!UICONTROL Make a request] den modul som kan misslyckas:

![HTTP-begäran](assets/http-make-request.png)

>[!ENDSHADEBOX]

Om resultatet av den eventuellt felaktiga modulen är för komplext för att lagras i en enkel variabel kan du använda ett datalager för att lagra och hämta resultatet. Datalagret skulle bara innehålla en post. Postens nyckel kan till exempel vara `Result`.

Mer information om datalager finns i [Datalager](/help/workfront-fusion/create-scenarios/map-data/data-stores.md).

#### Nackdelar

* Den här lösningen är mer komplex.
* Den här lösningen använder fler åtgärder.

## Resurser

* Mer information om Repeater-moduler och brytningsdirektiv finns i [Flödeskontroll](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/flow-control.md).
* Mer information om att hämta variabelmoduler finns i [Verktyg](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/tools-modules.md).
