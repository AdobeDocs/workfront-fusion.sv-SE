---
title: Hanterade SDL-översättningsmoduler
description: I ett Adobe Workfront Fusion-scenario kan du ansluta ditt SDL Managed Translation-konto till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 41953b04-9011-4ddb-9f53-cdf11e807e04
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# [!DNL SDL Managed Translation] moduler

I ett Adobe Workfront Fusion-scenario kan du ansluta ditt [!DNL SDL Managed Translation]-konto till flera tredjepartsprogram och -tjänster.

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

## Information om hanterat översättnings-API för SDL

SDL Managed Translation Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://languagecloud.sdl.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.4.26</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL SDL Managed Translation] moduler

>[!NOTE]
>
>Tidsgränsen för åtgärden för anrop till [!DNL SDL Managed Translation] är **120 sekunder**.

### Filer

#### [!UICONTROL Download Translated File]

Den här modulen hämtar innehållet i en översatt fil, som finns i det angivna projektet. Om den begärda filen ännu inte är i läget Nedland kanske inte innehållet i filen är fullständigt översatt. Om filen är i hämtningsstatus och du har hämtat den måste du markera filen som slutförd med metoden `Cancel or Complete File`.

#### [!UICONTROL Upload a File]

Den här modulen tillåter överföring av filer för översättning eller för inkludering i ett översättningsprojekt som referensmaterial. Överföringar måste skickas in med multipart/form-data och kan innehålla mer än en fil. Du anger `ProjectOptionId` som ska användas för att utvärdera de överförda filerna. Detta avgör om varje fil som du överför är en möjlig kandidat för översättning eller måste hanteras som referensmaterial. När det gäller arkiv (`zip `, `rar`, `7z`, `tar` filer) undersöker programmet innehållet i arkivet och anger om arkivet som helhet kan översättas eller om det innehåller en blandning av översättningsbara och icke-översättningsbara filer.

>[!NOTE]
>
>Vi rekommenderar inte att du överför mer än en fil åt gången eftersom det kan öka effekten av eventuella fel.

#### [!UICONTROL Add a Reference File]

Den här modulen lägger till en referensfil.

### Projekt

#### [!UICONTROL Create a project]

Den här modulen skapar det angivna projektet.

#### Avbryt eller slutföra ett projekt

Den här modulen avbryter eller slutför det angivna projektet. Om projektet väntar på att laddas ned, kommer projektet att gå igenom de sista stegen i arbetsflödet och slutligen fortsätta. Om projektet väntar på godkännande eller om leverantörsvalet avbryts. Om projektet har någon annan status kommer begäran att misslyckas.

#### [!UICONTROL Download Project Zip]

Den här modulen hämtar filen `zip` med översatta filer för det angivna projektet.

#### [!UICONTROL Read a Project]

Modulen hämtar det angivna projektet.

#### [!UICONTROL Get Projects at Status]

Den här modulen hämtar alla tillgängliga projekt med den angivna statusen. Den här metoden tillåter att resultaten växlas genom att ange frågeparametrarna `$top`, `$skip` och `$orderby`.

#### [!UICONTROL Get Projects List]

Hämtar en enkel lista över alla projekt, med allmän information om varje projekt. Den här metoden tillåter att resultaten blir sidor genom att ange frågeparametrarna `$top`, `$skip` och `$orderby`.

#### [!UICONTROL Search Project Creation Options]

Den här modulen hämtar alternativ för att skapa projekt.

### Övriga

#### [!UICONTROL Make an API Call]

Den här modulen utför ett godtyckligt auktoriserat API-anrop.
