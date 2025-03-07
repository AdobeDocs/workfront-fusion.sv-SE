---
title: Använd ömsesidig TLS i HTTP-moduler i Adobe Workfront Fusion
description: Du kan använda Mutual TLS i dina Adobe Workfront Fusion HTTP-moduler, vilket gör att båda sidor av informationstransaktionen kan verifiera den andres identitet.
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: 1fa1ef68267d971a2769400a031b333de2f684ce
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---

# Använd ömsesidig TLS i HTTP-moduler i [!DNL Adobe Workfront Fusion]

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Tillhandahåller ditt offentliga certifikat för [!DNL Workfront Fusion]

När du ansluter till en webbtjänst med en HTTP-begäran kräver webbtjänsten vanligtvis ett [!DNL Workfront Fusion] offentligt certifikat för verifiering. Detta gör att webbtjänsten kan jämföra det certifikat som anges i HTTP-begäran med det som finns tillgängligt, för att säkerställa att certifikatet finns på webbtjänstens tillåtelselista.

Instruktioner om hur du överför det offentliga certifikatet [!DNL Adobe Workfront Fusion] till en webbtjänst finns i webbtjänstens dokumentation.

>[!NOTE]
>
>Du kan behöva ange annan information utöver certifikatet. Information om vad en webbtjänst kräver finns i webbtjänstens API-dokumentation.

Du kan använda följande länkar för att hämta Workfront Fusion offentliga certifikat:

### Certifikat för 23 april 2024-7 maj 2025

>[!IMPORTANT]
>
>* Dessa [!DNL Workfront Fusion] offentliga certifikat upphör att gälla den 7 maj 2025. När ditt certifikat har upphört att gälla måste du överföra ett nytt certifikat till webbtjänsten. Vi rekommenderar att du:
>
>   * Notera förfallodatumet och ange en påminnelse för dig själv om att överföra certifikatet till din webbtjänst.
>   * Bokmärk den här sidan för att enkelt hitta nya certifikat.
>
>* Dessa är mTLS-certifikat som inte är jokertecken.

* [Hämta [!DNL Workfront Fusion] certifikat 2023](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem)
* [Hämta [!DNL Workfront Fusion] EU-certifikat 2023](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem)

  För användning i EU


## Aktivera Ömsesidig TLS i [!DNL Workfront Fusion] HTTP-moduler

Alla [!DNL Workfront Fusion] [!UICONTROL HTTP]-förfrågningsmoduler har möjlighet att aktivera ömsesidigt TLS.

Så här aktiverar du Ömsesidig TLS i en [!UICONTROL HTTP]-begärandemodul:

1. Lägg till en [!UICONTROL HTTP]-begärandemodul i ditt scenario.
1. Börja konfigurera modulen.

   Instruktioner om hur du konfigurerar en [!UICONTROL HTTP]-begärandemodul finns i lämplig artikel under [Universella anslutningar](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors).

1. Aktivera **[!UICONTROL Show advanced settings]** längst ned i modulen.
1. Aktivera **[!UICONTROL Use Mutual TLS]**.
