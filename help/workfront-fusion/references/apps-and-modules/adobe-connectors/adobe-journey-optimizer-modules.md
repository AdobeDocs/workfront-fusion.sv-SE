---
title: Adobe Journey Optimizer moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Adobe Journey Optimizer] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 1d0ccf4d-9f06-4210-86ec-7da7970f6a47
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '3296'
ht-degree: 0%

---

# [!DNL Adobe Journey Optimizer] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Adobe Journey Optimizer] samt ansluta det till flera tredjepartsprogram och -tjänster. Med modulerna [!DNL Adobe Journey Optimizer] kan du skapa, läsa, uppdatera eller ta bort poster, eller utföra ett anpassat API-anrop till API:t [!DNL Adobe Journey Optimizer] .


Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

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

Innan du kan använda [!DNL Adobe Journey Optimizer]-anslutningen måste du se till att följande krav uppfylls:

* Du måste ha ett aktivt [!DNL Adobe Journey Optimizer]-konto.

## Adobe Journey Optimizer API-information

Adobe Journey Optimizer Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>{connection.url}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.7.11</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till Adobe Journey Optimizer

Du kan skapa en anslutning i alla Adobe Journey Optimizer-moduler.

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning i någon av modulerna.

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
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Organization ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Sandbox Name]</td>
        <td>Ange namnet på den sandlåda som anslutningen ska använda.</td>
        </tr>
      </tbody>
    </table>



   <!--Markdown 0032 placeholder-->


## [!DNL Adobe Journey Optimizer]-moduler och deras fält

När du konfigurerar [!DNL Adobe Journey Optimizer]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Adobe Journey Optimizer] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Konfigurationshantering](#configuration-management)
* [Pakethantering](#package-management)
* [Posthantering](#record-management)
* [Meddelandehantering](#message-management)
* [Statuskontroller](#status-checks)
* [Sökningar](#searches)
* [Övriga](#other)




### Konfigurationshantering

* [Skapa en konfiguration](#create-a-configuration)
* [Distribuera en konfiguration](#deploy-a-configuration)
* [Uppdatera en konfiguration](#update-a-configuration)
* [Avdistribuera en konfiguration](#undeploy-a-configuration)
* [Kontrollera om konfigurationen kan distribueras](#check-if-configuration-can-be-deployed)
* [Ta bort en konfiguration](#delete-a-configuration)
* [Hämta en konfiguration](#get-a-configuration)

#### Skapa en konfiguration

Den här åtgärdsmodulen skapar en slutpunkt för begränsning eller en slutpunktskonfiguration.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Ange om du skapar en begränsning eller en begränsning.<ul><li><p><b>Takning</b></p>Fortsätt till <a href="#capping-fields" class="MCXref xref" >Fånga fält</a>.</li><li><p><b>Begränsning</b></p>Fortsätt till <a href="#throttling-fields" class="MCXref xref" >Begränsa fält</a>.</li></ul></td> 
  </tr> 
   </tbody> 
</table>

##### Fånga fält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange eller mappa URL:en för den slutpunkt som du vill konfigurera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL IMS Org ID]</td> 
   <td>Ange eller mappa organisationens Adobe IMS ID.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Methods]</td> 
   <td>Välj de metoder som ska användas i den här konfigurationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Service]</td> 
   <td>Ange om du använder en åtgärd eller en datakälla för den här konfigurationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum HTTP connections]</td> 
   <td>Ange eller mappa maximalt antal samtidiga anslutningar till den här slutpunkten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum calls]</td> 
   <td>Ange eller mappa det maximala antalet anrop som ska utföras under den period som anges i fältet Tidsperiod.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Time period (milliseconds)]</td> 
   <td>Ange eller mappa antalet millisekunder som relaterar till fältet Maximalt antal anrop.</td> 
  </tr> 
 </tbody> 
</table>

##### Begränsningsfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för den här konfigurationen.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för den här konfigurationen.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL URL pattern]</td> 
   <td>Ange eller mappa URL:en för den slutpunkt som du vill strypa.</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Methods]</td> 
   <td>Välj de metoder som ska användas i den här konfigurationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max throughput]</td> 
   <td>Ange om du använder en åtgärd eller en datakälla för den här konfigurationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum HTTP connections]</td> 
   <td>Ange eller mappa maximalt antal samtidiga anslutningar till den här slutpunkten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum calls]</td> 
   <td>Ange eller mappa det maximala dataflöde som du vill ha för den här slutpunkten. Värdet måste vara mellan 200 och 5 000.</td> 
  </tr> 
 </tbody> 
</table>

#### Distribuera en konfiguration

Den här åtgärdsmodulen distribuerar den angivna konfigurationen för begränsning eller begränsning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Ange om du distribuerar en capping-konfiguration eller en begränsningskonfiguration.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Ange eller mappa ID:t för konfigurationen som du vill distribuera.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en konfiguration

Den här åtgärdsmodulen uppdaterar den angivna konfigurationen för begränsning och begränsning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Ange om du uppdaterar en takkonfiguration eller en begränsningskonfiguration.<ul><li><p><b>Takning</b></p>Mer information finns i <a href="#capping-fields" class="MCXref xref" >Fånga fält</a> i avsnittet Skapa en konfiguration i den här artikeln.</li><li><p><b>Begränsning</b></p>Mer information om fält finns i <a href="#throttling-fields" class="MCXref xref" >Begränsa fält</a> i avsnittet Skapa en konfiguration i den här artikeln.</li></ul></td> 
  </tr> 
  </tbody> 
</table>

#### Avdistribuera en konfiguration

Den här åtgärdsmodulen avdistribuerar en begränsning eller begränsning av konfigurationen. Konfigurationstillståndet ändras tillbaka till tillståndet före distributionen (`created` eller `updated`).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Välj om du vill avdistribuera en takkonfiguration eller en strypningskonfiguration.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Ange eller mappa ID:t för konfigurationen som du vill ta bort distributionen från.</td> 
  </tr> 
 </tbody> 
</table>

#### Kontrollera om konfigurationen kan distribueras

Den här åtgärdsmodulen verifierar om det går att distribuera en begränsning eller begränsning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Ange om du kontrollerar en takkonfiguration eller en begränsningskonfiguration.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Ange eller mappa ID:t för konfigurationen som du vill kontrollera.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en konfiguration

Den här åtgärdsmodulen tar bort en slutpunkt eller begränsningskonfiguration.

Om konfigurationen har distribuerats måste den avdistribueras innan den kan tas bort.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Välj om du vill ta bort en takkonfiguration eller en begränsningskonfiguration.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Ange eller mappa ID:t för konfigurationen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en konfiguration

Den här åtgärdsmodulen returnerar konfigurationen för begränsning eller begränsning som identifieras av det angivna ID:t. Den senaste definitionen returneras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Välj om du hämtar en capping-konfiguration eller en begränsningskonfiguration.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Configuration ID]</td> 
   <td>Ange eller mappa ID:t för konfigurationen som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>




### Pakethantering

* [Skapa ett paket](#create-a-package)
* [Uppdatera ett paket](#update-a-package)
* [Ta bort ett paket](#delete-a-package)
* [Söka efter ett paket](#look-up-a-package)
* [Importera ett paket](#import-a-package)
* [Publicera ett paket](#publish-a-package)
* [Skicka en import](#submit-an-import)



#### Skapa ett paket

Den här åtgärdsmodulen skapar ett paket med flera artefakter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för paketet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning av paketet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>Ange eller mappa den tidsstämpel som definierar paketets förfallodatum. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package type]</td> 
   <td>Välj den typ av paket som du vill skapa.<ul><li><p><b>Fullständig</b></p>Paketet innehåller alla artefakter</p></li><li><p><b>Delvis</b></p><p>Paketet innehåller bara artefakter som du lägger till. </p></li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>Om du skapar ett partiellt paket klickar du på <b>Lägg till artefakt</b> för varje artefakt som du vill lägga till och anger artefaktens ID, typ och titel. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Sandbox]</td> 
   <td>Ange eller mappa namnet och IMS-organisationsnumret för sandlådan som innehåller objekten som du vill att paketet ska innehålla.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera ett paket

Den här åtgärdsmodulen lägger till eller tar bort artefakter från ett paket eller uppdaterar paketets metadata.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select action]</td> 
   <td>Välj den åtgärd som du vill utföra.<ul><li><p><b>Lägg till artefakt</b></p><p>För varje artefakt som du vill lägga till klickar du på <b>Lägg till artefakt</b> och anger artefaktens ID, typ och titel. Ange eller mappa sedan utgångsdatumet för paketet. </p></li><li><p><b>Ta bort artefakt</b></p><p>För varje artefakt som du vill ta bort klickar du på <b>Lägg till artefakt</b> och anger artefaktens ID, typ och titel. </p></li><li><p><b>Uppdatera metadata</b></p><p>Ange nya värden för namn, beskrivning eller källsandlådans namn eller IMS-organisations-ID.</p></li></ul></td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort ett paket

Den här åtgärdsmodulen tar bort ett paket med flera felaktigheter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Söka efter ett paket

Den här åtgärdsmodulen hämtar information om det angivna paketet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill returnera information för.</td> 
  </tr> 
 </tbody> 
</table>

#### Importera ett paket

Den här åtgärdsmodulen hämtar objekt som står i konflikt i den angivna målsandlådan. Objekt i konflikt representerar liknande objekt som redan finns i målsandlådan.

Du måste publicera ett paket innan du kan importera det.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket du vill importera.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Ange eller mappa namnet på den sandlåda där du vill importera paketet.</td> 
  </tr> 
 </tbody> 
</table>

#### Publicera ett paket

Du måste publicera ett paket innan du kan importera det.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill publicera.</td> 
  </tr> 
 </tbody> 
</table>

#### Skicka en import

Den här åtgärdsmodulen skickar en import för ett paket när du har granskat konflikter och tillhandahållna ersättningar. Resultatet anges som en nyttolast, som startar importjobbet för målsandlådan enligt vad som anges i nyttolasten.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill publicera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för importjobbet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning av importjobbet</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Destination sandbox) Name]</td> 
   <td>Ange eller mappa namnet på den sandlåda som du skickar importen till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Destination sandbox) IMS Org ID]</td> 
   <td>Ange eller mappa Adobe IMS-organisations-ID:t för den sandlåda som du skickar importen till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) ID]</td> 
   <td>Ange eller mappa ID:t för sandlådan som innehåller det paket som du vill publicera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) Type]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL (Source sandbox) Link]</td> 
   <td>Ange eller mappa länken för det paket som du vill publicera.</td> 
  </tr> 
 </tbody> 
</table>


<!--

### Artifact management

* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)

#### Copy artifacts synchronously

This action module copies artifacts from a source sandbox into a destination sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the new file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination sandbox]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to copy, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

#### Export Artifacts asynchronously

This action module exports artifacts from the specified sandbox.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Enter or map a name for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Enter or map a description for the export file</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Artifacts]</td> 
   <td>For each artifact you want to export, click <b>Add artifact</b> and continue to <a href="#artifact-fields" class="MCXref xref" >Artifact fields</a>.</td> 
  </tr> 
 </tbody> 
</table>

##### Artifact fields

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Enter or map the ID of the artifact.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Enter or map the artifact type, such as <code>REGISTRY_SCHEMA<code> or <code>JOURNEY</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Version]</td> 
   <td>Enter or map the visibility of the artifact. This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Enter or map the visibility (tenant or global). This applies only to Registry objects.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Found]</td> 
   <td>Select <b>Yes</b> if this item was found using a GET operation.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tasks]</td> 
   <td>For each task you want to add, click <b>Add task</b> and fill in the following:
   <ul>
   <li><p><b>Method</b></p></li>
   <li><p><b>Action</b></p></li>
   <li><p><b>Using</b></p></li>
   <li><p><b>With</b></p></li>
   </ul>
   </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Messages]</td> 
   <td>For each task you want to add, click <b>Add message</b> and fill in the following:
   <ul>
   <li><p><b>Status</b></p><p>Enter or map the status that this message represents, such as <code>ERROR</code>.</li>
   <li><p><b>Attempt</b></p><p>Enter or map the attempt number related to this message. This may be useful if different attempts produce different messages.</p></li>
   <li><p><b>Message</b></p><p>Enter or map the text of the message.</li>
   <li><p><b>Object</b></p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



#### Import Artifacts asynchronously

This action module imports a snapshot containing artifacts.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Snapshot ID]</td> 
   <td>Enter or map the ID of the snapshot you want to import.</td> 
  </tr> 
 </tbody> 
</table>

-->

### Posthantering

* [Skapa en post](#create-a-record)
* [Uppdatera en post](#update-a-record)
* [Ta bort en post](#delete-a-record)
* [Laga en post](#patch-a-record)
* [Hämta en post](#get-a-record)

#### Skapa en post

Den här åtgärdsmodulen skapar en ny innehållsmall eller ett nytt innehållsfragment.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Ange om du skapar en innehållsmall eller ett innehållsfragment.<ul><li><p><b>Innehållsmall</b></p>Fortsätt till <a href="#template-fields" class="MCXref xref" >Mallfält</a>.</li><li><p><b>Innehållsfragment</b></p>Fortsätt till <a href="#fragment-fields" class="MCXref xref" >fragmentfält</a>.</li></ul></td> 
  </tr> 
  </tbody> 
</table>

##### Mallfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för innehållsmallen.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för innehållsmallen.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Välj den typ av mall som du vill skapa.</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channels]</td> 
   <td>Markera de kanaler som ingår i den här mallen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content template origin]</td> 
   <td>Välj mallens källa.</td>  
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Om du vill ta med anpassade egenskaper i den nya mallen väljer du Lägg till metadata och anger eller mappar metadatans nyckel och värde. Upprepa för varje anpassat fält som du vill inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email HTML]</td> 
   <td>Ange eller mappa HTML för e-postmeddelandet som ingår i den här mallen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Editor context]</td> 
   <td>Om du vill inkludera anpassade egenskaper i e-postmeddelandet väljer du Lägg till redigerarkontext och anger eller mappar kontextens nyckel och värde. Upprepa för varje anpassat fält som du vill inkludera.</td> 
  </tr> 
 </tbody> 
</table>

##### Fragmentfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för det här innehållsfragmentet.</td> 
<tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för det här innehållsfragmentet.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Välj den typ av mall som du vill skapa.</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channels]</td> 
   <td>Markera de kanaler som ingår i den här mallen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content fragment origin]</td> 
   <td>Välj källan för det här fragmentet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>Om du vill ta med anpassade egenskaper i den nya mallen väljer du Lägg till metadata och anger eller mappar metadatans nyckel och värde. Upprepa för varje anpassat fält som du vill inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td>Ange eller mappa fragmentets innehåll.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Editor context]</td> 
   <td>Om du vill inkludera anpassade egenskaper i e-postmeddelandet väljer du Lägg till redigerarkontext och anger eller mappar kontextens nyckel och värde. Upprepa för varje anpassat fält som du vill inkludera.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en post

Den här åtgärdsmodulen uppdaterar en innehållsmall eller ett fragment.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Ange om du uppdaterar en takkonfiguration eller en begränsningskonfiguration.<ul><li><p><b>Mall</b></p>Mer information om fält finns i <a href="#template-fields" class="MCXref xref" >Mallfält</a> i avsnittet Skapa en post i den här artikeln.</li><li><p><b>Fragment</b></p>För fält, se <a href="#fragment-fields" class="MCXref xref" >Fragmentfält</a> i avsnittet Skapa en post i den här artikeln.</li></ul></td> 
  </tr> 
  </tbody> 
  </table>

#### Ta bort en post

Den här åtgärdsmodulen tar bort en innehållsmall eller ett innehållsfragment.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Välj om du vill ta bort en innehållsmall eller ett innehållsfragment.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Ange eller mappa ID:t för mallen eller fragmentet som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Laga en post

Den här åtgärdsmodulen uppdaterar en post med PATCH med JSON-pekarformat

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Välj om du vill korrigera en innehållsmall eller ett innehållsfragment.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Ange eller mappa ID:t för mallen eller fragmentet som du vill korrigera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Payload data]</td> 
   <td>Så här lägger du till en post i nyttolasten för den här korrigeringen: <ol><li>Klicka på <b>Lägg till en post</b>.</li><li>Välj åtgärden: Lägg till, Ta bort eller Ersätt.</li><li>I fältet Sökväg väljer du om du vill laga namnet eller beskrivningen.</li><li> I fältet Från anger eller mappar du en sträng som innehåller ett JSON-pekarvärde.</li><li>I fältet Värde anger du värdet som ska användas i åtgärden.</li></ol></td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en post

Den här åtgärdsmodulen returnerar innehållsmallen eller innehållsfragmentet som identifieras av det angivna ID:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Välj om du hämtar en innehållsmall eller ett innehållsfragment.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Template/Fragment ID]</td> 
   <td>Ange eller mappa ID:t för mallen eller fragmentet som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>


### Meddelandehantering

* [Utlösa en enastående meddelandekörning](#trigger-a-unitary-message-execution)
* [Trigga ett målgruppsbaserat budskap](#trigger-an-audience-based-message)
* [Kontrollera status för ett publikbaserat meddelande](#check-the-status-for-audience-based-message)



#### Utlösa en enastående meddelandekörning

Den här åtgärdsmodulen utlöser ett enhetsmeddelande till de mottagare som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request ID]</td> 
   <td>Ange eller mappa ID:t för den förfrågan som är kopplad till det här meddelandet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Ange eller mappa ID:t för kampanjen som är associerad med det här meddelandet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipients]</td> 
   <td>För varje mottagare som du vill ska få det här meddelandet klickar du på <b>Lägg till mottagare</b> och anger följande:
   <ul>
   <li><p><b>Typ</b></p>Välj <code>aep</code>.</li>
   <li><p><b>Användar-ID</b></p>Ange eller mappa mottagarens Adobe Experience Platform-profilidentifierare.</li>
   <li><p><b>Namnutrymme</b></p>Ange eller mappa mottagarens Adobe Experience Platform Profile-namnutrymme.</li>
   <li><p><b>E-postadress</b></p></li>
   <li><p><b>Mobiltelefonnummer</b></p></li>
   <li><p><b>Förnamn</b></p></li>
   <li><p><b>Efternamn</b></p></li>
   <li><p><b>Produkt</b></p>Ange eller mappa den produkt som är associerad med det här meddelandet. Detta används för dynamisk variabelersättning i meddelandeinnehållet.</li>
   </ul></td> 
  </tr> 
 </tbody> 
</table>

#### Trigga ett målgruppsbaserat budskap

Den här åtgärdsmodulen utlöser körningen av ett målgruppsbaserat meddelande baserat på den begäran och kampanj som du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request ID]</td> 
   <td>Ange eller mappa ID:t för den förfrågan som är kopplad till det här meddelandet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign ID]</td> 
   <td>Ange eller mappa ID:t för kampanjen som är associerad med det här meddelandet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Product]</td> 
   <td>Ange eller mappa den produkt som är associerad med det här meddelandet. Detta används för dynamisk variabelersättning i meddelandeinnehållet.</td> 
  </tr> 
 </tbody> 
</table>

#### Kontrollera status för målgruppsbaserat meddelande

Den här åtgärdsmodulen kontrollerar statusen för ett målgruppsbaserat batchmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message execution ID]</td> 
   <td>Ange eller mappa ID:t för den meddelandekörning som du vill kontrollera.</td> 
  </tr> 
 </tbody> 
</table>

### Statuskontroller

<!--* [Check service health](#check-service-health)-->
* [Kontrollera importberoenden](#check-the-import-dependencies)
* [Kontrollera status för ett importjobb](#check-the-status-of-an-import-job)

<!--

#### Check service health

This action module checks that the service represented by the connection is running.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Journey Optimizer], see <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Create a connection to [!DNL Adobe Journey Optimizer]</a> in this article.</td> 
  </tr> 
 </tbody> 
</table>

-->

#### Kontrollera importberoenden

Den här åtgärdsmodulen kontrollerar beroenden för paketartefakter. På så sätt kan du kontrollera om du har behörighet att importera paketartefakter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill kontrollera behörigheter för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Ange eller mappa namnet på sandlådan som du vill importera paketet till.</td> 
  </tr> 
 </tbody> 
</table>

#### Kontrollera status för ett importjobb

Den här åtgärdsmodulen kontrollerar om ett importjobb lyckades eller misslyckades.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td>Ange eller mappa ID:t för jobbet som du vill hämta data för.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [Lista alla beroende objekt](#list-all-dependent-objects)
* [Listkonfigurationer](#list-configurations)
* [Visa export- och importjobb](#list-export-and-import-jobs)
* [Listpaket](#list-packages)
* [Listposter](#list-records)

#### Lista alla beroende objekt

Den här sökmodulen visar alla beroende objekt för objekt i det angivna paketet

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package objects]</td> 
   <td>För varje objekt i paketet som du vill returnera beroende objekt för klickar du på <b>Lägg till objekt</b> och anger objektets namn och typ.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Package ID]</td> 
   <td>Ange eller mappa ID:t för det paket som du vill visa beroende objekt för.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Target sandbox]</td> 
   <td>Ange eller mappa namnet på den sandlåda som innehåller det paket som du vill visa beroende objekt för.</td> 
  </tr> 
 </tbody> 
</table>

#### Listkonfigurationer

Den här åtgärdsmodulen visar alla konfigurationer för begränsning eller begränsning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select configuration type]</td> 
   <td>Välj om du vill visa en lista över befintliga konfigurationer eller en begränsad konfiguration.</td> 
  </tr> 
 </tbody> 
</table>

#### Visa export- och importjobb

I den här sökmodulen visas aktuella export- och importjobb. Du kan använda frågeparametrar för att filtrera listan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>Välj om du vill beställa resultat efter skapat datum eller ändrat datum.</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Query parameter]</td> 
   <td>För varje frågeparameter som du vill filtrera efter klickar du på <b>Lägg till frågeparameter</b>, markerar fältet och operatorn och anger fältvärdet för filtret.</td> 
  </tr> 
 </tbody> 
</table>



#### Listpaket

Den här sökmodulen visar alla paket i din organisation. Du kan använda frågeparametrar för att filtrera listan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
      <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
      <td>Välj om du vill beställa resultat efter skapat datum eller ändrat datum.</td>
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Query parameter]</td> 
   <td>För varje frågeparameter som du vill filtrera efter klickar du på <b>Lägg till frågeparameter</b>, markerar fältet och operatorn och anger fältvärdet för filtret.</td> 
  </tr> 
 </tbody> 
</table>

#### Listposter

I den här sökmodulen visas alla konfigurationer för begränsning och begränsning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select content type]</td> 
   <td>Välj om du hämtar en innehållsmall eller ett innehållsfragment.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>Ange eller mappa parameternamnet som du vill sortera listan efter. Lägg till <code>-</code> eller <code>+</code> för att sortera fallande eller stigande. Om inget tecken anges sorteras listan fallande.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>Det här fältet används för sidnumrering. Ange eller mappa villkoren för nästa sida med avseende på den egenskap som anges i fältet Ordna efter.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td>Ange eller mappa parameternamnet som du vill sortera listan efter. Lägg till <code>-</code> eller <code>+</code> för att sortera fallande eller stigande. Om inget tecken anges sorteras listan fallande.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by property]</td> 
   <td>För varje egenskapsfilter som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger egenskapens nyckel och värde. Poster som innehåller det angivna värdet för egenskapen tas med i listan.</td> 
  </tr> 
 </tbody> 
</table>


### Övriga


#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat API-anrop till Adobe Journey Optimizer API.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Journey Optimizer] finns i <a href="#create-a-connection-to-adobe-journey-optimizer" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Journey Optimizer]</a> i den här artikeln.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>Ange en sökväg som är relativ till bas-URL:en.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
      </td>
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till auktoriserings-, <code>x-api-key</code>- och <code>x-gw-ims-org-id</code>-huvuden.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Ange frågesträngen för begäran.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>







<!--

* [Check if configuration can be deployed](#check-if-configuration-can-be-deployed)
* [Check service health](#check-service-health)
* [Check the import dependencies](#check-the-import-dependencies)
* [Check the status for audience-based message](#status-for-audience-based-message)
* [Copy artifacts synchronously](#copy-artifacts-synchronously)
* [Create a configuration](#create-a-configuration)
* [Create a package](#create-a-package)
* [Create a record](#create-a-record)
* [Delete a configuration](#delete-a-configuration)
* [Delete a package](#delete-a-package)
* [Delete a record](#delete-a-record)
* [Deploy a configuration](#deploy-a-configuration)
* [Export artifacts asynchronously](#export-artifacts-asynchronously)
* [Get a configuration](#get-a-configuration)
* [Get a record](#get-a-record)
* [Import a package](#import-a-package)
* [Import artifacts asynchronously](#import-artifacts-asynchronously)
* [List all dependent objects](#list-all-dependent-objects)
* [List export and import jobs](#list-import-and-export-jobs)
* [Look up a package](#look-up-a-package)
* [Make a custom API call](#make-a-custom-api-call)
* [Patch a record](#patch-a-record)
* [Publish a package](#publish-a-package)
* [Submit an import](#submit-an-import)
* [Trigger a unitary message execution](#trigger-a-unitary-message-execution)
* [Trigger an audience-based message](#trigger-an-audience-based-message)
* [Undeploy a configuration](#undeploy-a-configuration)
* [Update a configuration](#update-a-configuration)
* [Update a package](#update-a-package)
* [Update a record](#update-a-record)
* [List configurations](#list-configurations)
* [List packages](#list-packages)
* [List records](#list-records)

-->
