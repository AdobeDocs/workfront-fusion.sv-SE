---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: Konfigurera problemlösning för throw-fel
description: I vissa fall kanske du vill stoppa scenariokörningen följt av återställnings- eller implementeringsfasen eller stoppa bearbetningen av en väg och eventuellt lagra den i kön för Visa och lösa ofullständiga körningar i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Konfigurera `throw`-fellösning

I vissa fall kanske du vill stoppa scenariokörningen följt av återställnings- eller implementeringsfasen, eller stoppa bearbetningen av en väg och eventuellt lagra den i kön med ofullständiga körningar.

För närvarande kan inte felhanteringsdirektiven användas utanför omfånget för en felhanterarväg, och Adobe Workfront Fusion innehåller inte någon modul som gör att du enkelt kan generera (utlösa) fel villkorligt.

Du kan använda följande tillfällig lösning för att efterlikna `throw`-felfunktionen.

Mer information om ofullständiga körningar finns i [Visa och lösa ofullständiga körningar i Adobe Workfront Fusion](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Mer information om felhanteringsdirektiv finns i [Direktiv om felhantering i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

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

## Tillfällig lösning för `throw`

Om du vill att ett fel ska inträffa kan du konfigurera en modul så att den automatiskt misslyckas under åtgärden. En möjlighet är att använda modulen [!UICONTROL JSON] > [!UICONTROL Parse JSON], som är konfigurerad att generera ett fel (`BundleValidationError` i det här fallet):

![JSON-fel](assets/json-parse-json.png)

Du kan sedan bifoga ett av felhanteringsdirektiven till felhanteringsvägen:

* **Återställning**: Tvinga scenariokörningen att stoppa och utföra återställningsfasen.
* **Verkställ**: Tvinga scenariokörningen att stoppa och utföra implementeringsfasen.
* **Ignorera**: Stoppa bearbetning av en väg.
* **Brytning**: Stoppa bearbetningen av en väg och lagra den i kön med ofullständiga körningsmappar.

I följande exempel visas hur direktivet [!DNL Rollback] används:

![](assets/rollback-directive.png)
