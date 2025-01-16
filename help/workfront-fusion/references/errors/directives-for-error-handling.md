---
content-type: reference
title: Direktiv för felhantering
description: I den här artikeln beskrivs direktiv som du kan använda för felhantering i dina  [!DNL Adobe Workfront Fusion] -scenarier.
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---

# Direktiv för felhantering

Med felhanteringsdirektiv kan du välja vad som ska hända när ett scenario påträffar ett fel.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> Nytt: Standard<p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] licens</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront]: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>


Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Direktiv för felhantering

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
>* [!DNL Workfront Fusion] har för närvarande ingen Throw-modul som gör att du enkelt kan generera (utlösa) fel villkorligt, men en tillfällig lösning kan användas för att efterlikna dess funktioner.
>
>  Mer information finns i [Konfigurera `throw` fellösning](/help/workfront-fusion/create-scenarios/config-error-handling/throw.md).

## Resurs

* Mer information om återställning och återställningsfasen finns i [Återställning](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback) i artikeln Körning av scenarier, cykler och faser.
* Mer information om implementeringsfasen finns i [Verkställ](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#commit) i artikeln Körning av scenarier, cykler och faser.
