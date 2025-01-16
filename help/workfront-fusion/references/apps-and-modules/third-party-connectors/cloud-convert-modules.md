---
title: CloudConvert-moduler
description: CloudConvert-moduler
author: Becky
feature: Workfront Fusion
exl-id: 52c4d18a-8bee-44d6-9a2c-cc9e157e1dde
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2487'
ht-degree: 0%

---

# [!DNL CloudConvert] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder CloudConvert samt ansluta det till flera tredjepartsprogram och -tjänster. Med modulerna [!DNL CloudConvert] kan du övervaka och hantera jobb, uppgifter samt importera och exportera filer i ditt [!DNL CloudConvert]-konto.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## API-information för CloudConvert

CloudConvert-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://api.cloudconvert.com/v2/</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.14.22</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL CloudConvert] till [!DNL Workfront Fusion] {#connect-cloudconvert-to-workfront-fusion}

Om du vill ansluta ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] måste du hämta API-nyckeln från ditt [!DNL CloudConvert]-konto.

1. Logga in på ditt [!DNL CloudConvert]-konto och öppna [!UICONTROL Dashboard].
1. Öppna avsnittet **[!UICONTROL Authorization]>[!UICONTROL API Keys]**.
1. Klicka på **[!UICONTROL Create New API key]**.
1. Ange namnet på API-nyckeln, aktivera de scope som du vill använda och klicka sedan på **[!UICONTROL Create]**.
1. Kopiera den angivna token och lagra den på en säker plats.
1. I [!DNL Workfront Fusion] börjar du skapa ett scenario och öppnar dialogrutan **[!UICONTROL Create a connection]** för modulen [!DNL CloudConvert].

   Instruktioner finns i [Skapa ett scenario i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

1. Ange den token som du sparade i steg 5 och klicka sedan på **[!UICONTROL Continue]** för att upprätta anslutningen.

## [!DNL CloudConvert]-moduler och deras fält {#cloudconvert-modules-and-their-fields}

När du konfigurerar [!DNL CloudConvert] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL CloudConvert] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Vanliga uppgifter](#common-tasks)
* [Jobb](#jobs)
* [Uppgifter](#tasks)
* [Övriga](#other)

### Vanliga uppgifter

* [Hämta en webbplats](#capture-a-website)
* [[!UICONTROL Convert a file]](#convert-a-file)
* [Skapa ett arkiv](#create-an-archive)
* [Sammanfoga filer](#merge-files)
* [Optimera en fil](#optimize-a-file)

#### [!UICONTROL Capture a Website]

Den här åtgärdsmodulen hämtar en angiven webbplats och sparar den i PDF, JPG eller PNG-format.

Du anger webbplatsens URL och annan information, till exempel var du vill att informationen ska lagras.

Modulen returnerar filens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange URL-adressen till den webbplats du vill hämta. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format] </td> 
   <td>Välj om du vill spara den hämtade webbplatsen i PNG-, JPG- eller PDF-format. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td>Ange ett filnamn (inklusive filtillägg) för målutdatafilen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>(Valfritt) Definiera begäranderubriker. </p> <p>Detta är användbart när den angivna URL:en kräver auktorisering. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Conversion and engine specific options] </p> </td> 
   <td>Ange konverterings- och motorspecifika alternativ. Information om tillgängliga alternativ finns i <a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API </a> -dokumentationen för <code>input_format</code> och <code>output_format</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a file] </td> 
   <td> <p>Aktivera det här alternativet om du även vill inkludera fildata i modulens utdata.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Convert a file]

Konverterar en fil till ett valt utdataformat.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input file]</td> 
   <td>Välj om du vill överföra en fil med [!DNL Workfront Fusion] eller ange den URL som filen ska överföras från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Import a File from URL]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL URL]</strong> </p> <p>Ange URL-adressen till filen som du vill konvertera.</p> </li> 
     <li> <p><strong>[!UICONTROL Headers]</strong></p> <p>Definiera begäranderubriker (valfritt). Detta är användbart när den angivna URL:en kräver behörighet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Format]</td> 
   <td>Välj om du vill ange indataformatet för filen som du vill konvertera. Om inget anges används indatafilens tillägg som indataformat.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Input Format]</td> 
   <td>Välj filens aktuella format.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td>Välj det målfilformat som du vill konvertera filen till.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL File Name]</td> 
   <td>Välj ett filnamn (inklusive filtillägg) för målutdatafilen.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Conversion and engine specific options] </p> </td> 
   <td>Ange konverterings- och motorspecifika alternativ. Information om tillgängliga alternativ finns i <a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API </a> -dokumentationen för <code>input_format</code> och <code>output_format</code>.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Download a file] </td> 
   <td> <p>Aktivera det här alternativet om du även vill inkludera fildata i modulens utdata.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an Archive]

Gör att du kan lägga till en eller flera filer i arkivet ZIP, RAR, 7Z, TAR, TAR.GZ eller TAR.BZ2.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Input Files]</p> </td> 
   <td> <p>Ange filer som du vill lägga till i arkivet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a file from URL]</p> </td> 
   <td> <p><strong>[!UICONTROL URL]</strong> </p> <p>Ange URL-adressen till filen som du vill arkivera.</p> <p><strong>[!UICONTROL Headers]</strong> </p> <p>Definiera begäranderubriker (valfritt). Detta är användbart när den angivna URL:en kräver behörighet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p> Välj målformatet för den arkiverade filen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p> Ange filnamnet (inklusive filtillägg) för målutdatafilen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options] </td> 
   <td> <p>Ange konverterings- och motorspecifika alternativ. Information om tillgängliga alternativ finns i <a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API </a> -dokumentationen för <code>input_format</code> och <code>output_format</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a File]</td> 
   <td> <p>Aktivera det här alternativet om du även vill inkludera fildata i modulens utdata.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Merge Files]

Sammanfogar minst två filer till en PDF. Om indatafilerna inte är PDF konverteras de automatiskt till PDF.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Input Files]</p> </td> 
   <td> <p>Ange de filer som du vill sammanfoga.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a file from URL]</p> </td> 
   <td> <p><strong>[!UICONTROL URL]</strong> </p> <p>Ange URL-adressen till filen som du vill arkivera.</p> <p><strong>[!UICONTROL Headers]</strong> </p> <p>Definiera begäranderubriker (valfritt). Detta är användbart när den angivna URL:en kräver behörighet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p> Välj målformatet för den sammanfogade filen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p> Ange filnamnet (inklusive filtillägg) för målutdatafilen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options] </td> 
   <td> <p>Ange konverterings- och motorspecifika alternativ. Information om tillgängliga alternativ finns i <a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API </a> -dokumentationen för <code>input_format</code> och <code>output_format</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a File]</td> 
   <td> <p>Aktivera det här alternativet om du även vill inkludera fildata i modulens utdata.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Optimize a File]

Den här åtgärdsmodulen optimerar och komprimerar en fil i formatet PDF, PNG eller JPG.

Du anger filen och parametrarna för optimering och lagring.

Modulen returnerar filens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input File]</td> 
   <td>Ange om du vill överföra en fil med Workfront Fusion eller ange den URL som filen ska överföras från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Upload a File]</p> </td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Import a file from URL] </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL URL]</strong>: Ange URL-adressen till filen som du vill konvertera.</li> 
     <li><strong>[!UICONTROL Headers]</strong>: (Valfritt) Definiera begäranderubriker. Detta är användbart när den angivna URL:en kräver auktorisering.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Optimization for] </td> 
   <td> <p>Välj optimeringsprofil för specifika målbehov.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Web]</strong>: Optimering för webben (standard)</p> 
      <ul> 
       <li>Ta bort överflödiga och onödiga data för webben</li> 
       <li>Nedsampla, klippa och komprimera bilder på ett intelligent sätt</li> 
       <li>Sammanfoga och skapa deluppsättningar av teckensnitt</li> 
       <li>Konvertera färger till RGB</li> 
      </ul> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL Print]</strong>: Optimering för utskrift</p> 
      <ul> 
       <li> <p>Ta bort överflödiga och onödiga data för utskrift</p> </li> 
       <li> <p>Nedsampla, klippa och komprimera bilder på ett intelligent sätt</p> </li> 
       <li> <p>Sammanfoga och skapa deluppsättningar av teckensnitt</p> </li> 
       <li> <p>Konvertera färger till CMYK</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Archive]</strong>: Optimering för arkiveringsändamål</p> 
      <ul> 
       <li> <p>Ta bort överflödiga och onödiga data för arkivering</p> </li> 
       <li> <p>Komprimera bilder på ett intelligent sätt</p> </li> 
       <li> <p>Sammanfoga och skapa deluppsättningar av teckensnitt</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Scanned images]</strong>: Optimering för skannade bilder</p> 
      <ul> 
       <li> <p>Profil optimerad för PDF som huvudsakligen består av rasterbilder</p> </li> 
       <li> <p>Komprimera bilderna utan att försämra den visuella kvaliteten avsevärt</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL maximal size reduction]</strong>: Optimering för maximal storleksminskning</p> 
      <ul> 
       <li> <p>Använd största möjliga komprimering</p> </li> 
       <li> <p>Kan minska den visuella kvaliteten</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input format] </td> 
   <td>Välj formatet för den indatafil som du vill optimera. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p>Ange ett filnamn (inklusive filtillägg) för målutdatafilen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options]</td> 
   <td> <p>Ange konverterings- och motorspecifika alternativ. Information om tillgängliga alternativ finns i <a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API </a> -dokumentationen för <code>input_format</code> och <code>output_format</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a file]</td> 
   <td> <p>Aktivera det här alternativet om du även vill inkludera fildata i modulens utdata.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Jobb

* [[!UICONTROL Create a Job (advanced)]](#create-a-job-advanced)
* [[!UICONTROL New Job Event]](#new-job-event)
* [[!UICONTROL List Jobs]](#list-jobs)
* [[!UICONTROL Get a Job]](#get-a-job)
* [[!UICONTROL Delete a Job]](#delete-a-job)

#### [!UICONTROL Create a Job (advanced)]

Den här modulen skapar ett jobb. Ett jobb kan vara en eller flera uppgifter som identifieras i fältet [!UICONTROL Name] och länkas mellan varandra med hjälp av fältet [!UICONTROL Input].

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input Files]</td> 
   <td> <p>Välj om du vill överföra en fil med [!DNL Workfront Fusion] eller ange den URL som filen ska överföras från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a File from URL]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL URL]</strong>: Ange URL-adressen till filen som du vill bearbeta.</li> 
     <li><strong>[!UICONTROL Headers]</strong>: (Valfritt) Definiera begäranderubriker. Detta är användbart när den angivna URL:en kräver auktorisering.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Tasks]</p> </td> 
   <td> <p>Lägg till uppgifter som ska utföras i jobbet.</p> <p>Beskrivningarna av operationsfälten finns i motsvarande avsnitt.</p> 
    <ul> 
     <li><a href="#convert-a-file" class="MCXref xref">[!UICONTROL Convert a file]</a> </li> 
     <li><a href="#capture-a-website" class="MCXref xref">[!UICONTROL Capture a Websit]e</a> </li> 
     <li><a href="#optimize-a-file" class="MCXref xref">[!UICONTROL Optimize a File]</a> </li> 
     <li><a href="#create-an-archive" class="MCXref xref">[!UICONTROL Create an Archive]</a> </li> 
     <li><a href="#merge-files" class="MCXref xref">[!UICONTROL Merge Files]</a> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL Execute a Command]</strong> </p> <p>Mer information om hur du kör ett kommando finns i <a href="https://cloudconvert.com/api/v2/command#command-tasks">[!DNL CloudConvert] API-dokumentationen </a>.</p> </li> 
     <li> <p><strong>[!UICONTROL Export a File to Temporary URL]</strong> </p> <p> Ange aktivitetens namn och indatans aktivitetsnamn (t.ex. konvertering).</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag] </td> 
   <td> <p>Ange en tagg. Taggar är godtyckliga strängar som identifierar jobbet. De har ingen effekt och kan användas för att associera jobbet med ett ID.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Job]

Den här modulen tar bort ett jobb, inklusive alla uppgifter och data.

>[!NOTE]
>
>Jobb tas bort automatiskt 24 timmar efter att de har avslutats.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Job]

Den här modulen hämtar jobbinformation.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Jobs]

Den här modulen hämtar alla jobb som har körts i ditt konto.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status] </td> 
   <td> <p>Välj jobbstatus att filtrera returnerade jobb efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange antalet jobb som Workfront Fusion 2.0 ska returnera under en körningscykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL New Job Event]

Utlöses när ett jobb i ditt konto eller din uppgift skapas, avslutas eller misslyckas.

>[!NOTE]
>
>* Jobbet som skapas av modulen [!UICONTROL Create a Job (advanced)] består av *flera* uppgifter.
>* Utlösaren [!UICONTROL New Job Event] aktiveras också när en *enskild*-aktivitet skapas, har slutförts eller misslyckats.
>

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhhook name]</td> 
   <td>Ange webbkrokens namn. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format] </td> 
   <td>Välj om du vill spara den hämtade webbplatsen i PNG-, JPG- eller PDF-format. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event]</td> 
   <td>Ange om modulen ska aktiveras när jobbet eller uppgiften skapas, avslutas eller misslyckas.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* Om du arbetar med Array Aggregator (du t.ex. har många filer i olika format att konvertera) använder du alternativet **[!UICONTROL I don't know the input format]** i dialogrutan [!UICONTROL Add a task]. Annars returneras felet.
>* Länkar aktiviteter inom jobbet (namn > indata, namn > indata,..):
>
>  ![](/help/workfront-fusion/references/apps-and-modules/assets/linking-name-across-jobs-350x808.png)>

### Uppgifter

* [[!UICONTROL Get a Task]](#get-a-task)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL List Tasks]](#list-tasks)
* [[!UICONTROL Retry a Task]](#retry-a-task)
* [[!UICONTROL Cancel a Task]](#cancel-a-task)
* [[!UICONTROL Delete a Task]](#delete-a-task)

#### [!UICONTROL Cancel a Task]

Den här modulen avbryter en aktivitet som har statusen Väntar eller Bearbetning.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> Ange eller mappa ID:t för uppgiften som du vill avbryta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Task]

Ta bort en uppgift, inklusive alla data.

>[!NOTE]
>
>Uppgifter tas bort automatiskt 24 timmar efter att de har avslutats.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> Ange (mappa) ID:t för uppgiften som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

Den här modulen hämtar filnamn och fildata från den angivna aktiviteten.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> Ange eller mappa ID:t för uppgiften som du vill hämta filen från.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Task]

Den här modulen hämtar aktivitetsinformation.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p>Ange eller mappa ID:t för uppgiften som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Tasks]

Den här modulen hämtar alla uppgifter i ditt konto baserat på filterinställningar.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status] </td> 
   <td> <p>Välj uppgiftsstatus för att filtrera returnerade uppgifter efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID] </td> 
   <td> <p>Ange eller mappa jobb-ID:t så att det endast returnerar uppgifter inom det angivna jobbet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>Ange åtgärdstypen om du bara vill returnera uppgifter med den angivna åtgärden. </p> <p>Obs! Använd modulen [!UICONTROL List Possible Operations] för att hämta åtgärder.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Retry a Task]

Den här modulen skapar en ny uppgift baserat på inställningarna (nyttolast) för en annan uppgift.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> Ange eller mappa ID:t för uppgiften som du vill skapa en ny uppgift från.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [[!UICONTROL Get My Info]](#get-my-info)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Get My Info]

Hämtar autentiserad kontoinformation om den aktuella användaren.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL CloudConvert]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL CloudConvert] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Gör att du kan utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [Fusion App]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>Ange en relativ sökväg till <code>https://api.cloudconvert.com/</code>. Exempel: <code>/v2/tasks</code></p> <p>En lista över tillgängliga slutpunkter finns i <a href="https://cloudconvert.com/api/v2">[!DNL CloudConvert] API v2-dokumentationen </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion 2.0 lägger till behörighetshuvuden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödtexten för API-anropet i form av ett standard-JSON-objekt. Om du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.<img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel:** Listaktiviteter

Följande API-anrop returnerar alla uppgifter från ditt CloudFront-konto:

URL: `/v2/tasks`

Metod: `GET`

![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-api-example-input.png)

Det går att hitta matchningar av sökningen i modulens utdata under [!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL data].

I vårt exempel returnerades 6 uppgifter:

![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-api-example-output.png)

## Felsökning {#troubleshooting}

I följande tabell finns information om möjliga fel och deras lösningar:

<table style="table-layout:auto">
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> <p>Fel</p> </th> 
   <th>Nästa steg</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL The output file size exceeds the limit allowed for your scenario.]</span> </p> </td> 
   <td> <p>Se filstorleksbegränsningarna.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL You have exceeded the maximum conversion time.]</span> </p> </td> 
   <td> <p>Kostnadsfri [!DNL CloudConvert]-plan erbjuder 25 konverteringsminuter dagligen. Om din användning överskrider gränsen för kostnadsfri prenumeration kan du byta till ett (förbetalt) paket eller en prenumeration.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL Failed to read frame size: Could not seek to 1508. �/output/JLIADSA00137P0.mp3: Invalid argument.]</span> </p> </td> 
   <td> <p>Detta fel inträffar t.ex. vid konvertering av filer från MP3 till WAV. Se till att du har valt rätt region eftersom den kommer att hitta referenser till filer, men inte bara till rätt fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL RuntimeError:] </p> <p><span style="font-weight: normal;">[!UICONTROL Maximum number of repeats exceeded.]</span> </p> </td> 
   <td> <p>Leta reda på motsvarande [!DNL CloudConvert]-jobb i [!DNL CloudConvert]-kontrollpanelens lista över jobb och kontrollera jobbets varaktighet:</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-duration-350x177.png" style="width: 350;height: 177;"> </p> <p>Tidsgränsen för modulen [!DNL CloudConvert] &gt; [!UICONTROL Convert a File] är 3 minuter. Om jobbets varaktighet överstiger 3 minuter (möjligen på grund av en tillfällig överbelastning av tjänsten [!DNL CloudConvert]), genereras felet ovan i modulen.</p> <p>Här bör du tänka på något av följande:</p> 
    <ul> 
     <li>Aktivera alternativet <strong>[!UICONTROL Allow storing of Incomplete Executions]</strong> i scenarioinställningarna för att lagra de ofullständiga körningarna för senare manuell lösning. Du kan också koppla en felhanteringsväg till modulen [!DNL CloudConvert] med direktivet [!UICONTROL Break] för att lösa de ofullständiga körningarna automatiskt.</li> 
     <li>Inaktivera alternativet <strong>[!UICONTROL Download a file] </strong> i modulen [!DNL CloudConvert] &gt; [!UICONTROL Convert a file]. I det här fallet väntar modulen inte på konverteringsresultatet. Skapa ett nytt scenario och använd utlösaren [!DNL CloudConvert] &gt; [!UICONTROL New Job Event] för att få konverteringsresultatet.</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelarbetsflöde för [!DNL CloudConvert]-koppling

>[!INFO]
>
>**Exempel:** Konverterar en video från MOV till MP4-format
>
>1. Besök [https://cloudconvert.com/video-converter](https://>cloudconvert.com/video-converter)
>1. Klicka på **[!UICONTROL Select File]** och välj MOV-exempelfilen.
>1. Klicka på listrutan bredvid **[!UICONTROL Convert to]** och välj **[!UICONTROL MP4]**.
>
>1. Klicka på ikonen **[!UICONTROL wrench]**.
>1. Konfigurera inställningarna för MP4-komprimering så som du vill ha dem.
>1. Klicka på **[!UICONTROL Convert]**.
>1. När konverteringen är klar klickar du på **[!UICONTROL Download]**.
>1. Granska den konverterade videon.
>1. Upprepa steg 1 till 8 tills du har hittat de optimala konverteringsinställningarna för steg 5.
>1. Besök [https://cloudconvert.com/api/v2/convert#convert-tasks](https://cloudconvert.com/api/v2/convert#convert-tasks)
>1. Välj **[!UICONTROL mov]** som **[!UICONTROL input_format]**-fält.
>
>1. Välj **[!UICONTROL mp4]** som **[!UICONTROL output_format]**-fält.
>
>1. En lista med alla möjliga parametrar som video_codec, crf, osv. visas.
>1. I Workfront Fusion 2.0 infogar du modulen **[!UICONTROL CloudConvert]** > **[!UICONTROL Convert a File]** i ditt scenario.
>
>1. Öppna modulens inställningar.
>1. Konfigurera modulen enligt nedan:
>
>   ![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-mp4-example.png)
>
>1. Se till att inkludera alla inställningar i fältet Konvertering och motorspecifika alternativ: för varje inställning från steg 5 letar du reda på motsvarande parameter från steg 13 och dess motsvarande värde.
