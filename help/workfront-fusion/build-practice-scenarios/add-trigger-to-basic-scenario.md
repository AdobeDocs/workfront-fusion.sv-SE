---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Lägga till en utlösarmodul i ett grundläggande scenario
description: Lär dig hur du lägger till en utlösarmodul så att scenariot regelbundet kan söka efter nya begäranden och konvertera dem till projekt.
author: Becky
feature: Workfront Fusion
exl-id: cd8ac958-b7a6-4536-89d8-c79a2f8940a6
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Lägga till en utlösarmodul i ett grundläggande scenario

Utlösarmoduler placeras i början av ett scenario. Dessa moduler startar en scenariokörning när en viss tjänst har ändrats. Ändringen kan vara att skapa nya poster, ta bort poster, uppdatera poster och så vidare. Du anger villkoren för de ändringar som börjar scenen.

Avsökningsmoduler kontrollerar tjänsten vid ett angivet tidsintervall och returnerar information om ändringar som gjorts under det tidsintervallet. Om inga ändringar har gjorts körs inte scenariot av utlösaren.

I det här exemplet lägger du till en utlösarmodul som körs var 15:e minut och startar ett scenario om någon begäran har skickats till en viss kö. Scenariot konverterar sedan dessa begäranden till ett projekt.

I det här exemplet ändras scenariot som skapades i [Skapa ett grundläggande scenario](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

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

## Lägga till och konfigurera utlösarmodulen

### Lägg till utlösarmodulen

1. Öppna scenariot i scenarioredigeraren.
1. Högerklicka på den första (sökmodulen) och välj **Ta bort modul**.

   Modulen tas bort och en tom platshållare lämnas kvar.

1. Klicka på den tomma modulen och välj **Adobe Workfront** i listan med program.
1. Välj **Bevakade poster**.
1. Se till att modulen använder samma anslutning som resten av modulerna i scenariot.
1. Välj **Utgåva** i fältet Posttyp.
1. Välj **Endast nya poster** i fältet Filter.
1. I rutan Utdata väljer du `ID`, `Name` och `Project ID`.
1. Klicka på **OK** om du vill spara modulinställningarna.

   Ett fönster med namnet Välj var du vill starta visas.

1. Välj **Från och med nu**.

### Schemalägg utlösarmodulen

1. Klicka på klockan i modulen Bevakade poster.

   Fönstret Schemainställningar öppnas.

1. I fältet Kör scenario väljer du **Med regelbundna intervall**.

1. Klicka på **OK**.

### Uppdatera den andra modulen

Eftersom den första modulen har ersatts måste den andra modulen mappas till den nya första modulen.

1. Öppna objektmodulen Konvertera.
1. Ta bort det svarta ID-blocket i fältet Problem ID. Blocket är svart eftersom modulen som det mappades från inte längre är tillgänglig.
1. Markera ID-blocket under den första modulen (bevakade poster) för att mappa det till den andra modulen.
1. Klicka på **OK**.

### Testa och aktivera

1. Gå till den Workfront-miljö som Fusion ansluter till och lägg till ett problem.
1. Klicka på **[!UICONTROL Run once]** i det nedre vänstra hörnet i scenarioredigeraren.
1. Granska utdata för att kontrollera att scenariot kördes som förväntat.
1. När du är säker på att scenariot fungerar som förväntat klickar du på växeln **Schemaläggning** längst ned till vänster på skärmen till **På**.

   Detta aktiverar scenariot.
1. I [!DNL Workfront Fusion] klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.

   >[!IMPORTANT]
   >
   >Spara ofta när du finslipar ett scenario.

## Resurs

* Mer information om utlösarmoduler finns i [Utlösarmoduler](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) i översikten över artikelmoduler.
