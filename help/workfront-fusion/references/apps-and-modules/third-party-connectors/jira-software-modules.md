---
title: Jira Software-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder [!DNL Jira] Programvara, samt ansluta den till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 92cac080-d8f6-4770-a6a6-8934538c978b
source-git-commit: d4187aff574ceaf4d27112fc2ce8880421e77d0d
workflow-type: tm+mt
source-wordcount: '1912'
ht-degree: 0%

---

# [!DNL Jira Software] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Jira Software] samt ansluta det till flera tredjepartsprogram och -tjänster.

Dessa instruktioner gäller både Jira Cloud- och Jira Server-moduler.

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Om du vill använda [!DNL Jira] moduler måste du ha ett [!DNL Jira]-konto.

## Jira API-information

Jira-anslutningen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"></td> 
   <td> Jira Cloud</td> 
   <td> Jira Server</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersion</td> 
   <td> 2</td> 
   <td> 2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersionAgile</td> 
   <td> 1,0 </td> 
   <td> 1,0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>1.7.29</td> 
   <td>1.0.19</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Jira Software] till [!DNL Workfront Fusion]

Anslutningsmetoden baseras på om du använder [!DNL Jira Cloud] eller [!DNL Jira Server].

* [Anslut [!DNL Jira Cloud] till Workfront Fusion](#connect-jira-cloud-to-workfront-fusion)
* [Anslut [!DNL Jira Server] till [!DNL Workfront Fusion]](#connect-jira-server-to-workfront-fusion)

### Anslut [!DNL Jira Cloud] till [!DNL Workfront Fusion]

Anslut [!DNL Jira Cloud] till [!DNL Workfront Fusion]

Om du vill ansluta [!DNL Jira Software] till [!DNL Workfront Fusion] måste du skapa en API-token och infoga den tillsammans med din tjänst-URL och ditt användarnamn i fältet [!UICONTROL Create a connection] i [!DNL Workfront Fusion].

#### Skapa en API-token i [!DNL Jira]

1. Skapa en API-token i Jira.

   Vi rekommenderar att du söker efter&quot;Skapa en API-token&quot; i Jiras dokumentation.
1. När du har skapat token kopierar du den till en säker plats.

   >[!IMPORTANT]
   >
   >Du kan inte visa variabeln igen när du har stängt den här dialogrutan.
1. Lagra den genererade token på en säker plats.
1. Fortsätt med [Konfigurera  [!DNL Jira] API-token i [!DNL Workfront Fusion]](#configure-the-jira-api-token-in-workfront-fusion).

#### Konfigurera API-token [!DNL Jira] i [!DNL Workfront Fusion]

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL connection] i någon [!DNL Jira Cloud]-modul i [!DNL Workfront Fusion].
1. Ange följande information:

   * **Miljö**
   * **Typ**
   * **[!UICONTROL Service URL]:** Detta är den bas-URL som du använder för att komma åt ditt Jira-konto. Exempel: `yourorganization.atlassian.net`
   * **[!UICONTROL Username]**
   * **[!UICONTROL API token]:** Detta är den API-token som du skapade i avsnittet [Skapa en API-token i  [!DNL Jira]](#create-an-api-token-in-jira) i den här artikeln.

1. Klicka på [!UICONTROL Continue] för att skapa anslutningen och återgå till modulen.

### Anslut [!DNL Jira Server] till [!DNL Workfront Fusion]

Om du vill auktorisera en anslutning mellan [!DNL Workfront Fusion] och [!DNL Jira Server] behöver du din konsumentnyckel, privata nyckel och tjänst-URL. Du kan behöva kontakta din [!DNL Jira]-administratör för att få tillgång till den här informationen.

* [Generera offentliga och privata nycklar för din [!DNL Jira] anslutning](#generate-public-and-private-keys-for-your-jira-connection)
* [Konfigurera klientappen som en konsument i  [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)
* [Skapa en anslutning till  [!DNL Jira] Server eller Jira Data Center i [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Generera offentliga och privata nycklar för din [!DNL Jira]-anslutning

Om du vill hämta en privat nyckel för din [!DNL Workfront Fusion Jira]-anslutning måste du generera offentliga och privata nycklar. Detta görs via datorns terminal. Du kan hitta terminalen genom att söka efter terminaler på startmenyn eller i datorns sökfält (inte sökfältet i webbläsaren).

1. Kör följande `openssl`-kommandon i terminalen.

   * `openssl genrsa -out jira_privatekey.pem 1024`

     Det här kommandot genererar en 1024-bitars privat nyckel.

   * `openssl req -newkey rsa:1024 -x509 -key jira_privatekey.pem -out jira_publickey.cer -days 365`

     Det här kommandot skapar ett X509-certifikat.

   * `openssl pkcs8 -topk8 -nocrypt -in jira_privatekey.pem -out jira_privatekey.pcks8`

     Det här kommandot extraherar den privata nyckeln (PKCS8-format) till filen `jira_privatekey.pcks8`.

   * `openssl x509 -pubkey -noout -in jira_publickey.cer  > jira_publickey.pem`

     Det här kommandot extraherar den offentliga nyckeln från certifikatet till filen `jira_publickey.pem`.

     >[!NOTE]
     >
     >Om du använder Windows kan du behöva spara den offentliga nyckeln till filen `jira_publickey.pem` manuellt:
     >
     >1. Kör följande kommando i terminalen:
     >   
     >   `openssl x509 -pubkey -noout -in jira_publickey.cer`
     >   
     >1. Kopiera terminalutdata, inklusive `-------BEGIN PUBLIC KEY--------` och `-------END PUBLIC KEY--------`.
     >   
     >1. Klistra in terminalutdata i en fil med namnet `jira_publickey.pem`.


1. Fortsätt till [Konfigurera klientappen som en konsument i [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)

#### Konfigurera klientappen som en konsument i [!DNL Jira]

1. Logga in på din [!DNL Jira]-instans.
1. Klicka på ikonen **[!UICONTROL [!DNL Jira] Settings]** ![Jira settings ](/help/workfront-fusion/references/apps-and-modules/assets/jira-settings-icon.png) > **[!UICONTROL Applications]**> **[!UICONTROL Application links]** i den vänstra navigeringspanelen.
1. I fältet **[!UICONTROL Enter the URL of the application you want to link]** anger du

   ```
   https://app.workfrontfusion.com/oauth/cb/workfront-jiraserver-oauth1
   ```

1. Klicka på **[!UICONTROL Create new link]**. Ignorera felmeddelandet&quot;Inget svar togs emot från den URL du angav&quot;.
1. I fönstret **[!UICONTROL Link applications]** anger du värden i fälten **[!UICONTROL Consumer key]** och **[!UICONTROL Shared secret]**.

   Du kan välja värden för dessa fält.

1. Kopiera värdena för fälten **[!UICONTROL Consumer key]** och **[!UICONTROL Shared secret]** till en säker plats.

   Du kommer att behöva dessa värden senare i konfigurationsprocessen.

1. Fyll i URL-fälten enligt följande:

   | Fält | Beskrivning |
   |---|---|
   | [!UICONTROL Request Token URL] | `<Jira base url>/plugins/servlet/oauth/request-token` |
   | [!UICONTROL Authorization URL] | `<Jira base url>/plugins/servlet/oauth/authorize` |
   | [!UICONTROL Access Token URL] | `<Jira base url>/plugins/servlet/oauth/access-token` |

1. Markera kryssrutan **[!UICONTROL Create incoming link]**.
1. Klicka på **[!UICONTROL Continue]**.
1. I fönstret **[!UICONTROL Link applications]** fyller du i följande fält:

   <table style="table-layout:auto"> 
    <col data-mc-conditions=""> 
    <col data-mc-conditions=""> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Consumer Key]</p> </td> 
      <td> Klistra in konsumentnyckeln som du kopierade till en säker plats.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer name]</td> 
      <td>Ange ett namn. Det här namnet är till för din egen referens.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Public key]</td> 
      <td>Klistra in den offentliga nyckeln från din <code>[!DNL jira_publickey.pem]</code>-fil.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]**.
1. Fortsätt till [Skapa en anslutning till [!DNL Jira Server] eller [!DNL Jira Data Center] i [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### Skapa en anslutning till [!DNL Jira Server] eller [!DNL Jira Data Center] i [!DNL Workfront Fusion]

>[!NOTE]
>
>Använd appen [!DNL Jira Server] för att ansluta till [!DNL Jira Server] eller [!DNL Jira Data Center].

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL connection] i någon [!DNL Jira Server]-modul i [!DNL Workfront Fusion].
1. Fyll i följande fält i panelen [!UICONTROL Create a connection]:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Ange ett namn för anslutningen</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Environment]</p> </td> 
      <td> <p>Välj om du använder en produktionsmiljö eller icke-produktionsmiljö.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Type]</p> </td> 
      <td> <p>Ange om du använder ett tjänstkonto eller ett personligt konto.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Consumer Key]</td> 
      <td>Klistra in den konsumentnyckel som du kopierade till en säker plats i <a href="#configure-the-client-app-as-a-consumer-in-jira" class="MCXref xref">Konfigurera klientappen som en konsument i [!DNL Jira]</a></td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Private Key]</td> 
      <td>Klistra in den privata nyckeln från filen <code>[!DNL jira_privatekey.pcks8]</code> som du skapade i <a href="#generate-public-and-private-keys-for-your-jira-connection" class="MCXref xref">Generera offentliga och privata nycklar för din [!DNL Jira]-anslutning</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Service URL]</td> 
      <td>Ange din [!DNL Jira]-instans-URL. Exempel: <code>yourorganization.atlassian.net</code></td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Jira Software]-moduler och deras fält

När du konfigurerar [!DNL Jira Software] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Jira Software] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

#### [!UICONTROL Watch for records]

Denna utlösarmodul startar ett scenario när en post läggs till, uppdateras eller tas bort.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>Välj den webkrok som du vill använda för att bevaka poster. </p> <p>Så här lägger du till en ny webbkrok:</p> 
    <ol> 
     <li value="1">Klicka på <strong>[!UICONTROL Add]</strong></li> 
     <li value="2">Ange ett namn för webkroken.</li> 
     <li value="3"> <p>Välj den anslutning som du vill använda för din webkrok. </p> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </li> 
     <li value="4"> <p>Välj den posttyp som du vill att programmet ska bevaka:</p> 
      <ul> 
       <li>[!UICONTROL Comment] </li> 
       <li>[!UICONTROL Issue]</li> 
       <li>[!UICONTROL Project] </li> 
       <li>[!UICONTROL Sprint]</li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Add issue to sprint]](#add-issue-to-sprint)
* [[!UICONTROL Create a Record]](#create-a-record)
* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Delete a record]](#delete-a-record)
* [[!UICONTROL Download an attachment]](#download-an-attachment)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Update a record]](#update-a-record)

#### [!UICONTROL Add issue to sprint]

Den här åtgärdsmodulen lägger till en eller flera utgåvor i en utskrift.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sprint ID]</td> 
   <td>Ange eller mappa Sprint-ID:t för den utskrift som du vill lägga till ett problem i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID or Keys]</td> 
   <td>För varje problem eller nyckel som du vill se upplevelsen klickar du på <b>[!UICONTROL Add item]</b> och anger ett ärende-ID eller en nyckel. Du kan ange upp till 50 i en modul.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Record]

Denna åtgärdsmodul skapar en ny post i Jira.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska skapa och fyll sedan i de andra fälten som är specifika för den posttypen visas i modulen.</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Jira Software]. Använd den här modulen för att skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Jira Software]-modulerna.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en sökväg i förhållande till<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a record]

Den här åtgärdsmodulen tar bort den angivna posten.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska ta bort. </p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>Ange eller mappa ID:t eller nyckeln för den post som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download an attachment]

Den här åtgärdsmodulen hämtar en viss bifogad fil.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för den bifogade fil som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser data från en enskild post i [!DNL Jira Software].

Du anger postens ID.

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av [!DNL Jira]-post som du vill att modulen ska läsa.</p> 
    <ul> 
     <li>[!UICONTROL Attachment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>Välj de utdata som du vill ta emot. Utdataalternativen är tillgängliga baserat på vilken typ av post som har valts i fältet [!UICONTROL Record Type].</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>Ange eller mappa det unika [!DNL Jira Software]-ID:t för posten som du vill att modulen ska läsa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a record]

Den här åtgärdsmodulen uppdaterar en befintlig post, t.ex. ett problem eller ett projekt.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska uppdatera. När du väljer en posttyp visas andra fält som är specifika för den posttypen i modulen.</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Transition issue]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID or Key]</td> 
   <td>Ange eller mappa ID:t eller nyckeln för den post som du vill uppdatera och fyll sedan i de andra fälten som är specifika för den posttypen som visas i modulen.</td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL List records]](#list-records)
* [[!UICONTROL Search for records]](#search-for-records)

#### [!UICONTROL List records]

Den här sökmodulen hämtar alla objekt av en viss typ som matchar din sökfråga

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska visa. När du väljer en posttyp visas andra fält som är specifika för den posttypen i modulen.</p> 
    <ul> 
     <li>[!UICONTROL Comment]</li> 
     <li>[!UICONTROL Issue]</li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Sprint issue]</li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Max Results]</p> </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska hämta under varje körningscykel för scenario.</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">Offset</td> 
    <td> Enter or map the ID of the first item you want to retrieve details for. This is a way to paginate the records. If you enter the 5000th item as the offset, the module would return items 5000-9999.</td> 
   </tr>
  --> 
 </tbody> 
</table>

#### [!UICONTROL Search for records]

Den här sökmodulen söker efter poster i ett objekt i [!DNL Jira Software] som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Jira Software]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta [!DNL Jira Software] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska söka efter. När du väljer en posttyp visas andra fält som är specifika för den posttypen i modulen.</p> 
    <ul> 
     <li>[!UICONTROL Issues]</li> 
     <li> <p>[!UICONTROL Issues by JQL (Jira Query Lanuguage)] </p> <p>Mer information om JQL finns i <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> på hjälpwebbplatsen för Atlassian. </p> </li> 
     <li>[!UICONTROL Project]</li> 
     <li>[!UICONTROL Project by issue]</li> 
     <li>[!UICONTROL User]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
