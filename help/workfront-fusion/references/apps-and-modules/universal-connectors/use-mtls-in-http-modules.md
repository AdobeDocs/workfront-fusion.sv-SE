---
title: Använd ömsesidig TLS i HTTP-moduler i Adobe Workfront Fusion
description: Du kan använda Mutual TLS i dina Adobe Workfront Fusion HTTP-moduler, vilket gör att båda sidor av informationstransaktionen kan verifiera den andres identitet.
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Använd ömsesidig TLS i HTTP-moduler i Adobe Workfront Fusion

## Översikt över Ömsesidig TLS

När du skickar data via Internet är det viktigt att se till att de kommer till eller kommer från rätt plats och att bara den avsedda mottagaren kan läsa dem. När TLS är aktiverat använder klienten (dator som begär information) certifikat för att verifiera serverns identitet (dator som tillhandahåller information). Detta gör säkra HTTP-anslutningar.

Med ömsesidig TLS kan den här identitetsbekräftelsen användas på båda sätt. När servern skickar sitt certifikat för att verifiera sin identitet till klienten, begär den även klientens certifikat. Detta garanterar att servern inte skickar information till en plats eller användare som skulle missbruka den.

>[!INFO]
>
>**Exempel:**
>
>* **TLS**: När en person skriver &quot;MyGreatBank.com&quot; i en webbläsare vill de vara säkra på att de går till My Great Bank, inte till en webbplats som kan missbruka eller sälja sin bankinformation. De vill också vara säkra på att deras bankkontoinformation är krypterad.
>
>   När webbläsaren (klienten) ansluter till MyGreatBank.com (servern) kräver TLS ett certifikat från MyGreatBank.com för att verifiera dess identitet. Certifikatet tillhandahålls av en certifikatutfärdare som [!DNL DigiCert] eller [!DNL Thawte]. Eftersom webbläsaren litar på certifikatutfärdaren tillåts anslutningen.
>
>* **Ömsesidig TLS**: MySoftware.com är en programvaruklient som behöver information från MyGreatBank.com API. MyGreatBank tillåter bara betrodda klienter att ansluta till sina servrar. Förutom den vanliga TLS-verifieringen av identiteten för MyGreatBank.com verifierar TLS/certifikatutfärdare även begäran från MySoftware.com.

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

## Ange ditt offentliga certifikat för Workfront Fusion

När du ansluter till en webbtjänst med en HTTP-begäran kräver webbtjänsten vanligtvis ett offentligt Workfront Fusion-certifikat för verifiering. Detta gör att webbtjänsten kan jämföra det certifikat som anges i HTTP-begäran med det som finns tillgängligt, för att säkerställa att certifikatet finns på webbtjänstens tillåtelselista.

Instruktioner om hur du överför det offentliga certifikatet för Adobe Workfront Fusion till en webbtjänst finns i webbtjänstens dokumentation.

>[!NOTE]
>
>Du kan behöva ange annan information utöver certifikatet. Information om vad en webbtjänst kräver finns i webbtjänstens API-dokumentation.

Du kan använda följande länkar för att hämta Workfront Fusion publika certifikat. Information om hur du hittar ditt datacenter finns i [Identifiera ditt datacenter](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md) i artikeln Konfigurera IP-adresser för Fusion på organisationens tillåtelselista.

### Certifikat för 2025

>[!IMPORTANT]
>
>* Dessa offentliga Workfront Fusion-certifikat upphör att gälla den **4 april 2026** (USA och EU) eller den **2 november 2025** (Azure). När ditt certifikat har upphört att gälla måste du överföra ett nytt certifikat till webbtjänsten. Vi rekommenderar att du:
>
>   * Notera förfallodatumet och ange en påminnelse för dig själv om att överföra certifikatet till din webbtjänst.
>   * Bokmärk den här sidan för att enkelt hitta nya certifikat.
>
>* Dessa är mTLS-certifikat som inte är jokertecken.

| Datacenter | Hämta länk | Giltiga datum |
|---|---|---|
| Amerikanskt datacenter | [Hämta Workfront Fusion US-certifikat 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-us-mtls-certificate.pem) | 3 mars 2025-4 april 2026 |
| EU Datacenter | [Hämta Workfront Fusion EU Certificate 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-eu-mtls-certificate.pem) | 3 mars 2025-4 april 2026 |
| Azure-kluster | [Hämta Workfront Fusion Azure Certificate 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-az-mtls-certificate.pem) | 24 oktober 2024-25 november 2025 |

<!--

### Certificates for 2024

>[!IMPORTANT]
>
>* We recommend installing the certificates for 2025, available above.
>* These Workfront Fusion public certificates expire on **May 7, 2025**. After yours expires you will need to upload a new certificate to the web service. We recommend that you:
>
>   * Make note of the expiration date and set a reminder for yourself to upload the certificate to your web service.
>   * Bookmark this page to easily find the new certificates.
>
>* These are non-wildcard mTLS certificates.

| Datacenter | Download link | Dates valid |
|---|---|---|
| US Datacenter | [Download Workfront Fusion Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |
| EU Datacenter | [Download Workfront Fusion EU Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |

-->

## Aktivera Ömsesidig TLS i Workfront Fusion HTTP-moduler

Alla begärandemoduler för Workfront Fusion [!UICONTROL HTTP] har möjlighet att aktivera ömsesidigt TLS.

Så här aktiverar du Ömsesidig TLS i en [!UICONTROL HTTP]-begärandemodul:

1. Lägg till en [!UICONTROL HTTP]-begärandemodul i ditt scenario.
1. Börja konfigurera modulen.

   Instruktioner om hur du konfigurerar en [!UICONTROL HTTP]-begärandemodul finns i lämplig artikel under [Universella anslutningar](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors).

1. Aktivera **[!UICONTROL Show advanced settings]** längst ned i modulen.
1. Aktivera **[!UICONTROL Use Mutual TLS]**.
