---
title: HTTP > Andra moduler
description: Adobe Workfront Fusion HTTP-appen innehåller olika moduler för kommunikation baserade på HTTP-protokollet (Hypertext Transfer Protocol). HTTP är grunden för datakommunikation för webben. Du kan använda modulerna för att hämta webbsidor och filer, anropa webhooks och API-slutpunkter och så vidare.
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# HTTP > Andra moduler

Appen Adobe Workfront Fusion [!UICONTROL HTTP] innehåller olika moduler för kommunikation baserade på HTTP-protokollet (Hypertext Transfer Protocol). HTTP är grunden för datakommunikation för webben. Du kan använda modulerna för att hämta webbsidor och filer, anropa webhooks och API-slutpunkter och så vidare.

Vilket som är rätt val för modulen beror på vilken autentiserings-/auktoriseringsmekanism som resursen du vill ha tillgång till. Följande är exempel på moduler

* **Gör en begäran**: Är främst avsedd för resurser som inte använder någon typ av autentisering eller auktorisering
* **Gör en grundläggande autentiseringsbegäran**: För resurser som använder [!DNL HTTP] grundläggande autentisering (BA)
* **Gör en OAuth 2.0-begäran**: För resurser som använder OAuth 2.0-auktoriseringsprotokollet
* **Gör en autentiseringsbegäran för klientcertifikat**: För resurser som använder auktoriseringsprotokoll som kräver ett certifikat på klientsidan
* **Gör en API-nyckelauktoriseringsbegäran**: För resurser som använder API-nycklar för auktorisering

>[!NOTE]
>
>Om du ansluter till en Adobe-produkt som inte har någon dedikerad anslutning rekommenderar vi att du använder Adobe Authenticator-modulen.
>
>Mer information finns i [Adobe Authenticator-modulen](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md).

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

## Begär moduler

I följande artiklar finns information om en specifik modul för begäranden:

* [[!UICONTROL HTTP] > [!UICONTROL Make a request]-modulen](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make a Basic Authorization request]-modulen](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-basic-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make an OAuth 2.0 request]-modulen](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make a Client Certificate Authorization request]-modulen](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-client-cert-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL Make an API Key Authorization request]](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-api-key-auth-request.md)

## Andra åtgärdsmoduler

* [[!UICONTROL Get a File]](#get-a-file)
* [[!UICONTROL Resolve a target URL]](#resolve-a-target-url)

### [!UICONTROL Get a File]

Den här åtgärdsmodulen hämtar en fil från den angivna URL:en. När filen har laddats ned kan du bearbeta filen ytterligare (mappa fildata) med hjälp av andra moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx )] </td> 
   <td> <p>Använd det här alternativet om du vill konfigurera felhantering.</p> <p>Mer information finns i <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Felhantering i Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Ange eller mappa URL:en för filen som du vill hämta. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules] </td> 
   <td> <p>Aktivera det här alternativet om du vill att cookies för den här webbplatsen ska vara tillgängliga för andra moduler. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Resolve a target URL]

Den här åtgärdsmodulen åtgärdar en kedja av HTTP-omdirigeringar och returnerar en mål-URL.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Ange eller mappa den URL som du vill matcha, till exempel en [!DNL bit.ly]-URL.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method] </td> 
   <td> <p>Välj om du vill använda metoden [!UICONTROL HEAD] eller metoden [!UICONTROL GET].</p> </td> 
  </tr> 
 </tbody> 
</table>

## Iteratormoduler

### [!UICONTROL Retrieve headers]

Den här modulen returnerar varje rubrik (namn och värde) från den angivna HTTP-modulen i ett separat paket.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Markera modulen som du vill hämta rubriker från.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Genererar JSON-webbtoken (JWT)

Du kan generera en JWT-token med hjälp av inbyggda funktioner:

Sidhuvud:

![JWT-rubrik](/help/workfront-fusion/references/apps-and-modules/assets/jwt-header-350x19.png)

Kod för kopiera&amp;klistra in:

```
{{replace(replace(replace(base64("{""alg"":""HS256"",""typ"":""JWT""}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Nyttolast:

![JWT-nyttolast](/help/workfront-fusion/references/apps-and-modules/assets/jwt-payload-350x17.png)

Kod för kopiera&amp;klistra in:

```
{{replace(replace(replace(base64("{""iss"":""key"",""exp"":" + (timestamp + 60) + "}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Token:

![JWT-token](/help/workfront-fusion/references/apps-and-modules/assets/jwt-token-350x15.png)

Kod för kopiera&amp;klistra in:

```
{{1.value}}.{{2.value}}.{{replace(replace(replace(sha256(1.value + "." + 2.value; "base64"; "secret"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```
