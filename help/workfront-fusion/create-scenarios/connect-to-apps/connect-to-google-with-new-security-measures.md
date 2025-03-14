---
title: Koppla Adobe Workfront Fusion till Google Services med uppdaterade säkerhetsfunktioner
description: Google har infört begränsningar för hur användare kan använda sina API:er. I den här artikeln beskrivs hur du ansluter Adobe Workfront Fusion till Google, som redovisar dessa säkerhetsåtgärder för uppdatering.
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Koppla Adobe Workfront Fusion till Google Services med uppdaterade säkerhetsfunktioner

Google har infört begränsningar för hur användare kan använda sina API:er. I den här artikeln beskrivs hur du ansluter Adobe Workfront Fusion till Google, som redovisar dessa säkerhetsåtgärder för uppdatering.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package 
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
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront Plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>Ultimate Workfront Plan: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Begränsningar för Google Services

Google införde restriktioner för hur användare kan använda sina API:er den 1 juni 2020. Dessa säkerhetsåtgärder skyddar Google-användare från att läsa eller missbruka deras personuppgifter på Google.

Dessa begränsningar gäller Gmail- och Google Drive-apparna.

Mer information om dessa begränsningar finns i&quot;Additional Requirements for Specific API Scopes&quot; i [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)

För att få åtkomst till begränsade omfattningar måste den anslutna tjänsten (Adobe Workfront Fusion eller någon annan tjänst som får åtkomst till användarens data via API:t) verifieras och ha en bedömningsrapport som visar att tjänsten är säker och transparent med hur informationen används. Workfront Fusion uppfyller alla Google krav för åtkomst till begränsade scope. De flesta tredjepartstjänsterna i Workfront Fusion har dock inte utvärderingsbrevet och uppfyller därför inte Google villkor. Därför har Workfront Fusion inte rätt att skicka data till dessa tjänster.

## Undantag från Google Services-begränsningar

Det finns några undantag som gör det möjligt att skicka data till en ej godkänd tredjepartstjänst som inte har utvärderingsversionsinformationen utan att bryta mot någon av de nya begränsningarna. De skiljer sig åt beroende på Google Workspace med Workfront Fusion OAuth-klienten, Google Workspace med en annan OAuth-klient eller @gmail.com och @googlemail.com.

* [Google Workspace med Workfront Fusion OAuth-klient](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspace med en annan OAuth-klient](#google-workspace-with-another-oauth-client)
* [@gmail.com och @googlemail.com](#gmailcom-and-googlemailcom)

### Google Workspace med Workfront Fusion OAuth-klient

Workfront Fusion använder det domänomfattande installationsundantaget. Installation i hela domänen passar för användare av Google Workspace och ger användare möjlighet att integrera icke godkända tjänster utan begränsningar. Om du använder Google Workspace behöver du inte utföra några ytterligare steg och kan ansluta direkt till ej godkända tjänster.

### Google Workspace med en annan OAuth-klient

Användare av Google Workspace som föredrar att använda sin egen OAuth-klient i stället för att använda Workfront Fusion OAuth-klienten kan ansluta till Google Services via internetanvändning. Det här alternativet är avsett för avancerade användare. Instruktioner finns i [Ansluta Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

### @gmail.com och @googlemail.com {#gmailcom-and-googlemailcom}

Användare som har tillgång till Google Services via @gmail.com eller @googlemail.com kan ansluta till Google Services via Personal Use. Det här alternativet är avsett för avancerade användare. Instruktioner finns i [Ansluta Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

## Vanliga frågor

* [Vilka appar i Adobe Workfront Fusion påverkas?](#what-apps-in-adobe-workfront-fusion-are-affected)
* [Har jag ett Google Workspace-konto?](#do-i-have-a-g-suite-account)
* [Vad ska jag göra om jag använder @gmail.com eller @googlemail.com?](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [Vad ska jag göra om jag använder Google Workspace?](#what-should-i-do-if-im-a-g-suite-user)

### Vilka appar i Adobe Workfront Fusion påverkas? {#what-apps-in-adobe-workfront-fusion-are-affected}

Google Drive, Gmail och Email (ansluten till Gmail-konto).

### Har jag ett Google Workspace-konto? {#do-i-have-a-g-suite-account}

Om din e-postadress slutar med @gmail.com eller @googlemail.com är ditt konto inte ett Google Workspace-konto. Om ditt Google-konto slutar med en anpassad domän som @my-company.com är det ett Google Workspace-konto.

### Vad ska jag göra om jag använder @gmail.com eller @googlemail.com? {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

Dessa nya begränsningar gäller endast om du integrerar Google Drive eller Gmail. Om du vill ansluta till Google Drive eller Gmail kan du

* Byt till Google Workspace

  eller

* Skapa en anpassad OAuth-klient. Det här alternativet är avsett för avancerade användare.

  Instruktioner finns i [Ansluta Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

Om du vill integrera någon annan tjänst än Google Drive eller Gmail gäller inte dessa begränsningar.

### Vad ska jag göra om jag använder Google Workspace? {#what-should-i-do-if-im-a-g-suite-user}

Det finns ingen nödvändig åtgärd.
