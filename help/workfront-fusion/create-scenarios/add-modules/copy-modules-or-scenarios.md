---
title: Kopiera moduler eller scenarier
description: Du kan kopiera moduler, grupper av moduler eller hela scenarier i Adobe Workfront Fusion. Med den här möjligheten kan du återanvända scenarier eller delar av scenarier utan att behöva skapa dem igen.
author: Becky
feature: Workfront Fusion
exl-id: 5cece7d4-b2c7-4276-8a6f-f65bad799c7a
source-git-commit: 860209fdcf2e7707663cc2d454c0499972b1261e
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Kopiera moduler eller scenarier

Du kan kopiera moduler, grupper av moduler eller hela scenarier i Adobe Workfront Fusion. Med den här möjligheten kan du återanvända scenarier eller delar av scenarier utan att behöva skapa dem igen.

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

Modulerna måste finnas i ett scenario innan du kan kopiera dem.

## Kopiera en modul eller en grupp moduler

När du kopierar en modul behåller kopian alla fältvärden och inställningar i den ursprungliga modulen.

Du kan klistra in modulen eller modulerna i ett annat område i samma scenario, eller i ett annat scenario.

Tänk på följande när du klistrar in moduler i ett annat scenario:

* Fältvärden som hämtar information från en annan modul som du inte kopierat kan inte längre komma åt den informationen. Du måste ange dessa fält för att hämta information från det nya scenariot.
* Om du klistrar in modulerna i ett scenario som ägs av ett annat team eller en annan organisation måste alla anslutningar uppdateras till anslutningar som ägs av det team eller den organisation som äger det nya scenariot.

### Kopiera moduler

Att kopiera en grupp moduler liknar att kopiera en enda modul.

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill kopiera en modul.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Högerklicka på den modul som du vill kopiera.

   >[!NOTE]
   >
   >Du kan markera mer än en modul genom att hålla ned [!UICONTROL shift] och klicka på de moduler som du vill kopiera. Om du kopierar en grupp moduler kopieras även alla kopplingslinjer, filter eller routningslogik mellan dem.

1. Välj **[!UICONTROL Copy module]**.
1. Flytta markören till området där du vill ha en kopia av scenariot.
1. Högerklicka och välj **[!UICONTROL Paste]**.
1. Koppla de inklistrade modulerna till scenariot genom att dra dem till rätt plats i scenariot.

   Du kan också använda kortkommandon för att kopiera och klistra in.

## Kopiera ett scenario genom att klona

När du klonar ett scenario skapas en kopia av scenariot, som du sedan kan redigera.

1. Öppna sidan med scenarioinformation:

   1. Klicka på fliken **[!UICONTROL Scenario]** i den vänstra panelen och klicka sedan på ett scenario som du vill ha information om.

      eller

      Om du arbetar med scenariot i scenarioredigeraren klickar du på vänsterpilen ![Avsluta redigeringspilen](assets/exit-editing-arrow.png) i fönstrets övre vänstra hörn.

1. Högerklicka på **[!UICONTROL Options]** längst upp till höger på sidan.
1. Välj **[!UICONTROL Clone]**.
1. (Valfritt) Ange ett namn för det nya scenariot.
1. (Valfritt) Aktivera **[!UICONTROL Keep the states of any new modules the same as those being duplicated]** för att se till att det kopierade scenariot även innehåller information om de senaste posterna som har bearbetats i det ursprungliga scenariot.
1. Klicka på **[!UICONTROL Save]** för att skapa scenariot.

## Kopiera ett scenario med hjälp av utkast

Scenarioteman representerar arrangemanget, mappningen och fältvärdena för ett givet scenario vid en viss tidpunkt. Du kan exportera en scenarioplan till en JSON-fil på datorn och sedan importera den när du skapar ett nytt scenario. Scenarier som importeras från en scenarioplan kan redigeras.

En scenarioplan representerar hela scenariot. Om du bara vill kopiera vissa moduler från ett scenario läser du [Kopiera en modul eller en grupp med moduler](#copy-a-module-or-a-group-of-modules) i den här artikeln.

### Exportera en scenarioplan

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill exportera en plan.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. I scenariot klickar du på menyn **[!UICONTROL More]** i scenarioinställningsområdet.
1. Klicka på **[!UICONTROL Export Blueprint]**.

   En JSON-fil skapas och hämtas till datorn. Du kan hitta filen i mappen [!DNL Downloads].

>[!NOTE]
>
>Information om hur du exporterar en plan för en tidigare version av ett scenario finns i [Visa och hantera scenarioversioner](/help/workfront-fusion/manage-scenarios/restore-a-scenario-version.md).

### Importera en plan

>[!IMPORTANT]
>
>Om du importerar en plan till ett befintligt scenario ersätter scenarioplanen det befintliga scenariot. Du kan inte lägga till en plan i ett befintligt scenario.

1. Börja skapa ett nytt scenario.
1. I scenariot klickar du på menyn **[!UICONTROL More]** i scenarioinställningsområdet.
1. Klicka på **[!UICONTROL Import Blueprint]**.
1. Klicka på **[!UICONTROL Browse]** i dialogrutan som visas
1. Navigera till den plan som du vill importera och klicka på **[!UICONTROL Open]**.
1. Klicka på **[!UICONTROL Save]**.

   En JSON-fil skapas och hämtas till datorn. Du kan hitta filen i mappen [!UICONTROL Downloads].

## Kopiera och återanvända scenarier med hjälp av mallar

Du kan skapa mallar som utgångspunkt för dina [!DNL Workfront Fusion]-scenarier. När du skapar ett scenario från en mall kan du ändra scenariot utan att ändra mallen. Fältvärden sparas inte i mallar.

Mer information om hur du skapar ett scenario med hjälp av en mall finns i [Skapa scenarier med mallar](/help/workfront-fusion/create-scenarios/add-modules/create-scenarios-with-fusion-templates.md).

## Felsökning

Om du kopierar och klistrar in moduler på det sätt som beskrivs i [Kopiera en modul eller en grupp av moduler](#copy-a-module-or-a-group-of-modules) och inget visas när du klistrar in, kontrollerar du inställningarna för webbläsarens plats så att det går att klistra in från Urklipp.
