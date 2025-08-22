---
title: Datadogmoduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Datadog samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: c8c5f2e3-5af1-4957-bb6f-6c19c35102c5
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---

# [!DNL Datadog] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Datadog] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Du måste ha ett [!DNL Datadog]-konto för att kunna använda [!DNL Datadog]-moduler.

## API-information för data

Datadoggkopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>1.0.11</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Datadog] till Workfront Fusion {#connect-datadog-to-workfront-fusion}

### Hämta API-nyckeln och programnyckeln {#retrieve-your-api-key-and-application-key}

Om du vill ansluta ditt [!DNL Datadog]-konto till Workfront Fusion måste du hämta en API-nyckel och en programnyckel från ditt [!DNL Datadog]-konto.

1. Logga in på ditt [!DNL Datadog]-konto.
1. Klicka på **[!UICONTROL Integrations]** i den vänstra navigeringspanelen och sedan på **[!UICONTROL APIs]**.
1. Klicka på **[!UICONTROL API Keys]** på huvudskärmen.
1. Hovra över det lila fältet för att visa API-nyckeln.
1. Kopiera API-nyckeln till en säker plats.
1. Klicka på **[!UICONTROL Application Keys]** på huvudskärmen.
1. Hovra över det lila fältet för att visa programnyckeln.
1. Kopiera programnyckeln till en säker plats.

### Skapa en anslutning till [!DNL Datadog] i Workfront Fusion

Du kan skapa en anslutning till ditt [!DNL Datadog]-konto direkt inifrån en [!UICONTROL Datadog]-modul.

1. Klicka på [!UICONTROL Datadog] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Fyll i modulens fält enligt följande:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection Name]</td> 
      <td> <p> Ange ett namn för anslutningen.</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om den här anslutningen är avsedd för en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL Domain] </td> 
      <td> <p>Välj den domän du vill ansluta till (USA eller EU).</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key Location] </td> 
      <td> <p>Välj om API-nyckeln ska inkluderas i huvudet eller i frågesträngen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td> <p> Ange din [!DNL Datadog] API-nyckel. </p> <p>Instruktioner om hur du hämtar API-nyckeln finns i <a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">Hämta API-nyckeln och programnyckeln</a> i den här artikeln.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Datadog]-moduler och deras fält

När du konfigurerar [!DNL Datadog]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Datadog] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Åtgärder

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Post Timeseries Points]](#post-timeseries-points)

#### [!UICONTROL Make an API Call]

Med den här åtgärdsmodulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Datadog]-konto till Workfront Fusion finns i <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Datadog] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Dedicated Domain]</td> 
   <td>Vissa av API-slutpunkterna för DataDialog som förväntar sig mycket inkommande trafik körs på deras dedikerade domäner. Markera den här kryssrutan om du vill använda den dedikerade domänen för ditt API-anrop.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code>https://api.datadoghq.com/api/</code>. Exempel:<code> /v1/org</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
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

**Exempel:** Följande API-anrop returnerar alla instrumentpaneler i ditt [!DNL Datadog]-konto:

URL: `/v1/dashboard`

Metod: `GET`

![Exempel på API-anrop för datadogg](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-example.png)

Resultatet finns i modulens utdata under Paket > Brödtext > kontrollpaneler.

I vårt exempel returnerades tre kontrollpaneler:

![API-svar för datablad](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-response-example.png)

#### [!UICONTROL Post Timeseries Points]

Med modulen kan du publicera tidsseriedata som kan visas på kontrollpanelerna för [!DNL Datadog].

Gränsen för komprimerade nyttolaster är 3,2 megabyte (3200000) och 62 megabyte (62914560) för dekomprimerade nyttolaster.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Datadog]-konto till Workfront Fusion finns i <a href="#connect-datadog-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Datadog] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> Välj den typ av mätvärden som du vill använda. 
   <ul>
   <li>Mätare</li>
   <li>Hastighet</li>
   <li>Antal</li>
   </ul>
   </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL Interval]</td> 
   <td> Om måttets typ är hastighet eller antal definierar du motsvarande intervall.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Points]</td> 
   <td><p>Lägg till punkter som hör till ett mätvärde.</p> <p>Detta är en JSON-array med punkter. Varje punkt har följande format: <code>[[POSIX_timestamp, numeric_value], ...] </code></p> <p>Obs!  <p>Tidsstämpeln måste vara i sekunder.</p> <p>Tidsstämpeln måste vara aktuell. Aktuell definieras som inte mer än 10 minuter i framtiden eller mer än 1 timme i det förflutna.</p> <p> Det numeriska värdeformatet ska vara ett flyttal.</p> </p> <p>Det här fältet måste innehålla minst 1 objekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Host]</td> 
   <td>Ange namnet på värden som genererade måttet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> För varje tagg som du vill lägga till i måttet klickar du på <b>Lägg till objekt</b> och anger taggens värde.</td> 
  </tr> 
 </tbody> 
</table>
