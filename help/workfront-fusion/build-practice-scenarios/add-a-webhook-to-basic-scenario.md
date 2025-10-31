---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Lägga till en webkrok i ett grundläggande scenario
description: Webhooks, som också kallas direktutlösare, är en specifik typ av utlösarmodul som kan starta ett scenario när en ändring görs, i stället för enligt ett visst schema.
author: Becky
feature: Workfront Fusion
exl-id: 28ecca1f-a9c3-4b3d-95f5-73cb9a5dc4b9
source-git-commit: 3a977d805c10fda7209b0634c6e32e818a980691
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# Lägga till en webkrok i ett grundläggande scenario

Webhooks, som också kallas direktutlösare, är en specifik typ av utlösarmodul som kan starta ett scenario när en ändring görs, i stället för enligt ett visst schema.

I det här exemplet lägger du till en webkrok för att starta ett scenario så snart en begäran har skickats till en viss begärandekö. Scenariot konverterar sedan dessa begäranden till ett projekt.

I det här exemplet ändras scenariot som skapades i [Skapa ett grundläggande scenario](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md).

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
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Förutsättningar

Du måste skapa scenariot som beskrivs i [Skapa ett grundläggande scenario](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md) innan du följer den här proceduren.

## Lägg till och konfigurera webkroken


### Lägg till webbkrokmodulen

1. Öppna scenariot i scenarioredigeraren.
1. Högerklicka på den första modulen och välj **Ta bort modul**.

   Modulen tas bort och en tom platshållare lämnas kvar.

1. Klicka på den tomma modulen och välj **Adobe Workfront** i listan med program.
1. Välj **Bevakade händelser**.
1. Klicka på **Lägg till** bredvid Webkrok-fältet.
1. i fältet Posttyp väljer du **Utgåva** så att modulen utlöser ändringar i utgåvor.
1. Välj **Nytt läge** i fältet Läge. Det här är ett obligatoriskt fält som används för filtret, som det här exemplet inte omfattar.
1. Välj **Endast ny post** i fältet Postens ursprung. Detta gör att scenariot kan utlösas när en utgåva läggs till, inte när någon uppdateras eller tas bort.
1. Klicka på **Spara** för att spara modulkonfigurationen.

## Uppdatera den andra modulen

1. Öppna scenariot.
1. Klicka på modulen **Konvertera objekt** för att öppna den.
1. Ta bort det svarta ID-blocket i fältet Problem ID. Blocket är svart eftersom modulen som det mappades från inte längre är tillgänglig.
1. Markera ID-blocket under den första modulen (bevakade händelser) för att mappa det till den andra modulen.
1. Klicka på **OK**.



### Testa och aktivera

1. Klicka på **[!UICONTROL Run once]** i det nedre vänstra hörnet i scenarioredigeraren.

   Scenariot måste köras för att du ska kunna bevaka den nya begäran.
1. Gå till den Workfront-miljö som Fusion ansluter till och lägg till ett problem.

   Scenariot ska köras.
1. Granska utdata för att kontrollera att scenariot kördes som förväntat.
1. När du är säker på att scenariot fungerar som förväntat klickar du på växeln **Schemaläggning** längst ned till vänster på skärmen till **På**.

   Detta aktiverar scenariot.
1. I Workfront Fusion klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.
