---
title: HubSpot CRM-moduler
description: Med Adobe Workfront Fusion HubSpot CRM-modulerna kan du övervaka händelser, poster, kontakter, ärenden, fil- och formuläröverföringar eller skapa, hämta, uppdatera och ta bort poster, kontakter, ärenden, händelser eller filer i ditt [!DNL HubSpot CRM] konto.
author: Becky
feature: Workfront Fusion
exl-id: b8a1bbcd-337e-4c92-a1a6-d6d4bab1f440
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '6638'
ht-degree: 0%

---

# [!DNL HubSpot CRM] moduler

Med Adobe Workfront Fusion [!DNL HubSpot CRM]-modulerna kan du övervaka händelser, poster, kontakter, ärenden, fil- och formulärinskickade meddelanden eller skapa, hämta, uppdatera och ta bort poster, kontakter, ärenden, händelser eller filer i ditt [!DNL HubSpot CRM]-konto.

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs</p>
   <p>eller</p>
   <p>Äldre: Workfront Fusion for Work Automation and Integration </p>
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Förutsättningar

Du måste ha ett [!DNL HubSpot CRM]-konto för att kunna använda [!DNL HubSpot CRM]-moduler.

## API-information för HubSpot CRM

HubSpot CRM-anslutningen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://api.hubapi.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v2.0.14</td> 
  </tr>
 </tbody> 
 </table>

## Anslut Adobe Workfront Fusion till [!DNL HubSpot CRM]

Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i [Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Välj anslutningstypen **HubSpot CRM** när du konfigurerar en anslutning. HubSpot CRM-typen (utgått) stöder befintliga anslutningar, men vi rekommenderar inte att du använder den för att skapa nya anslutningar.

## [!DNL HubSpot CRM]-moduler och deras fält

När du konfigurerar [!DNL Hubspot CRM]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Hubspot CRM] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [CRM-objekt](#crm-objects)
* [Register (avtal, kontakter och företag)](#records-deals-contacts-and-companies)
* [Kontakter](#contacts)
* [Erbjudanden](#deals)
* [Företag](#companies)
* [Åtaganden](#engagements)
* [Händelser och meddelanden](#events-and-notifications)
* [Filer](#files)
* [Uppgifter](#tasks)
* [Användare](#users)
* [Biljetter](#tickets)
* [Forms](#forms)
* [Sociala medier (sändning)](#social-media-broadcast)
* [Blogginlägg](#blog-posts)
  <!--* [Workflows]()-->
* [Prenumerationer](#subscriptions)
  <!--* [Associations]()-->
* [Övriga](#other)

### CRM-objekt

+++ **[!UICONTROL Search for CRM Objects]**

Den här sökmodulen söker efter CRM-objekt efter anpassade egenskaper eller efter fråga. Om du vill söka efter produkter eller radobjekt använder du en speciell anslutning med ett nödvändigt anpassat omfång.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet objekt som modulen ska returnera i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type to Search]</td> 
   <td>Välj den typ av Hubspot CRM-objekt som du vill söka efter.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Markera de egenskaper som du vill ska visas i modulens utdata. Vilka fält som är tillgängliga beror på vilket objekt du har markerat.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by] </td> 
   <td> <p>Välj hur du vill filtrera sökningen</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Query]</strong> </p> <p>Ange eller mappa frågan</p> </li> 
     <li> <p><strong>[!UICONTROL Properties]</strong> </p> <p>Ange grupper eller filter för sökningen.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td> <p>Klicka om du vill sortera resultaten. Om du väljer att sortera resultaten visas följande fält. </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Property name]</strong> </p> <p>Välj den egenskap som du vill sortera resultaten efter</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>Välj om du vill sortera resultaten i stigande eller fallande riktning.</p> </li> 
    </ul> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Startförskjutning</td> 
    <td>Ange eller mappa ID:t för det första objektet som du vill hämta information för. Den här modulen returnerar bara upp till 5 000 resultat i taget. Om du anger en startförskjutning kan du hämta andra objekt än de första 5 000. Om startförskjutningen är 5000 returnerar modulen 5000-9999.</td> 
   </tr>
 </tbody> 
</table>

+++

+++ **Bevakade CRM-objekt**

Den här utlösarmodulen startar ett scenario när ett CRM-objekt skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet objekt som modulen ska returnera i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object type to search]</td> 
   <td> <p>Välj den typ av objekt som du vill söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Välj de egenskaper som du vill ta med i utdata för den här modulen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created/Updated]</td> 
   <td>Välj om du vill titta på skapade (nya) eller uppdaterade (ändrade) objekt.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by]</td> 
   <td>Du kan lägga till ett filter för att se till att scenariot bara startar när vissa villkor uppfylls.<ul><li><b>Fråga</b><p>Ange frågan som du vill filtrera efter.</li><li><b>Egenskaper</b><p>För varje egenskap som du vill använda för att filtrera resultat klickar du på <b>Lägg till objekt</b> och anger egenskapsnamnet, operatorn och egenskapsvärdet.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Register (avtal, kontakter och företag)

+++ **Skapa en post**

Den här åtgärdsmodulen skapar en kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property groups]</td> 
   <td>För varje egenskap som du vill lägga till när du skapar posten väljer du gruppen där egenskapen finns. Egenskapsgruppen öppnas och du kan sedan fylla i värdet för egenskaperna. Vilka egenskapsgrupper och egenskaper som är tillgängliga beror på vilken typ av post du vill skapa.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Record (Legacy)]**

Den här åtgärdsmodulen skapar kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Fyll i alla egenskaper som du vill ange för posten. Vilka fält som är tillgängliga beror på vilken typ av post du vill skapa.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Delete a Record]**

Den här åtgärdsmodulen tar bort en kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av post som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange ID:t för den kontakt, det företag eller det avtal som du vill ta bort. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ [!UICONTROL Get a Record]

Den här åtgärdsmodulen hämtar information om en kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Välj posttyp.</p> 
    <ul> 
     <li>[!UICONTROL Contact]</li> 
     <li>[!UICONTROL Company] </li> 
     <li>[!UICONTROL Deal]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search Type]</td> 
   <td>Om du får en kontakt väljer du om du vill identifiera den med ID eller via e-postadress.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange ID:t för den kontakt, det företag eller det avtal som du vill hämta. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Ange e-postadressen till den kontakt vars information du vill hämta. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Record Property]**

Den här åtgärdsmodulen hämtar metadata för en viss postegenskap med dess (interna) namn.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av post som har den egenskap som du vill hämta metadata för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property Name]</td> 
   <td>Välj den egenskap som du vill hämta metadata för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Option ID]</td> 
   <td> <p> Vissa egenskaper har en uppsättning tillgängliga alternativ som en användare kan välja som egenskapsvärde. Ange ID:t för alternativet som representerar egenskapsvärdet som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Listposter**

Den här sökmodulen returnerar en lista med kontakter, företag eller avtal. Produktionen är begränsad till 5 000 kontakter, 12 500 företag eller 12 500 avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td> <p>Välj den typ av post som du vill returnera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Välj de egenskaper som du vill ta med i utdata för den här modulen.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Update a Record]**

Den här åtgärdsmodulen uppdaterar en kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av post som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search Type]</td> 
   <td> <p>Om du får en kontakt väljer du hur du vill identifiera posten:</p> 
    <ul> 
     <li> <p>[!UICONTROL ID]</p> </li> 
     <li> <p>[!UICONTROL Email]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange ID:t för den kontakt, det företag eller det avtal som du vill uppdatera. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Ange e-postadressen till den kontakt vars information du vill uppdatera. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Fyll i alla egenskaper som du vill ange för posten. Vilka fält som är tillgängliga beror på vilken typ av post du vill skapa.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Watch Records]**

Den här utlösarmodulen startar ett scenario när en kontakt, ett företag eller ett avtal har ändrats eller skapats under de senaste 30 dagarna. Utdata är begränsade till 10 000 poster.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td>Välj den typ av post som har den egenskap som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search]</td> 
   <td>Välj om du vill se nyligen ändrade eller nyligen skapade poster.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Välj de egenskaper som du vill inkludera i modulens utdata.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Kontakter

+++ **[!UICONTROL Add Contacts to a List]**

Den här modulen lägger till kontaktposter som redan har skapats i systemet i en kontaktlista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID] </td> 
   <td>Markera ID:t för listan som du vill lägga till kontakten i. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL IDs/Emails] </td> 
   <td> <p>Välj hur du vill identifiera de kontakter som du vill lägga till i listan:</p> 
    <ul> 
     <li> <p>[!UICONTROL IDs]</p> <p>Lägg till ID:n för de kontakter som du vill lägga till i listan.</p> </li> 
     <li> <p>[!UICONTROL Emails]</p> <p>Lägg till e-postadresserna till kontakterna som du vill lägga till i listan.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Skapa/uppdatera en kontakt**

Den här åtgärdsmodulen skapar en kontakt om den inte finns i en portal. Om kontakten finns i portalen uppdateras den med de angivna värdena.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Property groups]</td> 
   <td>För varje egenskap som du vill lägga till när du skapar kontakten väljer du den grupp där egenskapen finns. Egenskapsgruppen öppnas och du kan sedan fylla i värdena för egenskaperna.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create/Update a Contact (Legacy)]**

Skapar en kontakt om den inte redan finns i en portal, eller uppdaterar den med de senaste egenskapsvärdena om den finns i en portal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Properties]</td> 
   <td>Fyll i de egenskaper som du vill ange eller uppdatera för kontakten. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create/Update a Group of Contacts]** 

Skapar en grupp kontakter eller uppdaterar dem om de redan finns. Prestanda är bäst när gruppstorleken är begränsad till 100 kontakter eller färre. Ändringar som görs via den här slutpunkten bearbetas asynkront, så det kan ta flera minuter innan ändringar tillämpas på kontaktposter.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Batch of Contacts to Create/Update] </td> 
   <td> <p>Lägg till gruppen med kontakter.</p> <p>Klicka på <strong>[!UICONTROL Add item]</strong> om du vill lägga till en ny kontakt. I fönstret som visas anger eller mappar du följande information:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Search Type]</strong> </p> <p>Välj hur du vill identifiera kontakten:</p> 
      <ul> 
       <li> <p>[!UICONTROL ID]</p> <p>Ange ID:t för den kontakt som du vill skapa eller uppdatera. </p> </li> 
       <li> <p>[!UICONTROL Email]</p> <p>Ange e-postadressen till den kontakt som du vill skapa eller uppdatera. </p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Properties]</strong> </p> <p>Fyll i alla egenskaper som du vill ställa in eller uppdatera för kontakten.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List Contacts]**

Returnerar alla kontakter som har skapats i portalen. Utdata är begränsat till 5 000 kontakter. Om du vill visa tidigare eller nästa kontakter kan du använda parametern [!UICONTROL advanced] för att förskjuta listan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Det högsta antalet kontakter som Workfront Fusion får returnera under en körningscykel. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Markera de egenskaper som du vill ska visas i modulens utdata. </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Kontakt-ID [startförskjutning] </td> 
    <td>Ange eller mappa ID:t för användaren som du vill starta listan för. Om du till exempel anger kontakt-ID som ID för den 101:a kontakten kan modulen visa kontakter 101-5100 i stället för 1-5000. </td> 
   </tr>
 </tbody> 
</table>

+++

+++ **[!UICONTROL List Contacts of a Company]**

Hämtar en lista med kontakter i företaget. Utdata är begränsat till 5 000 kontakter. Om du vill visa tidigare eller nästa kontakter kan du använda parametern [!UICONTROL advanced] för att förskjuta listan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange ID:t för det företag vars kontakter du vill visa. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Det högsta antalet kontakter som Workfront Fusion får returnera under en körningscykel. </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Kontakt-ID [startförskjutning] </td> 
    <td>Ange eller mappa ID:t för användaren som du vill starta listan för. Om du till exempel anger kontakt-ID som ID för den 101:a kontakten kan modulen visa kontakter 101-5100 i stället för 1-5000. </td> 
   </tr>
 </tbody> 
</table>

+++

+++ **[!UICONTROL Merge contacts]**

Den här åtgärdsmodulen sammanfogar kontakter

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID 1] </td> 
   <td>Ange ID:t för den av kontakterna som du vill sammanfoga. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID 2] </td> 
   <td>Ange ID:t för den andra kontakten som du vill sammanfoga.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Remove a Contact from a List]**

Tar bort en kontakt från en kontaktlista.

>[!NOTE]
>
>Du kan inte ta bort kontakter manuellt från en dynamisk lista.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID] </td> 
   <td>Markera ID:t för listan som du vill ta bort kontakten från. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID] </td> 
   <td>Ange ID:t för den kontakt du vill ta bort från listan. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search for Contacts]**

Hämtar en lista med kontakter som använder sökfrågan.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>Ange sökfrågan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td>Ange eller mappa det högsta antalet kontakter som Workfront Fusion ska returnera under en körningscykel för ett scenario. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Watch contacts added to a list]**

Den här utlösarmodulen startar ett scenario när en ny kontakt läggs till i en lista. Detta är endast tillgängligt för användare med ett betalt Marketing-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td>Ange eller mappa ID:t för listan som innehåller de kontakter som du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Properties]</td> 
   <td>Välj de egenskaper som du vill inkludera i modulens utdata.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Erbjudanden

+++ **[!UICONTROL Get a Deal's CRM Pipeline]**

Returnerar en specifik avtalspipeline.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pipeline ID] </td> 
   <td>Ange eller mappa ID:t för den pipeline du vill hämta information för. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stage ID] </td> 
   <td>Ange eller mappa ID:t för den scen som du vill hämta information för. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List Deal/Ticket Pipelines]**

Returnerar alla erbjudanden och biljettpipelines för en viss portal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type] </td> 
   <td>Välj om du vill visa erbjudanden eller biljetter.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Företag

+++ **[!UICONTROL Search for Companies by domain]**

Hämtar en lista över företag baserat på en exakt matchning av egenskapen domain.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Domain] </td> 
   <td>Ange domänen för de företag som du vill söka efter, till exempel <code>[!DNL hubspot].com</code>. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Det högsta antalet företag Workfront Fusion ska returneras under en körningscykel. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output properties]</td> 
   <td>Markera de egenskaper som du vill ska visas i modulens utdata. </td> 
  </tr> 
 </tbody> 
</table>

+++

### Åtaganden

+++ **Koppla en koppling till ett CRM-objekt**

Den här åtgärdsmodulen associerar ett ärende med en kontakt, ett företag eller ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Välj den typ av CRM-post som du vill associera ett ärende med. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Engagement ID]</td> 
  <td>Ange eller mappa ID:t för det engagemang som du vill associera med objektet.</td> 
   </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
  <td>Ange eller mappa ID:t för den post som du vill associera kopplingen med.</td> 
   </tr> 
 </tbody> 
</table>

+++

+++ **Skapa ett engagemang**

Den här åtgärdsmodulen skapar ett engagemang (som en anteckning, uppgift eller aktivitet) med ett CRM-objekt i HubSpot. Åtaganden är all interaktion med en kontakt som ska loggas i CRM.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Is Active?]</td> 
   <td>Aktivera det här alternativet om det nya engagemanget ska vara aktivt när det skapas. Ett engagemang måste vara aktivt för att visas på tidslinjen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
  <td>Välj vilken typ av engagemang du vill skapa.
  <ul>
  <li><b>E-post</b><p></p>Fortsätt till <a href="#email-metadata" class="MCXref xref" >E-postmetadata</a>.</p></li>
  <li><b>Utlysning</b><p>Fortsätt till <a href="#call-metadata" class="MCXref xref" >Anropa metadata</a>.</p></li>
  <li><b>Möte</b><p>Fortsätt till <a href="#meeting-fields" class="MCXref xref" >Mötesfält</a>.</p></li>
  <li><b>Uppgift</b><p>Fortsätt till <a href="#task-fields" class="MCXref xref" >Aktivitetsfält</a>.</p></li>
  <li><b>Obs</b><p>I fältet Brödtext anger du texten i anteckningen.</p></li>
  </ul>
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Tidsstämpel</td> 
   <td>Ange eller mappa en tidsstämpel för ärendet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ägar-ID</td> 
   <td>Ange eller mappa ägar-ID:t för den person som förlovningen ska tilldelas till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UID</td> 
   <td>Ange eller mappa ett ID för engagemanget, som kan användas för alla objekttyper.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Portal-ID</td> 
   <td>Ange eller mappa portalens ID. Detta är användbart om din organisation har flera portaler.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Associerade kontakter</td> 
   <td>Klicka på <b>Lägg till objekt</b> och ange kontakt-ID för varje kontakt som du vill associera det här ärendet med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Associerade företag</td> 
   <td>För varje företag som du vill associera det här åtagandet med klickar du på <b>Lägg till artikel</b> och anger företags-ID.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Associerade erbjudanden</td> 
   <td>Klicka på <b>Lägg till objekt</b> och ange ett avtal-ID för varje avtal som du vill associera det här kopplingen med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Associerade biljetter</td> 
   <td>Klicka på <b>Lägg till objekt</b> och ange biljett-ID för varje biljett som du vill associera det här kopplingen med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Bifogade filer</td> 
   <td>För varje bifogad fil som du vill associera den här kopplingen med klickar du på <b>Lägg till objekt</b> och anger fil-ID:t för filen som du vill bifoga.</td> 
  </tr> 
 </tbody> 
</table>

#### E-postmetadata

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL From > Email]</p> </td> 
   <td> <p>Ange eller mappa den e-postadress som e-postmeddelandet ska skickas från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL First Name]</td> 
   <td>Ange eller mappa förnamnet på den person som e-postmeddelandet ska skickas från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Last Name]</td> 
  <td>Ange eller mappa efternamnet på den person som e-postmeddelandet ska skickas från.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Till</td> 
   <td>För varje e-postadress som du vill skicka e-postmeddelandet till klickar du på <b>Lägg till objekt</b> och anger eller mappar e-postadressen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kopia</td> 
   <td>För varje e-postadress som du vill kopiera e-postadressen till klickar du på <b>Lägg till objekt</b> och anger eller mappar e-postadressen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Hemlig kopia</td> 
   <td>Klicka på <b>Lägg till post</b> och ange eller mappa e-postadressen för varje e-postadress som du vill blockera e-postadressen till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ämne</td> 
   <td>Ange eller mappa texten i e-postmeddelandets ämne</td> 
  </tr> 
  <tr> 
   <td role="rowheader">HTML</td> 
   <td>Om du vill skicka ett HTML-formaterat e-postmeddelande anger eller mappar du brödtexten i e-postmeddelandet, inklusive HTML-taggar.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Text</td> 
   <td>Om du vill skicka ett e-postmeddelande med endast text anger eller mappar du texten i e-postmeddelandet.</td> 
  </tr> 
 </tbody> 
</table>

#### Samtalsmetadata

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL To Number]</p> </td> 
   <td> <p>Ange eller mappa det telefonnummer som samtalet ska göras till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From Number]</td> 
   <td>Ange eller mappa det telefonnummer som samtalet kommer att göras från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status]</td> 
  <td>Välj samtalets status.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Brödtext</td> 
   <td>Ange eller mappa information eller anteckningar för samtalet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Externt ID</td> 
   <td>Det här fältet representerar det interna ID:t för ett anrop som gjorts i HubSpot. Det kräver ingen åtgärd.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Varaktighet</td> 
   <td>Ange eller mappa samtalets längd i millisekunder</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID för externt konto</td> 
   <td>Det här fältet representerar det interna konto-ID:t för ett anrop som gjorts i HubSpot. Det kräver ingen åtgärd.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Inspelnings-URL</td> 
   <td>Ange eller mappa URL:en för inspelningsfilen.</td> 
  </tr> 
 </tbody> 
</table>

#### Mötesfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Title]</p> </td> 
   <td> <p>Ange eller mappa rubriken eller ämnet för mötet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa texten i mötesbeskrivningen eller informationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Time]</td> 
  <td>Ange eller mappa mötets starttid som en UNIX-tidsstämpel.
  </td> 
   </tr> 
  <tr> 
   <td role="rowheader">Sluttid</td> 
   <td>Ange eller mappa sluttiden för mötet som en UNIX-tidsstämpel.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppgiftsfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Subject]</p> </td> 
   <td> <p>Ange eller mappa uppgiftens titel eller ämne.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa texten för uppgiftsbeskrivningen eller detaljerna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Status</td> 
   <td>Välj status för uppgiften.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL For Object Type]</td> 
  <td>Ange antingen <code>CONTACT</code> eller <code>COMPANY</code>.
  </td> 
   </tr> 
 </tbody> 
</table>

+++

+++ **Ta bort ett åtagande**

Den här åtgärdsmodulen tar bort ett ärende med dess ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Ange eller mappa ID:t för det ärende som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Bevakade aktiviteter**

Den här utlösarmodulen startar ett scenario när ett nytt engagemang skapas i en portal. Den här modulen returnerar bara poster som har skapats under de senaste 30 dagarna eller de 10 000 senast skapade posterna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Det högsta antalet företag Workfront Fusion ska returneras under en körningscykel. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since]</td> 
   <td>Ange eller mappa det tidigaste datum som du vill se händelser för. Använd formatet <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Händelser och meddelanden

+++ **Skapa/uppdatera en tidslinjehändelse**

Den här åtgärdsmodulen skapar eller uppdaterar en tidslinjehändelse. Den här modulen kan bara användas med en utvecklaranslutning som innehåller din användaridentifierare, din HubSpot API-nyckel, klient-ID och Klienthemlighet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Ange eller mappa ID:t för programmet som den här händelsen tillhör.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td>Ange eller mappa ett ID för den här händelsen. Händelse-ID:n genereras inte av systemet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Type ID]</td> 
   <td>Ange eller mappa ID:t för händelsetypen för den här händelsen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Ange eller mappa e-postadressen till kontakten som du skapar händelsen för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object ID]</td> 
   <td>Ange eller mappa ID:t för kontakten som du skapar händelsen för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp]</td> 
   <td>Ange eller mappa tidsstämpeln för den här händelsen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom data]</td> 
   <td>För varje objekt med anpassade data som du vill lägga till i den här händelsen klickar du på <b>Lägg till objekt</b> och anger objektets namn och värde.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Visa tidslinjehändelsetyper**

Sökmodulen returnerar en lista med alla tidslinjehändelser för ett specifikt program. Den här modulen kan bara användas med en utvecklaranslutning som innehåller din användaridentifierare, din HubSpot API-nyckel, klient-ID och Klienthemlighet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Ange eller mappa ID:t för programmet som den här händelsen tillhör. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Se kalenderhändelser**

Den här utlösarmodulen startar ett scenario när en ny händelse läggs till i en kalender. Den innehåller upp till 500 uppgifter i intervallet mellan start- och slutdatumet. Den här modulen kan bara användas med en utvecklaranslutning som innehåller din användaridentifierare, din HubSpot API-nyckel, klient-ID och Klienthemlighet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Events Type]</td> 
   <td>Välj om du vill se sociala händelser, innehållshändelser eller alla händelser.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal filer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Ange eller mappa startdatumet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Ange eller mappa slutdatumet.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Bevakade meddelanden**

Den här utlösarmodulen startar ett scenario när ett nytt meddelande om ändringar skickas.  Den innehåller upp till 500 uppgifter i intervallet mellan start- och slutdatumet. Den här modulen kan bara användas med en utvecklaranslutning som innehåller din användaridentifierare, din HubSpot API-nyckel, klient-ID och Klienthemlighet. Du kan bara ha en webkrok-URL per utvecklarprogram i HubSpot.

Om du vill skapa en webkrok för den här modulen klickar du på **Lägg till** bredvid webkrokfältet och fyller i följande fält:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application ID]</td> 
   <td>Ange det program-ID som du vill använda för den här webkroken. Du hittar ID:t i din HubSpot-utvecklarportal.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscriptions]</td> 
   <td> <p>För varje typ av meddelanden som du vill bevaka klickar du på <b>Lägg till objekt</b> och väljer prenumerationstyp.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Force to Remove Old Subscriptions]</td> 
   <td>Aktivera det här alternativet om du vill frigöra eller ta bort gamla prenumerationer som är kopplade till den här webkroken.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Filer

+++ **[!UICONTROL Create a Folder]**

Den här modulen skapar en mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder Name] </td> 
   <td>Ange eller mappa ett namn för den nya mappen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent Folder ID] </td> 
   <td>Välj ID för den överordnade mappen för mappen som du skapar. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Ta bort en fil**

Den här åtgärdsmodulen tar permanent bort en fil och alla relaterade data och miniatyrbilder från filhanteraren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Ange eller mappa ID:t för filen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Delete a Folder]**

Markerar en mapp som borttagen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för mappen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Visa filer** 

Sökmodulen returnerar en lista med filer som lagras i filhanteraren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal filer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Ange eller mappa ID:t för mappen som innehåller de filer som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Om du bara vill inkludera filer som innehåller specifika tecken i filnamnet anger eller mappar du tecknen som du vill att filnamnet ska innehålla.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Move a File]**

Flyttar en fil till en annan mapp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID] </td> 
   <td>Ange eller mappa ID:t för filen som du vill flytta. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td>Markera ID:t för mappen där du vill flytta filen. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange ett namn för den flyttade filen.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Överför en fil** 

Den här åtgärdsmodulen överför en fil till filhanteraren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Access type] </td> 
   <td>Välj om du vill att filen ska vara privat, offentlig men inte indexerbar, eller offentlig och indexerbar. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td>Markera ID:t för mappen där du vill överföra filen. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Overwrite]</td> 
   <td>Aktivera det här alternativet om du vill skriva över filen om den redan finns i mappen.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Bevakade filer**

Den här utlösarmodulen startar ett scenario när en ny fil sparas i filhanteraren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal filer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td>Ange eller mappa ID:t för mappen som innehåller de filer du vill bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Om du bara vill inkludera filer som innehåller specifika tecken i filnamnet anger eller mappar du tecknen som du vill att filnamnet ska innehålla.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Uppgifter

+++ **Skapa en kalenderaktivitet**

Den här åtgärdsmodulen skapar en ny uppgift för en kalender. Anslutningen som används i den här modulen måste använda autentiseringsuppgifterna för en användare med ett betalt Marketing-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för den nya kalenderaktiviteten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>Ange eller mappa en beskrivning för den nya kalenderaktiviteten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Owner ID]</td> 
   <td>Ange eller mappa ägar-ID:t för användaren som är tilldelad den här uppgiften.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Date]</td> 
   <td>Ange eller mappa datumet för den här uppgiften.<p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>Välj händelsetyp.<ul><li><b>Blogginlägg</b><p>Ange ID för innehållsgrupp. Detta är bloggsidans ID.</p></li><li><b>E-post</b><p>Ange eller mappa sökvägen till den e-postmall som du vill använda.</li><li><b>Landningssida</b><p>Ange eller mappa sökvägen till den landningssidmall som du vill använda.</li><li><b>Egen</b></li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td>Ange om händelsen är i läget"Att göra" eller"Klar".</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Campaign GUID]</td> 
   <td>Ange eller mappa det interna HubSpot-ID:t för kampanjen som den här händelsen är en del av.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Ta bort en kalenderaktivitet**

Den här åtgärdsmodulen tar bort en kalenderuppgift. Anslutningen som används i den här modulen måste använda autentiseringsuppgifterna för en användare med ett betalt Marketing-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för uppgiften som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Se aktivitetshändelser**

Den här utlösarmodulen startar ett scenario när det finns en ny aktivitetshändelse i en kalender. Anslutningen som används i den här modulen måste använda autentiseringsuppgifterna för en användare med ett betalt Marketing-konto. Modulen returnerar upp till 500 händelser.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal filer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Date]</td> 
   <td>Ange eller mappa det tidigaste datum som du vill se händelser för. Använd formatet <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Date]</td> 
   <td>Ange eller mappa det senaste datum som du vill se händelser för. Använd formatet <code>MM/DD/YYYY h:mm</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Användare

+++ **Hämta en ägare**

Den här åtgärdsmodulen returnerar information om en ägare.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Owner ID]</td> 
   <td> <p>Ange eller mappa ID:t för ägaren som du vill returnera information för.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Listägare**

Den här sökmodulen returnerar en lista över alla ägare i ett HubSpot-konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Biljetter

<!-- Create a Ticket Need to find a working connection-->

+++ **[!UICONTROL Delete a Ticket]**

Tar bort en befintlig biljett med dess ID.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange ID:t för biljetten som du vill ta bort. </td> 
  </tr> 
 </tbody> 
</table>

+++

<!-- Get a Ticket  Need to find a working connection-->

<!-- List Tickets  Need to find a working connection-->

&lt;!— Uppdatera en biljett Behöver hitta en fungerande anslutning—>

<!-- Watch Tickets Need to find a working connection-->

### Forms

+++ **Hämta en fil som har överförts via formuläret**

Den här åtgärdsmodulen returnerar en fil som har överförts via ett formulär.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File URL]</td> 
   <td>Ange eller mappa URL:en för filen som du vill hämta. Detta finns i formulärets metadata.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Lista Forms**

Den här åtgärdsmodulen returnerar alla formulär som har skapats i det konto som är kopplat till anslutningen som används för den här modulen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det högsta antal formulär som modulen kan returnera i en körningscykel.</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--#### Submit Data to a Form Need to find a working connection-->



&lt;!—### Bevakade inlämningar för ett formulär - Behöver hitta en fungerande anslutning>—>

### Sociala medier (sändning)

+++ **Avbryt ett sändningsmeddelande**

Den här åtgärdsmodulen avbryter en schemalagd sändning, till exempel ett tweet eller ett Facebook-inlägg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Broadcast ID]</td> 
   <td>Ange eller mappa ID:t för sändningen som du vill avbryta.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Skapa ett sändningsmeddelande**

Den här åtgärdsmodulen skapar och publicerar omedelbart ett meddelande på den angivna sociala mediekanalen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Channel ID]</td> 
   <td>Ange eller mappa ID:t för kanalen som du vill använda för den här sändningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title]</td> 
   <td>Ange eller mappa en titel för den här sändningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>Ange eller mappa texten i sändningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Photo URL]</td> 
   <td>Ange eller mappa URL-adressen till ett foto som du vill ta med i sändningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Thumbnail URL]</td> 
   <td>Ange eller mappa URL:en för en miniatyrbild som du vill använda för den här sändningen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Trigger at]</td> 
   <td>Ange eller mappa det datum och den tid som du vill att sändningen ska skickas. Om detta lämnas tomt skickas sändningen omedelbart.<p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Se utsändningsmeddelanden**

Den här utlösarmodulen startar ett scenario när ett meddelande skickas från HubSpot till den angivna kanalen för sociala medier.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet objekt som modulen ska returnera i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by Status]</td> 
   <td>Om du bara vill starta scenariot när meddelandet har en viss status väljer du status.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter by Channel]</td> 
   <td>Om du bara vill starta scenariot när meddelandet finns på en viss kanal markerar du kanalen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Broadcast ID]</td> 
   <td>Om du bara vill starta scenariot när meddelandet är på eller efter ett visst datum anger eller mappar du datumet i formatet <code>MM/DD/YYYY</code>.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Blogginlägg

+++ **Skapa ett blogginlägg** 

Denna åtgärdsmodul skapar ett nytt blogginlägg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn</td> 
   <td>Ange eller mappa inläggsrubriken (inläggets interna namn).</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Bokför brödtext</td> 
   <td>Ange eller mappa huvuddelen av inlägget i HTML-format.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Bokför sammanfattning</td> 
   <td>Ange eller mappa en sammanfattning av inlägget. Sammanfattningen visas på huvudlistsidan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Författar-ID för blogg</td> 
   <td>Ange eller mappa ID:t för den författare som är associerad med inlägget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Innehållsgrupp-ID</td> 
   <td>Ange eller mappa ID:t för den blogg som det här inlägget tillhör.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sidfot - HTML</td> 
   <td>Ange eller mappa HTML för inbäddningskoder eller javascript som ska placeras före sidans tagg.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Head HTML</td> 
   <td>Ange eller mappa HTML för inbäddningskoder eller javascript som ska placeras överst.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kampanj-ID</td> 
   <td>Ange eller mappa ID:t för kampanjen som det här inlägget är associerat med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Aktuell bild</td> 
   <td>Ange eller mappa URL:en för bilden som det här inlägget ska använda som aktuell bild.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nyckelord</td> 
   <td>För varje nyckelord som du vill lägga till i det här inlägget klickar du på <b>Lägg till objekt</b> och anger nyckelords-GUID.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Meta Description</td> 
   <td>Ange eller mappa texten för taggen <code>meta</code> på sidan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Publiceringsdatum</td> 
   <td>Ange eller mappa datumet då blogginlägget ska publiceras. <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn</td> 
   <td>Aktivera det här alternativet om du vill publicera blogginlägget direkt när det skapas. Om inställningen är Ja ignoreras fältet Publiceringsdatum.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Instruktionsmarginal</td> 
   <td>Ange eller mappa instruktionsmarginalen för inlägget. Instruktionsmarginalen läggs till i slutet av domänen och utgör URL:en för blogginlägget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ämne-ID</td> 
   <td>För varje ämne som du vill lägga till i inlägget klickar du på <b>Lägg till objekt</b> och anger ämne-ID:t.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd aktuell bild</td> 
   <td>Aktivera det här alternativet om du vill använda den aktuella bilden för blogginlägget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Widgetar</td> 
   <td>Ange eller mappa en datastruktur som innehåller datumet för alla moduler för det här blogginlägget. Detta avser blogginläggets moduler, inte Fusion-moduler.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Ta bort ett blogginlägg**

Den här åtgärdsmodulen tar bort ett blogginlägg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för det blogginlägg som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Visa blogginlägg** 

Den här sökmodulen hämtar inlägg från en HubSpot-blogg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gräns</td> 
   <td>Ange eller mappa det maximala antalet blogginlägg som ska returneras i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Arkiverad</td> 
   <td>Aktivera det här alternativet om du vill inkludera arkiverade inlägg i dina resultat.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Författar-ID för blogg</td> 
   <td>Ange eller mappa ID:t för en författare för att returnera inlägg som är kopplade till den författaren.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kampanj-ID</td> 
   <td>Ange eller mappa ID:t för en kampanj för att returnera inlägg som är associerade med kampanjen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Innehållsgrupp-ID</td> 
   <td>Ange eller mappa ID:t för en blogg för att returnera inlägg som är kopplade till den bloggen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn</td> 
   <td>Ange ett postnamn om du bara vill returnera inlägg med det namnet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter skapad</td> 
   <td>Välj Filter om du vill returnera inlägg med det skapade tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter uppdaterad</td> 
   <td>Välj Filter om du vill returnera inlägg med det uppdaterade tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter borttaget</td> 
   <td>Välj Filter om du vill returnera inlägg med det borttagna tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Instruktionsmarginal</td> 
   <td>Ange eller mappa en instruktionsmarginal för att returnera inlägg som matchar instruktionsmarginalen. Instruktionsmarginalen läggs till i slutet av domänen och utgör URL:en för blogginlägget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Läge</td> 
   <td>Välj ett läge (Utkast, Publicerat eller Schemalagt) om du bara vill inkludera resultat i det läget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Beställ efter publiceringsdatum</td> 
   <td>Välj om du vill sortera resultaten stigande eller fallande efter publiceringsdatum.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Publicera/avpublicera ett blogginlägg**

Den här åtgärdsmodulen schemalägger eller avbryter publiceringen av ett blogginlägg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för det blogginlägg som du vill schemalägga eller avbryta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td>Välj om du vill schemalägga blogginlägget eller avbryta ett tidigare schemalagt blogginlägg.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Blogginlägg**

Den här utlösarmodulen startar ett scenario när ett blogginlägg som matchar de villkor du anger skapas, uppdateras eller tas bort.



Den här sökmodulen hämtar inlägg från en HubSpot-blogg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gräns</td> 
   <td>Ange eller mappa det maximala antalet blogginlägg som ska returneras i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Arkiverad</td> 
   <td>Aktivera det här alternativet om du vill inkludera arkiverade inlägg i dina resultat.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Författar-ID för blogg</td> 
   <td>Ange eller mappa ID:t för en författare för att returnera inlägg som är kopplade till den författaren.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kampanj-ID</td> 
   <td>Ange eller mappa ID:t för en kampanj för att returnera inlägg som är associerade med kampanjen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Innehållsgrupp-ID</td> 
   <td>Ange eller mappa ID:t för en blogg för att returnera inlägg som är kopplade till den bloggen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Namn</td> 
   <td>Ange ett postnamn om du bara vill returnera inlägg med det namnet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter skapad</td> 
   <td>Välj Filter om du vill returnera inlägg med det skapade tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter uppdaterad</td> 
   <td>Välj Filter om du vill returnera inlägg med det uppdaterade tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Filtrera efter borttaget</td> 
   <td>Välj Filter om du vill returnera inlägg med det borttagna tidsvärdet.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Instruktionsmarginal</td> 
   <td>Ange eller mappa en instruktionsmarginal för att returnera inlägg som matchar instruktionsmarginalen. Instruktionsmarginalen läggs till i slutet av domänen och utgör URL:en för blogginlägget.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Läge</td> 
   <td>Välj ett läge (Utkast, Publicerat eller Schemalagt) om du bara vill inkludera resultat i det läget.</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--+++**Workflows**>

<!--### Workflows May need connection

#### Add a Contact to a Workflow


#### Remove a Contact from a Workflow

-->

<!--+++-->

### Prenumerationer

+++ **Uppdatera e-postprenumeration**

Den här åtgärdsmodulen uppdaterar en e-postprenumeration i HubSpot.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email]</td> 
   <td>Ange eller mappa e-postadressen för den prenumeration som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Statuses]</td> 
   <td>För varje status som du vill uppdatera prenumerationen för klickar du på <b>Lägg till objekt</b> och anger statusens ID, och om e-postadressen kommer att prenumerera på den statusen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Portal Subscription Legal Status]</td> 
   <td>Om du vill registrera den juridiska grunden för den här prenumerationen för GDPR väljer du den juridiska statusen för den här prenumerationen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Portal Subscription Legal Basis Explanation]</td> 
   <td>Om du vill lägga till en anteckning om den rättsliga grunden för den här prenumerationen för GDPR anger eller mappar du texten i anteckningen.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **Se tidslinjen för prenumerationer för en portal**

Den här utlösarmodulen startar ett scenario när en ny tidslinjeprenumeration för e-post läggs till i portalen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antalet objekt som modulen ska returnera i en körningscykel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start Timestamp]</td> 
   <td>Om du vill returnera resultat från ett visst datum eller senare anger du datumet i formatet <code>MM/DD/YYYY.</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End Timestamp]</td> 
   <td>Om du vill returnera resultat från och med ett visst datum anger du datumet i formatet <code>MM/DD/YYYY.</code></td> 
  </tr> 
 </tbody> 
</table>

+++

<!--+++**Associations**-->

<!--### Associations-->

<!--#### Associate CRM Objects  May need connection

This action module associates two CRM objects.-->

<!--#### Associate Multiple CRM Objects  May need connection-->



<!--#### Delete an Association May need connection-->



<!--#### Delete Multiple Associations between CRM Objects May need connection-->



<!--#### List Associations for a CRM Object May need connection-->

<!--+++-->

### Övriga

+++ **[!UICONTROL Make an API Call]**

Gör att du kan utföra ett anpassat API-anrop.

>[!NOTE]
>
>Följande slutpunkter togs bort i HubSpot API den 31 augusti 2023 och kan inte längre användas i Fusion-moduler.
>
>* Visa innehållshändelser
>* Visa sociala händelser
>* Visa kalenderaktivitetshändelser
>* Visa alla kalenderhändelser
>* Skapa kalenderuppgift
>* Hämta kalenderaktivitet med ID
>* Uppdatera kalenderaktivitet
>* Ta bort en kalenderuppgift

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL HubSpot CRM]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Skapa en anslutning till Adobe Workfront Fusion - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till https://api.hubapi.com/. Till exempel /kontakter/v1/lists/all/contact/all</p> <p>En lista över tillgängliga slutpunkter finns i <a href="https://legacydocs.hubspot.com/docs/overview">[!DNL HubSpot] API-dokumentationen </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-metod som du vill använda:</p> <p>[!UICONTROL GET]</p> <p>för att hämta information för ett tävlingsbidrag.</p> <p>[!UICONTROL POST]</p> <p>för att skapa ett nytt inlägg.</p> <p>[!UICONTROL PUT]</p> <p>om du vill uppdatera/ersätta en befintlig post.</p> <p>[!UICONTROL PATCH]</p> <p>för att göra en partiell postuppdatering.</p> <p>[!UICONTROL DELETE]</p> <p>om du vill ta bort en post.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p> Ange önskade begäranderubriker. Du behöver inte lägga till auktoriseringsrubriker. Vi gjorde det redan för dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Ange frågesträngen för begäran.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödtexten för API-anropet i form av ett standard-JSON-objekt. Om du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.<img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**Exempel:** Följande API-anrop returnerar alla kontakter i ditt [!DNL HubSpot]-konto:
>
>**URL**: `/contacts/v1/lists/all/contacts/all`
>
>**Metod**: `GET`
>
>![Konfiguration av Hubspot-API](/help/workfront-fusion/references/apps-and-modules/assets/hubspot-api-config.png)
>
>Det går att hitta matchningar av sökningen i modulens utdata under [!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL contacts].
>
>I vårt exempel returnerades tre kontakter:
>
>![Utdata för Hubspot-API](/help/workfront-fusion/references/apps-and-modules/assets/hubspot-api-output.png)

+++

## Skapa ett nytt program

1. Logga in på ditt [!DNL HubSpot]-utvecklarkonto.
1. Välj alternativet **[!UICONTROL Create an App]**.
1. Ange appnamnet och [!UICONTROL Save] dialogrutan.
1. Välj de omfattningar du behöver för din webkrok.

   Du kan till exempel lägga till kontaktomfattningar för att aktivera modulen när en ny kontakt skapas eller tas bort.

   [!UICONTROL contacts scope] är allt du behöver för att ta emot kontakter, erbjudanden och webbhookar för företagshändelser.

   >[!IMPORTANT]
   >
   >Fyll inte i fältet [!UICONTROL Redirect URL].
