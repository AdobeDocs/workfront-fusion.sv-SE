---
title: Anslut Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient
description: Du kan använda Adobe Workfront Fusion för att ansluta till Google Services med en anpassad OAuth-klient. Den här proceduren kräver ett befintligt Google-konto.
author: Becky
feature: Workfront Fusion
exl-id: 2f0bc289-4ecf-4a31-9d7b-641bbca6fc95
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 0%

---

# Anslut Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient

Du kan använda Adobe Workfront Fusion för att ansluta till Google Services med en anpassad OAuth-klient. Den här proceduren kräver ett befintligt Google-konto.

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

Du behöver ett befintligt Google-konto för att kunna ansluta.

## Anslut Fusion till Google-tjänster med en anpassad OAuth-klient

Om du vill skapa den här anslutningen måste du skapa och konfigurera ett projekt på Google Cloud-plattformen och sedan konfigurera anslutningen i Fusion baserat på det projektet.

>[!NOTE]
>
>Detta förfarande är avsett för
>
>* Personlig användning (`@gmail.com` och `@googlemail.com` användare)
>* Intern användning (Google Workspace-användare som föredrar att använda en anpassad OAuth-klient)

* [Skapa ett projekt på Google Cloud Platform](#create-a-project-on-google-cloud-platform)
* [Konfigurera inställningar för OAuth-medgivande](#configure-oauth-consent-settings)
* [Skapa OAuth-autentiseringsuppgifter](#create-oauth-credentials)
* [Ansluta till Google i Workfront Fusion](#connect-to-google-in-workfront-fusion)

### Skapa ett projekt på Google Cloud Platform

Så här skapar du ett projekt på Google Cloud Platform:

1. Börja skapa ett projekt på Google Cloud Platform.

   Instruktioner finns i [Skapa ett Google Cloud-projekt](https://developers.google.com/workspace/guides/create-project) i Google-dokumentationen.
1. När du aktiverar API:er måste du aktivera Google Drive API samt API:t för alla Google-program som du vill använda (till exempel Google Sheets API).
1. Slutför projektet.
1. Fortsätt till avsnittet [Konfigurera inställningar för OAuth-medgivande](#configure-oauth-consent-settings) i den här artikeln.

### Konfigurera inställningar för OAuth-medgivande

1. Börja konfigurera OAuth för ditt projekt

   Instruktioner finns i [Konfigurera OAuth-medgivandeskärmen och välj omfattningar](https://developers.google.com/workspace/guides/configure-oauth-consent) i Google-dokumentationen.
1. Välj **Extern** och klicka sedan på **Skapa**.

   >[!NOTE]
   >
   >Du debiteras inte när du väljer det här alternativet. Mer information finns i Google information om undantag från verifieringskraven.

1. Fyll i de obligatoriska fälten enligt följande:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>Programnamn</p> </td> 
      <td> <p>Ange namnet på den app som begär samtycke.</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>Adobe Workfront Fusion </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">E-post till användarsupport</td> 
      <td>Ange en e-postadress dit användare kan kontakta dig med frågor om deras samtycke när de ansluter till den här appen.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">E-postadresser</td> 
      <td>Ange en eller flera e-postadresser som Google kan använda för att meddela dig om ändringar i projektet.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **Lägg till domän** under Godkända domäner och ange `workfrontfusion.com`.
1. Lägg till följande omfattningar:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>Service/API</th> 
      <th>Obligatoriska omfattningar</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td> <p>Gmail</p> </td> 
      <td> <p>https://mail.google.com/</p> <p>https://www.googleapis.com/auth/gmail.labels</p> <p>https://www.googleapis.com/auth/gmail.send</p> <p>https://www.googleapis.com/auth/gmail.readonly</p> <p>https://www.googleapis.com/auth/gmail.compose</p> <p>https://www.googleapis.com/auth/gmail.insert</p> <p>https://www.googleapis.com/auth/gmail.modify</p> <p>https://www.googleapis.com/auth/gmail.metadata</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Google Drive</p> </td> 
      <td> <p>https://www.googleapis.com/auth/drive</p> <p>https://www.googleapis.com/auth/drive.readonly</p> </td> 
     </tr> 
    </tbody> 
   </table>

   Du kan behöva utöka listan eller gå till nästa sida i listan för att se alla.

1. (Valfritt) Lägg till testanvändare i projektet.
1. Granska informationen och klicka sedan på **Tillbaka till instrumentpanelen**.

   >[!NOTE]
   >
   >Du behöver inte skicka in ditt samtycke-skärm och din ansökan för verifiering från Google.

1. Fortsätt till [Skapa OAuth-autentiseringsuppgifter](#create-oauth-credentials).

### Skapa OAuth-autentiseringsuppgifter

1. Börja skapa autentiseringsuppgifter för OAuth-klient-ID.

   Instruktioner finns i [Skapa autentiseringsuppgifter för åtkomst](https://developers.google.com/workspace/guides/create-credentials) i Google-dokumentationen.

   >[!NOTE]
   >
   >Om detta inte är det första API:t eller tjänsten (Gmail eller Google Drive) som du har aktiverat behöver du inte skapa nya autentiseringsuppgifter.

1. Fyll i de obligatoriska fälten enligt följande:

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Programtyp</td> 
      <td> <p> Webbprogram</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Namn</td> 
      <td>Workfront Fusion </td> 
     </tr> 
    </tbody> 
   </table>

1. Ange **ett** av följande under auktoriserade omdirigerings-URI:er:

   * För Gmail eller Google Drive: `https://app.workfrontfusion.com/oauth/cb/google-restricted`

   * För andra Google-appar: `https://app.workfrontfusion.com/oauth/cb/google`

1. Klicka på **Skapa**.

   Klient-ID och Klienthemlighet visas.

1. Kopiera klient-ID och klienthemlighet till en säker plats. Du kommer att använda dem för att skapa en anslutning i Workfront Fusion.
1. Fortsätt till [Anslut till Google i Workfront Fusion](#connect-to-google-in-workfront-fusion).

### Ansluta till Google i Workfront Fusion

Hur du skapar en anslutning till Google varierar beroende på om du använder en modul från en Google-tjänst (till exempel Google Sheets eller Google Docs) eller om du ansluter till Google via HTTP >Gör en OAuth2.0-begärandemodul.

* [Ansluta till Google i en Google-tjänst](#connect-to-google-in-a-google-service)
* [Anslut till Google via HTTP > Gör en OAuth2.0-begärandemodul](#connect-to-google-in-the-http--make-an-oauth20-request-module)

#### Ansluta till Google i en Google-tjänst

1. I Workfront Fusion letar du reda på den Google-modul som du behöver för att skapa en anslutning.
1. Klicka på **Skapa en anslutning** och sedan på **Visa avancerade inställningar**.
1. Fyll i fälten Anslutningsnamn, Miljö och Typ.
1. Ange klient-ID och klienthemlighet som du hämtade i [Skapa OAuth-autentiseringsuppgifter](#create-oauth-credentials) i respektive fält och klicka sedan på **Fortsätt**.

1. Logga in med ditt Google-konto.

   Fönstret **Den här appen är inte verifierat**. Observera att &quot;app&quot; som omnämns i fönstertiteln är OAuth-klienten som du skapade ovan.

1. Klicka på **Avancerat** och sedan på **Gå till Workfront Fusion (osäkert)** för att tillåta åtkomst med din anpassade OAuth-klient.

1. Klicka på **Tillåt** för att bevilja Workfront Fusion-behörighet.
1. I fönstret som visas klickar du på **Tillåt** igen för att bekräfta dina val.

   Anslutningen till den önskade Google-tjänsten med en anpassad OAuth-klient har upprättats.

#### Anslut till Google via HTTP > Gör en OAuth2.0-begärandemodul {#connect-to-google-in-the-http--make-an-oauth20-request-module}

Instruktioner om hur du ansluter till Google i HTTP > Gör en OAuth2.0-begärandemodul finns i [Instruktioner för hur du skapar en anslutning till Google i HTTP > Skapa en OAuth 2.0-begärandemodul](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module) i artikeln HTTP > Skapa en OAuth 2.0-begärandemodul.

## Möjligt felmeddelande:[403 Åtkomst inte konfigurerad]

Om felmeddelandet `403 Access Not Configured` visas måste du aktivera motsvarande API i din Google Cloud-plattform. Om du vill aktivera API:t följer du stegen i avsnittet [Skapa ett projekt på Google Cloud-plattformen](#create-a-project-on-google-cloud-platform) i den här artikeln.
