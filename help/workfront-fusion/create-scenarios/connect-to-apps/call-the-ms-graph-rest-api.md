---
title: Anropa MS Graph REST API
description: Anropa MS Graph REST API via Adobe Workfront Fusion HTTP &> Make an OAuth 2.0 request module
author: Becky
feature: Workfront Fusion
exl-id: f411c807-955d-44fe-98b1-3ebba3fe0861
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 1%

---

# Anropa MS Graph REST API

Många Microsoft webbtjänster nås via Microsoft Graph API. Du kan skapa en anslutning till Microsoft Graph API genom att använda Workfront Fusion HTTP > Make an OAuth 2.0 request module.

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

## Registrera Workfront Fusion i Microsoft Application Registration Portal

Om du vill skapa en anslutning till Microsoft Graph REST API måste du först registrera Adobe Workfront Fusion.

1. Börja registrera ett nytt program enligt beskrivningen i [Registrera ett program med Microsoft identitetsplattform](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) i Microsoft-dokumentationen.

   Som en del av registreringen kräver Microsoft följande information:

   <table style="table-layout:auto">
      <tr>
        <td>Programnamn</td>
        <td>Ange ett namn för programmet, till exempel"My Workfront Fusion application".</td>
      </tr>
      <tr>
        <td>Omdirigeringsadress</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/oauth2</code></td>
      </tr>
    </table>

1. Anteckna program-ID när du har slutfört programregistreringen.

   >[!IMPORTANT]
   >
   >Du måste ha ett program-ID för att kunna konfigurera anslutningen i Workfront Fusion.

1. Skapa en klienthemlighet. Notera denna hemlighet.

   Instruktioner finns i [Registrera ett program med identitetsplattformen Microsoft](https://docs.microsoft.com/en-us/graph/auth-register-app-v2) i Microsoft-dokumentationen.

   >[!IMPORTANT]
   >
   >Du måste ange klienthemligheten för att kunna upprätta anslutningen i Workfront Fusion.

1. Konfigurera behörigheter för ditt program.

   Mer information om hur du hittar och konfigurerar dessa fält finns i avsnittet Konfigurera behörigheter för Microsoft Graph i [Få åtkomst utan användare](https://docs.microsoft.com/en-us/graph/auth-v2-service) i Microsoft-dokumentationen.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Vilken typ av behörigheter kräver ditt program?</td> 
      <td>Välj <code>Delegated permissions</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Välj behörigheter</td> 
      <td> <p>Välj följande behörigheter:</p> 
       <ul> 
        <li> <p><code>offline_access</code> </p> </li> 
        <li> <p><code>openid</code> </p> </li> 
        <li> <p>Andra behörigheter som krävs för integreringarna (Exempel: <code>User.Read</code>)</p> </li> 
       </ul> <p><b>Viktigt</b>: Du måste ha de valda behörigheterna för att kunna konfigurera anslutningen i Workfront Fusion.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Fortsätt till [Konfigurera din MS Graph API-anslutning i Workfront Fusion](#configure-your-ms-graph-api-connection-in-workfront-fusion).

## Konfigurera MS Graph API-anslutningen i Workfront Fusion

När du har registrerat Workfront Fusion enligt beskrivningen i [Registrera Workfront Fusion i Microsoft Application Registration Portal](#register-workfront-fusion-in-the-microsoft-application-registration-portal) kan du konfigurera anslutningen i HTTP > Skapa en Oauth 2.0-begärandemodul.

1. Lägg till en HTTP > Gör en OAuth 2.0-anropsmodul i ditt scenario.
1. Klicka på **Lägg till** bredvid anslutningsfältet.
1. Konfigurera anslutningsfälten enligt följande:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Anslutningsnamn</td> 
      <td>Ange ett namn för anslutningen.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Miljö</p> </td> 
      <td>Ange om du ansluter till ett produktions- eller icke-produktionskonto. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Typ</p> </td> 
      <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto. </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">Flödestyp</p> </td> 
      <td>Välj <code>Authorization Code</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Auktorisera URI</td> 
      <td>Ange <code>https://login.microsoftonline.com/common/oauth2/v2.0/authorize</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Token-URI</td> 
      <td>Ange <code>https://login.microsoftonline.com/common/oauth2/v2.0/token</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Omfång</td> 
      <td> <p>Ange de behörigheter du valde i när du registrerade dig, enligt beskrivningen i <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registrera Workfront Fusion i Microsoft Application Registration Portal</a>.</p> <p>Klicka på <b>Lägg till</b> för varje scope och ange behörigheten.</p> <p>Exempel: <code>offline_access</code>.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Omfångsavgränsare</td> 
      <td>Välj <code>SPACE</code>. </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Klient-ID</td> 
      <td>Ange program-ID från steg 2 i <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registrera Workfront Fusion i Microsoft Application Registration Portal</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Klienthemlighet</td> 
      <td>Ange den klienthemlighet som du skapade i steg 3 i <a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">Registrera Workfront Fusion i Microsoft Application Registration Portal</a>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Auktorisera parametrar</td> 
      <td> <p>Lägg till följande Authorize-parametrar. För varje parameter som du lägger till klickar du på <b>Lägg till objekt</b> och anger följande: </p> 
       <ul> 
        <li> <p>Nyckel:<code> response_mode</code> Värde: <code>query</code></p> </li> 
        <li> <p>Nyckel: <code>prompt </code>Värde: <code>consent</code></p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Åtkomsttokenparametrar</td> 
      <td>Du behöver inte ange något i det här fältet.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Uppdatera tokenparametrar</td> 
      <td> 
       <ol> 
        <li value="1"> <p>Klicka på <b>Lägg till objekt</b>.</p> </li> 
        <li value="2"> <p>Ange <b> i fältet </b>Nyckel<code>scope</code>.</p> </li> 
        <li value="3"> <p>I fältet <b>Värde</b> anger du alla omfång du har angett i omfångsfältet, avgränsade med blanksteg.</p> <p>Exempel: <code>offline_access openid User.Read</code></p> </li> 
       </ol> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Anpassade rubriker</td> 
      <td>Du behöver inte ange något i det här fältet.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Tokenplacering</td> 
      <td><code>In the header</code> </td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **Fortsätt**.
1. Klicka på **Acceptera** i det fönster som visas för att slutföra anslutningen och återgå till modulen.
