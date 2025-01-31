---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Lägga till ett filter i ett grundscenario
description: Med filter kan du kontrollera att ditt scenario bara utvecklas om vissa villkor uppfylls.
author: Becky
feature: Workfront Fusion
exl-id: 78ab27fe-e2dd-4b52-b986-77b4b7ea3b5e
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Lägga till ett filter i ett grundscenario

Med filter kan du kontrollera att ditt scenario bara utvecklas om vissa villkor uppfylls.

I det här exemplet lägger du till ett filter i ditt scenario som tillåter att ett nytt projekt skapas från en begäran endast om begäran skickades till en viss begärandekö.

I det här exemplet ändras scenariot som skapades i [Skapa ett grundläggande scenario](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

>[!NOTE]
>
>Workfront utlösarmoduler innehåller filter som tillåter att ett scenario startar endast om vissa villkor uppfylls. Men eftersom filter mellan moduler används för alla icke-utlösande och icke-Workfront-användningsfall är det viktigt att du lär dig hur du använder filter mellan moduler. I det här exemplet används ett mellanmodulsfilter för funktioner som kan uppfyllas med ett in-modul-filter.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> <p>Nytt: [!UICONTROL Standard]</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront]: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste skapa scenariot som beskrivs i [Skapa ett grundläggande scenario](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) innan du följer den här proceduren.

## Lägga till ett filter

### Förbered för att lägga till filtret

1. Öppna scenariot.
1. Klicka på den första modulen för att öppna den.
1. Välj `Project` i området **Utdata**.
Du bör nu ha `ID`, `Name` och `Project` markerat.
1. Klicka på OK för att spara modulinställningarna.
1. Öppna Workfront.
1. I Workfront letar du reda på det projekt som representerar begärandekön som Fusion-scenariot ska användas med.

   Det här projektet måste finnas på samma Workfront-konto som Fusion-anslutningen är konfigurerad för.

1. Anteckna projekt-ID:t i URL:en.

   Exempel: https://\&lt;MyDomain\>.my.workfront.com/project/\&lt;ProjectID\>/tasks

### Lägg till och konfigurera filtret

1. Återgå till scenariot i scenarioredigeraren.
1. Klicka på skiftnyckelsikonen ![skiftningsikonen](assets/wrench-icon.png) mellan den första och den andra modulen och välj **Konfigurera ett filter**.
1. I fältet Etikett anger du en etikett för det här filtret, till exempel &quot;Filter för begärandekö&quot;.
1. Mappa `projectID` från den första modulen i det övre fältet i området **Villkor**.

   ![Mappa projekt-ID](assets/map-proj-id.png)
1. Låt operatorn **Villkor** vara lika med.
1. Klistra in det projekt-ID som du antecknade från projekt-URL:en i [Förbered för att lägga till filtret](#prepare-to-add-the-filter) i det nedre fältet i området **Villkor**.
1. Klicka på **OK** om du vill spara filterinställningarna.

### Testa och aktivera

1. Gå till den Workfront-miljö som Fusion ansluter till och lägg till ett fel i projektet som du angav i filtret. Lägg till ytterligare ett problem i ett annat projekt.
1. Klicka på **[!UICONTROL Run once]** i det nedre vänstra hörnet i scenarioredigeraren.
1. Granska utdata för att kontrollera att scenariot kördes som förväntat.

   Båda utgåvorna ska visas i utdata från den första modulen, men bara utgåvan i det angivna projektet ska visas som indata i den andra modulen.
1. När du är säker på att scenariot fungerar som förväntat klickar du på växeln **Schemaläggning** längst ned till vänster på skärmen till **På**.

   Detta aktiverar scenariot.
1. I [!DNL Workfront Fusion] klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.

   >[!IMPORTANT]
   >
   >Spara ofta när du finslipar ett scenario.

## Resurs

* Mer information om filter finns i [Lägga till ett filter i ett scenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).
