---
title: Visa kontrollpanelen för prestanda för en organisation
description: Fusion-administratörer kan visa en kontrollpanel som visar en organisations exekveringsvärden.
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
source-git-commit: b4c9cd075cc2bb7aa3d5c568bb91fb8ce5c6f31e
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Visa kontrollpanelen för prestanda för en organisation

Med Fusion Performance Dashboard kan du snabbt se vilka scenarier som körs mest, var fördröjningar inträffar och hur effektivt dina arbetarpooler fungerar. Detta ger realtidsinsyn i körningsvolymer, ködjup, poolanvändning och prestanda på scenarienivå.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Adobe Workfront Workflow Ultimate och Adobe Workfront Automation and Integration Ultimate</p><p>Workfront Ultimate</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licenser</td> 
   <td> <p>Standard</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Komponenter i kontrollpanelen för prestanda

>[!NOTE]
>
>Mätvärden visas av arbetarpoolen. Om du vill visa en annan arbetarpool klickar du på fältet Pool i det övre vänstra hörnet av instrumentpanelen och väljer sedan den pool som du vill visa mätvärden för.

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

På kontrollpanelen för Fusion-prestanda kan du se följande mätvärden.

* **Körningar väntar på att bearbetas**
I det här diagrammet visas antalet körningar som väntar på att bearbetas (kallas även körningseftersläpning) vid en viss tidpunkt.

  Ett stort antal körningar som väntar på att bearbetas kan påverka prestanda i Fusion-instansen. Du får ett meddelande om din exekveringstid når 5 000 exekveringar. Vi rekommenderar att du identifierar ansvariga scenarier och ändrar eller inaktiverar dem. Om eftersläpningen med höga exekveringsfel kvarstår skyddar Fusion-teamet prestanda för din Fusion-instans genom att inaktivera de ansvariga scenarierna.
* **Poolanvändning**
I det här diagrammet visas användningen av arbetarpooler över tiden. Om det här diagrammet regelbundet visar användningen av arbetspoolen kanske du vill tilldela en annan pool vissa scenarier.

  Om en pool närmar sig 100 % utnyttjande kan andra resurser som använder samma pool fördröjas eller störas. Om detta inträffar rekommenderar vi att du omtilldelar ett scenario med hög användning till en annan arbetarpool eller ändrar befintliga scenarier så att de blir mindre resurskrävande.
* **Körningar per scenario**
I det här diagrammet visas körningar per scenario. Olika färger representerar olika scenarier. När du håller pekaren över diagrammet visas ett fönster som visar vilken färg som är det scenario som ska användas.

  Du kan använda det här diagrammet för att identifiera vilka scenarier som kan orsaka en exekveringseftersläpning eller användning av hög arbetarpool.
* **Varaktighet för körningar**
I det här diagrammet visas körningar per scenario. Olika färger representerar olika scenarier. När du håller pekaren över diagrammet visas ett fönster som visar vilken färg som är det scenario som ska användas.

  Du kan använda det här diagrammet för att identifiera scenarier som tar längre tid än vanligt, inklusive de som påverkas av problem med en ansluten app eller tjänst.

## Visa Fusion Performance Dashboard

1. Klicka på Prestanda i den vänstra navigeringen i Fusion.

   Kontrollpanelen öppnas.

1. Om du vill visa data för en viss tidpunkt håller du pekaren över kontrollpanelen och justerar markören så att den är över den tidpunkt som du vill visa.

   En linje visas över den tidpunkten i alla diagram och ett fönster med data för den tiden visas i varje diagram.
1. Om du vill visa data för ett specifikt scenario i diagrammet Körningar per scenario eller Körningstidens varaktighet, klickar du på ett fält i färgen för det scenario du vill visa data för. Om du vill återgå till vyn med alla scenarier klickar du på diagrammet igen.
1. Om du vill gå till ett specifikt scenario som visas i diagrammet Körningar per scenario eller Körningsplanens varaktighet högerklickar du på en färgstapel för scenariot och väljer **Öppna scenario på den nya fliken**.
1. Om du vill expandera ett diagram klickar du på ikonen **Expandera** ![Expandera](assets/expand-icon.png) längst upp till höger i det diagrammet.
1. Om du vill ändra tidsintervallet för kontrollpanelen markerar du fältet Tidsintervall i det övre högra hörnet av kontrollpanelen och väljer sedan en ny tidsram. Den längsta tillgängliga tidsramen är 24 timmar och den kortaste är 15 minuter.
1. Om du vill uppdatera diagrammen klickar du på ikonen Uppdatera i det övre högra hörnet av kontrollpanelen.
1. Om du vill visa en annan arbetarpool klickar du på fältet Pool i det övre vänstra hörnet av instrumentpanelen och väljer sedan den pool som du vill visa.



