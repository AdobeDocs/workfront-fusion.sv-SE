---
title: AWS S3-moduler
description: Med  [!DNL Adobe Workfront Fusion AWS] S3-modulerna kan du utföra åtgärder på dina S3-bucket.
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 0%

---

# AWS S3-moduler

Med S3-modulerna [!DNL Adobe Workfront Fusion AWS] kan du utföra åtgärder på dina S3-bucket.

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

Du måste ha ett [!UICONTROL AWS S3]-konto för att kunna använda [!DNL Amazon Web Service]-moduler.

## API-information för AWS S3

AWS S3-anslutningen har följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://s3.{{parameters.region}}.amazonaws.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL AWS] till Workfront Fusion {#connect-aws-to-workfront-fusion}

Om du vill ansluta [!DNL AWS S3] till Workfront Fusion måste du ansluta ditt [!DNL AWS]-konto till Workfront Fusion. Om du vill göra det måste du först skapa en API-användare i [!DNL AWS] [!UICONTROL IAM].

1. Logga in på ditt [!DNL AWS] [!UICONTROL IAM]-konto.
1. Navigera till **[!UICONTROL Identity and Access Management]** > **[!UICONTROL Access Management]** > **[!UICONTROL Users]**.

1. Klicka på **[!UICONTROL Add User]**.
1. Ange namnet på den nya användaren och välj alternativet **[!UICONTROL Programmatic access]** i avsnittet [!UICONTROL Access type].
1. Klicka på **[!UICONTROL Attach existing policies directly]** och sök sedan efter **[!UICONTROL AmazonS3FullAccess]** i sökfältet. Klicka på den när den visas och klicka sedan på **[!UICONTROL Next]**.

1. Gå igenom de andra dialogrutorna och klicka sedan på **[!UICONTROL Create User]**.
1. Kopiera tillhandahållen **[!UICONTROL Access key ID]** och **[!UICONTROL Secret access key]**.

1. Gå till Workfront Fusion och öppna [!DNL AWS S3]-modulens dialogruta **[!UICONTROL Create a connection]**.
1. Ange [!UICONTROL Access key ID] och [!UICONTROL Secret access key] från steg 7 till respektive fält och klicka på **[!UICONTROL Continue]** för att upprätta anslutningen.

Anslutningen har upprättats. Du kan fortsätta med att konfigurera modulen.

## [!DNL AWS S3]-moduler och deras fält

När du konfigurerar [!DNL AWS S3]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL AWS S3] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärder](#actions)
* [Sökningar](#searches)

### Åtgärder

* [[!UICONTROL Create Bucket]](#create-bucket)
* [[!UICONTROL Get File]](#get-file)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Upload File]](#upload-file)

#### [!UICONTROL Create Bucket]

Den här åtgärdsmodulen skapar en hink i AWS.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Ange namnet på den nya bucket.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i AWS-dokumentationen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get File]

Den här åtgärdsmodulen hämtar en fil från en bucket.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i [!DNL AWS]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Markera den hink du vill hämta filen från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Path]</p> </td> 
   <td> <p>Ange sökvägen till filen. Exempel: <code>/photos/2019/February/image023.jpg</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Den här åtgärdsmodulen gör ett anpassat anrop till AWS S3 API.

Mer information om API:t [!DNL Amazon S3] finns i [[!DNL Amazon S3] [!UICONTROL REST] API-introduktion ](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i [!DNL AWS]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>Ange en värd-URL. Sökvägen måste vara relativ till <code> https://s3.&lt;selected-region>.amazonaws.com/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>Välj den [!UICONTROL HTTP]-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP]-förfrågningsmetoder i Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>Lägg till en begäranderubrik. För varje rubrik som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger rubriken. Du kan använda följande vanliga begärandehuvuden. Mer information om begäranderubriker finns i <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html">[!DNL AWS S3] API-dokumentation </a>.</p> <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p> 
    <table style="table-layout:auto">
     <col> 
     <col> 
     <thead> 
      <tr> 
       <th>Rubriknamn</th> 
       <th> <p> Beskrivning</p> </th> 
      </tr> 
     </thead> 
     <tbody> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Length]</p> </td> 
       <td> <p>Meddelandets längd (utan rubriker) enligt RFC 2616. Den här rubriken krävs för [!UICONTROL PUT] och åtgärder som läser in XML, till exempel loggning och åtkomstkontrollistor.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Type]</p> </td> 
       <td> <p>Resursens innehållstyp om begärandeinnehållet finns i brödtexten. Exempel: <code>text/plain</code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-MD5]</p> </td> 
       <td> <p>Base64-kodade 128-bitars MD5-meddelandet (utan meddelandehuvuden) enligt RFC 1864. Den här rubriken kan användas som en meddelandeintegritetskontroll för att verifiera att data är samma data som ursprungligen skickades. Även om det är valfritt rekommenderar vi att du använder funktionen [!UICONTROL Content-MD5] som en helhetskontroll. Mer information om [!UICONTROL REST]-begärandeautentisering finns i <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">Signera och autentisera REST-begäranden</a> i AWS-dokumentationen.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Date]</p> </td> 
       <td> <p>Aktuellt datum och aktuell tid enligt den som gjorde begäran. Exempel: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>. När du anger rubriken <code>Authorization </code> måste du ange antingen rubriken <code>x-amz-date</code> eller rubriken <code>Date </code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>När ditt program använder [!UICONTROL 100-continue] skickas inte begärandetexten förrän det får en bekräftelse. Om meddelandet avvisas baserat på rubrikerna skickas inte meddelandets brödtext. Den här rubriken kan bara användas om du skickar en text.</p> <p>Giltiga värden: [!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
       <td> <p>För sökvägsbegäranden är värdet <code>s3.amazonaws.com</code>. För begäranden i virtuell stil är värdet <code>BucketName.s3.amazonaws.com</code>. Mer information finns i <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html">Virtuell värdtjänst</a> i AWS-dokumentationen.</p> <p>Den här rubriken krävs för HTTP 1.1 (de flesta verktygslådor lägger till den här rubriken automatiskt); valfri för HTTP/1.0-begäranden.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>När du använder signaturversion 4 för att autentisera begäran ger det här huvudet en hash av nyttolasten för begäran. När du överför ett objekt i segment ska du ange värdet <code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code> för att ange att signaturen endast omfattar rubriker och att det inte finns någon nyttolast. Mer information finns i <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html">Signaturberäkningar för auktoriseringshuvudet</a> i AWS-dokumentationen.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-date]</p> </td> 
       <td> <p>Aktuellt datum och aktuell tid enligt den som gjorde begäran. Exempel: <code>Wed, 01 Mar 2006 12:00:00 GMT</code>. När du anger rubriken <code>Authorization </code> måste du ange antingen rubriken <code>x-amz-date</code> eller rubriken <code>Date </code>. Om du anger båda gäller det angivna värdet för rubriken <code>x-amz-date</code>.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-security-token]</p> </td> 
       <td> <p>Den här rubriken kan användas i följande scenarier:</p> 
        <ul> 
         <li>Ange säkerhetstoken för [!DNL Amazon DevPay]-åtgärder. Varje begäran som använder [!DNL Amazon DevPay] kräver två <code>x-amz-security-token</code>-huvuden: en för produkttoken och en för användartoken. När [!DNL Amazon S3] tar emot en autentiserad begäran jämförs den beräknade signaturen med den angivna signaturen. Felaktigt formaterade flervärdesrubriker som används för att beräkna en signatur kan orsaka autentiseringsproblem.</li> 
         <li>Ange en säkerhetstoken när du använder temporära säkerhetsuppgifter. När du gör begäranden med temporära säkerhetsuppgifter som du fått från IAM (InDesign) måste du ange en säkerhetstoken med den här rubriken. Om du vill veta mer om tillfälliga säkerhetsbehörigheter går du till Göra förfrågningar.</li> 
        </ul> <p>Den här rubriken krävs för begäranden som använder [!DNL Amazon DevPay] och begäranden som signeras med temporära säkerhetsuppgifter.</p> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>Lägg till önskade frågesträngar, t.ex. parametrar eller formulärfält.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!   <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload File]

Den här åtgärdsmodulen överför en fil till en AWS S3-bucket.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i [!DNL AWS]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Folder] </p> </td> 
   <td> <p>Ange målmappen som du vill överföra en fil till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers] (valfritt)</p> </td> 
   <td> <p> För varje rubrik som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger rubrikens nyckel och värde.</p><p> Information om tillgängliga rubriker finns i <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html">PutObject</a> i AWS-dokumentationen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

* [[!UICONTROL List Files]](#list-files)
* [[!UICONTROL List Folders]](#list-folders)

#### [!UICONTROL List Files]

Returnerar en lista med filer från en angiven plats.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i [!DNL AWS]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Markera den [!DNL Amazon S3]-bucket som du vill söka efter filer.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix]</p> </td> 
   <td> <p> Ange en sökväg till en mapp där du vill söka efter filer, till exempel <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Folders]

Returnerar en lista med mappar från en angiven plats.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL AWS]-konto till Workfront Fusion finns i <a href="#connect-aws-to-workfront-fusion" class="MCXref xref"> Ansluta [!DNL AWS] till Workfront Fusion </a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>Välj regional slutpunkt. Mer information finns i <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">regionala slutpunkter</a> i [!DNL AWS]-dokumentationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>Markera den [!DNL Amazon S3]-bucket som du vill söka efter mappar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (valfritt)</p> </td> 
   <td> <p> Sökväg till en mapp som du vill söka efter mappar i, till exempel <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>
