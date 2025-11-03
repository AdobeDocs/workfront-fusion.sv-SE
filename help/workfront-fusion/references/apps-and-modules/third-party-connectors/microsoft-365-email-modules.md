---
title: Microsoft Office 365-e-post
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Microsoft Office 365-e-post och ansluta den till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 5d4072ba-c598-4347-a42f-c59c7add0a1b
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2452'
ht-degree: 0%

---

# [!DNL Microsoft Office 365 Email] moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!UICONTROL Microsoft Office 365 Email] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

## Förutsättningar

Du måste ha ett [!DNL Microsoft Office 365 Email]-konto för att kunna använda [!DNL Microsoft Office 365 Email]-moduler.

## Information om e-post-API för Microsoft Office 365

E-postkopplingen för Microsoft Office 365 använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.6.5</td> 
  </tr>
 </tbody> 
 </table>

## Ansluta tjänsten [!DNL Office 365 Email] till Workfront Fusion

Instruktioner om hur du ansluter ditt [!DNL Office 365 Email]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

## [!DNL Microsoft Office 365 Email]-moduler och deras fält

När du konfigurerar [!DNL Microsoft Office 365 Email]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Microsoft Office 365 Email] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Meddelande](#message)
* [Utkastmeddelande](#draft-message)
* [Bilaga](#attachment)
* [Övriga](#other)

### Meddelande

* [[!UICONTROL Create and Send a Message (legacy)]](#create-and-send-a-message)
* [[!UICONTROL Delete a Message]](#delete-a-message)
* [[!UICONTROL Get a message]](#get-a-message)
* [[!UICONTROL Move a Message]](#move-a-message)
* [[!UICONTROL Search messages]](#search-messages)
* [[!UICONTROL Watch Messages]](#watch-messages)



#### [!UICONTROL Create and Send a Message (legacy)]

Den här åtgärdsmodulen skapar och skickar ett e-postmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange eller mappa ämnesraden för meddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Ange eller mappa meddelandetexten i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj e-postmeddelandets betydelse</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source file]</strong> </p> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>För varje rubrik som du vill lägga till i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange namnet på rubriken</p> </li> 
     <li> <p><strong>[!UICONTROL Value]</strong> </p> <p>Ange ett värde för rubriken.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Message]

Den här åtgärdsmodulen tar bort ett befintligt e-postmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som du vill ta bort.</p> </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a message]

Den här åtgärdsmodulen hämtar metadata för ett specifikt meddelande

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som du vill hämta metadata för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get MIME contents]</td> 
   <td>Aktivera det här alternativet om du vill hämta data om MIME-innehållet i meddelandet. [!UICONTROL MIME]-innehåll kan innehålla bilder, ljud, video eller andra typer av filer.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a Message]

Den här åtgärdsmodulen flyttar ett e-postmeddelande till en markerad mapp i postlådan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som du vill flytta till en annan mapp.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder] </td> 
   <td> <p>Markera eller mappa ID:t för mappen där du vill flytta meddelandet.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search messages]

Den här sökmodulen söker efter meddelanden baserat på specifika villkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>Markera den mapp som innehåller de meddelanden som du vill söka i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Ange din sökfråga. Mer information om hur du skriver en sökfråga finns i [!DNL Microsoft] supportartikeln <a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&rs=en-us&ad=us">Sök efter e-post och personer i [!DNL Outlook.com]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>Välj hur du vill beställa resultaten:</p> 
    <ul> 
     <li>[!UICONTROL Subject (Ascending or descending)]</li> 
     <li>[!UICONTROL Created Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Last Modified Date Time (Ascending or descending)]</li> 
     <li>[!UICONTROL Received Date Time (Ascending or descending)]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange det högsta antalet meddelanden som Workfront Fusion ska returnera under en körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Messages]

Den här utlösarmodulen startar ett scenario när ett nytt e-postmeddelande skickas eller tas emot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Watch Messages]</p> </td> 
   <td> <p>Markera de meddelanden som du vill bevaka:</p> 
    <ul> 
     <li>[!UICONTROL Only Unread]</li> 
     <li>[!UICONTROL Only read]</li> 
     <li>[!UICONTROL All]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mail Folder]</td> 
   <td> <p>Markera den mapp som innehåller de meddelanden som du vill bevaka.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Ange din sökfråga. Modulen returnerar meddelanden som matchar den här frågan. Mer information om hur du skriver en sökfråga finns i [!DNL Microsoft] supportartikeln <a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&rs=en-us&ad=us">Sök efter e-post och personer i [!DNL Outlook.com]</a>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange det högsta antalet meddelanden som Workfront Fusion ska returnera under en körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Utkastmeddelande

* [Skapa ett utkast](#create-a-draft-message)
* [Skicka ett utkast](#send-a-draft-message)
* [Uppdatera ett meddelande](#update-a-message)

#### [!UICONTROL Create a Draft Message]

Den här åtgärdsmodulen skapar ett nytt e-postmeddelande som ett utkast.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange ämnesraden för meddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body Content Type]</td> 
   <td>Ange om meddelandets brödtext är HTML eller Text.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Ange eller mappa meddelandetexten i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj e-postmeddelandets betydelse</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source file]</strong> </p> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send a Draft Message]

Den här åtgärdsmodulen skickar ett e-postmeddelande som är i utkast.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Draft Message ID]</td> 
   <td> <p> Markera eller mappa meddelande-ID:t för utkastet som du vill skicka.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Message]

Den här åtgärdsmodulen uppdaterar ett befintligt meddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a message ID]</td> 
   <td> <p>Välj hur du vill identifiera meddelandet som ska uppdateras:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter Manually]</strong> </p> <p>Ange eller mappa meddelande-ID:t.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Markera mappen som innehåller meddelandet som du vill uppdatera och markera sedan meddelandet</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange ämnesraden för meddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Ange meddelandetexten i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj e-postmeddelandets betydelse</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source file]</strong> </p> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Mark it as Read]</td> 
   <td>Aktivera det här alternativet om du vill markera det uppdaterade meddelandet som läst.</td> 
  </tr> 
 </tbody> 
</table>

### Bilaga

* [[!UICONTROL Download an Attachment]](#download-an-attachment)
* [[!UICONTROL List Attachments]](#list-attachments)

#### [!UICONTROL Download an Attachment]

Den här modulen hämtar den angivna bifogade filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som innehåller den bifogade filen som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Attachment ID]</td> 
   <td> <p>Ange eller mappa ID:t för den bifogade fil som du vill hämta. Du kan hitta den här idén med modulen Listbilagor.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Attachments]

Den här modulen hämtar en lista med bilagor som tillhör det angivna meddelandet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som du vill hämta bilagor från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antalet bilagor som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [[!UICONTROL Add an Attachment]](#add-an-attachment)
* [Skapa och skicka ett meddelande](#create-and-send-a-message)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Add an Attachment]

Den här modulen lägger till en stor bifogad fil i ett meddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Message ID]</td> 
   <td> <p> Markera eller mappa ID:t för meddelandet som du vill lägga till en bifogad fil i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Välj en fil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create and Send a Message]

Den här åtgärdsmodulen skapar och skickar ett e-postmeddelande.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>Ange eller mappa ämnesraden för meddelandet.</p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td> <p>Ange eller mappa meddelandetexten i e-postmeddelandet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>Välj e-postmeddelandets betydelse</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL To Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC Recipients]</p> </td> 
   <td> <p><p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Bcc Recipients]</p> </td> 
   <td> <p>För varje mottagare som du vill skicka en kopia av e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange kontaktens e-postadress.</p> </li> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange kontaktens namn.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachments]</p> </td> 
   <td> <p>För varje bifogad fil som du vill lägga till i e-postmeddelandet klickar du på <b>Lägg till objekt</b> och anger följande:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source file]</strong> </p> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet Message Headers]</td> 
   <td> <p>Lägg till meddelanderubriker för e-postmeddelandet.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>Ange namnet på rubriken</p> </li> 
     <li> <p><strong>[!UICONTROL Email Address]</strong> </p> <p>Ange ett värde för rubriken.</p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL From email address]</td> 
   <td> <p> Om du vill använda en delad e-postadress anger du adressen här. Den användare vars autentiseringsuppgifter används i anslutningen som används för den här modulen måste ha åtkomst till den delade mappen.<p>Lämna det här fältet tomt om du vill använda anslutningsägarens egen e-postadress.</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Office 365]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till <code>https://graph.microsoft.com</code>. Exempel:<code> /v1.0/me/messages</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code>. Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>
