---
title: Datalagermoduler
description: Ett  [!DNL Adobe Workfront Fusion] datalager, som liknar en databas eller en enkel tabell, kan lagra data från scenarier, vilket gör det möjligt att överföra data mellan enskilda scenarier eller scenariokörningar. Du kan använda ett datalager för att lagra nya data från olika system under synkroniseringen.
author: Becky
feature: Workfront Fusion
exl-id: 0338b822-b345-429e-850d-3978b692231d
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 0%

---

# [!UICONTROL Data store] moduler

Ett [!DNL Adobe Workfront Fusion]-datalager, som liknar en databas eller en enkel tabell, kan lagra data från scenarier, vilket gör det möjligt att överföra data mellan enskilda scenarier eller scenariokörningar. Du kan använda ett datalager för att lagra nya data från olika system under synkroniseringen.

Med datalagermodulerna kan du lägga till, ersätta, uppdatera, hämta, ta bort, söka efter eller räkna poster i datalagret [!DNL Adobe Workfront Fusion].

<!--For information on creating, editing, and troubleshooting data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/)-->

En videointroduktion till datalager i Workfront Fusion finns på:

* [Datalager](https://video.tv.adobe.com/v/3427029/){target=_blank}

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

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Om du vill använda [!UICONTROL Data Store] moduler måste du först skapa ett datalager.

Mer information om hur du skapar datalager finns i [Skapa och hantera datalager](/help/workfront-fusion/create-scenarios/map-data/data-stores.md).

## [!UICONTROL Data store]-moduler och deras fält

När du konfigurerar datalagermoduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare datalagerfält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Du behöver inte skapa någon anslutning för att använda datalager.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Lägg till/ersätta en post](#addreplace-a-record)
* [Kontrollera förekomsten av en post](#check-the-existence-of-a-record)
* [Antal poster](#count-records)
* [Ta bort en post](#delete-a-record)
* [Ta bort alla poster](#delete-all-records)
* [Hämta en post](#get-a-record)
* [Sök i poster](#search-records)
* [Uppdatera en post](#update-a-record)

### [!UICONTROL Add/Replace a Record]

Den här åtgärdsmodulen lägger till eller ersätter en post.

Du anger datalagret och postens nyckel.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

>[!NOTE]
>
>Modulen genererar ett fel när du försöker lägga till en post som redan finns i datalagret med samma namn, och alternativet [!UICONTROL Overwrite an existing record] är inaktiverat.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Välj eller lägg till datalagret där du vill skapa en post. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Ange den unika nyckeln för den post som du vill att modulen ska lägga till eller ersätta. Nyckeln kan användas senare för att hämta posten. Om du lämnar det här fältet tomt genereras en nyckel automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing record] </td> 
   <td> <p>Aktivera det här alternativet om du vill skriva över posten. Den post som du vill skriva över måste anges i fältet Nyckel ovan.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record] </td> 
   <td> <p>Ange önskade värden för postens fält.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Check the Existence of a Record]

Den här åtgärdsmodulen anger om en viss post finns.

Du anger datalagret och postens nyckel.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Välj det datalager som du vill kontrollera om posten finns.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Ange den unika nyckeln för den post som du vill att modulen ska kontrollera om den finns.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Count Records]

Den här åtgärdsmodulen numrerar posterna i ett datalager.

Du anger datalagret.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Markera det datalager som innehåller de poster som du vill räkna.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete a Record]

Den här åtgärdsmodulen tar bort en post.

Du anger datalagret och postens nyckel.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Välj det datalager som du vill kontrollera om posten finns.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Ange den unika nyckeln för den post som du vill ta bort modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete All Records]

Den här åtgärdsmodulen tar bort alla poster från ett visst datalager.

Du anger datalagret.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store] </td> 
   <td> <p>Markera det datalager som du vill ta bort alla poster från.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a Record]

Denna åtgärdsmodul hämtar en post.

Du anger datalagret och postens nyckel.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Välj det datalager som du vill hämta en post från</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Ange den unika nyckeln för den post som du vill hämta modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search Records]

Den här sökmodulen söker efter poster i ett objekt i datalagret som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Markera det datalager som du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>Ange filtret för sökningen.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Sort]</p> </td> 
   <td> <p style="font-weight: normal;">För varje fält som du vill sortera efter fyller du i följande fält:</p> <p style="font-weight: bold;">[!UICONTROL Key]</p> <p>Markera kolumnnamnet som du vill sortera resultaten efter.</p> <p style="font-weight: bold;">[!UICONTROL Order]</p> <p>Välj om du vill sortera resultaten i stigande eller fallande ordning.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p> Ange det maximala antalet sökresultat som [!DNL Workfront Fusion] returnerar under en körningscykel.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> Om det här alternativet är aktiverat fortsätter den väg som den här modulen är en del av bearbetningen, även om den här modulen inte returnerar några resultat.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update a Record]

Den här åtgärdsmodulen uppdaterar en post.

Du anger datalagret och postens nyckel.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data store]</td> 
   <td> <p> Välj eller lägg till datalagret där du vill skapa en post. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>Ange den unika nyckeln för den post som du vill att modulen ska uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Insert missing record] </td> 
   <td> <p>Aktivera det här alternativet om du vill skapa en ny post om posten med den angivna nyckeln inte redan finns.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record]</td> 
   <td> <p> Ange önskade värden i postens fält som du vill uppdatera.</p> </td> 
  </tr> 
 </tbody> 
</table>
