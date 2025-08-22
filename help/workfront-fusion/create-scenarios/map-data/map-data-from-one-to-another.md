---
title: Mappa information från en modul till en annan
description: Mappning är processen att tilldela en moduls utdata, strukturerade till objekt, till en annan moduls indatafält.
author: Becky
feature: Workfront Fusion
exl-id: 1e3f7729-f48e-451e-a90b-d680c9e3bcbc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 0%

---

# Mappa information från en modul till en annan

Mappning är processen att tilldela en moduls utdata till en annan moduls indatafält.

Mappningspanelen visas när du klickar på ett fält där du kan infoga ett värde från en föregående modul i ett scenario.

Du kan också skapa en formel med valfri kombination av funktioner och mappade objekt från mappningspanelen med statisk text som du skriver. Dessa element kan kapslas i varandra.

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
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>[!UICONTROL Ultimate] Workfront: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Mappa ett objekt

När du har skapat en sekvens med moduler genom att länka två eller flera av dem, kan varje modul bearbeta värden för objekt som matats ut av modulerna som föregår den.

Så här tilldelar du utdataobjekt till en moduls indatafält:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill mappa data.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på den modul som ska bearbeta utdata från föregående modul eller moduler.
1. Klicka i ett fält på panelen Modulinställningar där du vill använda värdet för ett objekt som skapats från en föregående modul.

   Mappningspanelen öppnas.

1. (Valfritt) Om du vill söka efter ett visst fält på mappningspanelen klickar du på mappningspanelens sökfält och skriver in den term du vill söka efter. Klicka på fältet när det visas i listan.

   Sökresultaten innehåller söktermen och är inte skiftlägeskänsliga.
1. Om du vill välja ett värde som är ett element i en samling klickar du på pilen bredvid samlingen och markerar sedan elementet när det visas.

   ![Samlingselement](assets/collection-dropdown.png)

1. Klicka på ett objekt på mappningspanelen för att infoga det i fältet.

Mer information finns i [Konfigurera en modul](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md).


## Felsökning

### Problem: Saknade objekt på mappningspanelen

Mappningspanelen visar utdataobjekt från tidigare moduler. Det kan hända att vissa objekt saknas på den här panelen. Du kan köra modulen som saknar utdata i scenarioredigeraren, och mappningspanelen kan sedan inkludera dessa objekt i senare moduler. Den exakta proceduren varierar beroende på modulens typ

* [Direktutlösare](#instant-trigger)
* [Avsökningsutlösare](#polling-trigger)
* [Andra moduler](#other-modules)

#### Direktutlösare

1. Högerklicka på modulen och klicka sedan på **[!UICONTROL Run this module only]** på menyn som visas.

   Eftersom det här är en direktutlösare börjar programmet att leta efter händelser.

1. Skapa händelsen som modulen tittar på.

   Om modulen till exempel är en Workfront > Bevaka händelser-modul som tittar efter uppgiftstilldelningar, loggar du in på Workfront (som en användare som inte är den som Fusion-anslutningen använder) och tilldelar en uppgift.

1. När modulen är klar klickar du på bubblan ovanför modulen för att utforska dess fullständiga utdata.

   Mappningspanelen för senare moduler innehåller nu alla objekt i modulens utdata.

#### Avsökningsutlösare

1. Högerklicka på modulen och klicka sedan på **[!UICONTROL Run this module only]** på menyn som visas.
1. Om det inte finns några utdata klickar du på **[!UICONTROL Choose where to start]** och justerar inställningarna.
1. (Villkorligt) Om det inte finns någon händelse att bearbeta skapar du händelsen som modulen bevakar och upprepar steg 2.

   Om modulen till exempel är en Workfront > Bevakade poster-modul som bevakar uppgifter, loggar du in på Workfront (som en användare som inte är den som Fusion-anslutningen använder) och tilldelar en uppgift. Kör sedan modulen igen.

1. När modulen är klar klickar du på bubblan ovanför modulen för att utforska dess fullständiga utdata.

   Mappningspanelen för senare moduler innehåller nu alla objekt i modulens utdata.

#### Andra moduler

Du kan välja att köra:

* Hela scenariot (eller bara den del som innehåller modulen)
* Den enda modulen

Så här kör du en enskild modul:

1. Högerklicka på modulen och klicka sedan på **[!UICONTROL Run this module only]** på menyn som visas.
1. Ange exempelvärden för indataobjekten och klicka sedan på **[!UICONTROL OK]**.
1. När modulen är klar klickar du på bubblan ovanför modulen för att utforska dess fullständiga utdata.

   Mappningspanelen för senare moduler innehåller nu alla objekt i modulens utdata.
