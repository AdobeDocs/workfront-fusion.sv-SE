---
title: Kedjemoduler
description: Med hjälp av de här modulerna kan du kedja ihop olika scenarier och göra ett anrop till ett annat.
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# Kedjemoduler

Med hjälp av kedjemodulerna kan du koppla ett scenario till ett annat.

<!--This article will be about the specific module configuration-->

Instruktioner om hur du planerar kedjade scenarier finns i [Kedja flera scenarier tillsammans](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md).


## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens</td> 
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Workfront Fusion-licens krävs inte</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront package: Your organization must purchase Adobe Workfront Fusion.</li><li>Ultimate Workfront-paket: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Kedjemoduler och deras fält

### Utlösare

#### Ta emot data från överordnad

Den här modulen är utlösarmodulen i det underordnade scenariot och utlöses av Anropa en underordnad scenariomodul i det överordnade scenariot. Den tar emot data från det överordnade scenariot, som kan bearbetas i det underordnade scenariot.

Så här konfigurerar du Ta emot data från överordnad modul:

1. Om du vill använda en befintlig datastruktur i fältet Datastruktur väljer du den datastruktur som ska användas för scenariots indata.

   eller

   Om du vill skapa en ny datastruktur som ska användas som indatadata för scenariot klickar du på **Lägg till** bredvid fältet Datastruktur och skapar datastrukturen.

   Instruktioner om hur du skapar en datastruktur finns i [Datastrukturer](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

1. Klicka på **OK** för att spara modulen.

### Åtgärder

#### Anropa ett underordnat scenario

Den här modulen finns i det överordnade scenariot. Fälten återspeglar datastrukturen som angetts i Ta emot data från den överordnade modulen i det underordnade scenariot.

>[!NOTE]
>
>* Du kan välja ett befintligt underordnat scenario eller skapa ett nytt med denna modul.
>* Du kan skapa datastrukturen när du skapar ett underordnat scenario.

Konfigurera modulen Anropa ett underordnat scenario

1. Lägg till modulen Anropa ett underordnat scenario i ditt scenario.
1. Om du vill använda ett befintligt underordnat scenario markerar du det underordnade scenariot som du vill anropa i fältet Kedja.

   eller

   Om du vill skapa ett nytt underordnat scenario klickar du på Lägg till bredvid fältet Kedja. Det underordnade scenariot visas i ett separat fönster, där det överordnade och det överordnade svaret för Ta emot data från och Returnera svar från överordnade moduler är på plats.

   De fält som är konfigurerade i utlösarmodulen för det underordnade scenariot visas i modulen Anropa ett underordnat scenario.

1. Ange eller mappa den information som ska skickas till det underordnade scenariot till modulen Anropa ett underordnat scenario.
1. (Villkorligt) Om du vill att det överordnade scenariot ska fortsätta att köras utan att vänta på ett svar från det underordnade scenariot aktiverar du alternativet **Avsluta och glöm**.
1. Klicka på **OK** för att spara modulen.

>[!NOTE]
>
>Om du skapar ett nytt underordnat scenario för den här modulen öppnas det underordnade scenariot i ett separat webbläsarfönster så att du kan visa och konfigurera både det överordnade och det underordnade scenariot samtidigt.

#### Returnera svar till överordnad

Detta är i det underordnade scenariot och skickar data i den valda strukturen till det överordnade scenariot. Du kan mappa dessa data i senare moduler i det överordnade scenariot.

Om ditt underordnade scenario har flera vägar rekommenderar vi att du lägger till den här modulen till en väg som alltid körs och körs efter en annan väg.

Så här konfigurerar du modulen Lägg till svarare:

1. Om du vill använda en befintlig datastruktur markerar du den datastruktur som ska användas för de data som det underordnade scenariot returnerar till det överordnade scenariot i fältet Datastruktur.

   eller

   Om du vill skapa en ny datastruktur för data klickar du på **Lägg till** bredvid datastrukturfältet och skapar datastrukturen.

   Instruktioner om hur du skapar en datastruktur finns i [Datastrukturer](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md).

1. Klicka på **OK** för att spara modulen.
