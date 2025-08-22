---
title: Arkivera moduler
description: I ett Adobe Workfront Fusion-scenario kan du ansluta ett arkiv, t.ex. en zippad fil, till flera tredjepartsprogram och -tjänster. Du kan till exempel konfigurera ett scenario som
author: Becky
feature: Workfront Fusion
exl-id: 4b5ff3d5-601c-4119-ad70-3612ad5ba1ab
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# [!UICONTROL Archive] moduler

I ett Adobe Workfront Fusion-scenario kan du använda ett arkiv, t.ex. en zippad fil, så att du kan använda den i dina automatiseringar eller integreringar.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## [!UICONTROL Archive]-moduler och deras fält

När du konfigurerar [!UICONTROL Archive]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!UICONTROL Archive] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärder](#actions)
* [Aggregatorer](#aggregators)
* [Transformers](#transformers)

## Åtgärder

### [!UICONTROL Extract an archive]

Denna åtgärdsmodul extraherar en fil som du identifierar från ett arkiv.

Modulen returnerar filens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>  <p>Välj en källfil från en tidigare modul eller mappa källdata.</p></p>  </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:** Hämta ZIP-filen från den definierade [!DNL Dropbox]-mappen (till exempel Arkiv), extrahera den med modulen [!UICONTROL Archive] och skicka extraherade filer till den önskade e-postadressen som bilagor med modulen [!UICONTROL Email] eller [!DNL Gmail].

![Exempel på Dropbox](/help/workfront-fusion/references/apps-and-modules/assets/example-dropbox-350x134.png)

>[!ENDSHADEBOX]

## Aggregatorer

### [!UICONTROL Create an archive]

Den här aggregeringsmodulen lägger till önskade filer i ett [!UICONTROL ZIP]-, GZIP- eller [!UICONTROL TAR]-arkiv.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module]</td> 
   <td> <p> Markera modulen som du vill hämta filerna från.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type] </td> 
   <td> <p>Välj om du vill lägga till filer i ett [!UICONTROL ZIP]-, GZIP- eller [!UICONTROL TAR]-arkiv.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>Skriv en kommentar som du vill lägga till i arkivet.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Group by]</td> 
   <td> <p>Definiera ett uttryck som du vill gruppera aggregerade utdata med. Det här uttrycket kan innehålla ett eller flera mappade objekt. De aggregerade data delas sedan upp i grupper med hjälp av det här uttryckets värde. Varje grupp skickar som ett separat paket med en nyckel (det utvärderade uttrycket) och ett värde (den sammanställda texten). Du kan använda nyckeln som ett filter i efterföljande moduler.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Välj det här alternativet om du vill stoppa scenariot när det inte finns några resultat.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Archive name]</td> 
   <td> <p> Ange ett namn för det skapade arkivet. Lägg inte till ett tillägg.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:** Titta på inkommande e-post med modulen [!DNL Gmail] >[!UICONTROL Watch emails]. Om ett e-postmeddelande tas emot itereras dess bilagor in i enskilda paket, arkiveras sedan i filen [!DNL ZIP] och sparas i den definierade Dropbox-mappen.

![Exempel på Gmail](/help/workfront-fusion/references/apps-and-modules/assets/example-gmail-350x102.png)

>[!ENDSHADEBOX]

## Transformers

* [[!UICONTROL Deflate]](#deflate)
* [[!UICONTROL Inflate]](#inflate)

### [!UICONTROL Deflate]

Den här transformatormodulen komprimerar binära data med en deflationsalgoritm.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>Ange eller mappa de data som du vill komprimera med hjälp av deflate-funktionen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Inflate]

Den här transformatormodulen dekomprimerar binära data med en inflationsalgoritm.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Data] </td> 
   <td> <p>Ange eller mappa de data som du vill expandera med funktionen inflate.</p> </td> 
  </tr> 
 </tbody> 
</table>
