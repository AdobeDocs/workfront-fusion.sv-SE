---
title: Använd ömsesidig TLS i HTTP-moduler i Adobe Workfront Fusion
description: Du kan använda Mutual TLS i dina Adobe Workfront Fusion HTTP-moduler, vilket gör att båda sidor av informationstransaktionen kan verifiera den andres identitet.
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# Använd ömsesidig TLS i HTTP-moduler i [!DNL Adobe Workfront Fusion]

>[!NOTE]
>
>Adobe Workfront Fusion kräver en [!DNL Adobe Workfront Fusion]-licens förutom en Adobe Workfront-licens.

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
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
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

&#42;Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

&#42;&#42;Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)

## Tillhandahåller ditt offentliga certifikat för [!DNL Workfront Fusion]


När du ansluter till en webbtjänst med en HTTP-begäran kräver webbtjänsten vanligtvis ett [!DNL Workfront Fusion] offentligt certifikat för verifiering. Detta gör att webbtjänsten kan jämföra det certifikat som anges i HTTP-begäran med det som finns tillgängligt, för att säkerställa att certifikatet finns på webbtjänstens tillåtelselista.

Instruktioner om hur du överför det offentliga certifikatet [!DNL Adobe Workfront Fusion] till en webbtjänst finns i webbtjänstens dokumentation.

>[!NOTE]
>
>Du kan behöva ange annan information utöver certifikatet. Information om vad en webbtjänst kräver finns i webbtjänstens API-dokumentation.

Du kan använda följande länkar för att hämta Workfront Fusion offentliga certifikat:

### Certifikat för 23 april 2023-7 maj 2024

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

<!--

### Certificates for November 14, 2022 - July 15, 2023

>[!IMPORTANT]
>
>* These [!DNL Workfront Fusion] public certificates expire on July 15, 2023.
>* These are wildcard mTLS certificates.

* [Download [!DNL Workfront Fusion] Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion+2.0+public+certificates/app_workfrontfusion_com-jul-15-2023+updated.cer)
* [Download [!DNL Workfront Fusion] EU Certificate 2023](https://cdn.experience.workfront.com/Documentation/Workfront+Fusion/app-eu_workfrontfusion_com-jul-15-2023.cer)

   For use in the EU 

   -->

## Aktivera Ömsesidig TLS i [!DNL Workfront Fusion] HTTP-moduler

Alla [!DNL Workfront Fusion] [!UICONTROL HTTP]-förfrågningsmoduler har möjlighet att aktivera ömsesidigt TLS.

Så här aktiverar du Ömsesidig TLS i en [!UICONTROL HTTP]-begärandemodul:

1. Lägg till en [!UICONTROL HTTP]-begärandemodul i ditt scenario.
1. Börja konfigurera modulen.

   <!--For instructions on configuring an [!UICONTROL HTTP] request module, see the appropriate article under [[!UICONTROL Universal connectors] modules](/help/workfront-fusion/references/apps-and-modules/universal-connectors/).-->

1. Aktivera **[!UICONTROL Show advanced settings]** längst ned i modulen.
1. Aktivera **[!UICONTROL Use Mutual TLS]**.
