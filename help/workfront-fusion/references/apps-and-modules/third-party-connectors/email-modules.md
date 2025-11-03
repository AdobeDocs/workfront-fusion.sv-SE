---
title: E-postmoduler
description: I ett Adobe Workfront Fusion-scenario kan du ansluta ditt e-postkonto till flera tredjepartsprogram och -tjänster. På så sätt kan du hämta e-postmeddelanden via IMAP, skicka e-postmeddelanden via SMTP, skapa nya utkast, flytta och kopiera e-postmeddelanden från en mapp till en annan, markera e-postmeddelanden som lästa eller olästa samt ta bort e-postmeddelanden.
author: Becky
feature: Workfront Fusion
exl-id: 28a04bad-d3ef-4f3a-be93-8b04761a75e4
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 0%

---

# E-postmoduler

I ett Adobe Workfront Fusion-scenario kan du ansluta ditt e-postkonto till flera tredjepartsprogram och -tjänster. På så sätt kan du hämta e-postmeddelanden via IMAP, skicka e-postmeddelanden via SMTP, skapa nya utkast, flytta och kopiera e-postmeddelanden från en mapp till en annan, markera e-postmeddelanden som lästa eller olästa samt ta bort e-postmeddelanden.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla Adobe Workfront Workflow-paket och alla Adobe Workfront Automation and Integration-paket</p><p>Workfront Ultimate</p><p>Workfront Prime- och Select-paket med ytterligare köp av Workfront Fusion.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licenser</td> 
   <td> <p>Standard</p><p>Arbeta eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Koppla ditt e-postmeddelande till Workfront Fusion {#connect-your-email-to-workfront-fusion}

* [Anslut till Google](#connect-to-google)
* [Anslut till andra e-posttjänster (IMAP)](#connect-to-other-email-services-smap)

### Anslut till [!DNL Google]

Använd det här alternativet om du vill skapa scenarier med e-postmoduler som kräver en anslutning till ditt [!DNL Google]-konto. Det här är ett konto med begränsade scope.

Du kan skapa en anslutning till ditt [!DNL Google]-konto direkt från en e-postmodul.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon e-postmodul.
1. Välj **[!DNL Google]** som anslutningstyp.
1. Ange ett namn för anslutningen.
1. (Valfritt) Ange [!UICONTROL [!DNL Google] Client ID] och [!UICONTROL Client Secret].
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

### Anslut till andra e-posttjänster (IMAP)

Med IMAP-anslutning kan du få fjärråtkomst till din postlåda och läsa eller ändra meddelanden i din postlåda. IMAP-anslutningen används av de flesta e-postmoduler.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon e-postmodul.
1. Välj **[!UICONTROL Others (SMTP)]** som anslutningstyp.
1. Ange en **[!UICONTROL Name]** för anslutningen.
1. Välj **[!UICONTROL Email provider]** i listan. Om din e-postleverantör inte finns med i listan väljer du Annan.
1. Ange **[!UICONTROL User name]** och **[!UICONTROL Password]** för e-postkontot.
1. (Villkorligt) Om din leverantör inte finns med i listan anger du din **[!UICONTROL SMTP server]** och **[!UICONTROL Port]** och anger om du vill **[!UICONTROL Use a secure connection (TLS)]**. Du hittar den här informationen i avsnittet [!UICONTROL Help] för din postlåda. Kontakta din e-postleverantör om du inte har den här informationen tillgänglig.
1. Om du vill använda ett självsignerat certifikat aktiverar du alternativet **Avvisa oauktoriserade certifikat** och överför ditt självsignerade certifikat. Instruktioner finns i [Överföra ett självsignerat certifikat](#upload-a-self-signed-certificate)
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

#### Överför ett självsignerat certifikat

Så här lägger du till ett självsignerat certifikat:

1. Klicka på **Extract**.
1. Välj vilken typ av fil du extraherar.
1. Markera filen som innehåller certifikatet eller certifikatet.
1. Ange lösenordet för filen.
1. Klicka på **Spara** för att extrahera filen och återgå till modulinställningarna.

## [!UICONTROL Email]-moduler och deras fält

När du konfigurerar [!UICONTROL Email]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

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

Den här utlösarmodulen startar ett scenario när ett nytt e-postmeddelande tas emot för bearbetning enligt angivna villkor.

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
  <tr> 
   <td role="rowheader">[!UICONTROL Subject] </td> 
   <td> <p>Ange ämnet för det e-postmeddelande som du vill titta på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Phrase] </td> 
   <td> <p>Ange eventuella nyckelord om du bara vill se de e-postmeddelanden som innehåller nyckelorden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark message(s) as read when fetched]</td> 
   <td> <p>Aktivera det här alternativet om du vill markera det olästa e-postmeddelandet som läst när informationen har hämtats.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Ange eller mappa det högsta antalet e-postmeddelanden som Workfront Fusion ska returnera under en körningscykel för ett scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [[!UICONTROL Copy an Email]](#copy-an-email)
* [[!UICONTROL Create a Draft]](#create-a-draft)
* [[!UICONTROL Delete an Email]](#delete-an-email)
* [[!UICONTROL Get Emails]](#get-emails)
* [[!UICONTROL Mark an Email as Read]](#mark-an-email-as-read)
* [[!UICONTROL Mark an Email as Unread]](#mark-an-email-as-unread)
* [[!UICONTROL Move an Email]](#move-an-email)
* [[!UICONTROL Send an Email]](#send-an-email)

#### [!UICONTROL Copy an Email]

Den här åtgärdsmodulen kopierar ett e-postmeddelande eller ett utkast till en markerad mapp.

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
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill kopiera till målmappen.</p> <p>Du kan hämta UID för e-postmeddelandet genom att använda modulen [!UICONTROL Email] &gt; [!UICONTROL Watch Email] eller [!UICONTROL Search Email] .</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Draft]

Den här åtgärdsmodulen skapar och lägger till ett nytt utkast i en markerad mapp.

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
  <tr> 
   <td role="rowheader">[!UICONTROL Content] </td> 
   <td> <p>Ange eller mappa e-postinnehållet i HTML-format med HTML-taggar eller i oformaterad text.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Ange filnamnet, inklusive filtillägget. </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Ange sökvägen till den mapp där du vill överföra den bifogade filen.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Ange innehålls-ID:t som den bifogade filen (bilden) ska infogas i innehållet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>För varje e-postadress som du vill skicka en kopia av det här e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger e-postadressen. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> För varje e-postadress som du vill skicka en kopia av det här e-postmeddelandet till utan att e-postadressen visas i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger e-postadressen.</p> </td> 
  </tr> 
  <!--<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Enter or map the email address (and name, if needed) that appears in the [!UICONTROL From] field in the email. </p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code>.</p> <p>Note:  Normally, Workfront Fusion uses the email address that you entered when creating the connection as the sender address. If you enter any other email address, an error may occur when sending a message because your account may not have permission to send emails from a different address than your own. E.g. <code>test@mail.com</code> or "<code>John Bush" test@email.com</code>.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Sender]</p> </td> 
   <td> <p>Enter or map the email address that appears in the [!UICONTROL Sender] field in the email.</p> <p>Tip:  If you are unsure whether to use this field or the From field, we recommend choosing the From field.</p> <p>Important: Use the correct syntax: <code>name@email.com</code> or <code>"Name" name@email.com</code></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Reply-To]</td> 
   <td> <p> If you want replies to this email sent to a different address than the "[!UICONTROL from]" address, enter the email address where you want replies to this email sent.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL In-Reply-To]</td> 
   <td> <p> If you are replying to a specific email, enter or map the ID of the email you are replying to.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL References] </td> 
   <td> <p>Enter the message IDs of all the replies in the thread.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Priority]</p> </td> 
   <td> <p>Select the priority of the email:</p> 
    <ul> 
     <li>[!UICONTROL High]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL Low]</li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Headers]</p> </td> 
   <td> <p>Add the headers:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Key]</strong> </p> <p>Add the key. For example, Sender, Date, To, and so on.</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Enter the value for the key.</p> </li> 
    </ul> </td> 
  </tr> -->
 </tbody> 
</table>

#### [!UICONTROL Delete an Email]

Den här åtgärdsmodulen tar bort ett e-postmeddelande eller ett utkast från den markerade mappen.

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
   <td>Markera mappen som innehåller e-postmeddelandet som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill ta bort.</p> <p>Du kan hämta e-postmeddelandets UID genom att använda modulen E-post &gt; Bevaka e-post eller [!UICONTROL Search Email].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expunge]</td> 
   <td> <p>Aktivera det här alternativet om du vill ta bort alla meddelanden som har flaggats som [!UICONTROL Deleted] permanent i den öppna postlådan.</p> <p>Obs! I [!DNL Gmail] styrs det här beteendet av inställningen i avsnittet [!UICONTROL Settings] &gt;[!UICONTROL Forwarding POP/IMAP in IMAP access].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Emails]

Den här modulen returnerar e-postmeddelanden som matchar de angivna villkoren.

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
   <td role="rowheader">[!UICONTROL Recipient Email]</td> 
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
   <td> <p>Ange eller mappa nyckelord om du bara vill hämta e-postmeddelanden som innehåller nyckelorden.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email ID (UID)]</td> 
   <td> <p> Ange e-post-ID (UID) för e-postmeddelandet vars information du vill hämta.</p> <p>Du kan hämta UID för e-postmeddelandet med Workfront Fusions [!UICONTROL &#x200B; Watch Email]-modul eller [!UICONTROL Search Email]-modul.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of results]</td> 
   <td> <p> Det högsta antalet e-postmeddelanden som Workfront Fusion får returnera under en körningscykel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Continue the execution of the route even if the module returns no results]</td> 
   <td> <p> Välj om du vill fortsätta att köra modulen även om inga resultat returneras.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Mark an Email as Read]

Den här åtgärdsmodulen markerar ett e-postmeddelande eller ett utkast i en markerad mapp som läst genom att ange flaggan [!UICONTROL Read].

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
   <td>Markera den mapp som innehåller det e-postmeddelande som du vill markera som läst.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill markera som läst.</p> <p>Du kan hämta e-postmeddelandets UID genom att använda modulen E-post &gt; Bevaka e-post eller [!UICONTROL Search Email].</p> </td> 
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
   <td>Markera den mapp som innehåller det e-postmeddelande som du vill markera som oläst. Exempel: Primär.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill markera som oläst.</p> <p>Du kan hämta e-postmeddelandets UID genom att använda modulen E-post &gt; Bevaka e-post eller [!UICONTROL Search Email].</p> </td> 
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
   <td>Markera mappen som innehåller e-postmeddelandet som du vill flytta. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Destination Folder]</td> 
   <td> <p> Markera den mapp som du vill lägga till e-postmeddelandet i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Email ID (UID)]</p> </td> 
   <td> <p>Ange e-postadressen till UID-postmeddelandet som du vill flytta till målmappen.</p> <p>Du kan hämta e-postmeddelandets UID genom att använda modulen E-post &gt; Bevaka e-post eller [!UICONTROL Search Email].</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send an Email]

Skickar ett nytt e-postmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt e-postkonto till Workfront Fusion finns i <a href="#connect-your-email-to-workfront-fusion" class="MCXref xref">Ansluta ditt e-postmeddelande till [!UICONTROL Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Save Message after Sending]</td> 
   <td>När e-postmeddelandet har skickats sparas det i din postlåda. Aktivera det här alternativet om du vill spara e-postmeddelanden som skickats med Workfront Fusion till mappen <i>[!UICONTROL Sent mail]</i> eller en annan mapp i din postlåda. Vissa e-posttjänster, till exempel [!DNL Gmail], sparar skickade meddelanden automatiskt.</td> 
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
   <td> <p>Ange eller mappa e-postinnehållet i HTML-format med hjälp av HTML-taggar eller i oformaterad text, beroende på vad du väljer i fältet [!UICONTROL Content Type].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File name]</strong> </p> <p>Ange filnamnet, inklusive filtillägget. </p> </li> 
     <li> <p><strong>[!UICONTROL Data]</strong> </p> <p>Ange sökvägen till den mapp där du vill överföra den bifogade filen.</p> </li> 
     <li> <p><strong>[!UICONTROL Content-ID]</strong> </p> <p>Ange innehålls-ID:t som den bifogade filen (bilden) ska infogas i innehållet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy Recipient] </td> 
   <td> <p>För varje e-postadress som du vill skicka en kopia av det här e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger e-postadressen. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blind Copy Recipient]</td> 
   <td> <p> För varje e-postadress som du vill skicka en kopia av det här e-postmeddelandet till utan att e-postadressen visas i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger e-postadressen.</p> </td> 
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
<tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL From] </td> 
   <td> <p>Ange eller mappa e-postadressen (och namnet om det behövs) som visas i fältet [!UICONTROL From] i e-postmeddelandet. </p> <p>Viktigt: Använd rätt syntax: <code>name@email.com</code> eller <code>"Name" name@email.com</code>.</p> <p>Obs! Normalt används den e-postadress som du angav när du skapade anslutningen som avsändaradress i Workfront Fusion. Om du anger en annan e-postadress kan ett fel inträffa när du skickar ett meddelande, eftersom ditt konto kanske inte har behörighet att skicka e-post från en annan adress än din egen. Exempel: <code>test@mail.com</code> eller <code>John Bush" test@email.com</code>.</p> </td> 
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
