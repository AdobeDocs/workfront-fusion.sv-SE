---
title: Luftburna moduler
description: Adobe Workfront Fusion kräver en Adobe Workfront Fusion-licens förutom en Adobe Workfront-licens.
author: Becky
feature: Workfront Fusion
exl-id: 3b445b50-5812-4ded-9788-f467991e0b52
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1858'
ht-degree: 0%

---

# Luftburna moduler


Med [!DNL Airtable]-kopplingen för [!DNL Adobe Workfront Fusion] kan du starta ett scenario baserat på händelser i ditt [!DNL Airtable]-konto, skapa, överföra och uppdatera poster, söka efter poster och göra anpassade API-anrop till Airtable API.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

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
   <td> <p>[!UICONTROL [!DNL Workfront Fusion] för automatisering och integrering av arbetet] </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>Din organisation måste köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</td> 
  </tr> 
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Du måste ha ett Airtable-konto för att kunna använda funktionerna i den här artikeln.

<!--
<p>For more information, see the tutorial .</p>
-->

## Information om Airtable API

Airtable-kontakten använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://api.airtable.com/v0</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v3.3.28</td> 
  </tr>
 </tbody> 
 </table>

## Connect Airtable to Workfront Fusion {#connect-airtable-to-workfront-fusion}

<!--

1. Log in to your Airtable account.
1. Open your account overview and generate the API key.
-->
1. Öppna Workfront Fusion och dialogrutan **Skapa en anslutning** i den önskade modulen.
1. Ange ett namn för anslutningen.
1. (Valfritt) Klicka på Visa avancerade inställningar och ange ditt Airtable Client ID och Klienthemlighet.
1. Klicka på knappen **Fortsätt** för att skapa anslutningen och återgå till modulen.

## Luftburna moduler och deras fält

### Poster

* [Skapa en post](#create-a-record)
* [Ta bort en post](#delete-a-record)
* [Hämta en post](#get-a-record)
* [Sök i poster](#search-records)
* [Uppdatera en post](#update-a-record)
* [Uppdatera en post](#upsert-a-record)
* [Bevakningsposter](#watch-records)
* [Se svar](#watch-responses)
* [Anropa ett API](#make-an-api-call)

#### Skapa en post {#create-a-record}

Den här åtgärdsmodulen skapar en ny post.

Du anger vilka data som ska lagras i posten och var de ska lagras.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Välj basen som den nya posten ska tillhöra.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som den nya posten ska tillhöra.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Post</p> </td> 
   <td> <p>Ange värdena för den nya posten. Tillgängliga fält baseras på den tabell du har valt.</p> <!--<p>For more information on field types, search for "Supported field types" in the Airtable documentation.</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>Multiple lines of text, which may contain "mention tokens", for example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong> : Add the attachment. Airtable will download the file from the provided <code>url</code> and keep its own copy of it. If the File name field is left empty, Airtable generates the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05 (ISO 8601 formatted date)</li> 
     <li>Phone number:</li> 
     <li><strong>Emails</strong>: A valid email address.</li> 
     <li><strong>URL</strong>: A valid URL (for example, airtable.com or https://airtable.com/universe).</li> 
     <li><strong>Number</strong>: Enter a number.</li> 
     <li><strong>Currency</strong>: Currency value.</li> 
     <li><strong>Percent</strong>: A percentage value. Must be higher than or equal to 0.</li> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation. </li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs will be reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Smarta länkar</td> 
   <td> <p>Aktivera det här alternativet om du vill ange namn i stället för post-ID:n för fält som länkar till en annan tabell. Posten skapas automatiskt i den länkade tabellen om det inte finns någon matchning.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en post {#delete-a-record}

Den här åtgärdsmodulen tar bort en viss post.

Du anger postens ID och lokalisering.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Markera basen som innehåller den post som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som innehåller den post som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>Post-ID</td> 
   <td> <p>Ange eller mappa det unika Airtable-ID för posten som du vill att modulen ska ta bort. Du kan till exempel hämta ID:t med hjälp av modulen Sök efter poster.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en post {#get-a-record}

Den här åtgärdsmodulen hämtar postinformation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Markera den bas som innehåller tabellen med den post som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell</td> 
   <td> <p> Markera tabellen som innehåller den post som du vill hämta information för.</p> </td> 
  </tr> 
  <tr> 
   <td>Post-ID</td> 
   <td> <p> Ange eller mappa ID:t för den post som du vill hämta information för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Sök i poster {#search-records}

Den här sökmodulen söker efter poster i ett objekt i Airtable som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Välj basen som du vill söka efter poster.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som du vill söka efter poster.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Formel</p> </td> 
   <td> <p>En formel som används för att filtrera poster. Formeln utvärderas för varje post och om resultatet inte är <code>0</code>, <code>false</code>, <code>""</code>, <code>NaN</code>, <code>[]</code> eller <code>#Error!</code> inkluderas posten i svaret.</p> <p>Om den kombineras med <code>view</code> returneras endast poster i den vyn som uppfyller formeln.</p> <p>Om du till exempel bara vill inkludera poster där Namn inte är tomt, skickar du:<code> NOT({Name} = '')</code></p> <p>Om du vill veta mer kan du söka efter information om formelfältreferenser i dokumentationen till support för Airtable.</p> </td> 
  </tr> 
  <tr> 
   <td>Sortera </td> 
   <td> <p>Välj sorteringsriktning och det fält som du vill sortera resultaten efter.</p> </td> 
  </tr> 
  <tr> 
   <td>Visa </td> 
   <td> <p>Välj den vy som du vill söka efter poster i.</p> </td> 
  </tr> 
  <tr> 
   <td>Gräns</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en post {#update-a-record}

Den här åtgärdsmodulen uppdaterar en viss post.

Du anger ID:t för posten och de nya data som du vill att den ska innehålla.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Markera basen som innehåller den post som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som innehåller den post som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>Post-ID </td> 
   <td> <p>Ange eller mappa det unika Airtable-ID för posten som du vill att modulen ska uppdatera. Du kan till exempel hämta ID:t med hjälp av modulen Sök efter poster.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Post</p> </td> 
   <td> <p>Ange värdena för den nya posten. Vilka fält som är tillgängliga beror på vilken tabell du har valt.</p> <!--<p>In order to delete the content of the field, use the erase function. </p>  <p>Field types (via airtable.com/api):</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>The string can contain multiple lines of text with "mention tokens." For example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong>: Add the attachment. Airtable will download the file from the provided url and keep its own copy of it. If the File name field is left empty, Airtable will generate the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05. (ISO 8601 formatted date)</li> 
     <li><strong>Phone number</strong>: A telephone number, for example, (415) 555-9876.</li> 
     <li><strong>Email</strong>valid email address.</li> 
     <li><strong>URL</strong>: lid URL such as airtable.com or https://airtable.coiverse.</li> 
     <li><strong>Number</strongnter a number.</li> 
     <li><strong>Currency</stro Currency value.</li> 
     <li><strong>Percent</stronA percentage value; must be equal to or more than 0i> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation.</li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs is reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Smarta länkar</td> 
   <td> <p>Ange namn i stället för post-ID:n för fält som länkar till en annan tabell. Posten skapas automatiskt i den länkade tabellen om det inte finns någon matchning.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Skicka en post

Den här åtgärdsmodulen uppdaterar eller infogar en viss post.

Du anger ID:t för posten och de nya data som du vill att den ska innehålla.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Markera basen som innehåller den post som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som innehåller den post som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td>Post-ID </td> 
   <td> <p>Om du uppdaterar en post anger eller mappar du det unika Airtable-ID för posten som du vill att modulen ska uppdatera. Du kan till exempel hämta ID:t med hjälp av modulen Sök efter poster.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Post</p> </td> 
   <td> <p>Ange värdena för den nya posten. Vilka fält som är tillgängliga beror på vilken tabell du har valt.</p> <!-- <p>In order to delete the content of the field, use the erase function. </p>  <p>Field types (via airtable.com/api):</p> 
    <ul> 
     <li> <p><strong>Text</strong>: string</p> <p>A single line of text.</p> </li> 
     <li> <p><strong>Long text</strong>: string</p> <p>The string can contain multiple lines of text with "mention tokens." For example:</p><pre>&lt;airtable:mention id="menE1i9oBaGX3DseR"&gt;@Alex&lt;/airtable:mention&gt;</pre> </li> 
     <li><strong>Attachment</strong>: Add the attachment. Airtable will download the file from the provided url and keep its own copy of it. If the File name field is left empty, Airtable will generate the name automatically.</li> 
     <li><strong>Checkbox</strong>: Select one of the options.</li> 
     <li><strong>Multiple select</strong>: Select multiple options in the checklist.</li> 
     <li><strong>Single select</strong>: Select one option from the drop-down menu.</li> 
     <li><strong>Collaborator</strong>: Enter the email that uniquely identifies a user in Airtable who this base is shared with.</li> 
     <li><strong>Date</strong>: UTC date, for example, 2019-09-05. (ISO 8601 formatted date)</li> 
     <li><strong>Phone number</strong>: A telephone number, for example, (415) 555-9876.</li> 
     <li><strong>Email</strong>valid email address.</li> 
     <li><strong>URL</strong>: lid URL such as airtable.com or https://airtable.coiverse.</li> 
     <li><strong>Number</strongnter a number.</li> 
     <li><strong>Currency</stro Currency value.</li> 
     <li><strong>Percent</stronA percentage value; must be equal to or more than 0i> 
     <li><strong>Duration</strong>: Enter the duration time. If you need help, see the information about the duration field type in the Airtable support documentation.</li> 
     <li><strong>Rating</strong>: Enter the number. For example, "3 stars" is 3. A rating cannot be 0.</li> 
     <li><strong>Link</strong>: Enter the linked records IDs from the table. The order of record IDs is reversed compared to what you see in the app.</li> 
     <li><strong>Rollup</strong>: Computed value: COUNT(values)</li> 
     <li><strong>Lookup</strong>: Array of long text fields</li> 
     <li><strong>Autonumber</strong>: Automatically incremented unique counter for each record.</li> 
     <li> <p><strong>Barcode</strong>: The barcode object may contain the following two properties, both of which are optional.</p> <p>Barcode data (text)</p> <p>Barcode symbology, for example, "upce" or "code39" (type)</p> </li> 
    </ul> --></td> 
  </tr> 
  <tr> 
   <td>Smarta länkar</td> 
   <td> <p>Ange namn i stället för post-ID:n för fält som länkar till en annan tabell. Posten skapas automatiskt i den länkade tabellen om det inte finns någon matchning.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Bevakningsposter {#watch-records}

Den här utlösarmodulen startar ett scenario när en post skapas eller uppdateras i den angivna tabellen.

>[!NOTE]
>
>Om du vill använda den här modulen måste fältet Skapad tid eller Senast ändrad tid skapas i tabellen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>Bas </td> 
   <td> <p>Välj den bas som du vill bevaka för nya poster.</p> </td> 
  </tr> 
  <tr> 
   <td>Tabell </td> 
   <td> <p>Markera tabellen som du vill bevaka för nya poster.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Utlösarkonfiguration</p> </td> 
   <td> <p>Utlösarfält</p> <p>Ett <code>Created Time</code>- eller <code>Last Modified Time</code>-fält som används för att sortera poster. Om du inte har något <code>Created Time</code>- eller <code>Last Modified Time</code>-fält i ditt schema måste du skapa ett. </p> <p>Etikettfält</p> <p>Ett fält som används som etikett för en post, till exempel i dialogrutan Välj var du vill starta.</p> </td> 
  </tr> 
  <tr> 
   <td>Gräns</td> 
   <td> <p>Ange eller mappa det maximala antalet poster som modulen ska bevaka under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td>Visa</td> 
   <td> <p>Markera den vy som du vill använda.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>Formel</p> </td> 
   <td> <p>En formel som används för att filtrera poster. Formeln utvärderas för varje post och om resultatet inte är <code>0</code>, <code>false</code>, <code>""</code>, <code>NaN</code>, <code>[]</code> eller <code>#Error!</code> inkluderas posten i svaret.</p> <p>Om den kombineras med <code>view</code> returneras endast poster i den vyn som uppfyller formeln.</p> <p>Om du till exempel bara vill inkludera poster där Namn inte är tomt, skickar du:<code> NOT({Name} = '')</code></p> <p>Mer information finns i informationen om formelfältreferenser i dokumentationen för Airtable-stöd.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Se svar

Den här utlösarmodulen startar ett scenario när ett formulär skickas.

>[!NOTE]
>
>Den här funktionaliteten är endast tillgänglig för den betalda Airtable Pro-planen.

Webbhoks-URL:en måste genereras i Workfront Fusion och sedan läggas till i formulärkonfigurationen i Airtable.

1. Lägg till modulen Bevaka nya svar i ditt Workfront Fusion-scenario.
1. Generera och kopiera webboks-URL:en.

   <!--For instructions, see [ (webhooks) in Adobe Workfront Fusion](/help/workfront-fusion/).-->

1. Logga in på ditt Airtable-konto.
1. Öppna basen och tabellen som du vill använda för formuläret och skapa en formulärvy.
1. Ange formuläret efter behov, rulla nedåt i formuläret och aktivera alternativet Omdirigera till URL när formuläret har skickats.
1. Ange den webkroks-URL som genereras i steg 2 i den dialogruta som visas och lägg till ?record_id={record_id} precis efter webkroks-URL:en för att inkludera post-ID:t i modulens utdata. Klicka sedan på Spara. Den resulterande URL:en ser till exempel ut så här:
1. Gå tillbaka till ditt Workfront Fusion-scenario och kör modulen Bevakade svar bara för att läsa in fält från Airtable och för att kunna mappa dessa fält till de andra modulerna.
1. Skicka formuläret i Airtable där alternativet Omdirigera till URL när formuläret har skickats är aktiverat och Webkroks URL har lagts till (steg 6 ovan).

   Modulen Bevakade svar aktiveras och önskade data läses in.

1. Lägg till Airtable > Get a Record-modulen precis efter Airtable > Watch Responses-modulen och mappa record_id till fältet Record ID.

Varje gång formuläret skickas aktiveras nu modulen Bevakade svar i ditt Workfront Fusion-scenario, och modulen Hämta en post returnerar den skickade formulärinformationen.

#### Anropa ett API

#### Anpassat API-anrop

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Airtable]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Airtable]-modulerna.

Åtgärden baseras på den entitetstyp (Allocadia-objekttyp) som du anger.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Anslutning</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Airtable-konto till Workfront Fusion finns i <a href="#connect-airtable-to-workfront-fusion" class="MCXref xref">Connect Airtable till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Ange en relativ sökväg till <code>https://api.airtable.com/</code>. Exempel: <code>v0/{base}/{table}</code> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Metod</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sidhuvuden</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Frågesträng</td> 
   <td> <p>Lägg till frågan för API-anropet i form av nyckel och värde</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Brödtext</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
