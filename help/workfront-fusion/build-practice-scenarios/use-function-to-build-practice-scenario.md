---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Använda en funktion för att uppdatera ett projekt i ett grundläggande scenario
description: Lär dig hur du lägger till en funktion för att uppdatera en arbetsuppgift i Workfront.
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
source-git-commit: 8884aef2237ad358c774110b81ac17b9efb386d4
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Använda en funktion för att uppdatera ett projekt i ett grundläggande scenario

Att uppdatera en arbetsuppgift från Workfront är ett vanligt användningsområde för Workfront Fusion. I det här exemplet använder du en funktion för att ändra namnet på ett projekt till versaler.

Fusion innehåller många typer av funktioner som gör att du kan omvandla och utföra villkorsstyrd logik på dina data. Mer information om hur du använder funktioner finns i [Funktionsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md).

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

## Uppdatera ett projekt med en funktion

### Lägg till modulen Uppdatera post i ditt scenario

1. Öppna scenariot i scenarioredigeraren.
1. Håll pekaren över den partiella cirkeln till höger om den andra modulen och klicka sedan på **[!UICONTROL Add another module]**.
1. Välj [!DNL Adobe Workfront] i listan med program och välj sedan modulen **[!UICONTROL Update Record]**.
1. I fältet ID markerar du det ID-block som finns under objektmodulen Konvertera. Detta är ID:t för det projekt som skapades av den modulen.

   ![ID från Konvertera objekt](assets/id-convert-object.png)

1. Välj Projekt i fältet Posttyp eftersom objektet som ska uppdateras är ett projekt.
1. Välj Namn i området Välj fält att mappa.

   Ett namnfält öppnas.
1. Fortsätt till [Mappa funktionen för namnuppdateringen](#map-the-function-for-the-name-update).

### Mappa funktionen för namnuppdatering

När det här scenariot konverterar en begäran till ett projekt är projektets namn detsamma som begäran. Funktionen här har det namnet och alla bokstäver i det får en inledande versal.

1. Klicka på fältet **Namn**.

   Mappningspanelen öppnas.
1. Klicka på ikonen **Text och binära funktioner** på mappningspanelen. ![Ikon för textfunktioner](assets/toolbar-icon-text&binary-functions.png)
1. Markera funktionen **upper**.

   Funktionen visas i fältet Namn, inklusive formateringen för de indata som förväntas.

   Indata för det här exemplet är namnet på det problem som projektet konverterades från.

1. Flytta markören mellan parenteserna eftersom det är här inmatningen ska placeras.
1. Klicka på ikonen **Modulutdata** på mappningspanelen. ![Ikon för modulutdata](assets/toolbar-icon-functions-you-map-from-other-modules.png)
1. Markera namnblocket som utdata från din första modul.

   Namnblocket visas i funktionen.

   ![Namnblock i funktion](assets/map-name.png)

1. Klicka på **OK** om du vill spara modulinställningarna.

### Testa och aktivera

1. Testa scenariot genom att klicka på **Kör en gång** i skärmens nedre vänstra hörn.
1. Granska utdata för att kontrollera att scenariot kördes som förväntat.
1. När du är säker på att scenariot fungerar som förväntat klickar du på växeln **Schemaläggning** längst ned till vänster på skärmen till **På**.

   Detta aktiverar scenariot. Aktiva scenarier körs enligt det schema som angetts i utlösarmodulen.
1. I [!DNL Workfront Fusion] klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.

   >[!IMPORTANT]
   >
   >Spara ofta när du finslipar ett scenario.

## Resurs

* [Mappa objekt med funktioner](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)
