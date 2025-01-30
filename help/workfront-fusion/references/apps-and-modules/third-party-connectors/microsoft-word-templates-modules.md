---
title: Microsoft Word-mallmoduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Microsoft Word-mallar samt ansluta dem till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: a5ba5634-226b-4886-a4f1-3a14948c1605
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 0%

---

# [!DNL Microsoft Word Template] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Microsoft Word Templates] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Workfront Fusion for Work Automation and Integration </p>
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

Om du vill använda [!DNL Miscrosoft Word Templates] med [!DNL Adobe Workfront Fusion] måste du ha ett [!DNL Office 365]-konto. Du kan skapa en på `www.office.com`.



## Ansluter tjänsten [!DNL Office] till [!DNL Workfront Fusion]

Instruktioner om hur du ansluter ditt [!DNL Office]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

## Använder [!DNL Microsoft Word Templates] moduler

Du kan använda en [!DNL Microsoft Word Template]-modul för att sammanfoga data från flera webbtjänster till ett [!DNL Microsoft Word]-dokument.

Du kan till exempel använda den här [!DNL Microsoft Word]-mallen:

![Word-mall före](/help/workfront-fusion/references/apps-and-modules/assets/word-template-before-filled-350x62.png)

Så här skapar du det här dokumentet:

![Word-mallen fylld](/help/workfront-fusion/references/apps-and-modules/assets/word-template-exampled-filled-350x85.png)

## Om värdetaggar

En [!DNL Microsoft Word]-mall är ett vanligt [!DNL Microsoft Word]-dokument (.docx-fil) med särskilda taggar i texten som avgör var och hur data ska sammanfogas eller fyllas i. Det finns tre typer av taggar:

* [Enkel värdetagg](#simple-value-tag)
* [Villkorstagg](#condition-tag)
* [Loop-tagg](#loop-tag)

### Enkel värdetagg {#simple-value-tag}

En enkel värdetagg ersätts med ett motsvarande värde. Taggens namn motsvarar fältets [!UICONTROL Key]-värde, som är placerat inom dubbla klammerparenteser, till exempel `{{name}}`.

**Exempel:** Om du vill skapa ett dokument med texten &quot;Hi, Petr!&quot; kan du använda en [!DNL Microsoft Word Template]-modul för att skapa följande mall:

```
> Hi {{name}}!
```

Om du vill göra det ställer du in modulen enligt följande:

![Enkelt värde för Word-mall](/help/workfront-fusion/references/apps-and-modules/assets/word-template-simple-value-350x286.png)

### Villkorstagg {#condition-tag}

Du kan använda ett villkorsmärkord för att figursätta text som bara ska återges när vissa villkor uppfylls. Om du vill radbryta texten placerar du den mellan inledande och avslutande villkorstaggar, till exempel &quot;hasPhone&quot;, om villkoret är huruvida data innehåller ett telefonnummer eller inte. Namnet på en öppningstagg föregås av hash-tecknet #. Namnet på en avslutande tagg föregås av ett snedstreck /, vilket visas i exemplet nedan.

**Exempel:** Om du vill skapa ett dokument som innehåller en kunds telefonnummer om indata innehåller ett telefonnummer, men ingen e-postadress, kan du använda en [!DNL Microsoft Word Template]-modul och skapa följande mall:

```
> {{#hasPhone}}Phone: {{phone}} {{/hasPhone}}
> {{#hasEmail}}Email: {{email}} {{/hasEmail}}
```

Om du vill göra det ställer du in modulen enligt följande:

![Villkorlig Word-mall](/help/workfront-fusion/references/apps-and-modules/assets/word-template-conditional-350x501.png)

I dokumentet visas telefonnumret så här:

```
> Phone: 4445551234
```

### Loop-tagg {#loop-tag}

Du kan använda en loop-tagg, som också kallas avsnittstagg, för att upprepa ett textavsnitt. Radbryt texten genom att placera den mellan de inledande och avslutande looptaggarna. Namnet på en öppningstagg föregås av hash-tecknet #; namnet på en avslutande tagg föregås av ett snedstreck /.

**Exempel:** Om du vill skapa ett dokument med namn och telefonnummer för varje kontakt i en kundlista kan du använda en [!DNL Microsoft Word Template]-modul och skapa följande mall:

```
> {{#contact}}
>     {{name}}, {{phone}}
> {{/contact}}
```

Om du vill göra det ställer du in modulen enligt följande:


![Fylla i ett dokument](/help/workfront-fusion/references/apps-and-modules/assets/word-template-fill-out-a-document-350x732.png)

Modulen skulle skapa följande dokument:

```
> Jan Toman, 4445551234
> Eduard Salo, 4445552345
```

## [!DNL Microsoft Word Template] moduler

Dessa moduler kräver ingen anslutning.

* [Fylla i ett dokument](#fill-out-a-document)
* [Fylla ett dokument med en datauppsättning](#fill-a-document-with-a-batch-of-data)

### [!UICONTROL Fill out a document] {#fill-out-a-document}

Med den här transformerarmodulen kan du fylla ett dokument med data som du anger. Den kan användas med enkla värdetaggar, villkorstaggar eller looptaggar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start delimiter of the text being replaced]</td> 
   <td> <p>Ange de tecken som du vill markera början av texten som ska ersättas. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>Ange <code>&#91;&#91;</code> som ska ersätta <code>[[replace_me]]</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL End delimiter of the text being replaced]</p> </td> 
   <td> <p>Ange de tecken som du vill markera slutet av texten som ska ersättas. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>Ange <code>&#93;&#93;</code> som ska ersättas <code>[[replace_me]]</code></p>. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p> Välj en källfil från en tidigare modul eller mappa källfilens data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of filled out file]</td> 
   <td>Ange ett filnamn (inklusive filtillägg) för målutdatafilen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data source]</td> 
   <td> <p>Välj ett alternativ för att ange om de data du använder kommer från ett formulär eller från en samling rådata (obearbetade datordata).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values]</td> 
   <td> <p>Detta måste vara en array med samlingar där:</p> 
    <ul> 
     <li>Varje samling motsvarar en datapost och innehåller ett objekt <code>entry</code></li> 
     <li>Objektet <code>entry </code> innehåller en samling av <code>key </code>och <code>value</code></li> 
     <li>Objektet <code>key </code> innehåller taggens namn</li> 
     <li>objektet <code>value </code> innehåller taggens värde</li> 
    </ul> 
    <p>Så här lägger du till en post:</p>
    <ol> 
     <li> Klicka på <b>[!UICONTROL Add Item]</b>. </li> 
     <li>Välj värdetyp för posten.</li> 
     <li>Lägg till namnet och värdet. Mer information finns i exemplet för den valda värdetypen i den här artikeln. 
      <ul> 
       <li><a href="#simple-value-tag" class="MCXref xref">Enkel värdetagg</a></li> 
       <li><a href="#condition-tag" class="MCXref xref">Villkorstagg</a></li> 
       <li><a href="#loop-tag" class="MCXref xref">Loop-tagg</a></li> 
      </ul></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Fill a document with a batch of data] {#fill-a-document-with-a-batch-of-data}

Den här aggregeringsmodulen är användbar om dina datainmatningar kommer som separata paket. Med den här modulen kan du enkelt ställa in den struktur som krävs för fältet Värde och mappa objekt till varje värdeobjekt. Till skillnad från Fyll i en dokumentmodul tillåter fältet Värden i Fyll i ett dokument med en batch med data-modul endast en post som innehåller variabler.

Du kan också använda den här modulen om dina dataposter kommer som en array genom att använda modulen *Iterator* för att omvandla innehållet i arrayen till en serie paket.

De faktiska värdena skapas och fylls i för varje inkommande paket. Mallen skapas när alla indatapaket har bearbetats.

Den här aggregeringsmodulen är särskilt användbar när du vill skapa listor eller rapporter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td>Markera modulen som är textens källa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start delimiter of the text being replaced]</td> 
   <td> <p>Ange de tecken som du vill markera början av texten som ska ersättas. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>Ange <code>&#91;&#91;</code> som ska ersätta <code>[[replace_me]]</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL End delimiter of the text being replaced]</p> </td> 
   <td> <p>Ange de tecken som du vill markera slutet av texten som ska ersättas. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>Ange <code>&#93;&#93;</code> som ska ersätta <code>[[replace_me]]</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td> Definiera ett uttryck som innehåller ett eller flera mappade objekt. De aggregerade data separeras under Grupper med samma uttrycksvärde. Varje grupp returnerar som ett separat paket som innehåller en nyckel med det utvärderade uttrycket och den aggregerade texten. På så sätt kan du använda Key (Nyckel) som ett filter i efterföljande moduler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>Aktivera det här alternativet om du vill stoppa bearbetningen när en aggregering inte innehåller några paket.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p> Välj en källfil från en tidigare modul eller mappa källfilens data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of filled out file]</td> 
   <td>Ange ett filnamn (inklusive filtillägg) för målutdatafilen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values]</td> 
   <td> <p>Detta måste vara en array med samlingar där:</p> 
    <ul> 
     <li>Varje samling motsvarar en datapost och innehåller ett objekt <code>entry</code></li> 
     <li>Objektet <code>entry </code> innehåller en samling av <code>key </code>och <code>value</code></li> 
     <li>Objektet <code>key </code> innehåller taggens namn</li> 
     <li>objektet <code>value </code> innehåller taggens värde</li> 
    </ul> 
    <p>Så här lägger du till en post:</p>
    <ol> 
     <li> Klicka på <b>[!UICONTROL Add Item]</b>. </li> 
     <li>Välj värdetyp för posten.</li> 
     <li>Lägg till namnet och värdet. Mer information finns i exemplet för den valda värdetypen i den här artikeln. 
      <ul> 
       <li><a href="#simple-value-tag" class="MCXref xref">Enkel värdetagg</a></li> 
       <li><a href="#condition-tag" class="MCXref xref">Villkorstagg</a></li> 
       <li><a href="#loop-tag" class="MCXref xref">Loop-tagg</a></li> 
      </ul></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
