---
title: Mappa objekt med funktioner
description: När du mappar objekt kan du använda funktioner för att skapa enkla eller komplexa formler.
author: Becky
feature: Workfront Fusion
exl-id: b9d7643e-febf-42e2-9ddc-8ec8eba98e7a
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---

# Mappa ett objekt med funktioner

När du mappar objekt kan du använda funktioner för att skapa enkla eller komplexa formler. De tillgängliga funktionerna liknar funktionerna i Excel och i vissa programmeringsspråk:

* De utvärderar allmän logik, matematik, text, datum och arrayer.
* Med dem kan du utföra villkorsstyrd logik och omformningar av objektvärden, som att konvertera text till versaler, trimma text, konvertera ett datum till ett annat format och mycket mer.

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
     <p>Du måste vara Workfront Fusion-administratör för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Infoga funktioner i fält

Så här infogar du en funktion i ett fält:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill mappa data.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka i det fält där du vill infoga en funktion.
1. Markera fliken som innehåller den funktion som du vill infoga på mappningspanelen.

   Mer information om mappning av panelflikar finns i [Funktionsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)
   1. Klicka på funktionsnamnet.

      eller

      Dra funktionen till fältet.
1. Konfigurera funktionsparametrarna.

   Om du vill ha en förklaring av funktionsparametrarna håller du pekaren över funktionen på mappningspanelen.

   Mer information om funktioner och deras parametrar finns i artiklarna under [Funktionsreferenser: artikelindex](/help/workfront-fusion/references/mapping-panel/functions/functions-toc.md).

1. Fortsätt konfigurera modulen eller klicka på **OK**.

>[!TIP]
>
>När du skapar en komplex formel som du vill återanvända i ett annat fält kan du klicka på fältet som innehåller kombinationen, använda Cmd-A eller Ctrl-A för att markera den och sedan kopiera och klistra in den i det andra fältet.


>[!BEGINSHADEBOX]

**Exempel:** En del datatyper hindrar användare från att ange fler än ett visst antal tecken. Du kan använda delsträngsfunktionen för att begränsa ett värde till ett visst antal tecken.

I det här exemplet begränsar delsträngsfunktionen projektnamnet till 50 tecken.

![Exempel på begränsning av möteslängd](assets/example-meet-length-restriction-350x184.png)

>[!ENDSHADEBOX]

## Kapslingsfunktioner

Du kan kapsla in funktioner i varandra.

>[!BEGINSHADEBOX]

**Exempel:**

I det här exemplet begränsar delsträngsfunktionen det trimmade projektnamnet till 50 tecken.

![Rensat namn](assets/trimmed-name-under-50.png)

>[!ENDSHADEBOX]

Så här kapslar du en funktion:

1. Klicka i det fält där du skapar en formel.

   Mappningspanelen öppnas.

1. Klicka på den första funktionen som du vill lägga till. Det här är funktionen på utsidan. Om följande exempel visas är detta funktionen `substring`.
1. I den funktionen klickar du där du vill att den kapslade funktionen ska placeras. I det här exemplet placeras den kapslade funktionen i stället för den första parametern.
1. Klicka på den kapslade funktionen på mappningspanelen. I det här exemplet är det här funktionen `trim`.
1. Fortsätt konfigurera funktionen efter behov.
1. Fortsätt konfigurera modulen eller klicka på **OK**.

## Använd [!DNL Google Sheets]-funktioner

Om Workfront Fusion inte innehåller någon funktion som du vill använda, men den finns i [!DNL Google Sheets], kan du använda den genom att följa de här stegen:

1. Skapa ett nytt tomt kalkylblad i [!DNL Google Sheets].
1. Öppna ditt scenario i Workfront Fusion.
1. Lägg till modulen **[!DNL Google Sheets]** >**[!UICONTROL Update a cell]** i scenariot.

1. Konfigurera modulen:

   1. Välj det nya kalkylbladet i fältet **[!UICONTROL Spreadsheet]**.
   1. Infoga formeln som innehåller [!DNL Google Sheets] funktioner i fältet **[!UICONTROL Value]**.

      Du kan använda utdata från föregående moduler som vanligt.

      ![Använd funktioner för Google-blad](assets/exploit-google-sheet-functions-350x218.png)

1. Infoga modulen **[!UICONTROL Google Sheets]>[!UICONTROL Get a cell]** för att få fram det beräknade resultatet.
1. Konfigurera modulen med samma cell-ID som du använde i steg 4.

   ![Använd funktioner för Google-blad](assets/exploit-google-sheet-functions-2-350x187.png)
