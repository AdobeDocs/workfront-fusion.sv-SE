---
title: Adobe Experience Manager Assets moduler
description: Med Adobe Experience Manager Assets Connector for Adobe Workfront Fusion kan du skapa, överföra och uppdatera material samt kopiera eller flytta mappar och resurser.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: tm+mt
source-wordcount: '3734'
ht-degree: 0%

---

# Adobe Experience Manager Assets moduler

Med Adobe Experience Manager Assets Connector for Adobe Workfront Fusion kan du skapa, överföra och uppdatera material samt kopiera eller flytta mappar och resurser.

En videointroduktion till Adobe Experience Manager Assets Connector finns på:

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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

* Du måste ha ett Adobe Experience Manager Assets-konto för att kunna använda dessa moduler.
* Du måste konfigurera flödet från server till server i Adobe Developer-konsolen.

  Instruktioner om hur du konfigurerar server-till-server-flödet i Adobe Developer-konsolen finns i [Generera åtkomsttoken för serversidans API:er](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
* Ditt Adobe Experience Manager-konto måste ha skrivbehörighet.

  Instruktioner om hur du lägger till skrivbehörigheter till ditt Adobe Experience Manager tekniska konto finns i [Tjänstens autentiseringsuppgifter](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) i Adobe Experience Manager-dokumentationen.

## Adobe Experience Manager Assets API-information

Adobe Experience Manager Assets Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.8.61</td> 
  </tr>
 </tbody> 
 </table>

## Anslut Adobe Experience Manager Assets till Workfront Fusion {#connect-adobe-experience-manager-assets-to-workfront-fusion}

Så här skapar du en anslutning för dina Adobe Experience Manager Assets-moduler:

1. Klicka på Lägg till bredvid rutan Anslutning.

2. Välj den typ av anslutning som du skapar:

   * **AEM Assets as a Cloud Service**

     Den här konfigurationen kräver information från Adobe Admin Console.

   * **AEM Assets Basic (Adobe Managed Services)**

     Den här konfigurationen kräver ett användarnamn och lösenord.

3. Fyll i fälten för den typ av anslutning som du skapar.

   Information om AEM Assets as a Cloud Service finns i [Konfigurera anslutningen för AEM Assets as a Cloud Service](#configure-the-connection-for-aem-assets-as-a-cloud-service).

   Information om AEM Assets Basic (Adobe Managed Services) finns i [Konfigurera anslutningen för AEM Assets Basic](#configure-the-connection-for-aemassets-basic-adobe-managed-services).

4. Klicka på **Fortsätt** för att spara anslutningen och återgå till modulen.


### Konfigurera anslutningen för AEM Assets as a Cloud Service

>[!NOTE]
>
>* Informationen för dessa fält genereras som en del av konfigurationen av server-till-server-flödet på Adobe Developer Console. Dessa värden finns i JSON-tjänstens inloggningsinformation som genereras som en del av den konfigurationen.
>
>   Instruktioner om hur du konfigurerar server-till-server-flödet på Adobe Developer Console finns i [Generera åtkomsttoken för API:er på serversidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
>
>* Ditt Adobe Experience Manager-konto måste ha skrivbehörighet.
>
>   Instruktioner om hur du lägger till skrivbehörigheter till ditt Adobe Experience Manager tekniska konto finns i [Tjänstens autentiseringsuppgifter](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) i Adobe Experience Manager-dokumentationen.


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">Anslutningsnamn</td>
                  <td>
                      <p>Ange ett namn för anslutningen.</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">Instans-URL utan avslutande snedstreck</td>
                  <td>Ange URL:en för din Adobe Experience Manager-instans. Ta inte med ett snedstreck <code>/</code> i slutet av URL:en.</td>
              </tr>
              <tr>
                  <td role="rowheader">Fyllningsalternativ för kontoinformation</td>
                  <td>Välj om du vill ange JSON som beskriver din kontoinformation eller om du vill ange information manuellt.</td>
              </tr>
              <tr>
                  <td role="rowheader">Teknisk kontoinformation i JSON-format</td>
                  <td>Om du anger JSON anger eller klistrar du in den JSON som beskriver din kontoinformation.</td>
              </tr>
              <tr>
                  <td role="rowheader">Klient-ID</td>
                  <td>Om du anger information manuellt anger du klient-ID:t som genereras i Server-till-server-inställningarna.</td>
              </tr>
              <tr>
                  <td role="rowheader">Klienthemlighet</td>
                  <td>Om du anger information manuellt anger du den klienthemlighet som genererats i Server-till-server-konfigurationen.</td>
              </tr>
              <tr>
                  <td role="rowheader">Tekniskt konto-ID</td>
                  <td>Om du anger information manuellt anger du ID för det tekniska kontot. Det här är ID-fältet i JSON-filen för klientinloggningsuppgifter.</td>
              </tr>
              <tr>
                  <td role="rowheader">Organisations-ID</td>
                  <td class="">Ange organisationens ID om du anger information manuellt. Detta är "org"-fältet i JSON-filen för klientinloggningsuppgifter.</td>
              </tr>
              <tr>
                  <td role="rowheader">Meta Scopes</td>
                  <td>Ange de Meta-scope som genereras i Server-till-server-konfigurationen.</td>
              </tr>
              <tr>
                  <td role="rowheader">Privat nyckel</td>
                  <td>Ange den privata nyckel som genererats för att vinna konfigurationen från server till server. Om du vill extrahera den privata nyckeln klickar du på Extrahera, anger filen som ska extraheras och lösenordet för filen.</td>
              </tr>
              <tr>
                  <td role="rowheader">Autentiserings-URL</td>
                  <td>Ange autentisering-URL för det här kontot.</td>
              </tr>
          </tbody>
      </table>


### Konfigurera anslutningen för AEM Assets Basic (Adobe Managed Services)

<table style="table-layout:auto"> 
        <col/>
        <col />
        <tbody>
            <tr>
                <td role="rowheader">Anslutningsnamn</td>
                <td>
                    <p>Ange ett namn för anslutningen.</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">Instans-URL utan avslutande snedstreck</td>
                <td>Ange URL:en för din Adobe Experience Manager-instans. Ta inte med ett snedstreck <code>/</code> i slutet av URL:en.</td>
            </tr>
            <tr>
                <td role="rowheader">Användarnamn</td>
                <td>Ange användarnamnet för det AEM Assets-konto som den här anslutningen använder.</td>
            </tr>
            <tr>
                <td role="rowheader">Lösenord</td>
                <td>Ange lösenordet för det AEM Assets-konto som den här anslutningen använder.</td>
            </tr>
        </tbody>
    </table>


## Adobe Experience Manager Assets-moduler och deras fält

När du konfigurerar Adobe Experience Manager Assets-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Adobe Experience Manager Assets-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Filåtgärder](#files-operations)
* [Övriga](#other)
* [Assets (Author API)](#assets-author-api)
* [Händelser (författar-API)](#events-author-api)
* [Metadata (författar-API)](#metadata-author-api)
* [Importera (Author API)](#import-author-api)
* [Relationer (Författar-API)](#relations-author-api)
* [Mappar (API för mappar)](#folders-folders-api)

### Filåtgärder

* [fullständig överföring](#complete-upload)
* [Få försignerat lagringsutrymme](#get-presigned-storage)
* [Initiera överföring](#initiate-upload)
* [Överföra en resurs](#upload-an-asset)

#### fullständig överföring

Den här åtgärdsmodulen slutför en initierad överföring när alla delar av filen har överförts.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filnamn</td> 
   <td> <p>Ange eller mappa ett namn för den överförda filen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Överför token</td> 
   <td>Ange eller mappa överföringstoken för binärfilen enligt initieringen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">MIME-typ</td> 
   <td>Ange eller mappa MIME-typen för den färdiga filen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Fullständig URI</td> 
   <td>Ange eller mappa den fullständiga URI:n för filen.</td> 
  </tr> 
 </tbody> 
</table>


#### Få försignerat lagringsutrymme

Den här åtgärdsmodulen skapar en temporär försignerad URL för att på ett säkert sätt överföra eller hämta filer från AEM utan att det krävs direkta autentiseringsuppgifter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uppslagstyp</td> 
   <td> <p>Välj om du vill söka efter resursen med dess sökväg eller ID.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgång</td> 
   <td>Välj sökvägen till resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UDID</td> 
   <td>Ange eller mappa resursens UDID.</td> 
  </tr> 
 </tbody> 
</table>

#### Initiera överföring

Den här åtgärdsmodulen initierar en överföring.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mål</td> 
   <td> <p>Välj den mapp där du vill överföra en fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filnamn</td> 
   <td> <p>Ange eller mappa ett namn för den överförda filen</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximal filstorlek</td> 
   <td>Ange eller mappa den överförda filens storlek i byte.</td> 
  </tr> 
 </tbody> 
</table>


#### Överföra en resurs

Den här åtgärdsmodulen överför en resurs till ditt Adobe Experience Manager Assets-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mål</td> 
   <td> <p>Välj den mapp där du vill överföra en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Source</td> 
   <td>Ange eller mappa källfilens namn och data.</td> 
  </tr> 
 </tbody> 
</table>

### Övriga


* [Kopiera en mapp eller resurs](#copy-a-folder-or-asset)
* [Skapa en post](#create-a-record)
* [Ta bort en mapp, resurs eller återgivning](#delete-a-folder-asset-or-rendition)
* [Hämta en mapplista](#get-a-folder-listing)
* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Flytta en mapp eller resurs](#move-a-folder-or-asset)
* [Uppdatera en post](#update-a-record)



#### Kopiera en mapp eller resurs

Den här åtgärdsmodulen kopierar en mapp eller resurs till en annan plats på ditt Adobe Experience Manager Assets-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj om du vill kopiera en mapp eller en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mapp/resurs</td> 
   <td>Markera eller mappa mappen eller resursen som du vill kopiera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Målsökväg</td> 
   <td>Markera eller mappa sökvägen till platsen för den nya mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn på kopierad mapp/resurs</td> 
   <td>Ange ett namn för den nya mappen eller resursen. Mappnamnet som visas i Adobe Experience Manager Assets är samma som det ursprungliga namnet. Namnet som anges här visas i URL:en för den nya mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kopiera underordnade</td> 
   <td>Om du kopierar en mapp aktiverar du det här alternativet för att kopiera alla undermappar eller resurser i mappen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Skriv över</td> 
   <td>Aktivera det här alternativet om du vill skriva över mappar eller resurser på målplatsen som har samma namn som mappen eller resursen som kopieras.</td> 
  </tr> 
 </tbody> 
</table>



#### Skapa en post

Den här åtgärdsmodulen skapar en mapp eller en resurskommentar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Objekttyp</td> 
   <td> <p>Välj om du vill skapa en mapp eller en kommentar för en resurs.</p> 
    <ul> 
     <li> <p>Mapp</p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p>Namn</p> <p>Ange ett namn för mappen. Det här namnet visas i filsökvägen och får inte innehålla blanksteg eller andra tecken. </p> </li> 
       <li> <p>Titel</p> <p>Ange en rubrik för mappen, som kan visas i stället för namnet.</p> </li> 
      </ul> </li> 
     <li> <p>Resurskommentar</p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p>Val av resurs</p> <p>Markera eller mappa ID:t för resursen som du vill lägga till en kommentar i.</p> </li> 
       <li> <p>Kommentar</p> <p>Ange texten för kommentaren.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en mapp, resurs eller återgivning

Den här åtgärdsmodulen tar bort en mapp, en resurs eller en återgivning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj om du vill ta bort en mapp, en resurs eller en återgivning.</p> 
    <ul> 
     <li> <p>Mapp</p> <p>Markera mappen som ska tas bort genom att markera mapparna i sökvägen.</p> </li> 
     <li> <p>Tillgång</p> <p>Markera resursen genom att markera mapparna i sökvägen och sedan den resurs du vill ta bort.</p> </li> 
     <li> <p>Återgivning</p> <p>Markera återgivningen genom att markera mapparna i sökvägen.</p> <p>Ange eller mappa återgivningens namn.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en mapplista

Den här åtgärdsmodulen hämtar en representation av en befintlig mapp och av dess underordnade enheter (mappar eller resurser).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mapp</td> 
   <td>Markera eller mappa mappen som du vill hämta. Om du vill lägga till undermappar i sökvägen klickar du på plusikonen och väljer undermappen.</td> 
  </tr> 
 </tbody> 
</table>

#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat API-anrop till Adobe Experience Manager Assets API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL</p> </td> 
   <td> <p>Ange en relativ sökväg till din Adobe Experience Manager bas-URL.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Metod</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sidhuvuden</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Frågesträng</td> 
   <td> <p>Ange frågesträngen för begäran. För varje nyckel/värde-par klickar du på <b>Lägg till objekt</b> och anger nyckel och värde.</p> </td> 
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

#### Flytta en mapp eller resurs

Den här åtgärdsmodulen flyttar resursen eller mappen på den angivna sökvägen till en ny plats.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj om du vill flytta en mapp eller en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mapp/resurs</td> 
   <td>Markera eller mappa mappen eller resursen som du vill flytta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Målsökväg</td> 
   <td>Markera eller mappa sökvägen till den plats där du vill flytta mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn på flyttad mapp/resurs</td> 
   <td>Ange ett nytt namn för den flyttade mappen eller resursen. Mappnamnet som visas i Adobe Experience Manager Assets är samma som det ursprungliga namnet. Namnet som anges här visas i URL:en för den flyttade mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Skriv över</td> 
   <td>Aktivera det här alternativet om du vill skriva över mappar eller resurser på målplatsen som har samma namn som mappen eller resursen som flyttas.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en post

Den här åtgärdsmodulen uppdaterar en befintlig post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj om du vill ta bort metadata för resursen eller en resursåtergivning.</p> 
    <ul> 
     <li> <p>Resursmetadata</p> 
      <ul> 
       <li> <p>Välj den resurs som du vill uppdatera metadata för.</p> </li> 
       <li> <p>Ange resursens nya namn.</p> </li> 
      </ul> </li> 
     <li> <p>Resursåtergivning</p> 
      <ul> 
       <li> <p>Välj den resurs som du vill uppdatera återgivningen för.</p> </li> 
       <li> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Assets (Author API)

* [Ta bort resurs](#delete-asset)
* [Hämta jobbstatus](#get-job-status)

#### Ta bort resurs

Den här åtgärdsmodulen tar bort en enskild resurs med dess ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tvinga</td> 
   <td>Aktivera det här alternativet om du vill tvinga resursen att ta bort, även om det refereras.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta jobbstatus

Den här åtgärdsmodulen hämtar aktuell status för ett asynkront jobb.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Jobb-ID</td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill hämta statusen för.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Händelser (författar-API)

#### Se händelser

Denna utlösarmodul startar ett scenario när en händelse inträffar i AEM Assets.

Modulen innehåller ett enda fält: Webkrok. Välj en befintlig webbkrok som ska användas för dessa händelser eller skapa en ny.

Så här skapar du en ny webbkrok:

1. Klicka på **Lägg till** bredvid Webkrok-fältet.
1. Fyll i följande fält:

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">Webkrocksnamn</td>
        <td>Ange ett namn för den här webbkroken.</td>
       </tr>
       <tr>
         <td role="rowheader">Anslutning</td>
        <td>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</td>
       </tr>
     </tbody>
   </table>

1. Klicka på Spara om du vill spara webkroken och återgå till modulen.


### Metadata (författar-API)

* [Hämta metadata för resurser](#get-asset-metadata)
* [Uppdatera metadata för resurs](#update-asset-metadata)

#### Hämta metadata för resurser

Denna åtgärdsmodul hämtar metadata om den angivna resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill hämta metadata för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera metadata för resurs

Denna åtgärdsmodul uppdaterar metadata för den angivna resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill uppdatera metadata för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uppdateringar</td> 
   <td> <p>För varje metadataobjekt som du vill uppdatera klickar du på <b>Lägg till objekt</b> och väljer åtgärden. Andra fält i rutan Lägg till objekt beror på den valda åtgärden.</p> </td> 
  </tr> 
 </tbody> 
</table>


### Importera (Author API)

* [Hämta importjobbsresultat](#get-import-job-results)
* [Hämta importjobbstatus](#get-import-job-status)
* [Överföra en resurs från en URL](#upload-an-asset-from-a-url)

#### Hämta importjobbsresultat

Den här åtgärdsmodulen hämtar resultat för det angivna importjobbet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Importera jobb-ID</td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill hämta resultat för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta importjobbstatus

Den här åtgärdsmodulen hämtar statusen för det angivna importjobbet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Importera jobb-ID</td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill hämta statusen för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Överföra en resurs från en URL

Den här åtgärdsmodulen överför en ny resurs genom att importera filer från de angivna URL-adresserna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Titel</td> 
   <td> <p>Ange eller mappa en titel för resursen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Beskrivning</td> 
   <td> <p>Ange eller mappa en beskrivning för resursen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ämne</td> 
   <td> <p>Ange eller mappa ett ämne för resursen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Skapare</td> 
   <td> <p>Ange eller mappa den som skapat resursen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Utgångsdatum</td> 
   <td> <p>Ange eller mappa tillgångens förfallodatum.</p><p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Anpassade metadata</td> 
   <td> <p>För varje objekt med anpassade metadata som du vill lägga till i resursen klickar du på <b>Lägg till objekt</b> och anger metadatans namn och värde.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mappsökväg eller ID</td> 
   <td> <p>Välj om du vill ange målmappen med dess sökväg eller ID och markera sedan sökvägen eller ange ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filer att importera</td> 
   <td> <p>För varje fil som du vill importera klickar du på <b>Lägg till objekt&lt;/&gt; och fyller i informationen för filen. <code>Title</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"></td> 
   <td> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

### Relationer (Författar-API)

* [Skapa resursrelationer](#create-asset-relations)
* [Ta bort tillgångsrelation](#create-asset-relations)
* [Hämta tillgångsrelationstyper](#get-asset-relation-types)
* [Hämta resursrelationer](#get-asset-relations)

#### Skapa resursrelationer

Den här åtgärdsmodulen skapar nya resursrelationer för den valda resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa den ID-resurs som du vill koppla andra resurser till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relaterade tillgångar</td> 
   <td> <p>För varje resurs som du vill relatera till den valda resursen klickar du på <b>Lägg till artikel</b> och anger eller mappar resursens ID och relationstypen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort tillgångsrelation

Den här åtgärdsmodulen tar bort en resursrelation för en tillgång.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa den ID-resurs som du vill ta bort en relation från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relaterade tillgångar</td> 
   <td> <p>Ange eller mappa den typ av relation som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ange ett specifikt ID för den relaterade tillgång som ska tas bort</td> 
   <td> <p>Markera den här rutan om du vill ta bort en viss relation. Om rutan inte är markerad tas alla relationer av den valda typen bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relaterat tillgångs-ID</td> 
   <td> <p>Om du tar bort en viss relation anger eller mappar du ID:t för relationen som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### Hämta tillgångsrelationstyper

Den här modulen visar de tillgångsrelationstyper som finns för den angivna resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa den ID-resurs som du vill visa relationstyper för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta resursrelationer

Den här modulen visar resursrelationerna för den angivna resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td> <p>Ange eller mappa den ID-resurs som du vill visa relationer för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Relationstyper</td> 
   <td> <p>Ange eller mappa en kommaavgränsad lista över de relationstyper som du vill visa relationerna för.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Mappar (API för mappar)

* [Skapa mappar](#create-folders)
* [Ta bort en mapp med ID](#delete-a-folder-by-id)
* [Ta bort mappar efter sökväg](#delete-folders-by-path)
* [Hämta mappjobbresultat](#get-folders-job-results)
* [Jobbstatus för Hämta mappar](#get-folders-job-status)
* [Visa mappar](#list-folders)

#### Skapa mappar

Den här åtgärdsmodulen skapar en ny mapp i Adobe Experience Manager Assets.



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mappar som ska skapas</td> 
   <td> <p>För varje mapp som du vill skapa klickar du på <b>Lägg till objekt</b> och anger följande information:</p>
   <ul>
   <li><b>Ny mapplats</b><p>Välj sökvägen till den plats där du vill skapa den nya mappen.</p></li>
       <li> <b>Namn</b> <p>Ange ett namn för mappen. Det här namnet visas i filsökvägen och får inte innehålla blanksteg eller andra tecken. </p> </li> 
       <li> <b>Titel</b> <p>Ange en rubrik för mappen, som kan visas i stället för namnet.</p> </li> 
   </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en mapp med ID

Den här åtgärdsmodulen tar bort Adobe Experience Manager Assets-mappen med det angivna ID:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mapp-ID</td> 
   <td> Ange eller mappa ID:t för mappen som du vill ta bort.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Ta bort undermappar</td> 
   <td> Aktivera det här alternativet om du vill ta bort mappen och alla dess undermappar.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Tvinga</td> 
   <td> Aktivera det här alternativet om du vill tvinga mapparna att tas bort, även om det refereras.</td>
  </tr> 
 </tbody> 
</table>

#### Ta bort mappar efter sökväg

Den här åtgärdsmodulen tar bort Adobe Experience Manager Assets-mapparna vid de angivna sökvägarna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mappsökvägar</td> 
   <td>För varje mapp som du vill ta bort klickar du på <b>Lägg till objekt</b> och väljer mappens sökväg.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Ta bort undermappar</td> 
   <td> Aktivera det här alternativet om du vill ta bort mappen och alla dess undermappar.</td>
  </tr> 
 <tr> 
   <td role="rowheader">Tvinga</td> 
   <td> Aktivera det här alternativet om du vill tvinga resursen att ta bort, även om det refereras.</td>
  </tr> 
 </tbody> 
</table>

#### Hämta mappjobbresultat

Den här modulen hämtar resultatet från ett asynkront jobb som skapats av Adobe Experience Manager Assets mapp-API:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Jobb-ID</td> 
   <td> Ange eller mappa ID:t för jobbet som du vill hämta resultat för.</td>
  </tr> 
 </tbody> 
</table>

#### Jobbstatus för Hämta mappar

Den här modulen hämtar status för ett asynkront jobb som skapats av Adobe Experience Manager Assets mapp-API:t.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Jobb-ID</td> 
   <td> Ange eller mappa ID:t för jobbet som du vill hämta statusen för.</td>
  </tr> 
 </tbody> 
</table>


#### Visa mappar

Den här modulen visar undermappar till den angivna mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Adobe Experience Manager Assets-konto till Workfront Fusion finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta Adobe Experience Manager Assets till Workfront Fusion</a> i den här artikeln.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">Mappsökväg eller ID</td> 
   <td> <p>Välj om du vill ange målmappen med dess sökväg eller ID och markera sedan sökvägen eller ange ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
i! I added a lot of modules to the AEM Assets connector and we need new documentation for them. The connector is available in the QA environment. Heres the added modules and a brief description of them, more info about them can be found in the Assets Author Api docs and the Folders Api docs. Im not fully confident that i kept all the best practices for naming things :sweat_smile:, i hope you can take a look at that as well. Let me know if theres anything i can tell about the modules and thanks again in advance!
Author API
Assets
Delete Asset
Deletes an asset when provided an Asset ID, There is a force parameter that when toggled will delete the folder regardless if it's referenced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get assets job status
Given an assets job ID will return the state that the job is currently in (PROCESSING, COMPLETED, etc.)
Events
AEM Assets events
The costumer can create a web hook in this module and register it in the Adobe admin console
Metadata
Get asset metadata
Given asset ID returns assets metadata.
Update asset metadata
Given asset ID, there are 6 patch operations that can be done with the metadata. The operations are visible in the module as well as the documentation.
Import
Get import job results
Given Job ID returns it's result.
Get import job status
Given Job ID returns its status.
Upload an asset from url
Takes global metadata which applies to all the assets and local ones which apply individually.In both it is also possible to specify custom metadata.
Also takes the folder path or folder ID to place the assets there and url-s of the assets.
Relations
Create asset relation
Given asset ID and a list of related asset ID as well as the relation types creates those relationships.
Delete asset relations
Given asset ID and relation type deletes all relations of that type. Can also specify a related asset to target only that.
 there is a checkbox that is checked by default and when unchecked reveals a field where the user can specify the related user ID.
Get asset relation types
Given asset ID returns all the relation types that the asset has.
Get asset relations
Given asset ID returns all relations. Can also specify a specific type of relation.
Folders API
Create folders
Given a list of folders with their path, name, title, creates them.
Delete a folder by ID
Given Folder ID deletes the folder. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Delete folders by path
Given a list of paths, deletes everything in them. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get folders job results
Given job ID returns its result.
Get folders job status
Given job ID returns its status.
List Folders
List folders under the given folder. In the module you can choose the root folder either by ID or by Path.
-->

