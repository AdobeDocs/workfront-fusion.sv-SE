---
title: Flödeskontroll
description: När du skapar eller redigerar ett scenario kan du konfigurera inställningar för att styra hur data flödar genom det.
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Flödeskontroll

När du skapar eller redigerar ett scenario kan du konfigurera inställningar för att styra hur data flödar genom det.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inget [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet], [!UICONTROL [!DNL Workfront Fusion] för Automatisering av arbete]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har planen [!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Adobe Workfront] måste din organisation köpa både [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln. [!DNL Workfront Fusion] ingår i planen [!UICONTROL Ultimate] [!DNL Workfront].</p>
   <p>eller</p>
   <p>Äldre produktkrav: Din organisation måste köpa [!DNL Adobe Workfront Fusion] och [!DNL Adobe Workfront] för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Kontakta [!DNL Workfront]-administratören om du vill ta reda på vilken plan, licenstyp eller åtkomst du har.

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Upprepare

Du kan använda en [!UICONTROL Repeater]-modul för att upprepa en uppgift ett visst antal gånger. En [!UICONTROL Repeater]-modul genererar paket, det ena efter det andra.

Du kan till exempel använda en [!UICONTROL Repeater]-modul för att skicka fem e-postmeddelanden med avsnitten &quot;Hello 1&quot;, &quot;Hello 2&quot; och så vidare, genom att ansluta modulen **[!UICONTROL Email]>[!UICONTROL Send me an email]** till modulen [!UICONTROL Repeater] .

Så här använder du en [!UICONTROL Repeater]-modul:

1. Klicka på ikonen [!UICONTROL Flow Control] ![Flödeskontroll](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) längst ned på skärmen och klicka sedan på **[!UICONTROL Repeater]** på den meny som visas.
1. Klicka på paketet [!UICONTROL Repeater] och klicka sedan på **[!UICONTROL Connect automatically]** i rutan som visas.
1. I rutan [!UICONTROL Flow Control] som visas skriver du det antal upprepningar (utgående paket) som du vill ha i rutan **[!UICONTROL Repeats]**.

   I vårt e-postexempel skriver du 5.

   ![Upprepare](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   Objektets värde ökar i varje repetition med det här värdet som anges i fältet **[!UICONTROL Step]**, som du kan visa genom att välja **[!UICONTROL Show advanced settings]**. Numret är som standard 1.

1. Klicka på **[!UICONTROL OK]** för att stänga rutan **[!UICONTROL Flow Control]**.

1. Klicka på appen eller tjänstmodulen som är ansluten till modulen [!UICONTROL Repeater].
1. Skriv den information som du vill upprepa i rutan som visas.

   I vårt e-postexempel skriver du Hello i rutan [!UICONTROL Subject] och sedan mappar du `i` från den upprepade modulen.

   ![Upprepare](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)

| Objekt | Beskrivning |
|---|---|
| [!UICONTROL Initial value] | Ange eller mappa numret som du vill att modulen ska ange som `i` i den första iterationen. Standardvärdet är 1. |
| [!UICONTROL Repeats] | Ange eller mappa det antal gånger som du vill att modulen ska upprepas. Talet måste vara större än eller lika med 0 och mindre än eller lika med 10 000. |
| [!UICONTROL Step] | Detta är talet som modulen ökar värdet för `i` med. Standardvärdet är 1. |

{style="table-layout:auto"}

>[!NOTE]
>
>Antalet upprepningar bestäms inte av värdet `i`, vilket skulle vara i en slinga i programmeringen. Modulen upprepas det antal gånger som anges i fältet [!UICONTROL Repeats]. Värdet `i` ändras för varje iteration i modulen [!DNL repeater] och kan mappas till senare moduler. I exemplet ovan mappas värdet för `i` till Hello-meddelandet, vilket resulterar i meddelanden som innehåller&quot;Hello 1&quot;,&quot;Hello 2&quot; och så vidare.

## [!UICONTROL Iterator]

En [!UICONTROL Iterator] är en särskild typ av modul som konverterar en array till en serie paket. Varje matrisobjekt blir ett separat paket i [!UICONTROL Iterator]-modulens utdata. Mer information finns i [Interpolatormodulen](/help/workfront-fusion/references/modules/iterator-module.md).

## Matrisaggregering

En arrayaggregator är en speciell typ av modul som gör det möjligt att sammanfoga flera paket till ett enda paket. Mer information finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

## [!UICONTROL Router]

Med modulen [!UICONTROL Router] kan du dela in ditt flöde i flera flöden och bearbeta data i varje flöde på olika sätt. När en [!UICONTROL Router]-modul tar emot ett paket vidarebefordrar den till varje ansluten väg i den ordning som rutterna kopplades till [!UICONTROL Router]-modulen. Mer information finns i [Routermodulen i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

<!--
<div>
<h2>Directives</h2>
<p>The error handling directives allow you to control how your scenario reacts to errors. For more information, see <a href="/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md" class="MCXref xref">Advanced error handling in Adobe Workfront Fusion</a> and <a href="/help/workfront-fusion/references/errors/directives-for-error-handling.md" class="MCXref xref">Directives for error handling in Adobe Workfront Fusion</a>.</p>
</div>
-->
