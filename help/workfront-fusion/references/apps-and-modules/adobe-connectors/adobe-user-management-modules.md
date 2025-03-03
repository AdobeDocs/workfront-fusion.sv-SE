---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe-moduler för användarhantering
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du automatisera arbetsflöden som hanterar användare i ditt Adobe-konto.
author: Becky
feature: Workfront Fusion
exl-id: e8fe8ec4-4b00-4c9a-81a5-acb2039b153b
source-git-commit: 234a6a537718328e92eec13672a73bc43add17c1
workflow-type: tm+mt
source-wordcount: '2323'
ht-degree: 0%

---

# Adobe-moduler för användarhantering

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som hanterar användare i ditt Adobe-konto.

Om du behöver instruktioner om hur du skapar ett scenario kan du läsa artiklarna under [Skapa ett scenario: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

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
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet], [!UICONTROL [!DNL Workfront Fusion] för Automatisering av arbete]</p>
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

+++

## Skapa en anslutning till Adobe användarhantering

Så här skapar du en anslutning för dina [!DNL Adobe User Management]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning.

1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>Ange om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials]-information i [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS Organization ID]</td>
        <td>Ange dina [!DNL Adobe] IMS-autentiseringsuppgifter. Unik identifierare för en organisation. Detta är en sträng i formatet A495E53@AdobeOrg där prefixet före @ är ett hexadecimalt tal. Du kan hitta det här värdet som en del av URL-sökvägen för organisationen i Admin Console eller i adobe.io-konsolen för användarhanteringsintegreringen.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Additional scopes]</td>
        <td>Klicka på <b>Lägg till objekt</b> och ange omfånget för varje ytterligare omfång som du vill lägga till.</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.



## Modulerna för användarhantering i Adobe och deras fält

När du konfigurerar Adobe-moduler för användarhantering visas de fält som listas nedan i Workfront Fusion. Dessutom kan ytterligare fält för användarhantering i Adobe visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [Sökningar](#searches)
* [Användaråtgärder](#user-actions)
* [Åtgärder för användargrupp](#user-group-actions)
* [Övriga](#other)

### Sökningar

* [Hämta användargrupper och produktprofiler](#get-user-groups-and-product-profiles)
* [Hämta användarinformation](#get-user-information)
* [Hämta användare i en användargrupp eller produktprofil](#get-users-in-a-user-group-or-product-profile)
* [Hämta användare i en organisation](#get-users-in-an-organization)

#### Hämta användargrupper och produktprofiler

Den här sökmodulen hämtar en lista över alla användargrupper och produktprofiler i organisationen, tillsammans med information om grupperna och profilerna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta användarinformation

Den här sökmodulen hämtar information om en enskild användare i organisationen, som identifieras av deras e-postadress.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">E-postadress</td> 
   <td>Ange eller mappa e-postadressen till användaren som du vill returnera information för. För användare med AdobeID, Enterprise och e-postfedererade bör detta vara den fullständiga e-postadressen inklusive domän. I samtliga fall är parametern inte skiftlägeskänslig.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta användare i en användargrupp eller produktprofil

Den här sökmodulen hämtar en lista över alla användare i den angivna användargruppen eller produktprofilen, tillsammans med information om användarna.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gruppnamn</td> 
   <td>Användargruppen, produktprofilnamnet eller en administrativ grupp. För en administratörsgrupp kan namnet vara någon av de fasta grupperna <code>_org_admin</code>, <code>_deployment_admin</code> eller <code>_support_admin</code>, eller en gruppspecifik administratörsgrupp. Dessa identifieras med ett prefix för gruppnamnet, till exempel <code>_admin_groupName</code>, <code>_product_admin_productName</code> eller <code>_developer_groupName</code>. Om gruppen finns men administratörsgruppen inte gör det returneras en tom lista.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Endast direkt</td> 
   <td>Ange om gruppfältet i den returnerade användarstrukturen bara innehåller de produktprofiler som användaren är direkt medlem av. Om värdet är false returneras alla grupper (användargrupper, produktprofiler och administratörsgrupper) som innehåller användaren, oavsett om ett berättigande för en viss produktprofil kommer direkt (via användartilldelning) eller indirekt (via en användargrupp som innehåller användaren som tilldelas produktprofilen). Om true returneras alla användargrupper och administratörsgrupper som innehåller användaren, men bara de produktprofiler som användaren uttryckligen har tilldelats ett berättigande för. En användare kan vara både direkt och indirekt medlem i en produktprofil.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Uteslut grupper</td> 
   <td>Ange om svaret utesluter att grupparrayen returneras för varje enskild användare.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Status</td> 
   <td>Det här alternativet gäller endast produktprofiler. Välj Aktiv om du vill visa användare som har etablerats för produkten och har en aktiv licens. Välj Inaktiv för att lista användare som har lagts till i produktprofilen men som inte har någon aktiv licens. Om inget anges returnerar modulen alla medlemsanvändare oavsett deras berättigandestatus.
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta användare i en organisation

Sökmodulen returnerar alla användare i organisationen som är kopplade till anslutningen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

### Användaråtgärder

* [Lägga till en användare som medlem i en grupp](#add-a-user-as-a-member-of-a-group)
* [Skapa en användare](#create-a-user)
* [Ta bort en användare från grupper](#remove-a-user-from-groups)
* [Uppdatera en användare](#update-a-user)

#### Lägga till en användare som medlem i en grupp

Den här åtgärdsmodulen lägger till en användare som medlem i den angivna gruppen eller de angivna grupperna. Den här modulen kan lägga till användaren i upp till fyra grupper.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>Ange eller mappa användaren som du vill lägga till i grupperna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Domän</td> 
   <td>För Federated ID:n som inte är e-postadresser anger du den domän som användaren tillhör.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupper</td> 
   <td>För varje grupp som du vill lägga till användaren i klickar du på <b>Lägg till objekt</b> och anger eller mappar gruppen. Du kan ange upp till fyra grupper och måste ange minst en.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd Adobe ID</td> 
   <td>Välj true om du vill vara säker på att användar-ID tolkas som att det refererar till en befintlig Adobe ID även om det finns en Enterprise eller Federated ID med samma namn.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en användare

Den här åtgärdsmodulen skapar en ny användare i organisationen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID-typ</td> 
   <td>Ange om du vill skapa en användare med en Adobe ID, en Enterprise ID eller en Federated ID. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Inloggning</td> 
   <td>Om du skapar en användare med Federated ID väljer du inloggningstyp.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">E-post</td> 
   <td>Ange eller mappa den nya användarens e-postadress.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Domän</td> 
   <td>Om du skapar en användare med en Federated ID med en domänbaserad inloggning anger eller mappar du domänen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>Om du skapar en användare med en Federated ID med en domänbaserad inloggning anger eller mappar du användaren som den nya användaren kommer att representera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Förnamn</td> 
   <td>Ange eller mappa användarens förnamn.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Efternamn</td> 
   <td>Ange eller mappa användarens efternamn.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Land</td> 
   <td>Ange eller mappa ISO-landskoden för två tecken. Detta kan inte ändras efter att användaren har skapats.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Alternativ</td> 
   <td>Välj den åtgärd som ska utföras om användaren redan finns i organisationen. Om inget alternativ är markerat och användaren redan finns, returnerar modulen ett fel.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd Adobe ID</td> 
   <td>Om true tolkas användar-ID:t som att det refererar till en befintlig Adobe ID, även om det finns en Enterprise eller Federated ID med samma namn.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en användare från grupper

Den här åtgärdsmodulen tar bort medlemskapet för en användare från de angivna grupperna. Du kan ta bort en användare från upp till fyra grupper i taget.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>Ange eller mappa användaren som du vill ta bort från grupperna.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Domän</td> 
   <td>För Federated ID:n som inte är e-postadresser anger du den domän som användaren tillhör.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Grupper</td> 
   <td>För varje grupp som du vill ta bort användaren från klickar du på <b>Lägg till objekt</b> och anger eller mappar gruppen. Du kan ange upp till fyra grupper och måste ange minst en.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd Adobe ID</td> 
   <td>Välj true om du vill vara säker på att användar-ID tolkas som att det refererar till en befintlig Adobe ID även om det finns en Enterprise eller Federated ID med samma namn.</td> 
  </tr> 
 </tbody> 
</table>



#### Uppdatera en användare

Denna åtgärdsmodul uppdaterar en befintlig användare.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>Ange eller mappa ID:t för den användare som du vill uppdatera. Detta är användarens e-postadress, till exempel <code>user@example.com</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Domän</td> 
   <td>Om du uppdaterar en användare med en Federated ID som inte är en e-postadress, anger eller mappar du den domän som användaren tillhör för att identifiera användaren.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">E-post</td> 
   <td>Ange eller mappa den nya e-postadressen för användaren.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Förnamn</td> 
   <td>Ange eller mappa användarens förnamn.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Efternamn</td> 
   <td>Ange eller mappa användarens efternamn.</td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder för användargrupp

* [Lägga till medlemskap för en användargrupp](#add-memberships-for-a-user-group)
* [Skapa en användargrupp](#create-a-user-group)
* [Ta bort en användargrupp](#delete-a-user-group)
* [Ta bort medlemskap för en användargrupp](#remove-memberships-for-a-user-group)
* [Uppdatera en användargrupp](#update-a-user-group)

#### Lägga till medlemskap för en användargrupp

Den här åtgärdsmodulen lägger till användare och produktprofiler i en användargrupp. Användare som läggs till i användargruppen får rätt till alla produktprofiler i användargruppen. Om du lägger till en produktprofil får användarna i användargruppen tillgång till den profilen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gruppnamn</td> 
   <td>Ange eller mappa namnet på gruppen som du vill ta bort användare eller profiler från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>För varje användare som du vill lägga till klickar du på <b>Lägg till användare</b> och anger användarens e-postadress.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Profiler</td> 
   <td>För varje profil som du vill lägga till i gruppen klickar du på <b>Lägg till användare</b> och anger profilnamnet</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en användargrupp

Den här åtgärdsmodulen skapar en ny användargrupp. Om det redan finns en grupp med det angivna namnet kan modulen uppdatera den befintliga gruppen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gruppnamn</td> 
   <td>Ange eller mappa ett namn för den nya användargruppen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Beskrivning</td> 
   <td>Ange eller mappa en beskrivning för den nya användargruppen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Alternativ</td> 
   <td>Välj den åtgärd som ska utföras om användargruppen redan finns i organisationen. Om inget alternativ är markerat och användargruppen redan finns, returnerar modulen ett fel.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en användargrupp

Den här åtgärdsmodulen tar bort en befintlig användargrupp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gruppnamn</td> 
   <td>Ange eller mappa namnet på gruppen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort medlemskap för en användargrupp

Den här åtgärdsmodulen tar bort användare eller profiler från en användargrupp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Gruppnamn</td> 
   <td>Ange eller mappa namnet på gruppen som du vill ta bort användare eller profiler från.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Användare</td> 
   <td>För varje användare som du vill ta bort klickar du på <b>Lägg till användare</b> och anger användarens e-postadress.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Profiler</td> 
   <td>För varje profil som du vill ta bort från gruppen klickar du på <b>Lägg till användare</b> och anger profilnamnet</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd Adobe ID</td> 
   <td>Om true tolkas användar-ID:t som att det refererar till en befintlig Adobe ID även om det finns en Enterprise eller Federated ID med samma namn.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en användargrupp

Den här åtgärdsmodulen uppdaterar en befintlig användargrupp.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ursprungligt gruppnamn</td> 
   <td>Ange eller mappa det aktuella namnet på gruppen som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Nytt gruppnamn</td> 
   <td>Ange eller mappa det nya namnet som du vill att gruppen ska ha.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Ursprungligt gruppnamn</td> 
   <td>Ange eller mappa den uppdaterade beskrivningen av gruppen.</td> 
  </tr> 
 </tbody> 
 </table>

### Övriga


#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Adobe API för användarhantering.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
      <td>Instruktioner om hur du skapar en anslutning till Adobe användarhantering finns i <a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >Skapa en anslutning till Adobe användarhantering</a> i den här artikeln.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>Ange en sökväg i förhållande till <code>https://usermanagement.adobe.io/v2/usermanagement/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>Metod</p>
      </td>
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">Sidhuvuden</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] lägger automatiskt till auktoriseringsrubriker och x-api-key-rubriker.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Frågesträng  </td>
      <td>
        <p>Ange frågesträngen för begäran.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">Brödtext</td>
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>
