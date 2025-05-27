---
title: Lägg till en routermodul och konfigurera flöden
description: Med routermodulen kan du dela in ditt flöde i flera flöden och bearbeta data i varje flöde på olika sätt. När en routermodul tar emot ett paket vidarebefordrar den till varje ansluten rutt i den ordning som rutterna kopplades till routermodulen.
author: Becky
feature: Workfront Fusion
exl-id: 8344cde4-df3e-4b72-9d10-46ff4b186400
source-git-commit: c1c11c6766678263b36488909c3799299a1c510a
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 0%

---

# Lägg till en routermodul och konfigurera flöden

Med routermodulen kan du dela in ditt scenario i flera vägar och bearbeta data i varje flöde på olika sätt. När en routermodul tar emot ett paket vidarebefordrar den det till varje ansluten rutt i den ordning som rutterna kopplades till routermodulen.

Rutorna bearbetas sekventiellt, inte parallellt. Ett paket skickas inte till nästa väg förrän det har bearbetats fullständigt av föregående väg.


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

## Lägga till en routermodul i ett scenario

Du måste lägga till en routermodul innan du konfigurerar vägar.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en router.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på det högra handtaget i modulen som du vill lägga till routern efter i scenarieredigeraren.
1. Välj **[!UICONTROL Flow Control]** > **Router** i listan med moduler som visas.

   ![Anslut vägen](assets/connect-the-router-350x108.png)

   eller

   Om du vill infoga routermodulen mellan två moduler klickar du på skiftnyckelsikonen under vägen som förbinder de två modulerna och väljer **[!UICONTROL Add a router]** på menyn.

   ![Infoga router](assets/insert-router-350x191.png)
1. Lägg till den första vägen till routern genom att klicka på routerns högra handtag och lägga till en modul, ungefär som när du lägger till en modul.
1. Klicka på routermodulen om du vill lägga till en annan väg. En rutt visas. Lägg till moduler på det här flödet efter behov.

   Du kan lägga till så många rutter du vill.

1. Om du vill verifiera riktningsordningen klickar du på ikonen Automatisk justering ![Automatisk justering](assets/auto-align.png) .

   Vägarna ordnas i den ordning de utförs. Den översta vägen körs först.

1. (Valfritt) Om du vill ändra flödesordningen högerklickar du på routermodulen och väljer **Ordningsvägar** Dra och släpp rutterna i den ordning som du vill att de ska köras i. Rutorna markeras med den första modulen som följer routern (den första modulen i rutten).

1. Fortsätt till [Lägg till ett filter i ett flöde](#add-a-filter-to-a-route).

## Lägga till ett filter i ett flöde

Du kan lägga ett filter på en väg efter routermodulen för att filtrera paket. Endast paket som passerar genom filtret hanteras av modulerna på vägen.

Om data passerar filtret för mer än en väg hanteras data av båda vägarna. Den översta vägen hanterar data först.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till ett filter.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på skiftnyckelsikonen ![skiftnyckel](assets/wrench-icon.png) på den bana där du vill ange ett filter. Detta är sökvägen mellan routermodulen och den första modulen i vägen.
1. Välj **Konfigurera ett filter.**
1. Lägg till en etikett i etikettfältet på panelen som visas. Den här etiketten visas i scenariot.
1. Konfigurera filtervillkor.

   Mer information finns i [Lägga till ett filter i ett scenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).

1. Klicka på **[!UICONTROL OK]** om du vill spara filterinställningarna.

1. Fortsätt till [Konfigurera en reservväg](#configure-a-fallback-route).

## Konfigurera ett reservflöde

Reservvägen är den väg som körs på alla paket som inte skickar något filter till en annan väg.

Du kan aktivera ett reservflöde på filterpanelen.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till ett reservflöde.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på skiftnyckelsikonen ![skiftnyckel](assets/wrench-icon.png) på den bana där du vill ange ett filter. Detta är sökvägen mellan routermodulen och den första modulen i vägen.
1. Välj **Konfigurera ett filter.**
1. Lägg till en etikett i etikettfältet på panelen som visas. Den här etiketten visas i scenariot.
1. Markera kryssrutan för reservflöde.

   ![Reservflöde](assets/fallback-route-350x260.png)

1. Klicka på **[!UICONTROL OK]** om du vill spara filterinställningarna.

Reservvägen är markerad med en annan pil i routermodulen:

![Pilsignatur i routern](assets/arrow-sign-in-router-module-350x361.png)

## Exempel: `if/else` användningsfall

>[!BEGINSHADEBOX]

Ett typiskt användningsfall för reservflödet är att fortsätta flödet med ett flöde om villkoret är uppfyllt och med ett annat flöde om det inte är uppfyllt. enligt följande:

I det här exemplet konfigureras den första vägen med ett filter. Detta representerar komponenten `if`.

![Konfigurera ett filter i flödet](assets/set-up-a-filter-2-350x242.png)

Den andra vägen är konfigurerad som en reservväg. Detta representerar komponenten `else`.

![Aktivera alternativ för återgång](assets/enable-fallback-route-option-350x238.png)

>[!ENDSHADEBOX]
