---
title: Adobe Substansmoduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Adobe Substance] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
source-git-commit: 2e44c89d487100b3245b40f6927185a0ff12ef2f
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 0%

---

# [!DNL Adobe Substance] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Substance] samt ansluta det till flera tredjepartsprogram och -tjänster.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Innan du kan använda [!DNL Adobe Substance]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Substance]-konto.



## [!DNL Adobe Substance]-moduler och deras fält

När du konfigurerar [!DNL Adobe Substance]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Adobe Substance] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En asterisk bredvid fältnamnet i en modul anger ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Sammansatta bilder](#composites)
* [Scener](#scenes)
* [Blanksteg](#spaces)

### Sammansatta bilder

#### Generera sammansatt 3D-objekt

Den här åtgärdsmodulen genererar innehåll för en 3D-sammansättning som innehåller den valda hjälteresursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Andra fält</td> 
   <td>Konfigurera andra fält efter behov. Mer information om fält finns i <a href="https://s3d.adobe.io/docs#/operations/v1/composites/compose">Adobe Substance API-dokumentationen</a>.</td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">Camera name</td> 
   <td>Enter or map the name of an existing camera that has been previously defined in the source 3D file.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Content class</td> 
   <td>Select whether you want the composite to have the style of art or of a photo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Enable ground plane</td> 
   <td>Enable this to enable the auto-generated ground plane under the hero asset. This is useful if the 3D scene contains only a hero asset, without additional elements.</td> 
  </tr> -->
 </tbody> 
</table>

### Scener

* [Konvertera 3D-filer](#convert-3d-files)
* [Skapa 3D-scen](#create-3d-scene)
* [Beskriv 3D-scen](#describe-3d-scene)
* [Återge 3D-objekt](#render-3d-object)
* [Återge 3D-objekt (grundversion)](#render-3d-object-basic-version)

#### Konvertera 3D-filer

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Format</td> 
   <td>Välj det format som du konverterar filen till.</td> 
  </tr> 
<tr> 
   <td role="rowheader">Startpunkt för modell</td> 
   <td>Vid konvertering används vanligtvis den första filen som anses vara en giltig 3D-modell. Definiera den här startpunkten så att den blir olika när det finns flera alternativ.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Källor</td> 
   <td>För varje fil som du vill konvertera klickar du på <b> Lägg till objekt </b> och anger filinformationen.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa 3D-scen

Den här åtgärdsmodulen skapar en scen med resurser som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Kodning</td> 
   <td>Välj filtyp för scenen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filens basnamn</td> 
   <td>Ange eller mappa ett namn för utdatafilen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Andra fält</td> 
   <td>Konfigurera andra fält efter behov. Mer information om fält finns i <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/assemble">Adobe Substance API-dokumentationen</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Källor</td> 
   <td>För varje fil som du vill använda klickar du på <b> Lägg till objekt </b> och anger filinformationen.</td> 
  </tr> 
 </tbody> 
</table>

#### Beskriv 3D-scen

Den här åtgärdsmodulen hämtar information om 3D-sceninnehåll.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Scenfil</td> 
   <td>Ange eller mappa sökvägen till scenfilen som du vill beskriva.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Källor</td> 
   <td>För varje fil som du vill beskriva klickar du på <b> Lägg till objekt </b> och anger filinformationen.</td> 
  </tr> 
 </tbody> 
</table>

#### Återge 3D-objekt

Denna åtgärdsmodul återger en bild av en scen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
   <td role="rowheader">Andra fält</td> 
   <td>Konfigurera andra fält efter behov. Mer information om fält finns i <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render">Adobe Substance API-dokumentationen</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Källor</td> 
   <td>För varje fil som du vill använda klickar du på <b> Lägg till objekt </b> och anger filinformationen.</td> 
  </tr> 
 </tbody> 
</table>

#### Återge 3D-objekt (grundversion)

Den här åtgärdsmodulen återger en bild av en scen, men har färre alternativ än objektmodulen Återge 3D.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
   <td role="rowheader">Andra fält</td> 
   <td>Konfigurera andra fält efter behov. Mer information om fält finns i <a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render-basic">Adobe Substance API-dokumentationen</a>.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Källor</td> 
   <td>För varje fil som du vill använda klickar du på <b> Lägg till objekt </b> och anger filinformationen.</td> 
  </tr> 
 </tbody> 
</table>

### Blanksteg

#### Skapa utrymme

Med den här åtgärdsmodulen kan du överföra och tillfälligt lagra filer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Substance]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <td role="rowheader">Filnamn</td> 
   <td>Ange eller mappa namnet på filen som överförs.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Fildata</td> 
   <td>Ange eller mappa filens binära data.</td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn</td> 
   <td>Ange eller mappa ett namn för flerdelsformulärvärdet.</td> 
  </tr> 
 </tbody> 
</table>
