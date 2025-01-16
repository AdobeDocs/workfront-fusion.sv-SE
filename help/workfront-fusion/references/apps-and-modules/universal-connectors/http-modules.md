---
title: HTTP&gt; Andra moduler
description: HTTP-appen  [!DNL Adobe Workfront Fusion] innehåller olika moduler för kommunikation baserade på HTTP-protokollet (Hypertext Transfer Protocol). HTTP är grunden för datakommunikation för webben. Du kan använda modulerna för att hämta webbsidor och filer, anropa webhooks och API-slutpunkter och så vidare.
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: 6398261775584e33515c546de4e7a72d5830ebe0
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# HTTP > Andra moduler

>[!NOTE]
>
>[!UICONTROL Adobe Workfront Fusion] kräver en [!UICONTROL Adobe Workfront Fusion]-licens utöver en [!UICONTROL Adobe Workfront]-licens.

Appen [!DNL Adobe Workfront Fusion] [!UICONTROL HTTP] innehåller olika moduler för kommunikation baserat på HTTP-protokollet (Hypertext Transfer Protocol). HTTP är grunden för datakommunikation för webben. Du kan använda modulerna för att hämta webbsidor och filer, anropa webhooks och API-slutpunkter och så vidare.

Vilket som är rätt val för modulen beror på vilken autentiserings-/auktoriseringsmekanism som resursen du vill ha tillgång till. Följande är exempel på moduler

* Gör en begäran:universell modul är främst avsedd för resurser som inte använder någon typ av autentisering/auktorisering
* Gör en grundläggande autentiseringsbegäran:för resurser som använder [!DNL HTTP] grundläggande autentisering (BA)
* Gör en OAuth 2.0-begäran: för resurser som använder OAuth 2.0-auktoriseringsprotokoll
* Gör en autentiseringsbegäran för klientcertifikat: för resurser som använder auktoriseringsprotokoll som kräver ett certifikat på klientsidan.
* Gör en API-nyckelauktoriseringsbegäran: för resurser som använder API-nycklar för auktorisering.

>[!NOTE]
>
>Om du ansluter till en Adobe-produkt som för närvarande inte har någon dedikerad anslutning rekommenderar vi att du använder Adobe Authenticator-modulen.
>
>Mer information finns i [Adobe Authenticator-modulen](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md).

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
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Ange eller mappa URL:en för filen som du vill hämta. </p> </td> 
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

![](/help/workfront-fusion/references/apps-and-modules/assets/jwt-header-350x19.png)

Kod för kopiera&amp;klistra in:

```
{{replace(replace(replace(base64("{""alg"":""HS256"",""typ"":""JWT""}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Nyttolast:

![](/help/workfront-fusion/references/apps-and-modules/assets/jwt-payload-350x17.png)

Kod för kopiera&amp;klistra in:

```
{{replace(replace(replace(base64("{""iss"":""key"",""exp"":" + (timestamp + 60) + "}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Token:

![](/help/workfront-fusion/references/apps-and-modules/assets/jwt-token-350x15.png)

Kod för kopiera&amp;klistra in:

```
{{1.value}}.{{2.value}}.{{replace(replace(replace(sha256(1.value + "." + 2.value; "base64"; "secret"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```
