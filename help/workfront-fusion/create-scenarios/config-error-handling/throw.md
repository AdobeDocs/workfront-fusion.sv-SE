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
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Konfigurera `throw`-fellösning

I vissa fall kanske du vill stoppa scenariokörningen följt av återställnings- eller implementeringsfasen, eller stoppa bearbetningen av en väg och eventuellt lagra den i kön med ofullständiga körningar.

För närvarande kan inte felhanteringsdirektiven användas utanför omfånget för en felhanterarväg, och Adobe Workfront Fusion innehåller inte någon modul som gör att du enkelt kan generera (utlösa) fel villkorligt.

Du kan använda följande tillfällig lösning för att efterlikna `throw`-felfunktionen.

Mer information om ofullständiga körningar finns i [Visa och lösa ofullständiga körningar i Adobe Workfront Fusion](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Mer information om felhanteringsdirektiv finns i [Direktiv om felhantering i Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

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

## Tillfällig lösning för `throw`

Om du vill att ett fel ska inträffa kan du konfigurera en modul så att den automatiskt misslyckas under åtgärden. En möjlighet är att använda modulen [!UICONTROL JSON] > [!UICONTROL Parse JSON], som är konfigurerad att generera ett fel (`BundleValidationError` i det här fallet):

![JSON-fel](assets/json-parse-json.png)

Du kan sedan bifoga ett av felhanteringsdirektiven till felhanteringsvägen:

* **Återställning**: Tvinga scenariokörningen att stoppa och utföra återställningsfasen.
* **Verkställ**: Tvinga scenariokörningen att stoppa och utföra implementeringsfasen.
* **Ignorera**: Stoppa bearbetning av en väg.
* **Brytning**: Stoppa bearbetningen av en väg och lagra den i kön med ofullständiga körningsmappar.

I följande exempel visas hur direktivet [!DNL Rollback] används:

![Återställningsdirektiv](assets/rollback-directive.png)
