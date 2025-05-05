---
title: Felsöka ett scenario
description: Med Adobe Workfront Fusion Devtool kan du förstå och felsöka scenarier. Utvecklingsverktyget lägger till en extra panel i Chrome Developer Tools. Med den här felsökningspanelen kan du kontrollera alla manuella körningar av ditt scenario, granska alla utförda åtgärder och se information om alla API-anrop som utförs. Du kan se vilken modul, åtgärd eller enskilt svar som orsakade felet och använda den kunskapen för att förfina ditt scenario.
author: Becky
feature: Workfront Fusion
exl-id: 34215370-27e3-4c28-8bd1-a16268900b86
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 0%

---

# Felsöka ett scenario

Utvecklingsverktyget [!DNL Adobe Workfront Fusion] hjälper dig att förstå och felsöka scenarier. Med utvecklingsverktyget kan du kontrollera alla manuella körningar av ditt scenario, granska alla utförda åtgärder och se information om alla API-anrop som utförs. Du kan se vilken modul, åtgärd eller enskilt svar som orsakade felet och använda den kunskapen för att förfina ditt scenario.

>[!NOTE]
>
>Loggning på felsökningspanelen kommer att vara begränsad eller otillgänglig för konfidentiella scenarier, automatiska körningar och framgångsrika åtgärder.

En videointroduktion och genomgång av verktyget Fusion Devtool finns på

* [Fusion Development Tool](https://video.tv.adobe.com/v/3427031/){target=_blank}
* [Gå igenom utvecklingsverktyget](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/fusion/troubleshooting-and-error-handling/dev-tool-walkthrough.html?lang=sv-SE)

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara administratör för [!DNL Workfront Fusion] för din organisation.</p>
     <p>Du måste vara administratör för [!DNL Workfront Fusion] för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Öppna utvecklingsverktyget

Om du använder Fusion i Adobe Unified Shell, eller har uppdaterat till den nya Fusion-upplevelsen, kan du komma åt utvecklingsverktyget från Scenarioredigeraren.

1. Klicka på ikonen **Hjälpverktyg** ![Hjälpverktyg](assets/debugger-icon.png) längst ned på skärmen.

Eller:

1. Gå till Scenarioredigeraren för det scenario som du vill felsöka.

   Information om hur du hittar scenarioredigeraren finns i [Scenarioredigeraren](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md).

1. Högerklicka i ett tomt område på sidan (inte i en modul).
1. Välj **Öppna utvecklingsverktyget**.

## Använd utvecklingsverktyget [!DNL Workfront Fusion]

Workfront Fusion Devtool är uppdelat i tre huvudavsnitt. De finns i den vänstra panelen i fönstret Utvecklare.

* [Live Stream](#live-stream)
* [Scenariofelsökare](#scenario-debugger)
* [verktyg](#tools)

### Live Stream

Live Stream visar vad som händer i bakgrunden när du klickar på Kör en gång i ditt scenario.

1. Klicka på **[!UICONTROL Live Stream]**-ikonen ![Live-strömsikonen](assets/live-stream-icon.png) för att öppna Live-strömsavsnittet.
1. Gör något av följande:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>Åtgärd</th> 
      <th>Instruktioner</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td role="rowheader">Visa begärandeinformation</td> 
      <td> <p>Du kan visa följande information för varje modul i ditt scenario</p> 
       <ul> 
        <li> <p>Begäranrubriker (API-slutpunkts-URL, http-metod, tid och datum då begäran anropades, begäranrubriker och frågesträng)</p> </li> 
        <li> <p>Begärandetext</p> </li> 
        <li> <p>Svarshuvuden</p> </li> 
        <li> <p>Svarstext</p> </li> 
       </ul> <p>Om du vill visa den här informationen klickar du på lämplig flik i den högra panelen i utvecklingsverktyget [!DNL Workfront Fusion].</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Sök efter händelser efter innehåll</p> </td> 
      <td> <p>Ange söktermen i sökfältet på den vänstra panelen i utvecklingsverktyget [!DNL Workfront Fusion] om du bara vill visa begäranden som innehåller söktermen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Rensa listan över förfrågningar </p> </td> 
      <td> <p>Klicka på papperskorgsikonen i det övre högra hörnet av utvecklingsverktygets vänstra panel för att rensa listan över begäranden som spelats in med utvecklingsverktyget [!DNL Workfront Fusion]. </p> </td> 
     </tr> 
     <!--<tr> 
      <td role="rowheader"> <p>Enable Console Logging</p> </td> 
      <td> <p>Click the computer icon <img src="assets/console-computer-icon.png"> in the top-right corner of the Devtool's left panel.</p> <p>Logging in the console is enabled when the computer icon is green.</p> </td> 
     </tr>-->
     <tr> 
      <td role="rowheader"> <p>Hämta begäran i Raw JSON-format eller cURL</p> </td> 
      <td> 
       <ul> 
        <li> <p><strong>Raw JSON</strong> </p> <p>Klicka på <strong>[!UICONTROL Copy RAW]</strong> i det övre högra hörnet av utvecklingsverktygets högra ruta.</p> </li> 
        <li> <p><strong>cURL</strong> </p> <p>Klicka på <strong>[!UICONTROL Copy cURL]</strong> i det övre högra hörnet av utvecklingsverktygets högra ruta.</p> </li> 
       </ul> </td> 
     </tr> 
    </tbody> 
   </table>

### Scenariofelsökning

Scenariofelsökaren är användbar för mer komplexa scenarier. Den visar historiken för scenariot som körs och gör att du kan söka efter moduler efter namn eller ID.

1. Klicka på ikonen **[!UICONTROL Scenario Debugger]** ![Felsökning](assets/scenario-debugger-icon.png) för att öppna Felsökning för scenario.
1. (Valfritt) Ange söktermen (namn eller modul-ID) i sökfältet.
1. Klicka på modulnamnet.
1. Klicka på åtgärden för att visa information om begäran.

### verktyg

Utvecklingsverktyget [!DNL Workfront Fusion] innehåller verktyg som gör det enklare att konfigurera ditt scenario.

1. Klicka på ikonen **[!UICONTROL Tools]** ![Konsolverktyg](assets/console-tools-icon.png) för att öppna verktygen.
1. Välj det verktyg som du vill använda
1. Konfigurera fälten enligt nedan.
1. Klicka på **[!UICONTROL Run]**.

Verktyg och deras fält:

* [Fokusera en modul](#focus-a-module)
* [Sök efter moduler genom att mappa](#find-modules-by-mapping)
* [Hämta appmetadata](#get-app-metadata)
* [Kopiera mappning](#copy-mapping)
* [Kopiera filter](#copy-filter)
* [Kopiera modulnamn](#copy-module-name)
* [Växla anslutning](#swap-connection)
* [Växla variabel](#swap-variable)
* [Bas 64](#base-64)
* [Mappa om Source](#remap-source)

#### [!UICONTROL Focus a Module]

Öppnar inställningarna för den angivna modulen efter ID.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Module ID]</td>
        <td>Ange ID:t för modulen för att öppna dess inställningar.</td>
    </tr>
</table>

#### [!UICONTROL Find Modules by Mapping]

Gör att du kan söka efter modulernas värden för en angiven term. Utdata innehåller ID:n för moduler som innehåller den term du har sökt efter.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Keyword]</td> 
   <td> <p> Ange den term som du vill söka efter. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Use Only Values]</p> </td> 
   <td> <p>Aktivera det här alternativet om du bara vill söka i modulfältets värden.</p> <p>Inaktivera det här alternativet om du även vill söka i modulfältens namn.</p> <p>Sökningen utförs med parametrarna name och label.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get App Metadata]

Hämtar metadata för programmet utifrån dess modulnamn eller ID. Detta är användbart när du behöver veta vilken version av programmet som används i ditt scenario.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Markera modulen som du vill hämta metadata för.</td>
    </tr>
</table>

#### [!UICONTROL Copy Mapping]

Kopierar värden från källmodulen till målmodulen.

>[!CAUTION]
>
>Kontrollera att du har angett rätt käll- och målmoduler. Om du väljer en annan typ av modul tas värdena i målmodulen bort.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Markera modulen eller ange ID:t för modulen som du vill kopiera fältvärden från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Markera modulen eller ange ID:t för modulen som du vill infoga källmodulens värden i.</p> <p>Viktigt: Värdena i målmodulen skrivs över.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy Filter]

Kopierar filterinställningarna från källmodulen till målmodulen.

>[!NOTE]
>
>Kopieringsåtgärden utförs på filtret till vänster om den valda modulen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td> <p> Markera modulen eller ange ID:t för modulen som du vill kopiera filtervärden från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Markera modulen eller ange ID:t för modulen där du vill infoga filtervärdena från källmodulen.</p> <p>Viktigt: Värdena i målmodulen skrivs över.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Preserve Fallback Route setting]</p> </td> 
   <td> <p>Källfiltret anges som reservflöde. Aktivera det här alternativet om du även vill ange att målfiltret ska anges som reservflöde.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Copy Module Name]

Kopierar namnet på den valda modulen till Urklipp.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Module] </td> 
   <td> <p>Markera modulen som du vill kopiera namnet på.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Swap Connection]

Duplicerar en anslutning från källmodulen till varje modul i scenariot för samma program.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source Module]</td>
        <td>Markera modulen eller ange ID:t för modulen som du vill duplicera anslutningen från.</td>
    </tr>
</table>

#### [!UICONTROL Swap Variable]

Söker efter angivna variabler i scenariot och ersätter dem med en ny variabel.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable to Find]</td> 
   <td> <p> Leta reda på variabeln som du vill ersätta från variabelmodulen i ditt scenario och kopiera den till det här ([!UICONTROL Variable to Find]) fältet. I fältet visas det med dubbla klamrar. Exempel: <code>&#123;&#123;5.value&#125;&#125;</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace With]</p> </td> 
   <td> <p>Leta reda på variabeln som du vill ersätta variabeln med från variabelmodulen i ditt scenario och kopiera den till det här ([!UICONTROL Variable to Find])-fältet. I fältet visas det med dubbla klamrar. Exempel: <code>&#123;&#123;5.value&#125;&#125;</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module]</p> </td> 
   <td> <p>Markera den variabelmodul i vilken du vill ersätta variabeln. Om ingen modul är markerad ersätts variabeln i hela scenariot.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Base 64]

Gör att du kan koda angivna data till Base64 eller avkoda Base64. Vissa begäranden kodas till Base64. Det här verktyget kan vara användbart när du vill söka efter vissa data i den kodade begäran.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>Välj om du vill koda data från fältet [!UICONTROL Raw Data] till Base64 eller avkoda Base64 till Raw-data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Raw Data]</p> </td> 
   <td> <p> Ange de data som du vill koda till Base64, eller Base64 om du vill avkoda till rådata, beroende på vilket alternativ som har valts i fältet [!UICONTROL Operation] ovan.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remap Source]

Gör att du kan ändra mappningskällan från en modul till en annan.

Du måste först lägga till den modul som du vill använda som källmodul i flödet i ditt scenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module] </td> 
   <td> <p> Markera den modul som du vill ersätta som mappningskälla för andra moduler i ditt scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Target Module]</p> </td> 
   <td> <p>Markera modulen som du vill använda som en ny mappningskälla.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Module to Edit]</p> </td> 
   <td> <p>Markera modulen som du vill ändra mappningen för om du inte vill ändra mappningen i hela scenariot. </p> </td> 
  </tr> 
 </tbody> 
</table>
