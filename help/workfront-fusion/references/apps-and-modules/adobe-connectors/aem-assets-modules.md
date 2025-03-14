---
title: Adobe Experience Manager Assets moduler
description: Med  [!DNL Adobe Experience Manager Assets] connector for [!DNL Adobe Workfront Fusion] kan du skapa, överföra och uppdatera resurser samt kopiera eller flytta mappar och resurser.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Assets] moduler

Med [!DNL Adobe Experience Manager Assets]-kopplingen för [!DNL Adobe Workfront Fusion] kan du skapa, överföra och uppdatera resurser samt kopiera eller flytta mappar och resurser.

En videointroduktion till Adobe Experience Manager Assets Connector finns på:

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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
   <p>Äldre: Workfront Fusion for Automation and Integration </p>
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

* Du måste ha ett [!DNL Adobe Experience Manager Assets]-konto för att kunna använda dessa moduler.
* Du måste konfigurera [!UICONTROL Server-to-server]-flödet i [!DNL Adobe Developer console].

  Instruktioner om hur du konfigurerar flödet [!UICONTROL Server-to-server] i [!DNL Adobe Developer console] finns i [Generera åtkomsttoken för API:er på serversidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
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

## Anslut [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion] {#connect-adobe-experience-manager-assets-to-workfront-fusion}

Så här skapar du en anslutning för dina [!DNL Adobe Experience Manager Assets]-moduler:

1. Klicka på [!UICONTROL Add] bredvid rutan [!UICONTROL Connection].

2. Välj den typ av anslutning som du skapar:

   * **[!DNL AEM Assets as a Cloud Service]**

     Den här konfigurationen kräver information från [!DNL Adobe Admin Console].

   * **[!DNL AEM Assets Basic]([!DNL Adobe Managed Services])**

     Den här konfigurationen kräver ett användarnamn och lösenord.

3. Fyll i fälten för den typ av anslutning som du skapar.

   För [!DNL AEM Assets as a Cloud Service], se [Konfigurera anslutningen för  [!DNL AEM Assets as a Cloud Service]](#configure-the-connection-for-aem-assets-as-a-cloud-service).

   För [!UICONTROL AEM Assets Basic] ([!DNL Adobe Managed Services]), se [Konfigurera anslutningen för [!UICONTROL AEM Assets Basic]](#configure-the-connection-for-aemassets-basic-adobe-managed-services).

4. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.


### Konfigurera anslutningen för [!DNL AEM Assets as a Cloud Service]

>[!NOTE]
>
>* Informationen för dessa fält genereras som en del av konfigurationen av [!UICONTROL Server-to-server]-flödet på [!DNL Adobe Developer Console]. Dessa värden finns i JSON-tjänstens inloggningsinformation som genereras som en del av den konfigurationen.
>
>   Instruktioner om hur du konfigurerar [!UICONTROL Server-to-server]-flödet på [!UICONTROL Adobe Developer Console] finns i [Generera åtkomsttoken för API:er på serversidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html#the-server-to-server-flow).
>
>* Ditt Adobe Experience Manager-konto måste ha skrivbehörighet.
>
>   Instruktioner om hur du lägger till skrivbehörigheter till ditt Adobe Experience Manager tekniska konto finns i [Tjänstens autentiseringsuppgifter](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials) i Adobe Experience Manager-dokumentationen.


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">[!UICONTROL Connection name]</td>
                  <td>
                      <p>Ange ett namn för anslutningen</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                  <td>Ange URL:en för din [!DNL Adobe Experience Manager]-instans. Ta inte med ett snedstreck <code>/</code> i slutet av URL:en.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Account details fill options]</td>
                  <td>Välj om du vill ange JSON som beskriver din kontoinformation eller om du vill ange information manuellt.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Technical account details in JSON format]</td>
                  <td>Om du anger JSON anger eller klistrar du in den JSON som beskriver din kontoinformation.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client ID]</td>
                  <td>Om du anger information manuellt anger du det klient-ID som genererats i [!UICONTROL Server-to-server]-konfigurationen.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Client Secret]</td>
                  <td>Om du anger information manuellt anger du den klienthemlighet som genererats i [!UICONTROL Server-to-server]-konfigurationen.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Technical account ID]</td>
                  <td>Om du anger information manuellt anger du ID för det tekniska kontot. Det här är fältet [!UICONTROL id] i JSON-filen för klientautentiseringsuppgifter.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Org ID]</td>
                  <td class="">Ange organisationens ID om du anger information manuellt. Det här är fältet [!UICONTROL org] i JSON-filen för klientautentiseringsuppgifter.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Meta Scopes]</td>
                  <td>Ange de metaomfång som genererats i [!UICONTROL Server-to-server]-inställningen.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Private key]</td>
                  <td>Ange den privata nyckel som genererats för att vinna inställningen [!UICONTROL Server-to-server]. Om du vill extrahera den privata nyckeln klickar du på [!UICONTROL Extract], anger filen som ska extraheras och lösenordet för filen.</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL Authentication URL]</td>
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
                <td role="rowheader">[!UICONTROL Connection name]</td>
                <td>
                    <p>Ange ett namn för anslutningen</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
                <td>Ange URL:en för din [!DNL Adobe Experience Manager]-instans. Ta inte med ett snedstreck <code>/</code> i slutet av URL:en.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Username]</td>
                <td>Ange användarnamnet för det [!DNL AEM Assets]-konto som den här anslutningen använder.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Password]</td>
                <td>Ange lösenordet för det [!DNL AEM Assets]-konto som den här anslutningen använder.</td>
            </tr>
        </tbody>
    </table>


## [!DNL Adobe Experience Manager Assets]-moduler och deras fält

När du konfigurerar [!DNL Adobe Experience Manager Essentials] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Adobe Experience Manager Essentials] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Kopiera en mapp eller resurs](#copy-a-folder-or-asset)
* [Skapa en post](#create-a-record)
* [Ta bort en mapp, resurs eller återgivning](#delete-a-folder-asset-or-rendition)
* [Hämta en mapplista](#get-a-folder-listing)
* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Flytta en mapp eller resurs](#move-a-folder-or-asset)
* [Uppdatera en post](#update-a-record)
* [Överföra en resurs](#upload-an-asset)

### [!UICONTROL Copy a folder or asset]

Den här åtgärdsmodulen kopierar en mapp eller resurs till en annan plats på ditt Adobe Experience Manager Assets-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill kopiera en mapp eller en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Asset]</td> 
   <td>Markera eller mappa mappen eller resursen som du vill kopiera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>Markera eller mappa sökvägen till platsen för den nya mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of copied folder] / [!UICONTROL asset]</td> 
   <td>Ange ett namn för den nya mappen eller resursen. Mappnamnet som visas i [!DNL Adobe Experience Manager Assets] är samma som det ursprungliga namnet. Namnet som anges här visas i URL:en för den nya mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy children]</td> 
   <td>Om du kopierar en mapp aktiverar du det här alternativet för att kopiera alla undermappar eller resurser i mappen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Aktivera det här alternativet om du vill skriva över mappar eller resurser på målplatsen som har samma namn som mappen eller resursen som kopieras.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Create a record]

Den här åtgärdsmodulen skapar en mapp eller en resurskommentar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object type]</td> 
   <td> <p>Välj om du vill skapa en mapp eller en kommentar för en resurs.</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p>[!UICONTROL Name]</p> <p>Ange ett namn för mappen. Det här namnet visas i filsökvägen och får inte innehålla blanksteg eller andra tecken. </p> </li> 
       <li> <p>[!UICONTROL Title]</p> <p>Ange en rubrik för mappen, som kan visas i stället för namnet.</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset comment]</p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p>[!UICONTROL Asset selection]</p> <p>Markera eller mappa ID:t för resursen som du vill lägga till en kommentar i.</p> </li> 
       <li> <p>[!UICONTROL Comment]</p> <p>Ange texten för kommentaren.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Delete a folder, asset, or rendition]

Den här åtgärdsmodulen tar bort en mapp, en resurs eller en återgivning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill ta bort en mapp, en resurs eller en återgivning.</p> 
    <ul> 
     <li> <p>[!UICONTROL Folder]</p> <p>Markera mappen som ska tas bort genom att markera mapparna i sökvägen.</p> </li> 
     <li> <p>[!UICONTROL Asset] </p> <p>Markera resursen genom att markera mapparna i sökvägen och sedan den resurs du vill ta bort.</p> </li> 
     <li> <p>[!UICONTROL Rendition]</p> <p>Markera återgivningen genom att markera mapparna i sökvägen.</p> <p>Ange eller mappa återgivningens namn.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a folder listing]

Den här åtgärdsmodulen hämtar en representation av en befintlig mapp och av dess underordnade enheter (mappar eller resurser).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Markera eller mappa mappen som du vill hämta. Om du vill lägga till undermappar i sökvägen klickar du på plusikonen och väljer undermappen.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Make a custom API call]

Den här åtgärdsmodulen gör ett anpassat API-anrop till API:t [!DNL Adobe Experience Manager Assets].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till din [!DNL Adobe Experience Manager]-bas-URL.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Ange frågesträngen för begäran. För varje nyckel/värde-par klickar du på <b>[!UICONTROL Add item]</b> och anger [!UICONTROL Key] och [!UICONTROL Value].</p> </td> 
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

### [!UICONTROL Move a folder or asset]

Den här åtgärdsmodulen flyttar resursen eller mappen på den angivna sökvägen till en ny plats.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill flytta en mapp eller en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] / [!UICONTROL Asset]</td> 
   <td>Markera eller mappa mappen eller resursen som du vill flytta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination path]</td> 
   <td>Markera eller mappa sökvägen till den plats där du vill flytta mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of moved folder] / [!UICONTROL asset]</td> 
   <td>Ange ett nytt namn för den flyttade mappen eller resursen. Mappnamnet som visas i [!DNL Adobe Experience Manager Assets] är samma som det ursprungliga namnet. Namnet som anges här visas i URL:en för den flyttade mappen eller resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Aktivera det här alternativet om du vill skriva över mappar eller resurser på målplatsen som har samma namn som mappen eller resursen som flyttas.</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update a record]

Den här åtgärdsmodulen uppdaterar en befintlig post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj om du vill ta bort metadata för resursen eller en resursåtergivning.</p> 
    <ul> 
     <li> <p>[!UICONTROL Asset metadata]</p> 
      <ul> 
       <li> <p>Välj den resurs som du vill uppdatera metadata för.</p> </li> 
       <li> <p>Ange resursens nya namn.</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL Asset rendition]</p> 
      <ul> 
       <li> <p>Välj den resurs som du vill uppdatera återgivningen för.</p> </li> 
       <li> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Upload an asset]

Den här åtgärdsmodulen överför en resurs till ditt [!DNL Adobe Experience Manager Assets]-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager Assets]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Adobe Experience Manager Assets] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination]</td> 
   <td> <p>Välj den mapp där du vill överföra en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>Ange eller mappa källfilens namn och data.</td> 
  </tr> 
 </tbody> 
</table>
