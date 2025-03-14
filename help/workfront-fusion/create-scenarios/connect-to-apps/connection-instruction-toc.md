---
title: Skapa anslutningar
description: En anslutning måste uppfylla de krav som anges i API:t för det program eller den webbtjänst den ansluter till. Instruktionerna för hur du konfigurerar en anslutning varierar därför beroende på programmet eller webbtjänsten. Den här artikeln kan hjälpa dig att identifiera och hitta instruktionerna för att ansluta [!DNL Adobe Workfront Fusion] till den app eller webbtjänst du valt.
author: Becky
feature: Workfront Fusion
exl-id: 281403a6-6f88-4976-8a10-1d0848ef9b35
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# Skapa anslutningar

En anslutning måste uppfylla de krav som anges i API:t för det program eller den webbtjänst den ansluter till. Instruktionerna för hur du konfigurerar en anslutning varierar därför beroende på programmet eller webbtjänsten. Den här artikeln kan hjälpa dig att identifiera och hitta instruktionerna för att ansluta [!DNL Adobe Workfront Fusion] till den app eller webbtjänst du valt.

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

## Anslut till ett program eller en webbtjänst som inte kräver konfiguration

I de flesta fall kan du använda modulen för att skapa en anslutning med liten eller ingen extra information. [!DNL Workfront Fusion] hanterar autentiseringen automatiskt.

Instruktioner om hur du skapar en anslutning utan att göra några speciella justeringar finns i [Skapa en anslutning - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md).

## Ansluta till en app eller tjänst från Adobe

Om du vill ansluta till en app eller tjänst från Adobe kan du behöva information från Adobe Admin Console, till exempel ditt Org ID eller ditt tekniska konto-ID.

Du kan också använda Adobe Authenticator-modulen för att ansluta till ett Adobe-API med en enda anslutning. Det gör det enklare att ansluta till Adobe-produkter som ännu inte har någon dedikerad Fusion-anslutning.

Mer information finns i [artikeln för anslutningen](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-adobe-products).

## Anslut till ett [!DNL Microsoft]-program eller en webbtjänst

I de flesta av [!DNL Microsoft]-apparna i [!DNL Workfront Fusion] kan du skapa en anslutning utan extra information.

Följande omständigheter kräver extra steg för att skapa en anslutning:

* Använda Microsoft Dynamics 365-moduler.

  Instruktioner finns i [Microsoft Dynamics 365-moduler](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md).

* Ansluta till Microsoft Graph API med en HTTP-modul

  Instruktioner finns i [Anropa MS Graph REST API](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md).

## Anslut till ett [!DNL Google]-program eller en webbtjänst

Hur du ansluter till [!DNL Google]-appar kan variera beroende på vilken typ av [!DNL Google]-konto du använder. Dessutom kan [!DNL Google]-säkerhetsåtgärder kräva extra konfiguration när du ansluter till [!DNL Workfront Fusion].

Mer information finns i:

* [Anslut Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)
* [Koppla Adobe Workfront Fusion till Google Services med uppdaterade säkerhetsfunktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-google-with-new-security-measures.md)

## Andra program som kräver ytterligare konfiguration

Vissa appar och tjänster följer inte den grundläggande konfigurationen för [!DNL Workfront Fusion]-anslutningar. Du hittar instruktioner om hur du ansluter de här apparna i artikeln för den appen.

Mer information finns i [artikeln för anslutningen](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-third-party-applications).
