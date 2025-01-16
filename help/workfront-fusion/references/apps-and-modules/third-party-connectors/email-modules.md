---
title: E-postmoduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du ansluta ditt e-postkonto till flera tredjepartsprogram och -tjänster. På så sätt kan du hämta e-postmeddelanden via IMAP, skicka e-postmeddelanden via SMTP, skapa nya utkast, flytta och kopiera e-postmeddelanden från en mapp till en annan, markera e-postmeddelanden som lästa eller olästa samt ta bort e-post.
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '2103'
ht-degree: 0%

---

# E-postmoduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du ansluta ditt e-postkonto till flera tredjepartsprogram och -tjänster. På så sätt kan du hämta e-post via IMAP, skicka e-postmeddelanden via SMTP, skapa nya utkast, flytta och kopiera e-postmeddelanden från en mapp till en annan, markera e-postmeddelanden som lästa eller olästa samt ta bort e-postmeddelanden.

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

## Koppla ditt e-postmeddelande till Workfront Fusion {#connect-your-email-to-workfront-fusion}

* [Anslut till Google](#connect-to-google)
* [Anslut till andra e-posttjänster (SMAP)](#connect-to-other-email-services-smap)

### Anslut till [!DNL Google]

Använd det här alternativet om du vill skapa scenarier med e-postmoduler som kräver en anslutning till ditt [!DNL Google]-konto. Det här är ett konto med begränsade scope.

Du kan skapa en anslutning till ditt [!DNL Google]-konto direkt från en e-postmodul.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon e-postmodul.
1. Välj **[!DNL Google]** som anslutningstyp.
1. Ange ett namn för anslutningen.
1. (Valfritt) Ange [!UICONTROL [!DNL Google] Client ID] och [!UICONTROL Client Secret].
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

### Anslut till andra e-posttjänster (SMAP)

Med SMAP-anslutning kan du få fjärråtkomst till din postlåda och läsa eller ändra meddelanden i din postlåda. SMAP-anslutningen används av de flesta e-postmoduler.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon e-postmodul.
1. Välj **[!UICONTROL Others (SMTP)]** som anslutningstyp.
1. Ange en **[!UICONTROL Name]** för anslutningen.
1. Välj **[!UICONTROL Email provider]** i listan. Om din e-postleverantör inte finns med i listan väljer du Annan.
1. Ange din **[!UICONTROL Email address]**, **[!UICONTROL Your full name]**, din **[!UICONTROL User name]** och din **[!UICONTROL Password]**.
1. (Villkorligt) Om din leverantör inte finns med i listan anger du din **[!UICONTROL SMTP server]** och **[!UICONTROL Port]** och anger om du vill **[!UICONTROL Use a secure connection (TLS)]**. Du hittar den här informationen i avsnittet [!UICONTROL Help] för din postlåda. Kontakta din e-postleverantör om du inte har den här informationen tillgänglig.
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!UICONTROL Email]-moduler och deras fält

När du konfigurerar [!UICONTROL Email] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Vissa e-postfält kan redan innehålla data eftersom du använde dem i en annan modul i scenariot. Läs hjälpdokumentationen för e-post om du behöver information om dem.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>Det unika e-post-ID som kallas [!UICONTROL Email ID (UID)] är e-postens identifierare. E-post-ID:t är specifikt för var och en av e-postmapparna.

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Iteratorer](#iterators)

### Utlösare

#### [!UICONTROL Watch Emails]

Utlöses när ett nytt e-postmeddelande tas emot för bearbetning enligt angivna villkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen som innehåller e-postmeddelanden som du vill bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>Välj de villkor som du vill använda för att bevaka e-postmeddelanden:</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>Ange e-postadressen till den avsändare vars e-postmeddelanden du vill bevaka.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
   <td> <p> Ange e-postadressen till mottagaren vars e-postmeddelanden du vill bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Ange ämnet för det e-postmeddelande som du vill titta på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Ange eventuella nyckelord om du bara vill se de e-postmeddelanden som innehåller specifika fraser.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>Aktivera det här alternativet om du vill markera det olästa e-postmeddelandet som läst när informationen har hämtats.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Det högsta antalet e-postmeddelanden [!DNL Workfront Fusion] ska returneras under en körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Send an Email]](#send-an-email)
* [[!UICONTROL Create a Draft]](#create-a-draft)
* [[!UICONTROL Mark an Email as Read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an Email as Unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an Email]](#move-an-email)
* [[!UICONTROL Copy an Email]](#copy-an-email)
* [[!UICONTROL Delete an Email]](#delete-an-email)
* [[!UICONTROL Get Emails]](#get-emails)

#### [!UICONTROL Send an Email]

Skickar ett nytt e-postmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!DNL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>När e-postmeddelandet har skickats sparas det i din postlåda. Aktivera det här alternativet om du vill spara e-postmeddelanden som har skickats med [!DNL Workfront Fusion] till mappen <i>[!UICONTROL Sent mail]</i> eller en annan mapp i postlådan. Vissa e-posttjänster, till exempel [!DNL Gmail], sparar skickade meddelanden automatiskt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>Lägg till de e-postadresser som du vill skicka e-postmeddelandet till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Ange eller mappa ämnesraden för e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>Välj typ [!UICONTROL content] för e-postmeddelandet:</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plaintext]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Ange eller mappa e-postinnehållet i HTML-format med hjälp av HTML-taggar eller i oformaterad text, beroende på vad du har valt i fältet [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Lägg till en bifogad fil:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Ange filnamnet. Exempel: sample.doc.</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Ange sökvägen till mappen som du vill överföra den bifogade filen till.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Ange [!UICONTROL content ID] för att infoga den bifogade filen (bilden) i innehållet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Ange eller mappa en eller flera e-postadresser som du vill skicka en kopia av det här e-postmeddelandet till. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Ange eller mappa en eller flera e-postadresser som du vill skicka en kopia av det här e-postmeddelandet till utan att e-postadressen visas i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Ange eller mappa e-postadressen (och namnet om det behövs) som visas i fältet [!UICONTROL From] i e-postmeddelandet. </p> <p>Viktigt: Använd rätt syntax: <code>name@email.com</code> eller <code>"Name" name@email.com</code>.</p> <p>Obs! I [!DNL Workfront Fusion] används normalt den e-postadress som du angav när du skapade anslutningen som avsändaradress. Om du anger en annan e-postadress kan ett fel inträffa när du skickar ett meddelande, eftersom ditt konto kanske inte har behörighet att skicka e-post från en annan adress än din egen. Exempel: <code>test@mail.com</code> eller <code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Ange eller mappa e-postadressen som visas i fältet [!UICONTROL Sender] i e-postmeddelandet.</p> <p>Tips! Om du är osäker på om du ska använda det här fältet eller fältet Från rekommenderar vi att du väljer fältet Från.</p> <p>Viktigt: Använd rätt syntax: <code>name@email.com</code> eller <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> Om du vill att svar på det här e-postmeddelandet ska skickas till en annan adress än"från"-adressen anger du den e-postadress dit du vill att svar på det här e-postmeddelandet ska skickas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> Om du svarar på ett visst e-postmeddelande anger eller mappar du ID:t för det e-postmeddelande du svarar på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Ange meddelande-ID för alla svar i tråden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Välj e-postens prioritet:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Lägg till rubrikerna:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Lägg till nyckeln. Till exempel [!UICONTROL Sender], [!UICONTROL Date], [!UICONTROL To] och så vidare.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Ange värdet för nyckeln.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Draft]

Skapar och lägger till ett nytt utkast i en markerad mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Markera den mapp där du vill skapa e-postutkastet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL To] </td> 
   <td> <p>Ange eller mappa den e-postadress som du vill skicka e-postmeddelandet till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Ange eller mappa ämnesraden för e-postmeddelandet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Content Type]</p> </td> 
   <td> <p>Välj innehållstyp för e-postmeddelandet:</p> 
    <ul> 
     <li>HTML</li> 
     <li>[!UICONTROL Plain Text]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Ange eller mappa e-postinnehållet i HTML-format med hjälp av HTML-taggar eller i oformaterad text, beroende på vad du har valt i fältet [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>Lägg till en bifogad fil:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Ange filnamnet. Exempel: sample.doc.</p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Ange sökvägen till mappen som du vill överföra den bifogade filen till.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Ange innehålls-ID:t som den bifogade filen (bilden) ska infogas i innehållet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>Ange eller mappa en eller flera e-postadresser som du vill skicka en kopia av det här e-postmeddelandet till. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> Ange eller mappa en eller flera e-postadresser som du vill skicka en kopia av det här e-postmeddelandet till utan att e-postadressen visas i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Ange eller mappa e-postadressen (och namnet om det behövs) som visas i fältet [!UICONTROL From] i e-postmeddelandet. </p> <p>Viktigt: Använd rätt syntax: <code>name@email.com</code> eller <code>"Name" name@email.com</code>.</p> <p>Obs! I [!DNL Workfront Fusion] används normalt den e-postadress som du angav när du skapade anslutningen som avsändaradress. Om du anger en annan e-postadress kan ett fel inträffa när du skickar ett meddelande, eftersom ditt konto kanske inte har behörighet att skicka e-post från en annan adress än din egen. Exempel: <code>test@mail.com</code> eller <code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Ange eller mappa e-postadressen som visas i fältet [!UICONTROL Sender] i e-postmeddelandet.</p> <p>Tips! Om du är osäker på om du ska använda det här fältet eller fältet Från rekommenderar vi att du väljer fältet Från.</p> <p>Viktigt: Använd rätt syntax: <code>name@email.com</code> eller <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> Om du vill att svar på det här e-postmeddelandet ska skickas till en annan adress än adressen [!UICONTROL from] anger du den e-postadress dit du vill att svar på det här e-postmeddelandet ska skickas.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> Om du svarar på ett visst e-postmeddelande anger eller mappar du ID:t för det e-postmeddelande du svarar på.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Ange meddelande-ID för alla svar i tråden.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Välj e-postens prioritet:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Lägg till rubrikerna:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Lägg till nyckeln. Till exempel Avsändare, Datum, Till och så vidare.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Ange värdet för nyckeln.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Read]

Markerar ett e-postmeddelande eller ett utkast i en markerad mapp som läst genom att ange flaggan [!UICONTROL Read].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Markera den mapp i e-postmeddelandet som du vill markera som läst. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill markera som läst.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt;[!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Unread]

Markerar ett e-postmeddelande eller ett utkast i en markerad mapp som oläst genom att ange flaggan Oläst.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Markera den mapp i e-postmeddelandet som du vill markera som oläst. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill markera som oläst.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt;[!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move an Email]

Flyttar ett valt e-postmeddelande eller ett utkast till en markerad mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>Markera den mapp som innehåller e-postmeddelandet som du vill flytta e-postmeddelandet från. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Markera den mapp som du vill lägga till e-postmeddelandet i. Exempel: Arbete.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill flytta till målmappen.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt;[!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy an Email]

Kopierar ett e-postmeddelande eller ett utkast till en markerad mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Folder]</td> 
   <td>Välj den mapp som du vill kopiera e-postmeddelandet från. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Markera den mapp som du vill kopiera e-postmeddelandet till. Exempel: Arbete.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill kopiera till målmappen.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt;[!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Email]

Tar bort ett e-postmeddelande eller ett utkast från den markerade mappen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>Markera mappen för det e-postmeddelande som du vill ta bort. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill ta bort.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt;[!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>Aktivera det här alternativet om du vill tillåta modulen att permanent ta bort alla meddelanden som har flaggats som [!UICONTROL Deleted] i den öppna postlådan.</p> <p>Obs! I [!DNL Gmail] styrs det här beteendet av inställningen i avsnittet [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Emails]

Returnerar e-postmeddelanden som matchar de angivna villkoren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till [!UICONTROL Workfront Fusion] finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Anslut din e-post till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder] </td> 
   <td> <p>Markera mappen som innehåller de e-postmeddelanden som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched] </td> 
   <td> <p>Aktivera det här alternativet om du vill markera det olästa e-postmeddelandet som läst när du har hämtat informationen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Criteria]</p> </td> 
   <td> <p>Välj villkoren för de e-postmeddelanden som du vill hämta:</p> 
    <ul> 
     <li>[!UICONTROL All Emails]</li> 
     <li>[!UICONTROL Only Read Emails]</li> 
     <li>[!UICONTROL Only Unread Emails]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sender Email Address] </td> 
   <td> <p>Ange eller mappa e-postadressen till den avsändare vars e-postmeddelanden du vill hämta.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Recipient Email Address]</td> 
   <td> <p> Ange eller mappa e-postadressen till mottagaren vars e-postmeddelanden du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From date] </td> 
   <td> <p>Ange eller mappa datumet för att hämta e-postmeddelanden som bearbetas på eller efter det angivna datumet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Before date]</td> 
   <td> <p> Ange eller mappa datumet för att hämta e-postmeddelanden som bearbetats på eller före det angivna datumet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Ange eller mappa ämnet för det e-postmeddelande som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Ange eller mappa nyckelord om du bara vill hämta e-postmeddelanden som innehåller specifika fraser.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Ange e-post-ID (UID) för e-postmeddelandet vars information du vill hämta.</p> <p>Du kan hämta UID för e-postmeddelandet med hjälp av [!UICONTROL  Watch Email]-modulen eller [!UICONTROL Search Email] för [!DNL Workfront Fusion].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Det högsta antalet e-postmeddelanden [!DNL Workfront Fusion] ska returneras under en körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> Välj om du vill fortsätta att köra modulen även om inga resultat returneras.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Iteratorer

#### [!UICONTROL Iterate Attachments]

Iterates fick bilagor en i taget.

Med e-postiteratormodulen kan du hantera e-postbilagor separat. Du kan till exempel ställa in att bevaka e-postmeddelanden för att iterera e-postmeddelanden med bilagor och ta emot aviseringar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module]</td> 
   <td> <p>Markera modulen som matar ut e-postmeddelandet med de bilagor som du vill iterera igenom.</p> </td> 
  </tr> 
 </tbody> 
</table>

Mer information om iteratorer finns i [iteratormodulen](/help/workfront-fusion/references/modules/iterator-module.md).
