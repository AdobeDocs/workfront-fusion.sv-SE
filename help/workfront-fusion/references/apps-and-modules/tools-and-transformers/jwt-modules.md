---
title: JWT-moduler
description: Appen  [!DNL Adobe Workfront Fusion] [!UICONTROL JWT] innehåller en modul som skapar JWT-tokens baserat på den angivna algoritmen.
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# modulen [!UICONTROL JWT]

Appen [!DNL Adobe Workfront Fusion] [!UICONTROL JWT] innehåller en modul som skapar JWT-tokens baserat på den angivna algoritmen.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet], [!UICONTROL [!DNL Workfront Fusion] för Automatisering av arbete]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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
