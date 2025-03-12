---
title: Modulen Adobe Authenticator
description: Med Adobe Authenticator-modulen kan du ansluta till alla Adobe-produkter med ett API, via en enda anslutning.
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 7652acb6654f4b1b0edc57d110478b309655a124
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 0%

---

# Adobe Authenticator moduler

Med Adobe Authenticator-modulen kan du ansluta till alla Adobe-API:er via en enda anslutning. Det gör det enklare att ansluta till Adobe-produkter som ännu inte har någon dedikerad Fusion-anslutning.

Fördelen med HTTP-modulerna är att du kan skapa en anslutning, som i en dedikerad app.

En lista över tillgängliga Adobe API:er finns i [Adobe API:er](https://developer.adobe.com/apis). Du kanske bara kan använda de API:er som du har tilldelats.

## Åtkomstkrav

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] package</td>
      <td>
        <p>Nytt: Alla</p><p>eller</p><p>Aktuell: [!UICONTROL Pro] eller högre</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] licens</td>
      <td>
        <p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Plan], [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] licens</td>
      <td>
   <p>Aktuellt krav på Fusion-licens: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Krav för äldre Fusion-licens: [!UICONTROL [!DNL Workfront Fusion] för Automation och integrering av arbetet] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">Produkt</td>
      <td>
   <p>Ny Workfront-plan: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Aktuell Workfront-plan: Din organisation måste köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td>
    </tr>
  </tbody>
</table>

## Förutsättningar

* Du måste ha tillgång till den Adobe-produkt som du vill att modulen ska ansluta till.
* Du måste ha tillgång till Adobe Developer Console.
* Du måste ha ett projekt på Adobe Developer Console som innehåller det API som du vill att modulen ska ansluta till. Du kan:

   * Skapa ett nytt projekt med API:t.

     eller
   * Lägg till API i ett befintligt projekt.

  Mer information om hur du skapar eller lägger till ett API i ett projekt på Adobe Developer Console finns i [Skapa ett projekt](https://developer.adobe.com/dep/guides/dev-console/create-project/) i Adobe-dokumentationen.

## Adobe Authenticator API-information

Adobe Authenticator Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.1.4</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning

En Adobe Authenticator-anslutning ansluter till ett enda projekt i Adobe Developer Console. Om du vill använda samma anslutning för mer än ett Adobe API lägger du till API:erna i samma projekt och skapar en anslutning till det projektet.

Du kan skapa separata anslutningar till separata projekt, men du kan inte använda en anslutning för att komma åt ett API som inte finns i det projekt som anges i anslutningen.

>[!IMPORTANT]
>
>Med Adobe Authenticator Connector kan du välja mellan att skapa en OAuth Server-till-server-anslutning eller en JWT-anslutning (Service Account). Adobe har ersatt JWT-inloggningsuppgifter, som kommer att sluta fungera efter 1 januari 2025. **Därför rekommenderar vi att du skapar OAuth-anslutningar.**
>
>Mer information om den här typen av anslutningar finns i [Autentisering från server till server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/) i Adobe-dokumentationen

Så här skapar du en anslutning:

1. Klicka på **Lägg till** bredvid anslutningsfältet i en Adobe Authenticator-modul.
1. Fyll i följande fält:

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Välj om du vill skapa en OAuth Server-till-Server-anslutning eller en JWT-anslutning (Service Account).</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange ditt klient-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe]-klienthemlighet. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>Om du har valt en OAuth-anslutning anger du de scope som behövs för den här anslutningen.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Ange ditt tekniska konto-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>Om du har valt en JWT-anslutning anger du ditt organisations-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>Om du har valt en JWT-anslutning anger du de metaomfång som krävs för den här anslutningen. </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Om du har valt en JWT-anslutning anger du den privata nyckel som skapades när dina autentiseringsuppgifter skapades i [!DNL Adobe Developer Console]. </p>
          <p>Så här extraherar du din privata nyckel eller ditt certifikat:</p>
          <ol>
            <li value="1">
              <p>Klicka på <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Välj vilken typ av fil du extraherar.</p>
            </li>
            <li value="3">
              <p>Markera filen som innehåller den privata nyckeln eller certifikatet.</p>
            </li>
            <li value="4">
              <p>Ange lösenordet för filen.</p>
            </li>
            <li value="5">
              <p>Klicka på <b>[!UICONTROL Save]</b> för att extrahera filen och återgå till anslutningsinställningarna.</p>
            </li>
          </ol>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Base URLs]</td>
        <td>Du måste lägga till de bas-URL:er som du vill att autentiseraren ska tillåta. När du använder Anpassa API-anropsmodulen senare i scenariot lägger du till en relativ sökväg till den valda URL:en. Genom att ange URL:er här kan du styra vad en anpassad API-anropsmodul kan ansluta till, vilket ökar säkerheten.<p>För varje bas-URL som du vill lägga till i autentiseraren klickar du på <b>Lägg till objekt</b> och anger bas-URL:en.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>Lämna det här tomt om du vill använda Adobe IMS-standardautentiserings-URL:en för <code>https://ims-na1.adobelogin.com</code>. Om du inte använder Adobe IMS för autentisering anger du den URL som ska användas för autentisering.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
      </tr>
    </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## Moduler

* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Göra ett anpassat API-anrop (äldre)](#make-a-custom-api-call-legacy)

### Göra ett anpassat API-anrop

Med den här åtgärdsmodulen kan du anropa alla Adobe API:er. Det stöder stora filer i stället för brödtext.

Denna modul gjordes tillgänglig den 14 november 2024. Alla Adobe Authenticator > Gör ett anpassat API-anrop som har konfigurerats före detta datum hanterar inte stora filer och betraktas nu som en anpassad API-anropsmodul (äldre).

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Instruktioner om hur du skapar en anslutning till modulen Adobe Authenticator finns i <a href="#create-a-connection" class="MCXref xref" >Skapa en anslutning</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>Ange bas-URL:en för den API-punkt som du vill ansluta till.</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Ange sökvägen i förhållande till bas-URL:en.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>Ange frågesträngen för begäran.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body Type]</td>
   <td> Välj innehållstyp för denna API-begäran:
   <ul>
   <li>Raw</li>
   <li>application/x-www-form-urlencoded</li>
   <li>multipart/form-data</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Request content]  </td>
      <td>
        <p>Ange innehållet i begäran. Det här alternativet är tillgängligt om du har valt innehållstypen <code>Raw</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Fields]  </td>
      <td>
        <p>För varje fil som du vill lägga till i API-begäran klickar du på <b>Lägg till objekt</b> och anger texten i filen (för rådata), eller anger nyckeln <code>uploadedFile</code> och mappar filens data. Det här alternativet är tillgängligt om du har valt brödtypen <code>application</code> eller <code>multipart</code> .</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Output Type]  </td>
      <td>
        <p>Välj den typ av data som du vill att modulen ska visa. Om du inte väljer någon typ väljs en typ automatiskt i modulen.</p>
      </td>
    </tr>
  </tbody>
</table>

### Göra ett anpassat API-anrop (äldre)

Med den här åtgärdsmodulen kan du anropa alla Adobe API:er.

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>Instruktioner om hur du skapar en anslutning till modulen Adobe Authenticator finns i <a href="#create-a-connection" class="MCXref xref" >Skapa en anslutning</a> i den här artikeln.</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
      </td>
      <td>
        <p>Ange bas-URL:en för den API-punkt som du vill ansluta till.</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>Ange sökvägen i förhållande till bas-URL:en.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Method]</p>
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till auktoriseringsrubriker.</p>
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
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> 
     </div> </p> </td>     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>Ange det maximala antal resultat som du vill att modulen ska returnera i en körningscykel.</p>
      </td>
    </tr>
  </tbody>
</table>
