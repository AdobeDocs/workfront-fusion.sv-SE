---
title: Flödeskontroll
description: När du skapar eller redigerar ett scenario kan du konfigurera inställningar för att styra hur data flödar genom det.
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---

# Flödeskontroll

När du skapar eller redigerar ett scenario kan du konfigurera inställningar för att styra hur data flödar genom det.

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
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: Arbete eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Workfront Fusion-licens krävs inte.</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront package: Your organization must purchase Adobe Workfront Fusion.</li><li>Ultimate Workfront-paket: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Upprepare

Du kan använda en [!UICONTROL Repeater]-modul för att upprepa en uppgift ett visst antal gånger. En [!UICONTROL Repeater]-modul genererar paket, det ena efter det andra.


<table>
    <tr>
        <td>[!UICONTROL Initial value]</td>
        <td>Ange eller mappa värdet som du vill att modulen ska ha i den första iterationen. Standardvärdet är 1.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Repeats]</td>
        <td>Ange eller mappa det antal gånger som du vill att modulen ska upprepas. Talet måste vara större än eller lika med 0 och mindre än eller lika med 10 000.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Step]</td>
        <td>Detta är talet som modulen ökar värdet med. Standardvärdet är 1.</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

Du kan till exempel använda en [!UICONTROL Repeater]-modul för att skicka fem e-postmeddelanden med avsnitten &quot;Hello 1&quot;, &quot;Hello 2&quot; och så vidare, genom att ansluta modulen **[!UICONTROL Email]>[!UICONTROL Send me an email]** till modulen [!UICONTROL Repeater] .

1. Klicka på ikonen [!UICONTROL Flow Control] ![Flödeskontroll](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif) längst ned på skärmen och klicka sedan på **[!UICONTROL Repeater]** på den meny som visas.
1. Klicka på modulen [!UICONTROL Repeater] och sedan på **[!UICONTROL Connect automatically]** i rutan som visas.

   Repeatermodulen öppnas.

1. I fältet **[!UICONTROL Repeats]** anger du antalet upprepningar (utgående paket) som du vill att modulen ska producera.

   I det här exemplet anger du 5.

   ![Upprepare](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   Objektets värde ökar i varje repetition med det här värdet som anges i fältet **[!UICONTROL Step]**, som du kan visa genom att välja **[!UICONTROL Show advanced settings]**. Numret är som standard 1.

1. Klicka på **[!UICONTROL OK]** för att stänga rutan **[!UICONTROL Flow Control]**.

1. Klicka på appen eller tjänstmodulen som är ansluten till modulen [!UICONTROL Repeater].
1. Skriv den information som du vill upprepa i rutan som visas.

   I vårt e-postexempel skriver du Hello i rutan [!UICONTROL Subject] och sedan mappar du `i` från den upprepade modulen.

   ![Upprepare](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>Antalet upprepningar bestäms inte av värdet `i`, vilket skulle vara i en slinga i programmeringen. Modulen upprepas det antal gånger som anges i fältet [!UICONTROL Repeats]. Värdet `i` ändras för varje iteration i modulen [!DNL repeater] och kan mappas till senare moduler. I exemplet ovan mappas värdet för `i` till Hello-meddelandet, vilket resulterar i meddelanden som innehåller&quot;Hello 1&quot;,&quot;Hello 2&quot; och så vidare.

>[!ENDSHADEBOX]

## [!UICONTROL Iterator]

En [!UICONTROL Iterator] är en särskild typ av modul som konverterar en array till en serie paket. Varje matrisobjekt blir ett separat paket i [!UICONTROL Iterator]-modulens utdata. Mer information finns i [Interpolatormodulen](/help/workfront-fusion/references/modules/iterator-module.md).

## Matrisaggregering

En arrayaggregator är en speciell typ av modul som gör det möjligt att sammanfoga flera paket till ett enda paket. Mer information finns i [Aggregatormodulen](/help/workfront-fusion/references/modules/aggregator-module.md).

## [!UICONTROL Router]

Med modulen [!UICONTROL Router] kan du dela in ditt flöde i flera flöden och bearbeta data i varje flöde på olika sätt. När en [!UICONTROL Router]-modul tar emot ett paket vidarebefordrar den till varje ansluten väg i den ordning som rutterna kopplades till [!UICONTROL Router]-modulen. Mer information finns i [Routermodulen i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).

## Direktiv

Med felhanteringsdirektiven kan du styra hur ditt scenario reagerar på fel.

Mer information om felhanteringsdirektiv finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

