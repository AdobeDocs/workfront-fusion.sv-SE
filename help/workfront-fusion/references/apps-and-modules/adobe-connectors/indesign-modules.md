---
filename: adobe-indesign-modules
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe InDesign moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Adobe InDesign och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
source-git-commit: 30ddefa8519e6f2052308482137d0fa018676902
workflow-type: tm+mt
source-wordcount: '1691'
ht-degree: 0%

---


# Adobe InDesign Modules

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Adobe InDesign och ansluta det till flera tredjepartsprogram och -tjänster.

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

Innan du kan använda Adobe InDesign Connector måste du ha ett aktivt Adobe InDesign-konto.

## Skapa en anslutning till Adobe InDesign

Så här skapar du en anslutning för dina Adobe InDesign-moduler:

1. Klicka på **Lägg till** bredvid rutan Anslutning i någon av Adobe InDesign-modulerna.

1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col>
      </col>
      <col>
      </col>
      <tbody>
        <tr>
          <td role="rowheader">Anslutningsnamn</td>
          <td>
            <p>Ange ett namn för anslutningen.</p>
          </td>
        </tr>
      <tr>
        <td role="rowheader">Miljö</td>
        <td>
          <p>Välj om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Typ</td>
        <td>
          <p>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
        <tr>
          <td role="rowheader">Klient-ID</td>
          <td>Ange ditt Adobe klient-ID. Detta hittar du i delen Information om autentiseringsuppgifter i Adobe Developer Console</td>
        </tr>
        <tr>
          <td role="rowheader">Klienthemlighet</td>
          <td>Ange din Adobe-klienthemlighet. Detta hittar du i delen Information om autentiseringsuppgifter i Adobe Developer Console</td>
        </tr>
        <tr>
          <td role="rowheader">IMS-organisations-ID</td>
          <td>Ange ditt organisations-ID för Adobe. Detta hittar du i delen Information om autentiseringsuppgifter i Adobe Developer Console</td>
        </tr>
      </tbody>
    </table>
1. Klicka på **Fortsätt** för att spara anslutningen och återgå till modulen.

## InDesign-moduler och deras fält

När du konfigurerar Adobe InDesign-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Adobe InDesign-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Åtgärder

* [Skapa återgivning](#create-rendition)
* [Ta bort ett eget skript](#delete-a-custom-script)
* [Sammanfoga data](#merge-data)
* [Omforma länkar](#remap-links)
* [Skicka en begäran om anpassad skriptkörning](#submit-a-custom-script-execution-request)

#### Skapa återgivning

Den här åtgärdsmodulen skapar och returnerar en JPEG-, PNG- eller PDF-återgivning av ett visst InDesign-dokument. Strukturen för `StatusCompletedRespons/output/data` finns i `RenditionOutputData`. En lista över möjliga felkoder i `FailedEvent` finns också i `RenditionFailedData`.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Typ</p>
      </td>
      <td>Välj filtypen för den återgivning som du vill skapa. 
      <ul><li>JPEG</li><li>PNG</li><li>PDF</li></ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill lägga till i återgivningen:<ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Måldokument</td>
      <td>Ange eller mappa dokumentet som ska bearbetas och återges. För närvarande stöds bara ett dokument i taget.</td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

#### Ta bort ett anpassat skript

Den här åtgärdsmodulen tar bort ett enskilt registrerat anpassat skript. Alla versioner av skriptet tas bort permanent.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Skriptnamn</p>
      </td>
      <td>Ange eller mappa namnet på skriptet som du vill ta bort.</td>
    </tr>
  </tbody>
</table>

#### Sammanfoga data

I den här modulen skapas InDesign-dokument eller PDF-filer genom att CSV-data sammanfogas med InDesign-mallar. Utdataformaten är bland annat JPEG-, PNG-, PDF- och InDesign-dokument.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill lägga till i datasammanfogningen:<ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Måldokument</td>
      <td>Ange eller mappa det dokument som ska användas som mall för sammanfogning.</td>
    </tr>
    <tr>
      <td role="rowheader">Datakälla</td>
      <td>Ange eller mappa de källfiler som ska användas.</td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

#### Omforma länkar

Den här modulen ersätter filbaserade länkar i InDesign-dokument med Adobe Experience Manager-URL:er (AEM). Detta kan vara användbart när du arbetar med Adobe Experience Manager med Adobe Asset Link.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
      </tr>
    <tr>
      <td role="rowheader">AEM Token</td>
      <td>Ange eller mappa den innehavartoken som genererats för AEM tekniska konto, utan nyckelordet innehavare.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill lägga till i modulen:<ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Måldokument</td>
      <td>Ange eller mappa det dokument där du vill mappa om länkar.</td>
    </tr>
    <tr>
      <td role="rowheader">Datakälla</td>
      <td>Ange eller mappa källfilerna som ska användas för att extrahera och matcha taggar.</td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

#### Skicka en begäran om anpassad skriptkörning

Den här åtgärdsmodulen skickar en körningsbegäran för ett anpassat skript. Du definierar indataresurserna och parametrarna som det anpassade skriptet ska använda under körningen.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Skript-ID</p>
      </td>
      <td>Ange eller mappa ID:t för det anpassade skriptet.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill skicka en körningsbegäran för <ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

### Sökningar

* [Hämta information om egna skript](#get-custom-script-details)
* [Hämta taggar för datasammanfogning](#get-data-merge-tags)
* [Hämta dokumentinformation](#get-document-information)
* [Visa egna skript](#list-custom-scripts)

#### Hämta information om egna skript

Den här sökmodulen hämtar information om ett enskilt registrerat skript, inklusive version, nedladdningslänk, registreringsdatum och skriptnamn.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Skriptnamn</p>
      </td>
      <td>Ange eller mappa namnet på skriptet som du vill hämta information för.</td>
    </tr>
  </tbody>
</table>

#### Hämta taggar för datasammanfogning

Den här modulen hämtar datasammanfogningstaggar från ett dokument.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill lägga till i modulen:<ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Måldokument</td>
      <td>Ange eller mappa dokumentet som du vill hämta taggar från.</td>
    </tr>
    <tr>
      <td role="rowheader">Datakälla</td>
      <td>Ange eller mappa källfilerna som ska användas för att extrahera och matcha taggar.</td>
    </tr>
    <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

#### Hämta dokumentinformation

Den här modulen hämtar omfattande information om INDD-/IDML-dokument och returnerar data baserat på de aktiverade informationstyper som anges i begäran.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>Assets</p>
      </td>
      <td>För varje resurs som du vill lägga till i modulen:<ol><li>Klicka på <b>Lägg till objekt</b>.</li><li>Välj eller mappa resursens källa.</li><li>Ange ett mål. Målet är en relativ sökväg till en tillfällig baskatalog (arbetskatalog) där resursen hämtas. Detta identifierar resurserna inom parametrarna. Det går inte upp med '..' eller /. Det måste finnas ett giltigt filnamn.</td>
    </tr>
    <tr>
      <td role="rowheader">Måldokument</td>
      <td>Ange eller mappa dokumentet som du vill hämta information från.</td>
    </tr>
     <tr>
      <td role="rowheader">Andra fält</td>
   <td>För andra fält, se information som ingår i modulen.</td>     </tr>
  </tbody>
</table>

#### Visa egna skript

Den här modulen hämtar information om den senaste versionen av alla registrerade anpassade skript, inklusive version, nedladdningslänk, registreringsdatum och skriptnamn. Resultaten sidnumreras baserat på listlängden.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
      </tr>
    <tr>
      <td role="rowheader">Sidnummer</td>
      <td>Ange eller mappa det sidnummer som du vill börja från.</td>
    </tr>
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det högsta antalet team eller grupper som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
  </tbody>
</table>


### Övriga

#### Göra ett anpassat API-anrop

Den här modulen gör ett anpassat API-anrop till Adobe InDesign API

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe InDesign finns i <a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">Skapa en anslutning till Adobe InDesign</a> i den här artikeln.</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>Sökväg</p>
      </td>
      <td>
        <p>Ange en relativ sökväg till <code>https://indesign.adobe.io/v3</code>.</p><p> Exempel: <code>/create-rendition</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Metod</p>
      </td>
      <td>
        <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i [HTTP request methods](/help/workfront-fusion/references/modules/http-request-methods.md).</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Sidhuvuden</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Frågesträng  </td>
      <td>
        <p>Ange frågesträngen för begäran.</p>
      </td>
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
