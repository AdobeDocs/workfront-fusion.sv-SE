---
title: Kundmoduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som använder Event och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: b7e16180-1db8-4aff-bb7b-69ca98194b00
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 0%

---

# [!DNL Cvent] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Cvent] samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

Du måste ha ett [!DNL Cvent]-konto för att kunna använda [!DNL Cvent]-moduler.

## Information om klient-API

Händelsekopplingen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> V200611.ASMX </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.7.14</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Cvent] till [!DNL Adobe Workfront Fusion] {#connect-cvent-to-adobe-workfront-fusion}

>[!NOTE]
>
>Modulerna [!DNL Cvent] fungerar genom ett [!UICONTROL SOAP] API. Om du vill skapa en anslutning till [!DNL Cvent] måste du se till följande:
>
>* Du har [!UICONTROL SOAP] åtkomst till API:t [!DNL Cvent].
>* IP-adresserna för [!DNL Workfront Fusion] har lagts till i din organisations tillåtelselista.
>
>  En lista över [!DNL Workfront Fusion] IP-adresser finns i [Konfigurera IP-adresser för Fusion i din organisations tillåtelselista](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)


Du kan skapa en anslutning till ditt [!DNL Cvent]-konto direkt inifrån en [!DNL Cvent]-modul.

1. Klicka på **[!UICONTROL Add]** bredvid fältet [!UICONTROL Connection] i någon [!DNL Cvent]-modul.
1. Markera det område som du vill ansluta till.

   * [!UICONTROL North America]
   * [!UICONTROL Europe]
   * [!UICONTROL Sandbox]

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Cvent]-moduler och deras fält

När du konfigurerar [!DNL Cvent] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Cvent] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärder](#actions)
* [Sökningar](#searches)

### Åtgärder

* [[!UICONTROL Custom API Call]](#create-meeting-request)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Register Invitee]](#register-invitee)
* [[!UICONTROL Add Invitee]](#add-invitee)
* [[!UICONTROL Delete Contact]](#delete-contact)
* [[!UICONTROL Update Contact]](#update-contact)
* [[!UICONTROL Create meeting request]](#create-meeting-request)

#### [!UICONTROL Custom API Call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Cvent]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Cvent]-modulerna.

När du konfigurerar den här modulen visas följande fält.

Modulen returnerar statuskoden, tillsammans med rubrikerna och brödtexten för API-anropet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Åtgärd</td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Brödtext (XML)</td> 
   <td> <p>Ange eller mappa innehållet i API-anropet. Detta får endast innehålla XML. Modulen kommer automatiskt att innehålla autentiseringshuvuden. </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser information om en viss post.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td>Välj objekttypen för den post som du vill läsa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact] / [!UICONTROL Event] / [!UICONTROL Invitee ID]</td> 
   <td> <p>Ange eller mappa ID:t för objektet som du vill läsa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i modulens utdata. Fälten är tillgängliga beroende på vilken objekttyp du har valt.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Register Invitee]

Den här åtgärdsmodulen registrerar en inbjudan för en händelse.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Inbjudan-ID</p> </td> 
   <td> <p>Ange eller mappa ID:t för den inbjudne som du vill registrera för en händelse.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Händelse-ID</td> 
   <td> <p>Ange eller mappa ID:t för händelsen som du vill registrera den inbjudne för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Invitee]

Den här åtgärdsmodulen bjuder in en kontakt till en händelse.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för kontakten som du vill lägga till i en händelse.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Ange eller mappa ID:t för händelsen som du vill lägga till kontakten i.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Contact]

Den här åtgärdsmodulen tar bort en enskild kontakt i Event.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID]</td> 
   <td> <p>Ange eller mappa ID:t för den kontakt du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Contact]

Den här åtgärdsmodulen uppdaterar en befintlig kontakt med dess ID.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för den kontakt du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>Markera de fält som du vill ange information för och fyll sedan i önskade värden för dessa fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> <p>Markera de fält som du vill ange information för och fyll sedan i önskade värden för dessa fält.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create meeting request]

Den här åtgärdsmodulen lägger till en mötesförfrågan till ditt konto.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Form ID]</p> </td> 
   <td> <p>Ange eller mappa ID:t för det formulär som du vill använda för att skapa den nya mötesförfrågan.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Meeting Request Fields]</td> 
   <td> <p>Markera de mötesförfrågningsfält som du vill ange information för och fyll sedan i önskade värden för dessa fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Request Fields]</td> 
   <td> <p>Markera de fält för händelsebegäran som du vill ange information för och fyll sedan i önskade värden för dessa fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL RFP Request Fields]</td> 
   <td> <p>Välj begäran om förslagsfält som du vill ange information för och fyll sedan i önskade värden för dessa fält.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

#### [!UICONTROL List records]

Den här sökmodulen hämtar information om alla poster av en viss typ.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Cvent]-konto till [!DNL Workfront Fusion] finns i <a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">Ansluta [!DNL Cvent] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td> <p>Välj den typ av post som du vill visa.</p> 
    <ul> 
     <li> <p>Alla händelser från ditt [!DNL Cvent]-konto</p> </li> 
     <li> <p>Alla sessioner för en händelse</p> </li> 
     <li> <p>Alla inbjudna till en händelse</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>Om du listar inbjudna eller sessioner anger eller mappar du ID:t för händelsen som de inbjudna eller sessionerna är kopplade till.</p> </td> 
  </tr> 
 </tbody> 
</table>
