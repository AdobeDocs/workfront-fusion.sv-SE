---
title: Anaplan-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Anaplan och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: b54a2ae43efb44ebd002357d7b2269f40523bc9f
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 0%

---

# [!DNL Anaplan] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Anaplan] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Innan du kan använda [!DNL Anaplan]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!UICONTROL Anaplan]-konto.
* Du måste konfigurera arbetsytor, modeller och andra [!DNL Anaplan]-objekt i ditt [!UICONTROL Anaplan]-konto innan Workfront Fusion kan interagera med dem.

## API-information för Anaplan

Anaplan-anslutningen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.11.5</td> 
 </tbody> 
</table>

## Anslut [!DNL Anaplan] till Workfront Fusion {#connect-anaplan-to-workfront-fusion}

Så här skapar du en anslutning för dina [!DNL Anaplan]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan [!UICONTROL Connection].
1. Fyll i följande fält:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för den nya anslutningen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Välj om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL email]</td>
        <td>
          <p>Ange e-postadressen för det här Anaplan-kontot</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Password]</td>
        <td>Ange lösenordet för det här Anaplan-kontot.</td>
      </tr>
     </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

<!--1. Click **[!UICONTROL Add]** next to the [!UICONTROL Connection] box.
1. Select the connection type.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Basic]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL Basic] connection requires only an email address and password to create the connection. </p> <p>Enter a name for the connection, then enter your email address and the password of your [!DNL Anaplan] account.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL CA Certificate]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL CA Certificate] connection requires a [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data]. You can generate these in your [!DNL Anaplan] account. For instructions, see the [!DNL Anaplan] documentation.</p> <p>Enter a name for the connection, then enter the [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data] that you generated in your [!DNL Anaplan] account.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Click **[!UICONTROL Continue]** to save the connection and return to the module.-->

## [!DNL Anaplan]-moduler och deras fält

När du konfigurerar [!DNL Anaplan]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Anaplan] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

#### [!DNL Watch records]

Den här utlösarmodulen startar ett scenario när en post av den valda typen skapas eller uppdateras.

>[!NOTE]
>
>Den här modulen returnerar data för nya poster. Den returnerar inte data från ändrade befintliga poster.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Typ av objekt som ska bevakas</td> 
   <td>Välj den typ av objekt som du vill bevaka. Scenariot börjar när den här typen av post skapas eller uppdateras.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID för &lt;Object&gt;</td> 
   <td>Ange ID:t för objektet i Anaplan, t.ex. en modell eller modul, som är associerat med objekten som du vill bevaka</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gräns</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Create a list item]](#create-a-list-item)
* [Ta bort en post](#delete-a-record)
* [Exportera data](#export-data)
* [Importera data](#import-data)
* [[!UICONTROL Make a custom API Call]](#make-a-custom-api-call)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Run an action]](#run-an-action)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Upload a file]](#upload-a-file)

#### [!UICONTROL Create a list item]

Den här åtgärdsmodulen lägger till ett nytt objekt i en lista i Anaplan.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Connection]</td>
        <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Workspace ID]</td>
        <td>Markera eller mappa ID:t för Anaplan Workspace som innehåller listan där du vill lägga till ett objekt.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Model ID]</td>
        <td>Markera eller mappa ID:t för den modell som innehåller listan där du vill lägga till ett objekt.</td>
    </tr>
    <tr>
        <td>[!UICONTROL List ID]</td>
        <td>Markera eller mappa ID:t för den lista där du vill skapa ett objekt.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Name]</td>
        <td>Ange ett namn för det nya objektet.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Code]</td>
        <td>Ange koden för den nya artikeln. Koder är användargenererade koder som gör att du kan skilja mellan radartiklar med samma namn.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Parent]</td>
        <td>Ange namnet på det överordnade objekt som du vill skapa det nya objektet under.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Properties]</td>
        <td>Om listan som du vill lägga till ett objekt i har anpassade egenskaper, markerar du de egenskaper som du vill lägga till värden för och lägger sedan till värdena.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Subsets]</td>
        <td>Om listan som du vill lägga till objekt i innehåller anpassade delmängder markerar du de delmängder som du vill lägga till objektet i.</td>
    </tr>
</table>

#### [!UICONTROL Delete a record]

Den här åtgärdsmodulen tar bort en befintlig post.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa det ID för Anaplan Workspace som innehåller det objekt du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model ID]</td> 
   <td>Ange eller mappa ID:t för den modell som innehåller objektet som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Markera den typ av objekt som ska tas bort.</p> 
    <ul> 
     <li> <p><b>Åtgärd</b> </p> <p>Markera eller mappa åtgärden som ska tas bort.</p> </li> 
     <li> <p><b>Listobjekt</b> </p> <p>Markera listan som du vill ta bort ett objekt från och ange eller mappa sedan ID:t eller koden för objektet som du vill ta bort</p>  </li> 
     <li> <p><b>[!UICONTROL File]</b> </p> <p>Markera eller mappa filen som ska tas bort.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL Export data]

Den här åtgärdsmodulen hämtar data från Anaplan med hjälp av exportdefinitioner.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa det ID för Anaplan Workspace som innehåller de data som du vill exportera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model ID]</td> 
   <td>Ange eller mappa ID:t för den modell som innehåller de data som du vill exportera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Exportera definition-ID</td> 
   <td> <p>Ange eller mappa ID:t för den Anaplan-exportdefinition som du vill använda.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### Importera data

Den här åtgärdsmodulen importerar data till Anaplan.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>Markera eller mappa ID:t för Anaplan Workspace där du vill importera data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model ID]</td> 
   <td>Ange eller mappa ID:t för modellen där du vill importera data.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Exportera definition-ID</td> 
   <td> <p>Ange eller mappa ID:t för den Anaplan-importdefinition som du vill använda.</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make a custom API Call]

Med den här modulen kan du utföra ett anpassat API-anrop till API:t [!DNL Anaplan].

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en sökväg i förhållande till <code>https://api.anaplan.com/2/0/</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Ange frågesträngen för begäran.</p> </td> 
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

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser en enda post.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj vilken typ av post som ska läsas.</p> 
    <ul> 
     <li> <p><b>Modell</b> </p> <p>Markera eller mappa ID:t för den modell som du vill läsa</p> </li> 
     <li> <p><b>Modelllista</b> </p> <p>Markera eller mappa ID:n för den Workspace och modell som innehåller den lista som du vill läsa och välj sedan List. I fältet [!UICONTROL Data type] väljer du om du vill läsa data eller metadata.</p> </li> 
     <li> <p><b>Modellversion</b> </p> <p>Markera eller mappa ID:t för den modell som du vill läsa.</p> </li> 
     <li> <p><b>Användare</b> </p> <p>Ange om du vill returnera data om ägaren till kontot som används eller om en annan användare. Om du väljer en annan användare markerar du namnet på användaren.</p> </li> 
     <li> <p><b>Workspace</b> </p> <p>Markera eller mappa ID:t för den Workspace som du vill läsa.</p> </li> 
     <li> <p><b>Visa</b> </p> <p>Markera eller mappa ID:t för den modell som innehåller vyn som du vill läsa.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Run an action]

Den här åtgärdsmodulen importerar, exporterar, tar bort eller bearbetar en åtgärd.

<table style="table-layout:auto"> 
     <col/>
     <col/>
     <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection]</td>
        <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect Anaplan to Workfront Fusion]</a> i den här artikeln.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Workspace ID]</td>
        <td>Markera eller mappa ID:t för [!DNL Anaplan] Workspace där du vill utföra åtgärden</td>
      </tr>
      <tr >
        <td role="rowheader">[!UICONTROL Model ID]</td>
        <td>Markera eller mappa ID:t för modellen där du vill utföra åtgärden.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Action type]</td>
        <td>
          <p>Välj den åtgärd som du vill utföra</p>
            <ul>
              <li>
                <p><b>[!UICONTROL Delete]</b>
                </p>
                <p>Ange eller mappa ID:t för åtgärden som du vill ta bort.</p>
              </li>
              <li>
                <p><b>[!UICONTROL Export]</b>
                </p>
                <p>Ange eller mappa ID:t för exportdefinitionen som du vill använda. Du kan exportera till följande filformat:</p>
                  <ul>
                    <li>
                      <p>XLS</p>
                    </li>
                    <li>
                      <p>XSX</p>
                    </li>
                    <li>
                      <p>CSV</p>
                    </li>
                  </ul>
                </li>
                <li>
                  <p><b>[!UICONTROL Import] </b>
                  </p>
                  <p style="font-weight: normal;">Ange eller mappa ID:t för importdefinitionen som du vill använda.</p>
                </li>
                <li>
                 <p><b>[!UICONTROL Process]</b>
                 </p>
                  <p>Ange eller mappa ID:t för processen som du vill använda. </p>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>


#### [!UICONTROL Update a record]

Den här åtgärdsmodulen uppdaterar en enskild post i [!UICONTROL Anaplan].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj den typ av post som du vill uppdatera.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL List item]</b> </p> <p>Mer information finns i <a href="#create-a-list-item" class="MCXref xref">Skapa ett listobjekt</a> i den här artikeln.</p> </li> 
     <li> <p><b>[!UICONTROL Module cell data]</b> </p> <p>När du uppdaterar celldata uppdateras även alla efterföljande beräkningar som använder dessa data.</p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Model ID]</b> </p> <p>Markera eller mappa modellen som innehåller cellen som du vill uppdatera.</p> </li> 
       <li> <p><b>[!UICONTROL Module ID]</b> </p> <p>Markera eller mappa modulen som innehåller cellen som du vill uppdatera</p> </li> 
       <li> <p><b>[!UICONTROL Line item name]</b> </p> <p>Markera eller mappa radobjektet i cellen som du vill uppdatera</p> </li> 
       <li> <p style="font-weight: bold;">[!UICONTROL Dimension ID]</p> <p>Markera eller mappa dimensionen som finns på radartikeln.</p> 
       <p><b>Obs! </b> 
       <ul>
       <li> Dimension-nyckeln (värde) måste vara antingen <code>dimensionName</code> (nästa) eller <code>dimensionId</code> (ID).</li>
       <li>Objektnyckeln (värdet) måste vara <code>itemName</code> (text), <code>itemCode</code> (text) eller <code>itemId</code> (ID).</li>
       <li>Dimension och artikelnycklar måste vara av samma typ (text eller ID).
       </ul>
        </p> 
        <p>Sök efter dimensioner i [!DNL Anaplan Anapedia] om du vill ha information om dimensioner.</p> </li> 
       <li> <p><b>[!UICONTROL Value]</b> </p> <p>Ange eller mappa cellens nya värde.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Model current fiscal year]</b> </p> <p>Ange Workspace-ID och modell-ID för den modell som du vill uppdatera räkenskapsåret för, och ange eller mappa sedan modellens nya år.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload file for action]

Den här åtgärdsmodulen överför en befintlig fil i Anaplan till ytterligare platser i Anaplan.
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Workspace ID]</td>
<td>Markera eller mappa ID:t för den [!DNL Anaplan] Workspace där du vill överföra en fil.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Model ID]</td>
<td>Markera eller mappa ID:t för modellen där du vill överföra en fil.</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL File ID]</td>
<td>Markera eller mappa ID:t för filen som du vill överföra.</td>
</tr>
</tbody>
</table>
</div>

### Sökningar

#### [!UICONTROL Get record]

Den här sökmodulen returnerar alla tillgängliga poster av den valda typen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Anaplan] finns i <a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Anaplan] till Workfront Fusion </a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record types]</td> 
   <td> <p>Välj den typ av post som du vill hämta.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Workspaces]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Models]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Line items]</b> </p> <p>Markera eller mappa ID:t för modellen som innehåller de [!DNL line] objekt som du vill hämta.</p> </li> 
       <li> <p><b>[!UICONTROL Model lists]</b> </p> <p>Markera eller mappa det ID för Workspace och det modell-ID som innehåller de modelllistor som du vill hämta.</p> </li> 
       <li> <p><b>[!UICONTROL Model calendar]</b> </p> <p>Markera eller mappa ID:t för den Workspace som innehåller den modellkalender som du vill hämta.</p> </li> 
       <li> <p><b>[!UICONTROL Model versions]</b> </p> </li> 
       <li> <p>Markera eller mappa ID:t för den modell som innehåller de modellversioner som du vill hämta.</p> </li> 
       <li> <p><b>[!UICONTROL Users]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Views]</b> </p> <p>Välj om du vill välja vy efter modul eller modell och markera eller mappa sedan ID:t för modulen eller modellen som innehåller vyn som du vill hämta.</p> </li> 
      </ul> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Return workspace size]</td> 
   <td>Aktivera det här alternativet om du vill returnera en uppskattning av arbetsytans aktuella storlek. Beräkningen baseras på storleken på alla moduler i arbetsytan.</td> 
  </tr> 
 </tbody> 
</table>
