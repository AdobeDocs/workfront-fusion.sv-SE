---
title: Adobe Creative Cloud Libraries-moduler
description: Med  [!DNL Adobe Workfront Fusion Adobe Creative Cloud] biblioteksmodulerna kan du starta ett scenario när ett element eller bibliotek skapas eller uppdateras. Du kan också överföra, hämta, arkivera eller lista element, eller ringa ett anrop till  [!DNL Adobe Creative Cloud Libraries] API:t.
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 0%

---

# Moduler för Adobe Creative Cloud Libraries

Med Adobe Workfront Fusion [!DNL Adobe Creative Cloud Libraries]-modulerna kan du starta ett scenario när ett element eller bibliotek skapas eller uppdateras. Du kan också överföra, hämta, arkivera eller lista element, eller ringa ett anrop till [!DNL Adobe Creative Cloud Libraries]-API:t.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

>[!IMPORTANT]
>
>Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs</p>
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL Adobe Creative Cloud Libraries]-konto för att kunna använda [!UICONTROL Adobe Creative Cloud]-moduler.

## API-information för Adobe Creative Cloud Libraries

Adobe Creative Cloud Libraries-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://cc-libraries.adobe.io/api/v1</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.1.7</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Adobe Creative Cloud Libraries]-moduler och deras fält

När du konfigurerar [!UICONTROL Adobe Creative Cloud Libraries]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Adobe Creative Cloud Libraries] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Element](#elements)

* [Bibliotek](#libraries)

* [Övriga](#other)


### Element

* [[!UICONTROL Archive an Element]](#archive-an-element)

* [[!UICONTROL Get an Element]](#get-an-element)

* [[!UICONTROL List Elements]](#list-elements)

* [[!UICONTROL Upload an Element]](#upload-an-element)

* [!UICONTROL [Se nytt element i bibliotek]](#watch-new-element-in-library)

* [[!UICONTROL Watch Updated Elements]](#watch-updated-elements)


#### [!UICONTROL Archive an Element]

Denna åtgärdsmodul arkiverar ett element från ett bibliotek.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Markera eller mappa biblioteket som innehåller elementet som du vill arkivera.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>Markera eller mappa elementet som du vill arkivera.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Get an Element]

Den här åtgärdsmodulen returnerar ett enskilt element från ett bibliotek.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td>Markera eller mappa biblioteket som innehåller elementet som du vill hämta.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>Ange eller mappa ID:t för elementet som du vill hämta.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>Välj den typ av information som modulen returnerar. </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>Basdata</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>Alla tillgängliga data</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>En förenklad lista med resurser som är associerade med bibliotekselementet</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL List Elements]

Den här åtgärdsmodulen hämtar en lista med element i ett bibliotek.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Markera eller mappa biblioteket som du vill lista element från.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Order by]</td>
      <td>Välj om du vill beställa resultat efter namn eller efter det senaste datum som elementet ändrades.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type]</td>
      <td >Ange eller mappa en MIME-typ för att begränsa resultaten till element som identifieras med den angivna MIME-typen. Exempel: <code>string</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>Välj den typ av information som modulen returnerar. </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>Basdata</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>Alla tillgängliga data</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>En förenklad lista med resurser som är associerade med bibliotekselementet</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch New Element in Library]

Denna utlösarmodul startar ett scenario när ett element läggs till i ett bibliotek.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Välj det bibliotek som du vill bevaka för uppdaterade element.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL Watch Updated Elements]

Den här utlösarmodulen startar ett scenario när ett element i ett bibliotek uppdateras.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Välj det bibliotek som du vill bevaka för nya element.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
    </tr>
  </tbody>
</table>

### Bibliotek

* [[!UICONTROL Watch New Libraries]](#watch-new-libraries)

* [[!UICONTROL Watch Updated Libraries]](#watch-updated-libraries)


#### [!UICONTROL Watch New Libraries]

Den här utlösarmodulen startar ett scenario när ett nytt bibliotek skapas.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch Updated Libraries]

Den här utlösarmodulen startar ett scenario när ett befintligt bibliotek uppdateras.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
    </tr>
  </tbody>
</table>

### Övriga

* [Göra ett API-anrop](#make-an-api-call)
* [Överför en resurs](#upload-an-asset)

#### [!UICONTROL Make an API Call]

Den här modulen gör ett anpassat API-anrop till API:t [!DNL Adobe Creative Cloud Libraries].

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>Instruktioner om hur du ansluter ditt Adobe Creative Cloud-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner.</a></p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Ange en relativ sökväg till <code>https://cc-libraries.adobe.io/api</code>.</p>
    <p>Till exempel <code>/v1/libraries</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL API version]</td>
      <td>
        <p>Välj den version av [!DNL Adobe Analytics]-API:t som du vill ansluta till.</p>
      </td>
    </tr>    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]</td>
      <td>
        <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"name":"something-urgent"}</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
       <tr>
      <td role="rowheader">[!UICONTROL Upload a transient document]</td>
      <td>
      <p>Om du vill överföra ett tillfälligt dokument anger du källfilen för dokumentet som du vill överföra.</p>
      <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p>
    </td>
    </tr>
</tbody>
</table>


#### [!UICONTROL Upload an Asset]

Denna åtgärdsmodul överför en liten filresurs till ett befintligt bibliotek. Största filstorlek är 1 GB.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>Välj en befintlig Creative Cloud Libraries-anslutning. Det går för närvarande inte att skapa en anslutning i Creative Cloud Libraries Connector. Befintliga anslutningar fungerar som förväntat.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >Välj det bibliotek som du vill överföra en resurs till.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Invocation Mode]</td>
      <td>
        <p>Välj det bearbetningsläge som den här förfrågningsprocessen ska anropas med.</p>
        <ul>
          <li>
            <p><b>[!UICONTROL sync]</b>
            </p>
            <p>API-anropet behandlas synkront. Svaret levereras när bearbetningen är slutförd (såvida inte samtalstiderna är slut).</p>
          </li>
          <li>
            <p><b>[!UICONTROL async]</b>
            </p>
            <p>Svaret på den asynkrona övervakaren returneras omedelbart, och bearbetningen av begäran sker asynkront. Anropet ansvarar för avsökningen av slutpunkten tills det är klart.</p>
          </li>
          <li>
            <p><b>[!UICONTROL sync,async]</b> (Standard)</p>
            <p>Ett försök görs att synkronisera begäran. När bearbetningen sträcker sig över mer än 5 000 ms returneras det asynkrona skärmsvaret. URL:en för övervakaren bör avfrågas tills begäran är slutförd.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element Type]</td>
      <td >Välj den typ av element som du vill överföra</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL File Type]</td>
      <td >Ange eller mappa MIME-typen för den överförda filen.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source File]</td>
      <td>
        <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p>
      </td>
    </tr>
  </tbody>
</table>





