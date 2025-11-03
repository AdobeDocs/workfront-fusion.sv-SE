---
content-type: reference
title: Direktiv för felhantering
description: I den här artikeln beskrivs direktiv som du kan använda för felhantering i dina Adobe Workfront Fusion-scenarier.
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: 99621f57da1eb294834a0eacfe527dcf017408e9
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Direktiv för felhantering

Med felhanteringsdirektiv kan du välja vad som ska hända när ett scenario påträffar ett fel.

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

+++## Direktiv för felhantering

Följande felhanteringsdirektiv finns i Workfront Fusion.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Återställning</p> <p> <img src="assets/rollback.png"> </p> </td> 
   <td> <ul><li><p>Scenariokörningen stoppas omedelbart.</li><li>En återställningsfas startas för alla moduler i ett försök att återställa alla till deras ursprungliga tillstånd. </li><li>Efterföljande moduler bearbetas inte.</p></li><li> <p>I de flesta fall inaktiveras scenariot efter det antal på varandra följande fel som anges under scenarieinställningarna. Mer information finns i <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors" class="MCXref xref">Antal efterföljande fel</a>.</p> </li><li><p>Scenariots körningsstatus är markerad som "Fel".</p></li></ul> <p><b>Obs!</b>: Detta är standardbeteendet om ingen felhanterarväg är kopplad till modulen och om inställningen <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions" class="MCXref xref">Tillåt lagring av ofullständiga körningar</a>Tillåt lagring av ofullständiga körningar under [!UICONTROL Scenario settings] inte är markerad.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Verkställ</p> <p> <img src="assets/commit.png"> </p> </td> 
   <td> <ul><li><p>Scenariokörningen stoppas omedelbart.</li><li>En implementeringsfas startas för alla moduler. </li><li>Efterföljande moduler bearbetas inte.</p></li><li> <p>Alla obearbetade paket ignoreras.</p> </li><li><p>Scenariots körningsstatus är markerad som "success". </p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Återuppta</p> <p> <img src="assets/resume.png"> </p> </td> 
   <td> <ul><li><p>Ett ersättningsutdata anges och skickas till modulen som påträffar ett fel.</p> </li><li><p>Efterföljande moduler bearbetas.</p></li><li> <p>Scenariots körningsstatus är markerad som "success".</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Ignorera</p> <p> <img src="assets/ignore.png"> </p> </td> 
   <td><ul><li> <p>Felet ignoreras.</li><li> Efterföljande moduler bearbetas inte.</p> </li><li><p>Om det finns obearbetade paket fortsätter scenariokörningen normalt.</p> </li><li><p>Scenariots körningsstatus är markerad som "success".</p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Brytning</p> <p> <img src="assets/break.png"> </p> </td> 
   <td><ul><li> <p>Scenario-körningens tillstånd lagras i kön med ofullständiga körningar där felet kan lösas manuellt. Mer information finns i <a href="/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md" class="MCXref xref">Visa och lösa ofullständiga körningar</a>.</p> <p>Det finns dock några undantag. Mer information finns i <a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow" class="MCXref xref">Tillåt lagring av ofullständiga körningar</a> i artikeln Konfigurera scenarioinställningar</a>.</p></li><li> <p>Efterföljande moduler bearbetas inte.</p></li><li> <p>Om det finns obearbetade paket fortsätter scenariokörningen normalt.</p> </li><li><p>Scenariots körningsstatus är markerad som "varning" när alternativet [!UICONTROL Automatically complete execution] är inaktiverat.</p></li></ul> <p>Mer information finns i avsnittet <a href="#break" class="MCXref xref">[!UICONTROL Break]</a> i den här artikeln</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Försök igen</p> <p> <img src="assets/retry.png"> </p> </td> 
   <td> <p>I vissa fall kan det vara användbart att köra en felande modul igen när det finns en möjlighet att orsaken till felet kan passera över tiden.</p> <p>Workfront Fusion innehåller för närvarande inte direktivet Retry, men det går att använda flera tillfälliga lösningar för att efterlikna dess funktionalitet. Mer information finns i <a href="/help/workfront-fusion/create-scenarios/config-error-handling/retry.md" class="MCXref xref">Försök hantera fel igen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* Felhanteringsdirektiv kan inte användas utanför en felhanteringsväg.
>* I Workfront Fusion finns för närvarande ingen Throw-modul som gör att du enkelt kan generera (utlösa) fel på ett villkorligt sätt, även om du kan använda en tillfällig lösning för att efterlikna dess funktionalitet.
>
>  Mer information finns i [Konfigurera `throw` fellösning](/help/workfront-fusion/create-scenarios/config-error-handling/throw.md).

## Resurser

* Mer information om återställning och återställningsfasen finns i [Återställning](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) i artikeln Körning av scenarier, cykler och faser.
* Mer information om implementeringsfasen finns i [Verkställ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#commit) i artikeln Körning av scenarier, cykler och faser.
