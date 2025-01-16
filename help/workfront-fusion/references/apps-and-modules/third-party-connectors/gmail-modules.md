---
title: Gmail-moduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Gmail samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 62269eca-c3cf-42fe-a866-fb66d2363b8d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# [!DNL Gmail] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Gmail] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
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

## Förutsättningar

Du måste ha ett [!DNL Gmail]-konto för att kunna använda [!DNL Gmail]-moduler.

## Anslut [!DNL Gmail] till [!DNL Workfront Fusion] {#connect-gmail-to-workfront-fusion}

* [Anslut [!DNL Gmail] till [!DNL Workfront Fusion] med [!DNL Google Workspace]](#connect-gmail-to-workfront-fusion-usingg-suite)
* [Anslut [!DNL Gmail] till [!DNL Workfront Fusion] med [!DNL gmail.com] eller [!DNL googlemail].com](#connect-gmail-to-workfront-fusion-using-gmailcom-or-googlemailcom)

### Anslut [!DNL Gmail] till [!DNL Workfront Fusion] med [!DNL  Google Workspace] {#connect-gmail-to-workfront-fusion-using-g-suite}

Instruktioner om hur du ansluter ditt [!DNL Google Workspace]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md.

### Anslut [!DNL Gmail] till [!DNL Workfront Fusion] med [!DNL gmail.com] eller [!DNL googlemail].com {#connect-gmail-to-workfront-fusion-using-gmail-com-or-googlemail-com}

Om du är [!DNL @gmail.com] eller [!DNL @googlemail.com] användare måste du skapa en OAuth-klient på [ [!DNL Google Cloud Platform]](https://console.developers.google.com/projectselector2/apis/dashboard?supportedpurview=project) för att få en [!UICONTROL Client ID] och [!UICONTROL Client Secret].

Stegvisa instruktioner om hur du skapar OAuth-klienten och hämtar en [!UICONTROL Client ID] och [!UICONTROL Client Secret] finns i [Ansluta Adobe Workfront Fusion till Google Services med en anpassad OAuth-klient](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md).

## [!DNL Gmail]-moduler och deras fält

När du konfigurerar [!DNL Gmail] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Gmail] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Iteratorer](#iterators)

### Utlösare

#### [!UICONTROL Watch emails]

Den här utlösarmodulen kör ett scenario när ett nytt e-postmeddelande tas emot för bearbetning.

Modulen returnerar alla standardfält som är associerade med posten eller posterna, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera den e-postmapp som du vill bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Filter type] </td> 
   <td> <p>Välj den filtertyp som du vill använda för att bevaka e-postmeddelanden</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Simple filter]</strong> </p> <p>Fyll i fälten [!UICONTROL Criteria], [!UICONTROL Sender Email Address], [!UICONTROL Subject] och [!UICONTROL Search Phrase]</p> </li> 
     <li> <p> <strong>[!UICONTROL Gmail filter]</strong> </p> <p>I fältet [!UICONTROL Query] anger du frågan som du vill använda för att filtrera e-postmeddelanden.</p> <p>Mer information om [!DNL Gmail]-filter finns i <a href="https://support.google.com/mail/answer/7190">Sökoperatorer</a> i [!DNL Gmail]-dokumentationen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Criteria]</td> 
   <td>Välj om du vill titta på [!UICONTROL all email], [!UICONTROL only read emails] eller [!UICONTROL only unread] e-postmeddelanden.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sender email address]</td> 
   <td> <p> Ange en e-postadress för att endast bevaka e-postmeddelanden som skickas från den adressen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject]</td> 
   <td>Ange en textsträng om du bara vill titta på e-postmeddelanden som har den textsträngen i ämnesraden.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search phrase]</td> 
   <td>Ange en textsträng om du bara vill titta på e-postmeddelanden som har textsträngen var som helst i e-postmeddelandet.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Mark email message(s) as read when fetched]</td> 
   <td> <p> Aktivera det här alternativet om du vill markera hämtade e-postmeddelanden som lästa.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of results]</td> 
   <td> <p> Ange det maximala antalet resultat som [!DNL Workfront Fusion] ska arbeta med under en cykel.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Send an email]](#send-an-email)
* [[!UICONTROL Create a draft]](#create-a-draft)
* [[!UICONTROL Mark an email as read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an email as unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an email]](#move-an-email)
* [[!UICONTROL Copy an email]](#copy-an-email)
* [[!UICONTROL Delete an email]](#delete-an-email)
* [[!UICONTROL Modify email labels]](#modify-email-labels)

#### [!UICONTROL Send an email]

Den här åtgärdsmodulen skickar ett nytt e-postmeddelande.

Du anger e-postmeddelandets mottagare.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!DNL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL From]</td> 
   <td> <p>Ange eller mappa en e-postadress till avsändaren.</p> <p>Obs! Om du anger en felaktig e-postadress kan ett fel uppstå när du skickar ett meddelande, eftersom ditt konto kanske inte har behörighet att skicka e-post från en annan adress än din egen.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To] </td> 
   <td> <p>Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje mottagare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject] </td> 
   <td> <p>Ange eller mappa e-postmeddelandets ämne.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Content] </td> 
   <td> <p>Ange eller mappa e-postinnehållet (meddelandetexten). HTML-taggar tillåts.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attachments] </td> 
   <td> <p>Klicka på <strong>[!UICONTROL Add]</strong> om du vill lägga till en bifogad fil. Du kan mappa en fil från de tidigare modulerna.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Copy recipients]</td> 
   <td> <p> Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje kopiemottagare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Blind copy recipients]</td> 
   <td> <p> Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje mottagare av en blind kopia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a draft]

Den här åtgärdsmodulen skapar ett nytt e-postutkast och lägger till det i en mapp som du anger.

Du anger i vilken mapp du vill skapa ett utkast.

Modulen returnerar ID:t för e-postutkastet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen [!DNL Gmail] som du vill skapa ett utkast i.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To] </td> 
   <td> <p>Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje mottagare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Subject] </td> 
   <td> <p>Ange eller mappa e-postmeddelandets ämne.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Content] </td> 
   <td> <p>Ange eller mappa e-postinnehållet (meddelandetexten). HTML-taggar tillåts.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Attachments] </td> 
   <td> <p>Klicka på <strong>[!UICONTROL Add]</strong> om du vill lägga till en bifogad fil. Du kan mappa en fil från de tidigare modulerna.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Copy recipients]</td> 
   <td> <p> Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje kopiemottagare.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Blind copy recipients]</td> 
   <td> <p> Klicka på <strong>[!UICONTROL Add]</strong> och ange eller mappa sedan e-postadressen för varje mottagare av en blind kopia.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an email as read]

Den här åtgärdsmodulen markerar ett e-postmeddelande som läst.

Du anger ID:t för e-postmeddelandet och dess mapp.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen [!DNL Gmail] som innehåller e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Ange eller mappa e-post-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an email as unread]

Den här åtgärdsmodulen markerar ett e-postmeddelande eller ett e-postutkast som oläst.

Du anger ID:t för e-postmeddelandet och dess mapp.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen [!DNL Gmail] som innehåller e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)] </td> 
   <td> <p>Ange eller mappa e-post-ID:t för e-postmeddelandet som du vill markera som oläst.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an email]

Den här åtgärdsmodulen flyttar ett e-postmeddelande eller ett e-postutkast till en mapp som du anger.

Du anger mapp, målmapp och ID för e-postmeddelandet.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera källmappen [!DNL Gmail] som innehåller e-postmeddelandet som du vill flytta.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination folder]</td> 
   <td> <p> Markera målmappen [!DNL Gmail] som du vill flytta e-postmeddelandet till.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Ange eller mappa e-post-ID:t för e-postmeddelandet som du vill flytta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy an email]

Den här åtgärdsmodulen kopierar ett e-postutkast eller ett e-postutkast till en mapp som du anger.

Du anger mapp, målmapp och ID för e-postmeddelandet.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>Markera källmappen [!DNL Gmail] som innehåller e-postmeddelandet som du vill kopiera.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination folder]</td> 
   <td> <p>Markera målmappen [!DNL Gmail] som du vill kopiera e-postmeddelandet till.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Email ID (UID)]</td> 
   <td> <p>Ange eller mappa e-post-ID:t för e-postmeddelandet som du vill kopiera.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an email]

Den här åtgärdsmodulen tar bort ett e-postmeddelande eller ett e-postutkast från en mapp som du anger.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL [!DNL Gmail] Meddelande-ID]</p> </td> 
   <td> <p>Ange eller mappa e-post-ID:t för e-postmeddelandet som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Permanently] </td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta modulen att ta bort e-postmeddelandet permanent i stället för att flytta det till papperskorgen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify email labels]

Den här åtgärdsmodulen ändrar etiketten för ett e-postmeddelande som du anger.

Modulen returnerar ID:t för e-postmeddelandet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Gmail]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-gmail-to-workfront-fusion" class="MCXref xref">Ansluta [!DNL Gmail] till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL [!DNL Gmail] Meddelande-ID]</td> 
   <td> <p> Ange eller mappa e-post-ID:t för e-postmeddelandet som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Labels to add]</p> </td> 
   <td> <p>Markera eller mappa etiketten som du vill lägga till i det markerade e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Labels to remove]</td> 
   <td> <p> Markera eller mappa etiketten som du vill ta bort från det markerade e-postmeddelandet.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Fälten [!UICONTROL Label to add] och [!UICONTROL Label to remove] läser bara in etiketter som skapats av användaren.

### Iteratorer

#### [!UICONTROL Iterate attachments]

Du kan iterera i e-postbilagor. Varje bifogad fil är ett separat paket i modulens utdata. Mer information finns i [Interpolatormodulen](/help/workfront-fusion/references/modules/iterator-module.md).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source module] </td> 
   <td> <p>Markera modulen som du vill iterera bilagor från. </p> </td> 
  </tr> 
 </tbody> 
</table>
