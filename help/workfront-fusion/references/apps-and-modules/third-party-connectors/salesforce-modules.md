---
title: Salesforce moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Salesforce och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 3c7c03a7-67ea-4673-90b0-7d0506d9fa10
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '2603'
ht-degree: 0%

---

# [!DNL Salesforce] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Salesforce] och ansluta det till flera tredjepartsprogram och -tjänster.

En videointroduktion till Salesforce Connector finns på:

* [Salesforce](https://video.tv.adobe.com/v/3427027/){target=_blank}

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

>[!NOTE]
>
>* Alla utgåvor av [!DNL Salesforce] har inte API-åtkomst. Mer information finns i informationen om [!DNL Salesforce] utgåvor med API-åtkomst på [!DNL Salesforce] Community-webbplatsen.
>* Information om specifika fel som returneras från API:t [!DNL Salesforce] finns i API-dokumenten för [!DNL Salesforce]. Du kan också kontrollera status för [!DNL Salesforce] API:t för eventuella tjänstavbrott.
>

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

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

Du måste ha ett [!DNL Salesforce]-konto för att kunna använda [!DNL Salesforce]-moduler.

## Salesforce API-information

Salesforce Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> {{connection.instanceUrl}}</td>
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v46.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.15.14</td> 
  </tr>
 </tbody> 
 </table>

## Om att söka efter [!DNL Salesforce] objekt

När du söker efter objekt kan du antingen ange enskilda sökord eller skapa en mer komplex fråga med jokertecken och operatorer:

* Använd asteriskens jokertecken (\*) som ersättning för noll eller flera tecken. En sökning efter Ca\* söker efter objekt som börjar med Ca
* Använd frågetecken som jokertecken (?) som ersättning för ett enda tecken. Om du söker efter Jo?n hittas objekt med termen John eller Joan men inte Jon
* Använd operatorn för citattecken (&quot; &quot;) för att hitta en exakt frasmatchning. Till exempel:&quot;Månadsmöte&quot;

Mer information om sökmöjligheter finns i [!DNL Salesforce]-utvecklardokumentationen om SOQL och SOSL.

## [!DNL Salesforce]-moduler och deras fält

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

* [[!UICONTROL Watch for Records]](#watch-for-records)
* [[!UICONTROL Watch Outbound Messages]](#watch-outbound-messages)
* [[!UICONTROL Watch a field]](#watch-a-field)

#### [!UICONTROL Watch for Records]

Den här utlösarmodulen kör ett scenario när en post i ett objekt skapas eller uppdateras. Modulen returnerar alla standardfält som är associerade med posten eller posterna, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type] </td> 
   <td> <p>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Fields]</td> 
   <td>Markera de fält som du vill att modulen ska bevaka. Vilka fält som är tillgängliga beror på posttypen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal count of records]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch]</td> 
   <td> <p>Ange om du vill att scenariot bara ska bevaka nya poster av den typ som du har valt, eller nya poster av den typ som du har valt och alla andra ändringar av poster av den typen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Outbound Messages]

Den här utlösarmodulen kör ett scenario när någon skickar ett meddelande. Modulen returnerar alla standardfält som är associerade med posten eller posterna, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

Den här modulen kräver extra inställningar:

1. Gå till konfigurationssidan för [!DNL Salesforce].

   Om du vill komma åt konfigurationssidan letar du upp och klickar på knappen [!UICONTROL Setup] i det övre högra hörnet av [!DNL Salesforce]-kontot. Gå till fältet [!UICONTROL Quick Find / Search] till vänster på konfigurationssidan för [!DNL Salesforce]. Sök efter [!UICONTROL Workflow Rules].

1. Klicka på **[!UICONTROL Workflow Rules]**.
1. På sidan [!UICONTROL Workflow Rules] som visas klickar du på **[!UICONTROL New Rule]** och väljer den objekttyp som regeln ska gälla för (till exempel [!UICONTROL Opportunity] om du övervakar uppdateringar av säljprojektsposter).
1. Klicka på **[!UICONTROL Next]**.
1. Ange ett regelnamn, utvärderingskriterier och regelvillkor och klicka sedan på **[!UICONTROL Save]** och **[!UICONTROL Next]**.

1. Klicka på **[!UICONTROL Done]**.
1. Klicka på **[!UICONTROL Edit]** från den nyligen skapade arbetsflödesregeln.
1. I listrutan **[!UICONTROL Add Workflow Action]** väljer du **[!UICONTROL New Outbound Message]**.

1. Ange namn, beskrivning, slutpunkts-URL och fält som du vill inkludera i det nya utgående meddelandet och klicka sedan på **[!UICONTROL Save]**.

   Fältet **[!UICONTROL Endpoint URL]** innehåller URL:en som anges för [!DNL Salesforce] [!UICONTROL Outbound Message] i [!DNL Workfront Fusion].

1. Konfigurera ett scenario som börjar med händelsen [!UICONTROL Outbound Message].

1. Klicka på ikonen **&lt;/>** längst ned till höger och kopiera den angivna URL:en.
1. Gå tillbaka till sidan **[!UICONTROL Workflow Rules]**, leta reda på den nya regeln och klicka sedan på **[!UICONTROL Activate]**.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Webhook]</td> 
   <td> <p>Välj den webkrok som du vill använda för att bevaka utgående meddelanden. Om du vill lägga till en webkrok klickar du på <strong>[!UICONTROL Add]</strong> och anger webkrokens namn och anslutning.</p> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type] </td> 
   <td> <p>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska bevaka för utgående meddelanden.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Fields]</td> 
   <td> <p>Markera de fält som du vill att modulen ska bevaka för utgående meddelanden. Vilka fält som är tillgängliga beror på posttypen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### *[!UICONTROL Watch a field]*

Denna utlösarmodul startar ett scenario när ett fält uppdateras i [!DNL Salesforce].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type] </td> 
   <td> <p>Välj den typ av post som innehåller fältet som du vill att modulen ska bevaka. Du måste välja en posttyp som har [!UICONTROL Field History] aktiverat i [!DNL Salesforce]-konfigurationen. Mer information finns i <a href="https://help.salesforce.com/articleView?id=tracking_field_history.htm&amp;type=5">Spåra fälthistorik</a> i [!DNL Salesforce]-dokumentationen. </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Field]</td> 
   <td> <p>Markera de fält som du vill att modulen ska bevaka för ändringar.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal fält som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Create a Record]](#create-a-record)
* [[!UICONTROL Read a Record]](#read-a-record)
* [[!UICONTROL Delete a Record]](#delete-a-record)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Upload Attachment/Document]](#upload-attachmentdocument)
* [[!UICONTROL Download Attachment/Document]](#download-attachmentdocument)
* [Överför fil](#upload-file)

#### [!UICONTROL Create a Record]

Den här åtgärdsmodulen skapar en ny post i ett objekt.

I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen. Detta minskar antalet fält som du måste bläddra igenom när du ställer in modulen.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Record Type] </p> </td> 
   <td> <p>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska skapa. Fälten blir tillgängliga baserat på den typ av post som valts i fältet [!UICONTROL Record Type]. Dessa fält är baserade på [!DNL Salesforce]-API:t.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td> <p>Markera de fält som du vill att modulen ska konfigurera när den nya posten skapas. Obligatoriska fält visas högst upp i listan. </p> <p>Fälten som du väljer öppnas under det här fältet. Du kan nu ange värden i dessa fält.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a Record]

Den här åtgärdsmodulen läser data från ett enskilt objekt i [!DNL Salesforce].

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr>
    <td>[!UICONTROL Connection]</td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Record Type]</td>
    <td>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska [åtgärd].read.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL Record Fields]</td>
    <td>Markera de fält som du vill att modulen ska läsa. Du måste markera minst ett fält.</td>
  </tr> 
  <tr>
    <td>[!UICONTROL ID]</td>
    <td> <p>Ange eller mappa det unika [!DNL Salesforce]-ID:t för posten som du vill att modulen ska läsa.</p> <p>Om du vill hämta ID:t öppnar du objektet [!DNL Salesforce] i webbläsaren och kopierar texten i slutet av URL:en efter det sista snedstrecket (/). Exempel: <code>https://eu5.salesforce.com/&lt;object ID&gt;</code></p> </td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Record]

Den här åtgärdsmodulen tar bort en befintlig post i ett objekt.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type] </td> 
   <td> <p>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Ange eller mappa det unika [!DNL Salesforce]-ID:t för posten som du vill att modulen ska ta bort.</p> <p>Om du vill hämta ID:t öppnar du objektet [!DNL Salesforce] i webbläsaren och kopierar texten i slutet av URL:en efter det sista snedstrecket (/). Exempel: <code>https://eu5.salesforce.com/&lt;object ID&gt;</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Salesforce]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Salesforce]-modulerna.

Modulen returnerar följande:

* **[!UICONTROL Status Code]** (tal): Detta anger om HTTP-begäran lyckades eller misslyckades. Det här är standardkoder som du kan söka efter på Internet.
* **[!UICONTROL Headers]** (objekt): En mer detaljerad kontext för svars-/statuskoden som inte relaterar till utdatatexten. Alla sidhuvuden som visas i en svarshuvud är inte svarshuvuden, så en del kanske inte är användbara för dig.

  Svarshuvuden beror på den HTTP-begäran du valde när du konfigurerade modulen.

* **[!UICONTROL Body]** (objekt): Beroende på den HTTP-begäran du valde när du konfigurerade modulen kan du få tillbaka data. Dessa data, till exempel data från en [!UICONTROL GET]-begäran, finns i det här objektet.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till <code> &lt;Instance URL&gt;/services/data/v46.0/</code>.</p> <p>En lista över tillgängliga slutpunkter finns i <a href="https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/intro_what_is_rest_api.htm">Salesforce REST API Developer Guide</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code>. Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt. Till exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Exempel:** Följande API-anrop returnerar listan över alla användare i ditt [!DNL Salesforce]-konto:
>
>* **URL**: `query`
>
>* **Metod**: [!UICONTROL GET]
>
>* **Frågesträng**:
>
>* **Nyckel**: `q`
>
>* **Värde**: `SELECT Id, Name, CreatedDate, LastModifiedDate FROM User LIMIT 10`
>
>Det går att hitta matchningar av sökningen i modulens utdata under **[!UICONTROL Bundle]> [!UICONTROL Body] >[!UICONTROL records]**.
>
>I vårt exempel returnerades sex användare:
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/matches-of-the-search-350x573.png)


#### [!UICONTROL Upload Attachment/Document]

Den här åtgärdsmodulen överför en fil och bifogar den till en post som du anger, eller överför ett dokument.

Modulen returnerar ID:t för den bifogade filen eller dokumentet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type of Upload]</td> 
   <td>Välj om du vill att modulen ska överföra en bifogad fil eller ett dokument.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för objektet som du vill överföra en bifogad fil till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder]</td> 
   <td>Markera den mapp som innehåller den fil som du vill att modulen ska överföra. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source File]</td> 
   <td>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download Attachment/Document]

Den här åtgärdsmodulen hämtar ett dokument eller en bifogad fil från en post.

Du anger postens ID och vilken typ av hämtning du vill använda.

Modulen returnerar ID:t för den bifogade filen eller dokumentet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr>
    <td>[!UICONTROL Connection]</td>
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Type of Download]</td>
    <td> <p>Ange vilken typ av fil du vill hämta från Salesforce.</p> 
     <ul> 
      <li>[!UICONTROL Attachment]</li> 
      <li>[!UICONTROL Document]</li> 
      <li>[!UICONTROL ContentDocument] (Detta är ett dokument som har överförts till ett bibliotek i [!DNL Saleforce CRM Content] eller [!DNL Salesforce Files].)</li> 
     </ul> </td>
  </tr> 
  <tr>
    <td> <p>[!UICONTROL ID] / </p> <p>[!UICONTROL Attachment ID] / </p> <p>[!UICONTROL ContentDocument ID]</p> </td>
    <td> <p>Ange eller mappa det unika [!DNL Salesforce]-ID:t för posten som du vill att modulen ska hämta.</p> <p>Om du vill hämta ID:t öppnar du objektet [!DNL Salesforce] i webbläsaren och kopierar texten i slutet av URL:en efter det sista snedstrecket (/). Exempel: <code>https://eu5.salesforce.com/&lt;object ID&gt;</code></p> </td>
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Update a Record]

Denna åtgärdsmodul redigerar en post i ett objekt.

I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen. Detta minskar antalet fält som du måste bläddra igenom när du ställer in modulen.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för den post som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Record Type] </p> </td> 
   <td> <p>Välj den typ av [!DNL Salesforce]-post som du vill att modulen ska uppdatera. Fälten blir tillgängliga baserat på vilken typ av post som har valts i fältet Posttyp. Dessa fält är baserade på [!DNL Salesforce]-API:t.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td> <p>Markera de fält som du vill att modulen ska konfigurera när den nya posten skapas. Obligatoriska fält visas högst upp i listan. </p> <p>Fälten som du väljer öppnas under det här fältet. Du kan nu ange värden i dessa fält.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Överför fil

Den här åtgärdsmodulen överför en fil till Salesforce.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL  Adobe Workfront Fusion] - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document linking]</td> 
   <td>Välj om en innehållsdokumentlänk ska användas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL linkedEntityId]</td> 
   <td>Om du använder dokumentlänkning anger eller mappar du det länkade objektets ID.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ShareType]</td> 
   <td>Om du använder dokumentlänkning väljer du behörigheter för filen.<ul><li><b>Behörighet för visningsprogram</b><p>Användaren kan visa filen.</p></li><li><b>Medarbetarbehörighet</b><p>Användaren kan visa och redigera filen.</p></li><li><b>Inkommande behörigheter</b><p>Behörigheterna baseras på användarens behörigheter till den relaterade posten, till exempel ett bibliotek.</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Om du använder dokumentlänkning anger eller mappar du dokumentets synlighet.<ul><li><b>AllaAnvändare</b><p>Tillgängligt för alla användare med behörigheter</p></li><li><b>InternalUsers</b><p>Tillgängligt för interna användare med behörigheter.</p></li><li><b>SharedUsers</b><p>Tillgängligt för användare som kan se den feed som filen skickas till.</p></li></ul></td> 
  </tr>

### Sökningar

#### [!UICONTROL Search with Query]

Den här sökmodulen söker efter poster i ett objekt i [!DNL Salesforce] som matchar den sökfråga du anger. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search Type]</td> 
   <td> <p>Välj den typ av sökning som du vill att modulen ska utföra:</p> 
    <ul> 
     <li> <p>[!UICONTROL Simple]</p> </li> 
     <li> <p>[!UICONTROL Using SOSL (Salesforce Object Search Language)]</p> </li> 
     <li> <p>[!UICONTROL Using SOQL (Salesforce Object Query Language)]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Type] </p> </td> 
   <td> <p>Om du valde den enkla söktypen väljer du den typ av [!DNL Salesforce]-post som du vill att modulen ska söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] / [!UICONTROL SOSL Query] / [!UICONTROL SOQL Query]</td> 
   <td> <p>Ange frågan som du vill söka efter.</p> <p>Mer information om SOSL finns i <a href="https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/sforce_api_calls_sosl.htm">Salesforce Object Search Language (SOSL)</a> i [!DNL Salesforce] -dokumentationen.</p> <p>Mer information om SOQL finns i <a href="https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/sforce_api_calls_soql.htm">Salesforce Object Query Language (SOQL)</a> i [!DNL Salesforce] -dokumentationen.</p> <p>Obs! Observera att värdet för parametern <code>RETURNING </code>påverkar modulens utdata. Om du använder <code>LIMIT</code> ignorerar [!DNL Fusion] inställningarna i fältet [!UICONTROL Maximal count of records]. Om du inte anger någon gräns infogas värdet [!UICONTROL LIMIT = Maximal count of records].</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal count of records]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search]

Den här åtgärdsmodulen hämtar alla poster som uppfyller ett visst villkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Salesforce]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till [!DNL  Adobe Workfront Fusion] - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>Välj den typ av objekt som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>Markera fältet som du vill söka efter, operatorn som du vill använda i frågan och värdet som du söker efter i fältet. Du kan koppla frågor med hjälp av AND eller OR.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Markera de fält som du vill inkludera i modulens utdata.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>Välj om du vill att modulen ska returnera alla matchande poster eller endast den första matchande posten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximal]</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska hämta under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>
