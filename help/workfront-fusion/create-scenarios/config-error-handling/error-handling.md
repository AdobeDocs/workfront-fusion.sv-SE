---
title: Lägg till felhantering
description: När fel inträffar under körningen av ett scenario beror det oftast på att en tjänst inte är tillgänglig på grund av ett fel, att en tjänst svarar med oväntade data eller att valideringen av indata misslyckas.
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Lägg till felhantering

Fel kan uppstå när ett scenario körs.

Ett fel kan till exempel uppstå på grund av:

* En tjänst är inte tillgänglig på grund av ett fel
* En tjänst svarar med oväntade data
* Validering av indata misslyckas
* Andra orsaker

Om en modul påträffar ett fel under scenariokörningen och det inte finns någon felhanteringsväg kopplad till modulen, körs standardfelhanteringslogiken.

Genom att lägga till en felhanterarväg till en modul kan du ersätta standardfelhanteringslogiken med din egen. Adobe Workfront Fusion innehåller fem olika direktiv som kan infogas i slutet av felhanterarvägen.

Mer information om standardfelhantering finns i [Feltyper](/help/workfront-fusion/references/errors/error-processing.md).

Mer information om felhanteringsdirektiv finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens</td> 
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront Plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>Ultimate Workfront Plan: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Lägga till en felhanterare

Så här lägger du till en felhanterare i en modul:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en felhanteringsväg.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Högerklicka på den modul efter vilken du vill lägga till en felhanterarväg och välj **[!UICONTROL Add error handler]**:

   ![](assets/error-handler-route.png)

   En felhanterarväg läggs till i modulen. Om modulen är den sista modulen i ett flöde följer felhanteraren direkt modulen. Om modulen har fler moduler efter det läggs en separat felhanterarväg till.

   I felhanteringsmodulen visas en lista över direktiv samt de program som används i ditt scenario.

   ![Felflöde](assets/error-route.png)

1. Välj ett av direktiven.

   eller

   Lägg till en eller flera moduler i felhanterarflödet.

   Om du lägger till fler moduler i flödet används direktivet Ignorera som standard. Om ett fel uppstår behandlas efterföljande moduler på det flödet.

   Mer information om direktiv finns i [Felhanteringsdirektiv](#error-handling-directives) i den här artikeln.

1. (Valfritt) Lägg till ett filter i felhanteringsflödet. Instruktioner finns i [Lägga till filtrering och kapsling i felhanteringsflöden](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md).

>[!NOTE]
>
>Observera att en felhanterarväg består av genomskinliga cirklar, medan en vanlig väg består av heldragna cirklar.

## Felhanteringsdirektiv

Direktiven förklaras kortfattat nedan. Mer information finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

Det finns fem direktiv som kan grupperas i följande kategorier baserat på om en scenariokörning fortsätter efter felet.

Följande direktiv ser till att en scenariokörning fortsätter:

* **[!UICONTROL Resume]**: Gör att du kan ange en ersättningsutmatning för modulen med felet. Scenariots körningsstatus har markerats som lyckad.
* **[!UICONTROL Ignore]**: ignorerar felet. Scenariots körningsstatus har markerats som lyckad.
* **[!UICONTROL Break]**: Lagrar indata till kön med ofullständiga körningar. Scenariots körningsstatus är markerad som varning.

  Mer information finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Om en scenariokörning ska stoppas när ett fel inträffar, ska du använda något av följande direktiv:

* **[!UICONTROL Rollback]**: Stoppar scenariokörningen omedelbart och anger dess status som fel.
* **[!UICONTROL Commit]**: Stoppar scenariokörningen omedelbart och anger att den har lyckats.

## Resurs

Mer information om felhantering finns i:

* [Direktiv om felhantering i Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [Lägg till filtrering och kapsling i felhanteringsflöden](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
