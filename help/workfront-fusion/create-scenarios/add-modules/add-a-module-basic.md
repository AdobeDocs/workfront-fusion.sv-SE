---
title: Lägga till en modul i ett scenario
description: I den här artikeln beskrivs den grundläggande processen att lägga till en modul i ett scenario.
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
source-git-commit: 62b09469c1d85fd2bd1f154cde339cc4a10fc34a
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---

# Lägga till en modul i ett scenario

Ett scenario består av en serie moduler som anger hur data ska omvandlas i en app eller överföras mellan program och webbtjänster. Du skapar en modul genom att lägga till och konfigurera moduler.

I den här artikeln beskrivs den grundläggande processen att lägga till en modul i ett scenario. Mer specifika instruktioner om hur du lägger till ett scenario finns i de andra artiklarna under [Lägg till moduler: artikelindex](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md).

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

## Lägg till den första modulen i ett scenario

Den första modulen i ett scenario är vanligtvis en utlösarmodul.

Mer information om utlösarmoduler finns i [Utlösarmoduler](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules) i översikten över artikelmodulen.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Börja skapa ett scenario genom att klicka på **Skapa ett nytt scenario** i skärmens övre högra hörn.

   Scenredigeraren öppnas med en platshållarmodul (frågetecken) och en lista över tillgängliga kopplingar.

   ![Platshållarmodul](assets/placeholder-module.png)

1. Välj den anslutning eller webkrok som ska starta det här scenariot. Du kan ange namnet på kopplingen i sökfältet i listan för att filtrera listan.
1. Konfigurera modulen.

   Instruktioner om hur du konfigurerar specifika moduler finns i artikeln för de valda programmen, som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>Om du har tagit bort den första modulen från ett scenario och vill ersätta den klickar du på platshållarmodulen (frågetecken) för att öppna listan med kopplingar.

## Lägg till en annan modul i ett scenario

1. Om du inte är i scenarioredigeraren för det scenario där du vill lägga till en modul klickar du på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Om du vill lägga till en modul i en annan modul håller du pekaren över det högra handtaget i modulen som du vill lägga till en modul efter och klickar sedan på **Lägg till en annan modul** när den visas.

   Listan med kopplingar öppnas och visar alla kopplingar som redan används i scenariot.

1. (Valfritt) Om du vill välja en annan koppling klickar du på **Lägg till en annan modul** i listan och väljer sedan kopplingen. Du kan ange namnet på kopplingen i sökfältet i listan för att filtrera listan.
1. Konfigurera modulen.

   Instruktioner om hur du konfigurerar specifika moduler finns i artikeln för de valda programmen, som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

## Infoga en modul mellan befintliga moduler i ett scenario

1. Om du inte är i scenarioredigeraren för det scenario där du vill lägga till en modul klickar du på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på den prickade banan mellan modulerna där du vill infoga en modul.
1. Välj **Lägg till en modul** på den meny som visas.

Listan med kopplingar öppnas och visar alla kopplingar som redan används i scenariot.

1. (Valfritt) Om du vill välja en annan koppling klickar du på **Lägg till en annan modul** i listan och väljer sedan kopplingen. Du kan ange namnet på kopplingen i sökfältet i listan för att filtrera listan.
1. Konfigurera modulen.

   Instruktioner om hur du konfigurerar specifika moduler finns i artikeln för de valda programmen, som listas i [Fusion-program och deras modulreferenser: artikelindex](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md).

>[!NOTE]
>
>Om du vill skapa en länk till en viss modul lägger du till `?moduleId=<module-id>` i URL:en när du visar följande sidor:
>
>* Scenarioredigeringssida (URL:en slutar på `/edit`)
>* En specifik scenariokörning (URL:en slutar på `/logs/<log-id>`)
>
>`<module-id>` refererar till numret bredvid moduletiketten när du visar scenariot.
>
>Detta kan vara användbart vid felsökning eller kopiering av modulkonfiguration.
