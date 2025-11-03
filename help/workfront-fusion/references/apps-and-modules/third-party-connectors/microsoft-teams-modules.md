---
title: Microsoft Teams moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder team samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: d3a37c06-8f92-4065-bc00-c35f84b03f82
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '3635'
ht-degree: 0%

---

# Microsoft Teams moduler

<!-- ADD REDIRECTS -->

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Microsoft Teams och ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

Om du vill använda Microsoft Teams-moduler måste du ha ett Microsoft Teams-konto som kan utföra åtgärden i modulen.

## Ansluta Microsoft Teams till Workfront Fusion

Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i [Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

## Microsoft Teams-moduler och deras fält

När du konfigurerar Microsoft Teams-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Microsoft Teams-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Team](#team)
* [Kanal](#channel)
* [Meddelande](#message)
* [medlem](#member)
* [Onlinemöte](#online-meeting)
* [Övriga](#other)

### Team

* [Skapa ett team från en grupp](#create-a-team-from-a-group)
* [Skapa en Office 365-grupp](#create-an-office-365-group)
* [Ta bort ett team eller en grupp](#delete-a-team-or-group)
* [Skaffa ett team](#get-a-team)
* [Lista alla team och grupper](#list-all-teams-and-groups)
* [Lista anslutna team](#list-joined-teams)
* [Uppdatera ett team](#update-a-team)
* [Se teamen](#watch-teams)

#### Skapa ett team från en grupp

Den här åtgärdsmodulen skapar ett team från en befintlig Microsoft Office 365-grupp och konfigurerar inställningar för det nya teamet.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupp-ID</td> 
   <td> <p>Markera gruppen som du vill skapa ett team från.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Tillåt medlemmar att skapa och uppdatera kanaler</td> 
   <td>Välj om du vill tillåta medlemmar att skapa och uppdatera kanaler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt medlemmar att ta bort kanaler</td> 
   <td>Välj om du vill tillåta medlemmar att ta bort kanaler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt medlemmar att lägga till och ta bort program</td> 
   <td>Välj om du vill tillåta medlemmar att lägga till och ta bort program.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt medlemmar att skapa, uppdatera och ta bort flikar</td> 
   <td>Välj om du vill tillåta medlemmar att skapa, uppdatera och ta bort flikar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt medlemmar att skapa och ta bort anslutningar</td> 
   <td>Välj om du vill tillåta medlemmar att skapa och ta bort kopplingar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt användare att redigera sina meddelanden</td> 
   <td>Välj om du vill tillåta användare att redigera sina meddelanden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt användare att ta bort sina meddelanden</td> 
   <td>Välj om du vill tillåta användare att ta bort sina meddelanden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt ägare att ta bort meddelanden</td> 
   <td>Välj om du vill tillåta ägare att ta bort meddelanden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt @team-omnämnanden</td> 
   <td>Välj om du vill tillåta @team-omnämnanden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt @channel-omnämnanden</td> 
   <td>Välj om du vill tillåta @channel-omnämnanden.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt Giphy</td> 
   <td>Välj om du vill tillåta Giphy-användning för det här teamet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt klistermärken och memes</td> 
   <td>Välj om du vill tillåta användare att inkludera etiketter och PM.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt anpassade PM</td> 
   <td>Välj om du vill tillåta användare att ta med egna PM.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt gäster att skapa och uppdatera kanaler</td> 
   <td>Välj om du vill tillåta gäster att skapa och uppdatera kanaler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillåt gäster att ta bort kanaler</td> 
   <td>Välj om du vill tillåta gäster att ta bort kanaler.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en Office 365-grupp

Den här åtgärdsmodulen skapar en grupp i Microsoft Office 365.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Visningsnamn</td> 
   <td> <p>Ange eller mappa namnet som den här gruppen visar i sin adressbok.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Alias för grupp</td> 
   <td>Ange eller mappa e-postalias för den här gruppen. Du kan inkludera gemener, siffror och understreck. För Office 365-grupptypen är detta gruppens e-postalias ([Alias]@[Din domän].onmicrosoft.com). För säkerhetsgruppstyp fungerar aliaset som ett smeknamn.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupptyp</td> 
   <td>Ange om du skapar en Office 365-grupp eller en säkerhetsgrupp.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Beskrivning</td> 
   <td>Ange eller mappa en beskrivning för gruppen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Säkerhet aktiverad</td> 
   <td>Aktivera det här alternativet om du vill att gruppen ska vara skyddad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ägare</td> 
   <td>Välj ägare för gruppen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Medlemmar</td> 
   <td>Välj medlemmar för den här gruppen.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort ett team eller en grupp

Den här åtgärdsmodulen tar bort det angivna teamet eller gruppen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupp-ID</td> 
   <td> <p>Ange eller mappa ID:t för gruppen som du vill ta bort.</p> 
   </tr> 
 </tbody> 
</table>

#### Skaffa ett team

Den här modulen hämtar egenskaper och relationer för det angivna Microsoft-teamet eller Office 365-gruppen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupp-ID</td> 
   <td> <p>Ange eller mappa ID:t för gruppen som du vill hämta information för.</p> 
   </tr> 
 </tbody> 
</table>

#### Lista alla team och grupper

I den här modulen visas alla team i Microsoft Teams och Office 365-grupper som är kopplade till organisationen. Du kan filtrera så att bara resultat som uppfyller de villkor du anger returneras.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filter</td> 
   <td> <p>Du kan ställa in ett filter så att det bara returnerar team och grupper som uppfyller de villkor du väljer.</p> <p>För varje filter anger du fältet som du vill att filtret ska utvärderas, operatorn och värdet som du vill att filtret ska tillåta. Du kan använda mer än ett filter genom att lägga till OCH- eller OR-regler.</p> </td> 
   </tr> 
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det högsta antalet team eller grupper som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>


#### Lista anslutna team

Den här åtgärdsmodulen visar de team som har anslutits av användaren som är kopplad till anslutningen som används i den här modulen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det högsta antalet team eller grupper som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera ett team

Den här åtgärdsmodulen uppdaterar egenskaperna för de angivna teamen i Microsoft Teams- eller Office 365-gruppen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Visningsnamn</td> 
   <td> <p>Ange eller mappa namnet som den här gruppen visar i sin adressbok.</p> 
   </tr> 
  <tr> 
   <td role="rowheader">Alias för grupp</td> 
   <td>Ange eller mappa e-postalias för den här gruppen. Du kan inkludera gemener, siffror och understreck. För Office 365-grupptypen är detta gruppens e-postalias ([Alias]@[Din domän].onmicrosoft.com). För säkerhetsgrupptyp fungerar aliasfunktionerna som ett smeknamn.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Beskrivning</td> 
   <td>Ange eller mappa en beskrivning för gruppen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Säkerhet aktiverad</td> 
   <td>Aktivera det här alternativet om du vill att gruppen ska vara skyddad.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Synlighet</td> 
   <td>Ange synlighet för Office 365-gruppen.</td> 
  </tr> 
 </tbody> 
</table>

#### Se teamen

Den här utlösarmodulen startar ett scenario när ett team skapas.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filter</td> 
   <td> <p>Du kan ställa in ett filter så att det bara bevakar grupper och grupper som uppfyller de kriterier du väljer.</p> <p>För varje filter anger du fältet som du vill att filtret ska utvärderas, operatorn och värdet som du vill att filtret ska tillåta. Du kan använda mer än ett filter genom att lägga till OCH- eller OR-regler.</p> </td> 
   </tr> 
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det högsta antalet team eller grupper som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

### Kanal

* [Skapa en kanal](#create-a-channel)
* [Ta bort en kanal](#delete-a-channel)
* [Skaffa en kanal](#get-a-channel)
* [Visa kanaler](#list-channels)
* [Uppdatera en kanal](#update-a-channel)

#### Skapa en kanal

Den här åtgärdsmodulen skapar en ny kanal för det angivna teamet.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Välj det team i Microsoft Teams som du vill skapa en kanal för.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanalnamn</td> 
   <td>Ange eller mappa ett namn för den nya kanalen.</td> 
  </tr> 
  <tr> 
   <td>Beskrivning</td> 
   <td>Ange eller mappa en beskrivning för den nya kanalen.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en kanal

Den här åtgärdsmodulen tar bort den angivna kanalen från ett Microsoft Team.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Ange eller mappa ID:t för det team i Microsoft Teams som du vill ta bort en kanal från.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Ange eller mappa ID:t för kanalen som du vill ta bort.</td> 
  </tr> 
  </tbody> 
</table>

#### Skaffa en kanal

Den här modulen hämtar egenskaper och relationer för en kanal.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Ange eller mappa ID:t för det team i Microsoft Teams som äger den kanal du vill hämta information för.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Ange eller mappa ID:t för kanalen som du vill hämta information för.</td> 
  </tr> 
  </tbody> 
</table>

#### Visa kanaler

I den här modulen visas kanaler som ägs av det angivna teamet i Microsoft Teams.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Välj det team i Microsoft Teams som du vill visa kanaler för.</p> </td> 
   </tr> 
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det maximala antalet kanaler som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
  </tbody> 
</table>

#### Uppdatera en kanal

Den här åtgärdsmodulen uppdaterar beskrivningen av den angivna kanalen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Välj det team i Microsoft Teams som äger den kanal du vill uppdatera.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanalnamn</td> 
   <td>Ange eller mappa namnet på kanalen som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td>Beskrivning</td> 
   <td>Ange eller mappa den nya beskrivningen för kanalen.</td> 
  </tr> 
 </tbody> 
</table>

### Meddelande

* [Svara på ett kanalmeddelande](#reply-to-a-channel-message)
* [Skicka ett meddelande](#send-a-message)
* [Titta på meddelanden](#watch-messages)
* [Se nya svar](#watch-new-replies)

#### Svara på ett kanalmeddelande

Den här åtgärdsmodulen skapar ett svar på ett meddelande i den angivna kanalen.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Välj det team i Microsoft Teams som äger den kanal som innehåller meddelandet som du vill svara på.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Markera kanalen som innehåller meddelandet som du vill svara på.</td> 
  </tr> 
  <tr> 
   <td>Meddelande-ID</td> 
   <td>Ange eller mappa ID:t för meddelandet som du vill svara på.</td> 
  </tr> 
  <tr> 
   <td>Innehållstyp</td> 
   <td>Ange om du vill skicka meddelandet i oformaterad text eller HTML-format.</td> 
  </tr> 
  <tr> 
   <td>Svarsmeddelande</td> 
   <td>Ange eller mappa texten i svarsmeddelandet som du vill skicka.</td> 
  </tr> 
 </tbody> 
</table>

#### Skicka ett meddelande

Den här åtgärdsmodulen skickar ett meddelande till en teamkanal eller till en chatt.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Meddelandetyp/td&gt; 
   <td> <p>Välj om du vill skicka ett kanalmeddelande eller ett chattmeddelande.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Om du skickar ett meddelande till en kanal anger eller mappar du ID:t för det team i Microsoft Teams som äger den kanal som du vill skicka ett meddelande till.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Om du skickar ett meddelande till en kanal anger eller mappar du ID:t för den kanal som du vill skicka ett meddelande till.</td> 
  </tr> 
  <tr> 
   <td>Skapa en ny chatt</td> 
   <td>Om du skickar ett chattmeddelande väljer du om du vill skapa en ny chatt.
   <ul><li><b>Ja</b><p>Välj om du vill ha en personlig chatt eller en gruppchatt och välj den medlem som du vill inkludera i chatten. Du måste välja den användare som är associerad med den anslutning som den här modulen använder, och en chatt får endast innehålla den användaren och en annan användare.</p><p>Om du skapar en gruppchatt kan du ange ett ämne i ämnesfältet.</p>
   <li><b>Nej</b><p>Ange eller mappa ID:t för det team som äger kanalen som du vill skicka ett meddelande till och ange eller mappa sedan ID:t för kanalen.</td> 
  </tr> 
  <tr> 
   <td>Meddelande</td> 
   <td>Ange eller mappa texten i meddelandet som du vill skicka.</td> 
  </tr> 
  <tr> 
   <td>Innehållstyp</td> 
   <td>Ange om du vill skicka meddelandet i oformaterad text eller HTML-format.</td> 
  </tr> 
 </tbody> 
</table>

#### Titta på meddelanden

Den här utlösarmodulen startar ett scenario när ett meddelande skickas till en teamkanal eller till en chatt.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Typ av meddelanden att bevaka</td> 
   <td> <p>Välj om du vill titta på kanalmeddelanden eller chattmeddelanden.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Om du tittar på kanalmeddelanden väljer du det team i Microsoft Teams som äger den kanal som du tittar efter meddelanden i.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Om du tittar på kanalmeddelanden väljer du den kanal som du vill bevaka för meddelanden.</td> 
  </tr> 
  <tr> 
   <td>Chatt-ID</td> 
   <td>Om du tittar på chattmeddelanden väljer du den chatt du vill bevaka för meddelanden.</td> 
  </tr> 
  <tr> 
   <td>Maximalt antal returnerade meddelanden</td> 
   <td>Ange det högsta antalet meddelanden som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

#### Se nya svar

Den här utlösarmodulen startar ett scenario när ett nytt svar tas emot av det angivna meddelandet.

Den här modulen är inte tillgänglig för personliga konton.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Team-ID</td> 
   <td> <p>Välj det team i Microsoft Teams som äger den kanal som du tittar efter svar på.</p> </td> 
   </tr> 
  <tr> 
   <td>Kanal-ID</td> 
   <td>Välj den kanal som du vill bevaka för svar.</td> 
  </tr> 
  <tr> 
   <td>Meddelande-ID</td> 
   <td>Välj den chatt som du vill bevaka för svar.</td> 
  </tr> 
  <tr> 
   <td>Maximalt antal returnerade svar</td> 
   <td>Ange det maximala antalet svar som Workfront Fusion returnerar under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

### medlem

* [Lägg till en medlem](#add-a-member)
* [Lägga till en medlem i en grupp](#add-a-member-to-a-group)

#### Lägg till en medlem

Den här åtgärdsmodulen lägger till en medlem i Microsoft Teams.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Medlemsnamn</td> 
   <td> <p>Ange eller mappa namnet på medlemmen som du vill lägga till i Microsoft Teams.</p> </td> 
   </tr> 
  <tr> 
   <td>Lösenord</td> 
   <td>Ange eller mappa lösenordet för medlemmen.</td> 
  </tr> 
 </tbody> 
</table>

#### Lägga till en medlem i en grupp

Den här åtgärdsmodulen lägger till en medlem i en Office 365-grupp.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Grupp-ID</td> 
   <td> <p>Markera gruppen som du vill lägga till en medlem i.</p> </td> 
   </tr> 
  <tr> 
   <td>Medlems-ID</td> 
   <td>Markera den medlem som du vill lägga till i gruppen.</td> 
  </tr> 
 </tbody> 
</table>

### Onlinemöte

* [Skapa ett onlinemöte](#create-an-online-meeting)
* [Ta bort ett onlinemöte](#delete-an-online-meeting)
* [Få ett onlinemöte](#get-an-online-meeting)
* [Uppdatera ett onlinemöte](#update-an-online-meeting)

#### Skapa ett onlinemöte

Den här åtgärdsmodulen skapar ett fristående möte som inte är associerat med en händelse i användarens kalender. Mötet visas inte i användarens kalender.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Ämne</td> 
   <td>Ange eller mappa ett ämne för det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Startdatum och -tid</td> 
   <td>Ange eller mappa det datum och den tidpunkt då du vill att mötet ska starta. En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Slutdatum och sluttid</td> 
   <td>Ange eller mappa det datum och den tidpunkt då du vill att mötet ska avslutas. En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåtna presentatörer</td> 
   <td>Välj den grupp som tillåts presentera i det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Bilagor</td> 
   <td>För varje deltagare som du vill lägga till i mötet klickar du på <b>Lägg till objekt</b> och väljer deltagarens namn och roll.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt deltagare att aktivera sina kameror</td> 
   <td>Välj om du vill att deltagarna ska kunna aktivera sina egna kameror.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt deltagare att aktivera sina mikrofoner</td> 
   <td>Välj om du vill att deltagarna ska kunna aktivera sina egna mikrofoner.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt möteschatt</td> 
   <td>Välj om du vill att möteschatten ska aktiveras, inaktiveras eller begränsas till mötessamtalets längd</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt Teams-reaktioner</td> 
   <td>Välj om du vill aktivera Teams-reaktioner för det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tråd-ID</td> 
   <td>Ange eller mappa ID:t för en tråd som är associerad med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Meddelande-ID</td> 
   <td>Ange eller mappa ID:t för ett meddelande som är associerat med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Meddelande-ID för svarskedja</td> 
   <td>Ange eller mappa ID:t för den svarskedja som är associerad med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Announce entry and exit</td> 
   <td>Välj om du vill att mötet ska tillkännages när deltagarna går in eller avslutar.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Omfång</td> 
   <td>Markera den grupp deltagare som kan kringgå väntetiden i lobbyn. Dessa deltagare ansluter sig till mötet direkt.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Möjliggör för användare med uppringd anslutning att kringgå lobbying</td> 
   <td>Välj om du vill att användare med modem ska kunna kringgå lobbyn.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Spela in automatiskt</td> 
   <td>Välj om du vill spela in mötet automatiskt.</td> 
   </tr> 
   </tbody> 
</table>

#### Ta bort ett onlinemöte

Den här åtgärdsmodulen tar bort onlinemötet med det angivna ID:t.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Mötes-ID</td> 
   <td> <p>Ange eller mappa ID:t för mötet som du vill ta bort.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Få ett onlinemöte

Den här åtgärdsmodulen hämtar information om onlinemötet med det angivna ID:t.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Mötes-ID</td> 
   <td> <p>Ange eller mappa ID:t för mötet som du vill hämta information för.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Uppdatera ett onlinemöte

Den här åtgärdsmodulen uppdaterar onlinemötet med det angivna ID:t.



<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Mötes-ID</td> 
   <td>Ange eller mappa ID:t för mötet som du vill uppdatera.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Ämne</td> 
   <td>Ange eller mappa ett ämne för det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Startdatum och -tid</td> 
   <td>Ange eller mappa det datum och den tidpunkt då du vill att mötet ska starta. En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Slutdatum och sluttid</td> 
   <td>Ange eller mappa det datum och den tidpunkt då du vill att mötet ska avslutas. En lista över datumformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåtna presentatörer</td> 
   <td>Välj den grupp som tillåts presentera i det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Bilagor</td> 
   <td>För varje deltagare som du vill lägga till i mötet klickar du på <b>Lägg till objekt</b> och väljer deltagarens namn och roll.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt deltagare att aktivera sina kameror</td> 
   <td>Välj om du vill att deltagarna ska kunna aktivera sina egna kameror.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt deltagare att aktivera sina mikrofoner</td> 
   <td>Välj om du vill att deltagarna ska kunna aktivera sina egna mikrofoner.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt möteschatt</td> 
   <td>Välj om du vill att möteschatten ska aktiveras, inaktiveras eller begränsas till mötessamtalets längd</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tillåt Teams-reaktioner</td> 
   <td>Välj om du vill aktivera Teams-reaktioner för det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Tråd-ID</td> 
   <td>Ange eller mappa ID:t för en tråd som är associerad med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Meddelande-ID</td> 
   <td>Ange eller mappa ID:t för ett meddelande som är associerat med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Meddelande-ID för svarskedja</td> 
   <td>Ange eller mappa ID:t för den svarskedja som är associerad med det här mötet.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Announce entry and exit</td> 
   <td>Välj om du vill att mötet ska tillkännages när deltagarna går in eller avslutar.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Omfång</td> 
   <td>Markera den grupp deltagare som kan kringgå väntetiden i lobbyn. Dessa deltagare ansluter sig till mötet direkt.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Möjliggör för användare med uppringd anslutning att kringgå lobbying</td> 
   <td>Välj om du vill att användare med modem ska kunna kringgå lobbyn.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Spela in automatiskt</td> 
   <td>Välj om du vill spela in mötet automatiskt.</td> 
   </tr> 
   </tbody> 
</table>

### Övriga

* [Kontrollera om användare finns](#check-presence-of-users)
* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Sök efter användare](#search-users)

#### Kontrollera om användare finns

Den här åtgärdsmodulen kontrollerar om de valda användarna finns på Microsoft Teams.

Den här modulen stöder inte personliga konton.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Användar-ID</td> 
   <td> <p>Markera de användare som du vill kontrollera närvaro för.</p> </td> 
   </tr> 
 </tbody> 
</table>

#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör en anpassad begäran till Microsoft Teams API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code>https://graph.microsoft.com</code>. Exempel:<code> /v1.0/groups</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
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

#### Sök efter användare

Den här modulen söker efter användare med villkor som du anger.

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Microsoft Teams-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filter</td> 
   <td> <p>Du kan ange att ett filter endast ska returnera användare som uppfyller de villkor som du väljer.</p> <p>För varje filter anger du fältet som du vill att filtret ska utvärderas, operatorn och värdet som du vill att filtret ska tillåta. Du kan använda mer än ett filter genom att lägga till OCH- eller OR-regler.</p> </td> 
   </tr> 
  <tr> 
   <td>Maximalt antal returnerade resultat</td> 
   <td>Ange det högsta antalet team eller grupper som Workfront Fusion ska returnera under en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>
