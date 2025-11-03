---
title: Qualtrics-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Qualtrics samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 80b441b7-c808-4c4f-b9ff-d614650dbb73
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Qualtrics-moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Qualtrics] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

Du måste ha ett [!DNL Qualtrics]-konto för att kunna använda [!UICONTROL Qualtrics]-moduler.

## Information om Qualtrics API

Qualtrics-kopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://{{connection.dataCenterCode}}.qualtrics.com/API/v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.1.1</td> 
  </tr>
 </tbody> 
 </table>

## Ansluter [!DNL Qualtrics] till Workfront Fusion

Du kan skapa en anslutning till ditt [!DNL Qualtrics]-konto direkt inifrån en [!UICONTROL Qualtrics]-modul.

1. Klicka på [!UICONTROL Qualtrics] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Ange följande information:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>Ange ett namn för den nya anslutningen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Data Center ID] </td> 
      <td>Använd formatet <code>&lt;Data Center ID>.qualtrics.com</code>.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td>Information om hur du hittar API-nyckeln finns i dokumentationen för [!DNL Qualtrics].</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Qualtrics]-moduler och deras fält

Följande moduler är tillgängliga för [!DNL Qualtrics]-anslutningen:

* [!UICONTROL Watch New Survey Response]
* [!UICONTROL Create a Directory Contact]
* [!UICONTROL Delete a Directory Contact]
* [!UICONTROL Get a Directory Contact]
* [!UICONTROL Update a Directory Contact]
* [!UICONTROL Create a New Survey Distribution via SMS]
* [!UICONTROL Distribute a Survey via Email]
* [!UICONTROL Make an API call]
* [!UICONTROL List Directory Contacts]
