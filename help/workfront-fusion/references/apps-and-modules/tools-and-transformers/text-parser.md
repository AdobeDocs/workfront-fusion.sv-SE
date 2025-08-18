---
title: Textparser
description: Du kan använda textanalysverktyget för att tolka text som ska användas i andra  [!DNL Adobe Workfront Fusion] scenariomoduler. Textparsern kräver ingen anslutning.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 885d714e-fc09-41a2-89dc-ebe29a355e43
source-git-commit: 679a4f5c91625dfecf32e10904700bf75ea7a7cf
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 0%

---

# [!UICONTROL Text parser]

Du kan använda [!UICONTROL Text parser tool] för att tolka text för användning i andra [!DNL Adobe Workfront Fusion] scenariomoduler. [!UICONTROL Text parser] kräver ingen anslutning.

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

## API-information för textparser

Textparserkopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Text parser]-moduler och deras fält

När du konfigurerar [!UICONTROL Text parser] moduler visar [!DNL Adobe Workfront Fusion] fälten som listas nedan. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Transformers

* [[!UICONTROL Get Elements from HTML]](#get-elements-from-html)
* [[!UICONTROL Get Elements from text]](#get-elements-from-text)
* [[!UICONTROL HTML to Text]](#html-to-text)
* [[!UICONTROL Match Pattern]](#match-pattern)
* [[!UICONTROL Replace]](#replace)

#### [!UICONTROL Get Elements from HTML]

Hämtar önskade element från HTML-kod.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module finds no matches]</td> 
   <td> <p>Aktivera det här alternativet för att se till att modulen inte stoppar scenariot om den inte returnerar några resultat.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Element type]</td> 
   <td> <p> Markera den typ av element som du vill hämta från HTML-koden. </p> 
    <ul> 
     <li>[!UICONTROL Image]</li> 
     <li>[!UICONTROL Link]</li> 
     <li>[!UICONTROL iFrame element(s)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>Ange eller mappa den HTML-kod som du vill hämta de angivna elementtyperna från.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Elements from text]

Tolkar element från text baserat på det angivna mönstret.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Input text]</td> 
   <td> <p>Ange eller mappa texten som du vill tolka.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Pattern]</td> 
   <td> <p>Markera mönstret som återspeglar elementen som du vill tolka från texten.</p> <p>Om du vill ange ett anpassat reguljärt uttryck väljer du Anpassad i listan och anger det anpassade uttrycket i fältet Anpassad regex.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Ignore Duplicate Occurrences]</td> 
   <td> <p>Markera den här rutan om du vill ignorera dubblettförekomster av ett textelement.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL HTML to Text]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL HTML] </td> 
   <td> <p>Ange den HTML-kod som du vill konvertera till oformaterad text.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Line break] </td> 
   <td> <p>Välj typ av radbrytning.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Uppercase headings]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill konvertera text i rubriktaggar (till exempel &lt;h2&gt; &lt;/h2&gt;) till versaler.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Match Pattern]

Med modulen [!UICONTROL Match pattern] kan du söka efter och extrahera strängelement som matchar ett sökmönster från en viss text. I den här modulen används reguljära uttryck (kallas även regex eller regexp).

Ett reguljärt uttryck är en teckensekvens där varje tecken antingen är ett metatecken med en speciell innebörd eller ett reguljärt tecken med en litteral betydelse. Dessa tecken och metatecken identifierar ett mönster som kan användas för att söka efter text. Om du t.ex. vill söka efter namn kan du skapa ett reguljärt uttryck som söker efter ett mönster som består av två ord i följd som börjar med versaler. Reguljära uttryck är ett kraftfullt verktyg för att söka efter och ändra text.

En diskussion om reguljära uttryck ligger utanför den här artikelns räckvidd. Vi rekommenderar följande resurser:

* En fullständig lista över metatecken finns i [Reguljära uttryck](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) i MDN-webbdokument.
* Om du vill ha en genomgång om hur du skapar reguljära uttryck rekommenderar vi [RegexOne](https://regexone.com/).
* Om du vill experimentera med reguljära uttryck rekommenderar vi webbplatsen [Reguljära uttryck 101](https://regex101.com/). Markera ECMAScript (JavaScript) FLAVOR i den vänstra panelen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>Ange mönstret för det reguljära uttrycket. </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span> <code>[+-]?(\d+(\.\d+)?|\.\d+)([eE][+-]?\d+)?</code> extraherar alla siffror i den angivna texten.</p> <p>Obs!  <p>Mönstret ska innehålla minst en hämtningsgrupp inom parentes <code>()</code>. Om mönstret inte innehåller några hämtningsgrupper är utdatapaketet tomt.</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>Aktivera det här alternativet om du vill hämta alla matchningar i texten. Alla matchningar görs i ett separat paket. Om det här alternativet är inaktiverat hämtar modulen endast den första posten.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> Aktivera det här alternativet för den här modulen för att behandla text som skiftlägeskänslig.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>Aktivera det här alternativet för att säkerställa att inledande och avslutande metatecken (<code>^</code> och <code>$</code>) matchar början eller slutet av varje rad, inte bara början eller slutet av hela indatasträngen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>Aktivera det här alternativet om du vill kontrollera att punkten (.) matchar radmatningstecken (<code>\n</code>).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p>Aktivera det här alternativet för att se till att modulen inte stoppar scenariot om den inte returnerar några resultat.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>Ange eller mappa den text som du vill matcha mönstret.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace]

Söker efter ett angivet värde eller reguljärt uttryck i den angivna texten och ersätter resultatet med det nya värdet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Pattern] </td> 
   <td> <p>Ange söktermen. Du kan också använda ett reguljärt uttryck. Mer information om det reguljära uttrycket finns i modulen <a href="#match-pattern" class="MCXref xref">[!UICONTROL Match Pattern]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New value]</td> 
   <td> <p> Ange det värde som ska ersätta söktermen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Global match]</td> 
   <td> <p>Aktivera det här alternativet om du vill hämta alla matchningar i texten. Alla matchningar görs i ett separat paket. Om det här alternativet är inaktiverat hämtar modulen endast den första posten.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Case sensitive]</td> 
   <td> <p> Aktivera det här alternativet för den här modulen för att behandla text som skiftlägeskänslig.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Multiline] </td> 
   <td> <p>Aktivera det här alternativet för att säkerställa att inledande och avslutande metatecken (<code>^</code> och <code>$</code>) matchar början eller slutet av varje rad, inte bara början eller slutet av hela indatasträngen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Singleline]</td> 
   <td>Aktivera det här alternativet om du vill kontrollera att punkten (.) matchar radmatningstecken (<code>\n</code>).</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text] </td> 
   <td> <p>Ange den text som du vill söka i.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Dataskrapning

Dataskrapning, som ibland kallas webbskrapning, dataextrahering eller webbskörning, är processen att samla in data från webbplatser och lagra dem i din lokala databas eller kalkylblad. Om du vill skrapa data från en webbplats och inte känner till reguljära uttryck, kan du använda ett dataskrapningsverktyg.

Om dataskrapningsverktyget har ett REST API kan du ansluta till det via våra universella [[!UICONTROL HTTP]-moduler](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors) och [Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md) .

## Felsökning av textparser

Använd den här informationen om du inte kan hämta en texttolk för att skapa utdata.

>[!BEGINSHADEBOX]

Exempel:

Modulen bör analysera filtypen för ett fildokument, &quot;filename.docx&quot;, och filnamnets filnamnstillägg varierar från DOCX till PDF till CSV.

Uttrycket som du kan använda i det här fallet är [!DNL \..+]

Det här reguljära uttrycket resulterar vanligtvis i en fullständig matchning.

Om du implementerar det här uttrycket i texttolken resulterar det dock inte i någon matchning:

![Ingen matchning](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-you-dont-get-a-match-350x365.png)

Anledningen till detta är att &quot;i&quot; endast visar antalet matchningar per matchning, så i det här fallet har vi två matchningar, och efter &quot;i&quot; finns därför ett numeriskt värde på 1 och 2. I det här exemplet används det om du någon gång behöver matcha eller skicka data via ett filter endast med det andra matchade värdet. Du kan ange vilket värde som representeras av det numeriska värdet.

![Matcha](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-matches-350x355.png)

För att kunna hämta de matchningsvärden som du behöver lägga till hakparenteser i den del som du vill analysera (till exempel för att extrahera från&quot;filename.docx&quot; -&quot;docx&quot; enbart), ska hakparenteserna tillämpas på \, enligt det regex-uttryck som vi använder för det här scenariot.(.+)

Detta hämtar DOCX-filen, placerar den i en grupp och lämnar &quot;.&quot; ur det.

![Hämta träffar](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-get-matches-350x592.png)

I utdata som visas i bilden nedan kommer den hämtade gruppen att matcha alla tecken (förutom radavslutningar).

![Utdata](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-output-350x389.png)

En annan tillfällig lösning som även innehåller regex är att använda funktionen replace

`{{replace("abcdefghijklmno pqr stuvw xyz.docx"; "/.\./"; ".")}}`

Ersätt sedan `abcdefghijklmno pqr stuvw xyz.docx` med den faktiska filnamnsvariabeln.

>[!ENDSHADEBOX]
