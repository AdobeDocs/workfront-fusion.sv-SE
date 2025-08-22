---
title: Lägga till ett filter i ett scenario
description: I vissa scenarier behöver du bara arbeta med paket som uppfyller specifika kriterier. Med filter kan du välja dessa paket.
author: Becky
feature: Workfront Fusion
exl-id: b507dca0-0e85-4ab7-8310-b6e6bcb7ae12
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Lägga till ett filter i ett scenario

I vissa scenarier behöver du bara arbeta med paket som uppfyller specifika kriterier. Med filter kan du välja dessa paket.

Du kan t.ex. skapa ett scenario med utlösaren [!UICONTROL Watch records] för Workfront så att endast uppgifter som tilldelats en viss användare kan fångas.

Du kan lägga till ett filter mellan två moduler och kontrollera om paket som tagits emot från de föregående modulerna uppfyller specifika filtervillkor:

* Om de gör det skickas paketen vidare till nästa modul i scenariot.
* Om de inte gör det avslutas behandlingen för paketen.

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

## Förutsättningar

Du måste lägga till båda modulerna i ett scenario innan du kan lägga till ett filter mellan dem.

## Lägg till ett filter mellan två moduler:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till ett filter.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på skiftnyckelsikonen ![skiftningsikonen](assets/wrench-icon.png) mellan modulerna där du vill lägga till ett filter och välj **Konfigurera ett filter**.
1. Ange **[!UICONTROL Label]** som filter i rutan som visas.
1. Definiera filtret **[!UICONTROL Condition]**.

   Ange fältet som du vill filtrera efter i det första fältet, operatorn och (om det behövs) värdet som du vill jämföra fältet med.

   >[!TIP]
   >
   >Du kan ange värden i filterfält från mappningspanelen
   >Mer information om mappning finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

   Om du till exempel vill att filtret ska skicka filer i Adobe Workfront som slutar med XML, anger du **[!UICONTROL File name]** i den första rutan och .**[!UICONTROL xml]** i den andra rutan. I listrutan mellan dem väljer du **[!UICONTROL Ends with (case insensitive)]**. Det här filtret gäller inkommande paket från den första modulen (Workfront). Endast paket som innehåller XML-filer överförs till nästa modul.

   ![Konfigurera ett filter](assets/set-up-filter-box.png)

1. Klicka på **[!DNL OK]**.

## Kopiera ett filter

För närvarande innehåller scenarioredigeraren en funktion för att kopiera ett filter.

>[!NOTE]
>
>Om du kopierar modulerna på någon sida av filtret kopieras även filtret.
>
>Mer information om att kopiera moduler finns i [Kopiera moduler eller scenarier i Adobe Workfront Fusion](/help/workfront-fusion/create-scenarios/add-modules/copy-modules-or-scenarios.md).

Om du vill kopiera ett filter utan att kopiera moduler kan du använda Fusion DevTool

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till ett filter.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Öppna Fusion DevTool genom att klicka på DevTool-ikonen ![DevTool](assets/debugger-icon.png) i skärmens nedre kant.

   Om du inte ser ikonen DevTool läser du [Felsöka ett scenario](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md) för instruktioner om hur du öppnar DevTool.

1. Klicka på ikonen **[!UICONTROL Tools]** ![DevTool-verktyg](assets/devtools-tools-icon.png) i det vänstra fältet.

1. Klicka på **[!UICONTROL Copy Filter]** och konfigurera sedan verktyget **[!UICONTROL Copy Filter]** på den högra panelen:

   1. Ange **[!UICONTROL Source Module]** som modul direkt efter det filter som du vill kopiera.
   1. Ange **[!UICONTROL Target Module]** som den modul som du vill placera filtret direkt efter.

1. Klicka på **[!UICONTROL Run]**.
