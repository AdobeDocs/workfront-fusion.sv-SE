---
title: JWT-moduler
description: Appen Adobe Workfront Fusion [!UICONTROL JWT] innehåller en modul som skapar JWT-tokens baserat på den angivna algoritmen.
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# modulen [!UICONTROL JWT]

Appen Adobe Workfront Fusion [!UICONTROL JWT] innehåller en modul som skapar JWT-tokens baserat på den angivna algoritmen.

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
   <p>Workfront Fusion-licens krävs inte</p>
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

## API-information för JWT

JWT-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
   <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.1.5</td> 
  </tr>
 </tbody> 
 </table>

## JWT-modulen och dess fält

### Generera JWT

Den här modulen genererar en JWT baserad på den valda algoritmen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Algorithm]</td> 
   <td> <p>Välj den algoritm med vilken du vill generera JWT.</p> <ul>
   <li><b>HS256</b>: HMAC med SHA-256-hash-algoritm</li>
   <li><b>HS384</b>: HMAC med SHA-384-hash-algoritm</li>
   <li><b>HS512</b>: HMAC med SHA-512-hash-algoritm</li>
   <li><b>RS256</b>: RSASSA-PKCS1-v1_5 med SHA-256-hash-algoritm</li>
   <li><b>RS384</b>: RSASSA-PKCS1-v1_5 med SHA-384-hash-algoritm</li>
   <li><b>RS512</b>: RSASSA-PKCS1-v1_5 med SHA-512-hash-algoritm</li>
   <li><b>PS256</b>: RSASSA-PSS som använder SHA-256-hash-algoritm (endast nod ^6.12.0 ELLER &gt;=8.0.0)</li>
   <li><b>PS384</b>: RSASSA-PSS som använder SHA-384-hash-algoritm (endast nod ^6.12.0 ELLER &gt;=8.0.0)</li>
   <li><b>PS512</b>: RSASSA-PSS som använder SHA-512-hash-algoritm (endast nod ^6.12.0 ELLER &gt;=8.0.0)</li>
   <li><b>ES256</b>: ECDSA använder P-256-kurva och SHA-256-hash-algoritm</li>
   <li><b>ES384</b>: ECDSA använder P-384-kurva och SHA-384-hash-algoritm</li>
   <li><b>ES512</b>: ECDSA använder P-521-kurva och SHA-512-hash-algoritm</li>
   </ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Payload] </td> 
   <td> <p>För varje nyttolastobjekt som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger objektets nyckel och värde.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Options] </td> 
   <td> <p>För varje alternativobjekt som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger objektets nyckel och värde.</p> <p>Följande tangenter är tillgängliga:
   <ul>
   <li><b>algoritm</b>: (standard: RS256)</li>
   <li><b>expirresIn</b>: Uttrycks i sekunder eller en sträng som beskriver ett tidsintervall (t.ex. 2 dagar, 10h, 7d). Ett numeriskt värde tolkas som antal sekunder. Om du använder en sträng måste du se till att ange tidsenheter (dagar, timmar osv.), annars används enheten i millisekunder som standard (120 är lika med 120 ms).</li>
   <li><b>notBefore</b>: Uttrycks i sekunder eller en sträng som beskriver ett tidsintervall (t.ex. 2 dagar, 10h, 7d). Ett numeriskt värde tolkas som antal sekunder. Om du använder en sträng måste du se till att ange tidsenheter (dagar, timmar osv.), annars används enheten i millisekunder som standard (120 är lika med 120 ms).
</li>
   <li><b>publik</b></li>
   <li><b>utfärdare</b></li>
   <li><b>jwtid</b></li>
   <li><b>ämne</b></li>
   <li><b>noTimestamp</b></li>
   <li><b>header</b></li>
   <li><b>keyid</b></li>
   <li><b>mutatePayload</b>: Om <code>true</code> ändras nyttolastobjektet direkt av signeringsfunktionen. Detta är användbart om du behöver en oformaterad referens till nyttolasten efter att anspråk har tillämpats på den men innan den har kodats till en token.</li>
   <li><b>allowInsecureKeySizes</b>: Om <code>true</code> tillåts att privata nycklar med en modulus under 2048 används för RSA.</li>
   <li><b>allowInvalidAsymmetricKeyTypes</b>: Om <code>true</code> tillåts asymmetriska nycklar som inte matchar den angivna algoritmen. Detta alternativ är endast avsett för bakåtkompatibilitet och bör undvikas.</li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>
