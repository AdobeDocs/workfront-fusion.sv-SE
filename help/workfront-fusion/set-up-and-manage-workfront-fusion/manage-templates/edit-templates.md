---
content-type: reference
title: Redigera mallar
description: I den här artikeln beskrivs hur du redigerar Fusion-mallar.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Redigera mallar

Adobe Workfront Fusion-mallar är färdiga scenarier som utformats för att automatisera och effektivisera olika arbetsflöden. Mallarna kan hjälpa er att snabbt konfigurera integreringar och automatiseringar utan att behöva bygga allt från scratch.

Om du är administratör har du behörighet att visa, ändra, byta namn på, publicera, godkänna och ta bort mallar som skapats av andra.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">Adobe Workfront</td>
      <td><p>Alla</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">Adobe Workfront-licens</td>
      <td><p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p></td>
    </tr>
    <tr>
      <td role="rowheader">Adobe Workfront Fusion-licens**</td>
      <td>
        <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
        <p>eller</p>
        <p>Äldre: Alla</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Produkt</td>
      <td>
        <p>Nytt:</p>
        <ul>
          <li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li>
          <li>[!UICONTROL Ultimate] Workfront-plan: Workfront Fusion ingår.</li>
        </ul>
        <p>eller</p>
        <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md). -->

+++

## Redigera Workfront Fusion-mallar som administratör

1. Klicka på **[!UICONTROL Administration]** i den vänstra navigeringspanelen för att öppna området [!UICONTROL Administration].
1. Klicka på **[!UICONTROL All Templates]** i den vänstra navigeringspanelen.
1. Klicka på **[!UICONTROL Detail]** till höger om mallen som du vill redigera.
1. (Valfritt) Byt namn på mallen genom att klicka på **Alternativ** i det övre högra hörnet och välja **Byt namn**.
1. (Valfritt) Om du vill ändra språk på mallen klickar du på ikonen **[!UICONTROL Create a new template]** ![Scenarioinställningar](assets/fusion-scenario-settings-icon.png) och väljer språk i listrutan Språk.

   >[!IMPORTANT]
   >
   >Valet Språk motsvarar de tillgängliga språken i systeminställningarna och gäller endast namnet på den offentliga mallen och dess beskrivning. Du kan inte ändra ett mallspråk när mallen har sparats.

1. (Valfritt) Om du vill redigera mallbeskrivningen klickar du på ikonen **[!UICONTROL Set up a template]** ![Scenarioinställningar](assets/fusion-scenario-settings-icon.png) och anger beskrivningen.
1. Lägg till eller redigera program, moduler och verktyg på samma sätt som när du skapar ett standardscenario.

   Mer information om hur du lägger till sammanhangsbaserad hjälp till modulerna finns i [Konfigurera [!UICONTROL Wizard]-funktioner](#set-up-wizard-functionality) i den här artikeln.

   <!--For more information on building a scenario, see [Create a scenario in Adobe Workfront Fusion](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >Om mallen innehåller moduler som kräver att anslutningen, inloggningsuppgifterna eller annan sekretesskänslig information läggs till, delas informationen inte med mallanvändarna.

1. (Valfritt) Klicka på **[!UICONTROL Run once]** för att testa mallen.
1. Klicka på ikonen **[!UICONTROL Save]** ![Spara ](assets/save-icon.png).


## Konfigurera [!UICONTROL Wizard]-funktioner

Med [!DNL Workfront Fusion template] [!UICONTROL Wizard] kan du ge framtida användare av mallen instruktioner eller information om de specifika fält som används i moduler.

1. Klicka på modulen som lagts till i mallen för att visa modulens fält.
1. Leta reda på fältet där du vill lägga till [!UICONTROL Wizard]-information och aktivera **[!UICONTROL Use in Wizard]** under fältet.
1. Ange den information som du vill göra synlig för användare i fältet [!UICONTROL Help].
1. (Valfritt) Aktivera **[!UICONTROL Use as default value]** om du vill tillåta användare att se den här texten när de använder mallen.
1. Upprepa steg 2-4 för varje fält som du vill ange information för.
1. Klicka på **[!UICONTROL OK]** om du vill spara ändringarna och stänga modulen.

Publiceringsprocessen är densamma som för en standardanvändare. Mer information finns i avsnittet [Publicera och dela mallar](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md).

## Mallstatus

Du kan kontrollera mallsidans status under mallnamnet.

Följande statusar är tillgängliga:

* **[!UICONTROL Private]**: Den här mallen visas bara för mallskaparen och deras team.
* **[!UICONTROL Published]**: Den här mallen visas bara för mallskaparen och deras team. När mallen har publicerats kan du skicka den för godkännande om du vill. Du kan även kopiera en delbar länk.
* **[!UICONTROL Approved]**: Den här mallen visas för alla Workfront Fusion-användare på fliken [!UICONTROL Public templates]. Du kan också kopiera en delbar länk genom att klicka på [!UICONTROL Options] i skärmens övre högra hörn.

Du kan även kontrollera statusen på fliken [!UICONTROL Team templates]. Om en mall publiceras visas en ikon till höger om mallnamnet.

* **Ögonikon**: Mallen publiceras, den är synlig för teamet.
* **Gula bockmarkeringsikonen**: Mallen är publicerad, den är bara synlig för teamet och den väntar på godkännande att läggas till på fliken Offentliga mallar.
* **Grön bockmarkeringsikon**: Mallen är tillgänglig på fliken Offentliga mallar och är synlig för alla Workfront Fusion-användare. Den är fortfarande synlig på fliken [!UICONTROL Team templates]. Mallförfattaren eller teammedlemmen kan fortfarande redigera den.

Mallar utan ikoner har statusen [!UICONTROL Private]. De publiceras inte och är bara synliga för teamet.

## Hitta SVG-information för en mall

1. Klicka på **[!UICONTROL Administration]** i den vänstra navigeringspanelen för att öppna området [!UICONTROL Administration].
1. Klicka på **[!UICONTROL Templates]** i den vänstra navigeringspanelen.
1. Klicka på mallen som du vill söka efter information för.
1. Klicka på **Alternativ** längst upp till höger.
1. Välj *SVG-diagram*.

Här ser du SVG-diagrammet och SVG-koden.
