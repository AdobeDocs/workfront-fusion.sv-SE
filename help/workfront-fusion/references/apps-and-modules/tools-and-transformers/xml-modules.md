---
title: XML
description: Med XML-appen kan du tolka en XML-formaterad text via XML-modulen &gt; Tolka XML och konvertera den till ett paket för att göra data tillgängliga för andra moduler. Du kan också konvertera ett paket till en XML-formaterad text via XML-&stämpeln;gt; Skapa XML-modul
author: Becky
feature: Workfront Fusion
exl-id: ab323361-cd04-4dcc-ab02-0fb468334fdb
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 1%

---

# XML

Med appen [!UICONTROL XML] kan du analysera en XML-formaterad text via modulen [!UICONTROL XML] > [!UICONTROL Parse XML] och konvertera den till ett paket för att göra data tillgängliga för andra moduler. Du kan också konvertera ett paket till en XML-formaterad text via modulen [!UICONTROL XML] > [!UICONTROL Create XML]

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

## Skapa XML

Modulen [!UICONTROL XML] > [!UICONTROL Create XML] konverterar ett paket till en XML-formaterad text.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Data structure]</p> </td> 
   <td> <p>Datastrukturen beskriver strukturen för den resulterande XML-filen. Om du har ett exempel på den XML som du vill skapa kan du använda den för att generera datastrukturen:</p> 
    <ol> 
     <li value="1">Klicka på knappen <strong>[!UICONTROL Add]</strong>.</li> 
     <li value="2">Klicka på knappen <strong>[!UICONTROL Generator]</strong>.</li> 
     <li value="3">Kopiera och klistra in XML-exemplet i datafältet Exempel.</li> 
     <li value="4">Klicka på knappen <strong>[!UICONTROL Save]</strong>.</li> 
     <li value="5">Kontrollera att datastrukturen har genererats.</li> 
     <li value="6">Klicka på <strong>[!UICONTROL Save]</strong> om du vill spara datastrukturen.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Root element name]</td> 
   <td>Ange namnet på XML-filens rotelement. Standardvärdet är <code>root</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype SYSTEM ID]</td> 
   <td>Ange filnamnet som ska användas i deklarationen <code>!DOCTYPE SYSTEM</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype PUBLIC ID]</td> 
   <td>Ange filnamnet som ska användas i deklarationen <code>!DOCTYPE PUBLIC</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Strip Xml Declaration]</td> 
   <td>Aktivera det här alternativet om du vill ta bort XML-deklarationen <code>&lt;?xml ... ?&gt;</code> och <code>&lt;!DOCTYPE ... &gt;</code> och bara lämna XML-rotelementet och dess innehåll.</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:**

Ett typiskt användningsfall är att omvandla data från ett [!DNL Google] >kalkylblad till XML.

1. Placera modulen [!DNL Google Sheets] > [!UICONTROL Select rows] i ditt scenario för att hämta data. Konfigurera modulen för att hämta rader från ditt [!DNL Google]-kalkylblad. Ställ in &#x200B;**[!UICONTROL Maximum number of returned rows]** på ett litet tal, men större än ett för testningsändamål (exempel, tre). Kör modulen [!DNL Google Sheets] genom att högerklicka på den och välja **[!UICONTROL Run this module only]**. Kontrollera modulens utdata.
1. Anslut modulen [!UICONTROL Array Aggregator] efter modulen [!DNL Google Sheets]. Välj modulen [!DNL Google Sheets] i fältet **[!UICONTROL Source node]** i modulens konfiguration. Låt de andra fälten vara som de är för tillfället.
1. Anslut modulen [!UICONTROL XML] > [!UICONTROL Create XML] efter modulen [!UICONTROL Array Aggregator].

   Modulens konfiguration kräver en datastruktur som beskriver strukturen för XML-utdata. Klicka på knappen **[!UICONTROL Add]** för att öppna datastrukturinställningarna. Det enklaste sättet att skapa den här datastrukturen är att generera den automatiskt från ett XML-exempel.

1. Klicka på knappen **[!UICONTROL Generator]** och klistra in XML-exemplet i fältet [!UICONTROL Sample data]:

   ![Exempeldatafält](/help/workfront-fusion/references/apps-and-modules/assets/sample-data-field-350x146.png)

1. Klicka på **[!UICONTROL Save]**.

   Fältet Specifikation i datastrukturen innehåller nu den genererade strukturen.
1. Ändra namnet på datastrukturen till något mer specifikt och klicka på **[!UICONTROL Save]**.

   Ett fält som motsvarar rotarrayattributet visas som ett mappningsbart fält i JSON-modulens inställningar.
1. Klicka på knappen **[!UICONTROL Map]** bredvid fältet och mappa `Array[]`-objektet från [!UICONTROL Array aggregator]-utdata till det:
1. Klicka på **[!UICONTROL OK]** för att stänga XML-modulens inställningar.
1. Öppna konfigurationen för modulen [!UICONTROL Array Aggregator]. Ändra **[!UICONTROL Target structure]** från anpassad till fältet i en XML-modul som motsvarar det överordnade XML-elementet.Mappa objekt från modulen [!DNL Google Sheets] till rätt fält.
1. Klicka på **[!UICONTROL OK]** för att stänga konfigurationen för modulen Array Aggregator.
1. Kör scenariot.

   XML-modulen matar ut rätt XML-fil.

1. Öppna inställningarna för modulen [!DNL Google Sheets] och öka [!UICONTROL Maximum number of returned rows] så att det blir större än antalet rader i kalkylbladet för att bearbeta alla data.

   Resultatet av XML kan sparas i [!DNL Dropbox], skickas som en bifogad fil via e-post, överföras via FTP till en server och så vidare.

>[!ENDSHADEBOX]

### Lägga till XML-attribut

Om du vill lägga till attribut i en komplex nod (en nod som ska innehålla andra noder) måste du lägga till en samling med namnet `_attributes` för den komplexa anteckningen i den anpassade datastrukturen. Samlingen mappas till nodattribut. Om du vill lägga till attribut i en textnod (till exempel: `<node attr="1">abc</node>`) måste du lägga till en samling `_attributes` för attribut och en textegenskap `_value` för nodvärdet för den här noden i din anpassade datastruktur.

```
{
   "name": "node",
   "type": "collection",
   "spec": [
      {
         "name": "_attributes",
         "type": "collection"
         "spec": [
            {
               "name": "attr1",
               "type": "text"
            }
         ]
      },
      {
         "name": "_value",
         "type": "text"
      }
   ]
}
```

## [!UICONTROL Parse XML]

Modulen [!UICONTROL XML] > [!UICONTROL Parse XML] tolkar en XML-formaterad text och returnerar ett enskilt paket som innehåller all information som extraherats från XML.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Data structure]</p> </td> 
   <td> <p>Datastrukturen beskriver XML-strukturen så att modulens utdata blir tillgängliga på mappningspanelen för följande moduler.</p> <p>Om du har ett exempel på den XML som du vill analysera kan du använda den för att generera datastrukturen:</p> 
    <ol> 
     <li value="1">Klicka på knappen <strong>[!UICONTROL Add]</strong>.</li> 
     <li value="2">Klicka på knappen <strong>[!UICONTROL Generator]</strong>.</li> 
     <li value="3">Kopiera och klistra in XML-exemplet i fältet <strong>[!UICONTROL Sample data]</strong>.</li> 
     <li value="4">Klicka på <strong>[!UICONTROL Save]</strong>.</li> 
     <li value="5">Kontrollera att datastrukturen har genererats.</li> 
     <li value="6"> <p>Klicka på knappen <strong>[!UICONTROL Save]</strong> om du vill spara datastrukturen.</p> <p>Du kan hoppa över steg 2-5 för att tillhandahålla en tom datastruktur. Om datastrukturen är tom är modulens utdata inte tillgängliga på mappningspanelen förrän modulen har körts minst en gång.</p> </li> 
    </ol> <p>Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">Datastrukturer</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Preserve numbers as text]</td> 
   <td>Aktivera det här alternativet för att säkerställa att tal förblir som textvärden (strängvärden). I annat fall byts tal ut mot talvärden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL XML]</p> </td> 
   <td> <p>Ange eller mappa den XML-formaterade text som du vill analysera.</p> <p>Om du använder en formel kontrollerar du att dess resultatvärdetyp är (eller kan tvingas till automatiskt) datatypen [!UICONTROL Text]. </p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/if-you-use-a-formula-350x164.png" style="width: 350;height: 164;"> </p> <p>Om resultatvärdestypen är [!UICONTROL Buffer] (binära data) använder du funktionen <code>toString()</code> för att konvertera den till datatypen Text. Mer information finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a> och <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Objektdatatyper</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**Exempel:**

Så här hämtar du en XML-fil från en URL och tolkar innehållet i den:

1. Skapa ett nytt scenario.
1. Lägg till modulen [!UICONTROL HTTP] > [!UICONTROL Get a file]
1. Öppna modulens konfiguration och konfigurera den enligt följande:

   **URL**: URL för XML-filen (t.ex. `https://siftrss.com/f/rqLy05ayMBJ`)

   ![URL för XML-filexempel](/help/workfront-fusion/references/apps-and-modules/assets/url-of-xml-file-350x184.png)

1. Klicka på **[!UICONTROL OK]** för att spara och stänga modulens konfiguration.
1. Lägg till [!UICONTROL XML] > modulen [!UICONTROL Parse XML], anslut den efter modulen [!UICONTROL HTTP] > [!UICONTROL Get a file] och konfigurera den enligt följande:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Data structure]</td> 
      <td> 
       <ol> 
        <li value="1">Klicka på knappen <strong>[!UICONTROL Add]</strong>.</li> 
        <li value="2">Klicka på knappen <strong>[!UICONTROL Generator]</strong>.</li> 
        <li value="3">Öppna en ny flik eller ett nytt fönster i webbläsaren.</li> 
        <li value="4">Placera den URL du använde i det tredje steget i adressfältet och hämta XML-filen.</li> 
        <li value="5">Markera all XML-text och kopiera den till Urklipp.</li> 
        <li value="6">Stäng fliken eller fönstret och återgå till ditt scenario.</li> 
        <li value="7">Klistra in den kopierade XML-texten i datafältet Exempel.</li> 
        <li value="8">Klicka på <strong>[!UICONTROL Save]</strong>.</li> 
        <li value="9">Kontrollera att datastrukturen har genererats.</li> 
        <li value="10">Klicka på <strong>[!UICONTROL Save]</strong> om du vill spara datastrukturen.</li> 
       </ol> <p>Du kan hoppa över steg 2 till 9 för att tillhandahålla en tom datastruktur. Om datastrukturen är tom är modulens utdata inte tillgängliga på mappningspanelen förrän modulen har körts minst en gång.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL XML]</td> 
      <td> <p>Mappa <code>Data </code>objektet från utdata från modulen [!UICONTROL HTTP] &gt; [!UICONTROL Get a file] till fältet. Använd funktionen <code>toString()</code> för att konvertera dess värde från datatypen [!UICONTROL Buffer] (binära data) till datatypen [!UICONTROL Text].</p> <p>Du kan kopiera och klistra in formelns kod i fältet: <code>&#123;&#123;toString(1.data)&#125;&#125;</code></p> <p>Mer information om datatyperna Buffer och Text finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">Objektdatatyper</a>.</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/paste-formula-code-350x99.png"> </p> </td> 
     </tr> 
    </tbody> 
   </table>

>[!ENDSHADEBOX]

### [!UICONTROL Parsing XML attributes]

Som standard placerar modulen [!UICONTROL XML] > [!UICONTROL Parse XML] attribut i en särskild samling `_attributes` som underordnade noden som har dessa attribut. Om noden är en textnod och har attribut läggs två specialegenskaper till: `_attributes` för attribut och `_value` för nodens textinnehåll.

>[!BEGINSHADEBOX]

**Exempel:** Denna XML:

```
<root attr="1">
<node attr="ABC">Hello, World</node>
</root>
```

konverteras till det här paketet:

![XML konverterad till paket](/help/workfront-fusion/references/apps-and-modules/assets/xml-converted-to-bundle.png)

>[!ENDSHADEBOX]

## Felsökning: Det går inte att mappa data från modulen [!UICONTROL Parse XML]

Kontrollera att datastrukturen är korrekt definierad. Du kan också använda en tom datastruktur och köra modulen minst en gång för att bearbeta en XML-inmatning.
