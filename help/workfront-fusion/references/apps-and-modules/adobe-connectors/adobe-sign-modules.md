---
title: Adobe Acrobat Sign moduler
description: Med  [!DNL Adobe Acrobat Sign] modulerna kan du starta ett [!DNL Adobe Workfront Fusion] scenario baserat på händelser i ditt [!DNL Adobe] Acrobat Sign-konto, skapa, läsa eller uppdatera avtal och andra poster, söka efter poster med villkor som du anger och överföra dokument.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 0ef9d40e-8ad6-434e-8fa0-076920ff29ea
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '5489'
ht-degree: 0%

---

# [!DNL Adobe Acrobat Sign] moduler

Med modulerna [!DNL Adobe Acrobat Sign] kan du starta ett [!DNL Adobe Workfront Fusion]-scenario baserat på händelser i ditt [!DNL Adobe Acrobat Sign]-konto, skapa, läsa eller uppdatera avtal och andra poster, söka efter poster med villkor som du anger och överföra dokument.

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

## API-information för [!DNL Adobe Acrobat Sign]

Adobe Acrobat Sign Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v6 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.35.1</td> 
  </tr>
 </tbody> 
</table>


## [!DNL Adobe Acrobat Sign] rekommendationer för anslutningsanvändning

Appen [!DNL Adobe Sign] gör det enklare och kraftfullare att automatisera affärsprocesser för e-signaturer i [!DNL Fusion].

Nya användare av [!DNL Adobe Sign] bör vara noga med att uppdatera avtal. Avtal ändras vanligtvis inte när de har startats. Vi rekommenderar att nya användare av [!DNL Adobe Sign] fokuserar på att skapa nya avtal med hjälp av modulen för att skapa avtal. Detta gör [!DNL Fusion] automatiseringar enklare och fungerar bättre med [!DNL Adobe Sign].

[!DNL Adobe Sign] avtal behöver ett fält att arbeta med. Det finns vissa alternativ för att göra detta, men det enklaste och vanligaste är att överföra ett tillfälligt dokument och sedan mappa dokumentet till ditt avtal.

![](/help/workfront-fusion/references/apps-and-modules/assets/adobe-sign-recommendations-350x168.png)

## [!DNL Adobe Acrobat Sign]-moduler och deras fält

När du konfigurerar [!DNL Adobe Acrobat Sign] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Adobe Acrobat Sign] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

<!--
* [Watch for agreements](#watch-for-agreements) 
* [Watch for events](#watch-for-events)
-->

+++ **[!UICONTROL Watch for agreements]**

Den här utlösarmodulen startar ett scenario när ett avtal skapas eller uppdateras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a></td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Välj om du vill söka efter nya poster, uppdaterade poster eller båda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type] </td> 
   <td>Välj den typ av post som du vill att posten ska bevakas.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Find text]</td> 
   <td> <p>Ange termer som du vill söka efter. Modulen returnerar poster som innehåller dessa termer som fältvärden.</p> <p>Mer information om hur du söker efter fält i [!DNL Adobe Acrobat Sign] finns i"Hur textsökning fungerar" i <a href="https://helpx.adobe.com/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">Adobe Sign Search - Så fungerar det</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned agreements]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Watch for events]**

Den här utlösarmodulen startar ett scenario när en händelse som du väljer inträffar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td>Välj den webkrok som du vill använda eller klicka på <b>[!UICONTROL Add]</b> och fyll i följande fält.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Ange ett namn för webkroken</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scopes]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Account]</p> </li> 
     <li> <p>[!UICONTROL Group]</p> </li> 
     <li> <p>[!UICONTROL User]</p> </li> 
     <li> <p>[!UICONTROL Resource]</p> <p>Om du väljer [!UICONTROL Resource] anger du resurs-ID och resurstyp.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource level]</td> 
   <td> <p>Välj den typ av resurs som du vill bevaka.</p> 
    <ul> 
     <li> <p>[!UICONTROL Agreements]</p> </li> 
     <li> <p>[!UICONTROL Widgets]</p> </li> 
     <li> <p>[!UICONTROL Megasigns]</p> </li> 
     <li> <p>[!UICONTROL Library Documents]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook subscription events]</td> 
   <td>Välj de [!DNL Adobe Sign]-händelser som du vill att modulen ska bevaka.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application display name]</td> 
   <td>Visningsnamnet för det program som webkroken skapas genom.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Application name]</td> 
   <td>Visningsnamnet för det program som webkroken skapas genom.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Problem notification emails]</td> 
   <td> <p>Den här inställningen fungerar endast för administratörskonton</p> <p>För varje e-postadress som du vill skicka problemmeddelanden till klickar du på <b>[!UICONTROL Add]</b> och anger e-postadressen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement conditional parameters]</td> 
   <td>Om du vill lägga till villkorsparametrar väljer du <b>[!UICONTROL Yes]</b> för den posttyp som du vill lägga till parametrar i och väljer sedan <b>[!UICONTROL Yes]</b> för de parametrar som du vill aktivera.</td> 
  </tr> 
 </tbody> 
</table>

+++

### Åtgärder

<!--
* [Create a record](#create-a-record) 
* [Create an agreement](#create-an-agreement) 
* [Create related records](#create-related-records) 
* [Custom API Call](#custom-api-call) 
* [List records](#list-records) 
* [Read a record](#read-a-record) 
* [Read related records](#read-related-records) 
* [Update a record](#update-a-record) 
* [Update related record](#update-related-record) 
* [Upload document](#upload-document)
-->

+++ **[!UICONTROL Create a record]**

Den här åtgärdsmodulen skapar en ny post av den valda typen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.Till exempel <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>Välj den typ av post som du vill skapa.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Group]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL Widget])</b> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group info]</td> 
   <td> <p>Ange eller mappa gruppens [!UICONTROL Name] och [!UICONTROL ID] och ange om den här gruppen är standardgruppen för kontot.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library document info]</td> 
   <td> <p>Fyll i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Files to send]</b> </p> <p>För varje fil som du vill lägga till klickar du på <b>[!UICONTROL Add item]</b> och fyller i fälten.</p> 
      <ul> 
       <li><b>[!UICONTROL Transient document ID]</b> <p>Ange ID:t för det tillfälliga dokumentet</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>Fyll i följande fält:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Ange mime-typen för den ursprungliga filen. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen <code>text/html</code> kommer att bearbetas i en annan webbläsare än en fil med MIME-typen <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange ett namn för filen.</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>Ange URL-adressen till filen som du vill skicka.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>Välj om det här dokumentet ska registreras.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Library template name]</b> </p> <p>Ange eller mappa namnet på biblioteksmallen</p> </li> 
     <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>Ange vem som ska ha åtkomst till biblioteksdokumentet.</p> </li> 
     <li> <p><b>[!UICONTROL Library document state]</b> </p> <p>Välj om dokumentet är i redigeringsläge eller aktivt.</p> </li> 
     <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>För varje biblioteksmalltyp som du vill använda klickar du på <b>[!UICONTROL Add item]</b> och väljer malltypen.</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>Ange det senaste datumet då en händelse inträffade i biblioteksdokumentet.</p> <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </li> 
     <li> <p><b>[!UICONTROL Library document status]</b> </p> <p>Välj biblioteksdokumentets status.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User info]</td> 
   <td> <p>Fyll i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>Ange användarens e-postadress.</p> </li> 
     <li> <p><b>[!UICONTROL Is account admin]</b> </p> <p>Markera det här alternativet om den skapade användaren är kontoadministratör.</p> </li> 
     <li> <p><b>[!UICONTROL User ID]</b> </p> <p>Ange användarens unika ID</p> </li> 
     <li> <p><b>[!UICONTROL Account ID]</b> </p> <p>Ange det unika ID:t för det [!DNL Adobe Acrobat Sign]-konto som är associerat med den här användaren.</p> </li> 
     <li> <p><b>[!UICONTROL First name]</b> </p> <p>Ange användarens förnamn.</p> </li> 
     <li> <p><b>[!UICONTROL Last name]</b> </p> <p>Ange användarens efternamn</p> </li> 
     <li> <p><b>[!UICONTROL Company]</b> </p> <p>Ange namnet på användarens företag.</p> </li> 
     <li> <p><b>[!UICONTROL Initials]</b> </p> <p>Ange användarens initialer.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange användarens språkområde. Detta avgör språket i användargränssnittet. </p> </li> 
     <li> <p><b>[!UICONTROL Phone]</b> </p> <p>Ange användarens telefonnummer</p> </li> 
     <li> <p><b>ID för primär grupp</b> </p> <p>Ange den grupp som den nya användaren ska läggas till i. Om inget anges läggs användaren till i kontots standardgrupp.</p> </li> 
     <li> <p><b>[!UICONTROL Job title]</b> </p> <p>Ange användarens jobbtitel.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Web form info]</td> 
   <td> <p>Fyll i följande fält</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File info]</b> </p> <p>För varje fil som du vill lägga till i webbformuläret klickar du på Lägg till och fyller i följande fält:</p> 
      <ul> 
       <li> <p>[!UICONTROL File type]</p> <p>[!UICONTROL Document]</p> </li> 
       <li> <p>[!UICONTROL Transient document]</p> </li> 
       <li> <p>[!UICONTROL URL file info]</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form name]</b> </p> <p>Ange ett namn för webbformuläret. Det här namnet används för att identifiera webbformuläret på platser som e-post och webbplatser.</p> </li> 
     <li> <p><b>[!UICONTROL Web form state]</b> </p> <p>Välj i vilket läge det nya webbformuläret ska skapas.</p> </li> 
     <li> <p><b>[!UICONTROL Web form participant set info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>Klicka på <b>[!UICONTROL Add item]</b> för varje medlem som du vill lägga till i deltagaruppsättningen. </p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Lämna det här alternativet tomt.</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>Om du vill lägga till ett säkerhetsalternativ för att autentisera den här användaren väljer du <b>[!UICONTROL Yes]</b>, markerar sedan säkerhetsalternativet och fyller i de fält som krävs.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> <p>Välj rollen. Alla medlemmar i den här deltagaruppsättningen delar rollen.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form additional participant sets info]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>Klicka på <b>[!UICONTROL Add item]</b> för varje medlem som du vill lägga till i deltagaruppsättningen.</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Lämna det här alternativet tomt.</p> </li> 
         <li> <p><b>[!UICONTROL Security option]</b> </p> <p>Om du vill lägga till ett säkerhetsalternativ för att autentisera den här användaren väljer du <b>[!UICONTROL Yes]</b>, markerar sedan säkerhetsalternativet och fyller i de fält som krävs.</p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Role]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Web form participant ID] </b> </p> <p>Ange webbformulärets deltagares ID.</p> </li> 
       <li> <p><b>[!UICONTROL Order]</b> </p> <p>Ange i vilken ordning den här deltagaruppsättningen ska interagera med webbformuläret. Deltagargruppen som har ordervärdet 1 måste till exempel gå först, 2 måste gå vidare. Ordernummer måste börja med ett och har inga mellanrum i serien. </p> </li> 
       <li> <p><b>[!UICONTROL Provider participant set info]</b> </p> <p>Om deltagaren är okänd anger du om leverantören måste ange information för deltagaren och anger ett meddelande med den information som du behöver för den okända deltagaren.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Authentication failure info]</b> </p> <p>Om du vill ge användarna en felsida eller felsida väljer du <b>[!UICONTROL Yes]</b> och fyller sedan i följande fält:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>Ange URL:en för felsidan</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>Aktivera alternativet om du vill att felsidan ska visas i webbformuläret</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>Ange fördröjningen i sekunder innan användaren omdirigeras till felsidan.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL CC info]</b> </p> <p>För varje e-postadress som du vill få ett e-postmeddelande när det slutliga avtalet på webbformuläret signeras klickar du på <b>[!UICONTROL Add item]</b> och anger e-postadressen.</p> </li> 
     <li> <p><b>[!UICONTROL Completion info]</b> </p> <p style="font-style: normal;">Om du vill skicka en sida med lyckade åtgärder till dina användare väljer du <b>[!UICONTROL Yes]</b> och fyller sedan i följande fält:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL URL]</b> </p> <p>Ange URL-adressen till sidan där åtgärden lyckades</p> </li> 
       <li> <p><b>[!UICONTROL Deframe]</b> </p> <p>Aktivera det här alternativet om du vill att framgångssidan ska visas i webbformuläret</p> </li> 
       <li> <p><b>[!UICONTROL Delay]</b> </p> <p>Ange fördröjningen i sekunder innan användaren omdirigeras till sidan för slutförande.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Group ID]</b> </p> <p>Ange ID:t för gruppen som webbformuläret tillhör. Om inget anges tillhör webbformuläret kontoanvändarens primära grupp.</p> </li> 
     <li> <p><b>[!UICONTROL Last event date]</b> </p> <p>Ange det datum då den senaste händelsen inträffade i webbformuläret. Använd formatet <code>yyyy-MM-dd'T'HH:mm:ssZ</code>.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange användarens språkområde. Detta avgör språket i användargränssnittet. </p> </li> 
     <li> <p><b>[!UICONTROL Security optio]n</b> </p> <p>Ange lösenordet som används för att skydda dokumentet. Du måste skicka detta lösenord till alla berörda parter separat.</p> </li> 
     <li> <p><b>[!UICONTROL Vaulting info]</b> </p> <p>Om ditt konto är inställt för dokumentsäkerhet och alternativet att aktivera per avtal kan du aktivera det här alternativet för att validera det här avtalet.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create an agreement]**

Den här åtgärdsmodulen skapar ett avtal, skickar det för signering och returnerar avtals-ID:t.

>[!NOTE]
>
>Vi rekommenderar att du överför dokumentet för signering som ett tillfälligt dokument och sedan mappar det till fältet [!UICONTROL File to send] i modulen [!UICONTROL Create an agreement]. Se till exempel&quot;Överför dokument&quot; i den här artikeln.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
<td>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a></td>  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.Till exempel <code>{"Content-type":"application/json"}</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Files to send]</td> 
   <td> <p>För varje objekt som du vill inkludera i avtalet klickar du på <b>[!UICONTROL Add Item]</b> och fyller i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL File Type]</b> </p> 
      <ul> 
       <li> <p><b>[!UICONTROL Document]</b> </p> <p>Fyll i följande fält:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>Ange eller mappa datumet då dokumentet skapades i formatet <code>yyyy-MM-dd'T'HH:mm:ssZ</code>. <code>2016-02-25T18:46:19Z</code> representerar till exempel UTC-tid.</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>Ange eller mappa dokumentets ID.</p> </li> 
         <li> <p><b>[!UICONTROL Label]</b> </p> <p>Ange eller mappa en unik etikett för filen. Om arbetsflödet är anpassat mappas en fil till motsvarande filelement i arbetsflödesdefinitionen. Detta måste anges när en anpassad begäran om att skapa ett arbetsflödesavtal skapas.</p> </li> 
         <li> <p><b>[!UICONTROL Number of pages]</b> </p> <p>Ange eller mappa antalet sidor i dokumentet.</p> </li> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Ange eller mappa mime-typen för den ursprungliga filen. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen <code>text/html</code> kommer att bearbetas i en annan webbläsare än en fil med MIME-typen <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange eller mappa ett namn för dokumentet.<br></p> </li> 
        </ul> </li> 
       <li> <p><b>[!UICONTROL Library document ID]</b> </p> <p>Ange ID för biblioteksdokumentet</p> </li> 
       <li> <p><b>[!UICONTROL Transient document ID]</b> </p> <p>Ange ID:t för det tillfälliga dokumentet</p> </li> 
       <li> <p><b>[!UICONTROL URL file transfer]</b> </p> <p>Fyll i följande fält:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Mime-Type]</b> </p> <p>Ange mime-typen för den ursprungliga filen. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen <code>text/html</code> kommer att bearbetas i en annan webbläsare än en fil med MIME-typen <code>image/jpeg</code>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange ett namn för filen.</p> </li> 
         <li> <p><b>[!UICONTROL URL]</b> </p> <p>Ange URL-adressen till filen som du vill skicka.</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Ange en etikett för filen.</p> </li> 
     <li> <p><b>[!UICONTROL Notarize]</b> </p> <p>Aktivera det här alternativet om du vill ange att filen måste antecknas.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement name]</td> 
   <td>Ange ett namn för det nya avtalet. Det här namnet används för att identifiera avtalet på platser som e-post och webbplatser.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant sets info]</td> 
   <td> <p>För varje deltagaruppsättning som du vill lägga till klickar du på <b>[!UICONTROL Add item]</b> och fyller i följande fält.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Members]</b> </p> <p>För varje person som du vill lägga till i deltagaruppsättningen klickar du på <b>[!UICONTROL Add item]</b> och anger personens e-postadress.</p> </li> 
     <li> <p><b>[!UICONTROL Order]</b> </p> <p>Ange ordningen för när den här deltagaruppsättningen ska signera avtalet. Deltagargruppen som har ordervärdet 1 måste signera först, 2 måste signera nästa och så vidare. Ordernummer måste börja med ett och har inga mellanrum i serien. </p> </li> 
     <li> <p><b>[!UICONTROL Role]</b> </p> <p>Välj en roll för deltagaruppsättningen. Alla deltagare i uppsättningen får den här rollen.</p> </li> 
     <li> <p><b>[!UICONTROL ID]</b> </p> <p>Ange eller mappa ID för den här deltagaruppsättningen.</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Ange eller mappa en unik etikett för deltagaruppsättningen. För anpassade arbetsflöden bör etiketten som anges i deltagaruppsättningen mappas till deltagarsteget i det anpassade arbetsflödet.</p> </li> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange ett namn för deltagaruppsättningen. Namnet måste vara unikt i avtalet.</p> </li> 
     <li> <p><b>[!UICONTROL Private message]</b> </p> <p>Ange eller mappa ett meddelande för den här deltagaruppsättningen. Alla deltagare i uppsättningen får det här meddelandet.</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> <p>Om begränsad dokumentsynlighet är aktiverat för det här avtalet anger du vilka filer som är synliga för den här deltagaruppsättningen. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Signature type]</td> 
   <td> <p>Välj den typ av signatur som avtalet kräver.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL E-sign]</b> </p> <p>Avtalet måste signeras elektroniskt.</p> </li> 
     <li> <p><b>[!UICONTROL Written]</b> </p> <p>Avtalet måste signeras för hand och det signerade avtalet måste skannas och överföras.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL State]</td> 
   <td> <p>Välj en status för det här avtalet.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Authoring]</b> </p> <p>Du kan fortfarande redigera eller lägga till fält i det här avtalet.</p> </li> 
     <li> <p><b>[!UICONTROL Draft]</b> </p> <p>Du kan skapa det här avtalet stegvis innan du skickar ut det.</p> </li> 
     <li> <p><b>[!UICONTROL In Process]</b> </p> <p>Detta avtal skickas omedelbart.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CCs]</td> 
   <td> <p>Du kan skicka det här avtalet till berörda parter som inte behöver signera, till exempel intressenter. De får ett e-postmeddelande i början av signeringsprocessen och ett annat när den slutliga signaturen tas emot. De får också en kopia av avtalet PDF. </p> <p>Klicka <b>[!UICONTROL Add item]</b> för varje person som du vill CC för det här avtalet och fyll i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Email]</b> </p> <p>Ange eller mappa den e-postadress som du vill ska ingå i avtalet.</p> </li> 
     <li> <p><b>[!UICONTROL Label]</b> </p> <p>Ange eller mappa en etikett för den här e-postadressen enligt arbetsflödesbeskrivningen</p> </li> 
     <li> <p><b>[!UICONTROL Visible pages]</b> </p> </li> 
     <li> <p>Om begränsad dokumentsynlighet är aktiverat för det här avtalet anger du vilka filer som är synliga för den här deltagaruppsättningen. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email option]</td> 
   <td> <p>För varje typ av e-post väljer du om den typen av e-post ska skickas till alla deltagare eller ingen.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Completion emails]</b> </p> <p>Skicka ett e-postmeddelande när avtalet har slutförts, annullerats, förfallit eller avvisats.</p> </li> 
     <li> <p><b>[!UICONTROL In-Flight emails]</b> </p> <p>Skickade ett e-postmeddelande när det här avtalet har delegerats eller ersatts.</p> </li> 
     <li> <p><b>[!UICONTROL Agreement initiation emails]</b> </p> <p>Skicka ett e-postmeddelande när avtalet skapas eller när en åtgärd begärs.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p>Ange eller mappa ett ID för det här avtalet. Du kan ange detta när avtalet skapas och använda det för att hitta avtalet i senare moduler eller frågor.</p> <p>Obs! Värdet för externt ID är synligt för alla deltagare via API:t, så det bör inte användas för att innehålla en känslig token.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Merge field info]</td> 
   <td> <p>För varje fält i avtalet som du vill ange ett standardvärde för klickar du på <b>[!UICONTROL Add item]</b> och anger standardvärdet och fältnamnet.</p> <p>Värdena presenteras för signerarna för redigerbara fält För skrivskyddade fält går det inte att redigera de angivna värdena under signeringsprocessen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Notary info]</td> 
   <td> <p>Fyll i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Appointment]</b> </p> <p>Ange eller mappa en föreslagen tid och ett datum för den avtalade tiden för att anteckna det här avtalet.</p> </li> 
     <li> <p><b>[!UICONTROL Note]</b> </p> <p>Ange eller mappa eventuella anteckningar som du vill inkludera om notariesessionen.</p> </li> 
     <li> <p><b>[!UICONTROL Payment]</b> </p> <p>Välj om notarien ska betalas av signeraren eller avsändaren av avtalet.</p> </li> 
     <li> <p><b>[!UICONTROL Notary Type]</b> </p> <p>Välj typ av notation</p> 
      <ul> 
       <li> <p>[!UICONTROL Provider notary]</p> <p>Den notarius publicus tillhandahålls av notarien.</p> </li> 
       <li> <p>[!UICONTROL BYON notary]</p> <p>Notarien tillhandahålls av kunden.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Post sign option]</td> 
   <td> <p>Välj om du vill att signerarna ska dirigeras till en lyckad sida efter att avtalet har signerats. Om du väljer <b>[!UICONTROL Yes]</b> fyller du i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Redirect delay]</b> </p> <p>Ange eller mappa ett tal som representerar antalet sekunder innan signeraren omdirigeras till framgångssidan. Om det här värdet är större än 0 kommer användaren först att se standardmeddelandet [!DNL Adobe Sign] om att åtgärden lyckades, och sedan kommer en fördröjning att dirigeras om till din sida om att åtgärden lyckades.</p> </li> 
     <li> <p><b>[!UICONTROL Redirect URL]</b> </p> <p>Ange eller mappa en offentligt tillgänglig URL som användaren ska skickas till när signeringsprocessen har slutförts.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Security option]</td> 
   <td> <p>Ange eller mappa det sekundära lösenordet som ska användas för att skydda dokumentet i PDF. </p> <p>Viktigt! [!DNL Adobe Sign] delar aldrig det här lösenordet, så du måste skicka det separat till alla relevanta parter.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Vaulting info]</td> 
   <td>Om ditt konto är inställt för dokumentsäkerhet och alternativet att aktivera per avtal kan du aktivera det här alternativet för att validera det här avtalet.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create related records]**

Den här åtgärdsmodulen skapar poster som är länkade till en modul som du väljer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj posttypen för den ursprungliga post som du vill associera de skapade posterna med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]/[!UICONTROL Library document]/[!UICONTROL User]/[!UICONTROL Widget ID]</td> 
   <td>Ange eller mappa ID:t för objektet som du vill associera den skapade posten med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement related field]</td> 
   <td> <p>Välj den typ av relaterat fält som du vill skapa</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Form fields]</b> </p> <p>Ange mall-ID för mallen som innehåller de fält som du vill skapa</p> </li> 
     <li> <p><b>[!UICONTROL Reminders]</b> </p> <p>Fyll i följande fält:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Recipient participant ID]</b> </p> <p>För varje deltagare som du vill få en påminnelse klickar du på [!UICONTROL Add item] och anger deltagarens ID.</p> </li> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>För nya poster måste statusen vara [!UICONTROL Active].</p> </li> 
       <li> <p><b>[!UICONTROL First reminder delay]</b> </p> <p>Ange fördröjningen i timmar innan den första påminnelsen skickas. Det minsta tillåtna värdet är 1 timme och det högsta värdet får inte vara mer än skillnaden mellan avtalsskapande och avtalets förfallotid i timmar. Om den här fördröjningen inte anges baseras den första påminnelsen på frekvensen.</p> </li> 
       <li> <p><b>[!UICONTROL Reminder frequency]</b> </p> <p>Ange hur ofta du vill att påminnelsen ska skickas. Om ingen frekvens anges skickas påminnelsen en gång.</p> </li> 
       <li> <p><b>[!UICONTROL Last sent date]</b> </p> <p>Det här fältet ställs in av systemet.</p> </li> 
       <li> <p><b>[!UICONTROL Next sent date]</b> </p> <p>Det här fältet måste vara tomt eller inställt på [!UICONTROL ONCE].</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>Skriv en anteckning som ska ingå i påminnelsen. Detta är användbart för att tala om för deltagaren varför deras deltagande krävs.</p> </li> 
       <li> <p><b>[!UICONTROL Start reminder counter from]</b> </p> <p>Välj om påminnelsen ska skickas baserat på när avtalet skapas när det blir tillgängligt.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Signer identity report]</b> </p> <p>Ange det lösenord som används för att skydda PDF-dokumentet.</p> </li> 
     <li> <p><b>[!UICONTROL Views]</b> </p> <p>Ange följande fält</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Markera namnet på den vy som du vill skapa.</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du automatiskt vill logga in användaren på den returnerade URL:en.</p> </li> 
       <li> <p><b>[!UICONTROL Frame Parent]</b> </p> <p>Ange eller mappa en kommaavgränsad lista över överordnade domänadresser där de returnerade URL:erna kan infogas. Om [!DNL Adobe Acrobat Sign]-sidorna är tomma kan de inte visas i iframe.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange det språk som du vill skapa vyn i. </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill visa den inbäddade sidan utan ett navigeringssidhuvud eller en sidfot.</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att avsnittet för filöverföring ska redigeras genom att filer läggs till eller tas bort. Detta är inte en åtkomstkontrollsmaskin. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Library document]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att biblioteksdokumentlänkar ska visas. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att den lokala filöverföringsknappen ska visas. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att länkarna ska bifoga dokument från webbkällor ska visas. Standardvärdet är Ja.</p> </li> 
       <li> <p><b>[!UICONTROL Is preview selected]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill ställa in redigeringsläget på sidan Disposition.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>För varje medlem som du vill dela avtalet med klickar du på <b>[!UICONTROL Add item]</b> och anger medlemmens e-postadress och ett meddelande till medlemmen.</p> </li> 
     <li> <p>[!UICONTROL Delegate participant set]</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Participant set ID]</b> </p> <p>Ange deltagaruppsättningens ID</p> </li> 
       <li> <p><b>[!UICONTROL Member info]</b> </p> <p>För varje medlem som du vill lägga till klickar du på [!UICONTROL Add item] och anger medlemmens e-postadress och telefoninformation.</p> </li> 
       <li> <p><b>[!UICONTROL Private message]</b> </p> <p>Skriv ett meddelande. Alla medlemmar i deltagaruppsättningen får det här meddelandet.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Library view info]</td> 
   <td> <p>Fyll i följande fält:</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange ett namn för biblioteksmallen. Det här namnet används i e-postmeddelanden och på webbplatser.</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du automatiskt vill logga in användaren på den returnerade URL:en.</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Ange eller mappa en kommaavgränsad lista över överordnade domänadresser där de returnerade URL:erna kan infogas. Om [!DNL Adobe Acrobat Sign]-sidorna är tomma kan de inte visas i iframe.</p> </li> 
     <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange det språk som du vill skapa vyn i. </p> </li> 
     <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill visa den inbäddade sidan utan ett navigeringssidhuvud eller en sidfot.</p> </li> 
     <li> <p><b>[!UICONTROL Send view configuration]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill konfigurera vyn [!UICONTROL Send] och fyll sedan i följande fält.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Agreement name]</b> </p> <p>Ange eller mappa avtalsnamnet för biblioteksdokumentet på dispositionssidan.</p> </li> 
       <li> <p><b>[!UICONTROL Can edit files]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att avsnittet för filöverföring ska redigeras genom att filer läggs till eller tas bort. Detta är inte en åtkomstkontrollsmaskin. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Local file]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att biblioteksdokumentlänkar ska visas. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>[!UICONTROL Web connectors]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att länkarna ska bifoga dokument från webbkällor ska visas. Standardvärdet är [!UICONTROL Yes].</p> </li> 
       <li> <p><b>Är förhandsgranskning markerad</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill ställa in redigeringsläget på sidan Disposition.</p> </li> 
      </ul> <p> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User view info]</td> 
   <td> <p>Fyll i följande fält</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Name]</b> </p> <p>Välj namnet på den begärda användarvyn.</p> </li> 
     <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill logga in användaren automatiskt. Välj <b>[!UICONTROL No]</b> om du vill begära inloggningsuppgifter. Standardvärdet är [!UICONTROL No].</p> </li> 
     <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Ange eller mappa en kommaavgränsad lista över överordnade domänadresser där de returnerade URL:erna kan infogas. Om [!DNL Adobe Acrobat Sign]-sidorna är tomma kan de inte visas i iframe.</p> </li> 
     <li> <p><b>Ingen fönsterflagga</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill visa den inbäddade sidan utan ett navigeringssidhuvud eller en sidfot.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Widget related fields]</td> 
   <td> <p>Markera den relaterade post som du vill skapa.</p> 
    <ul> 
     <li> <p>[!UICONTROL Views]</p> <p>Fyll i följande fält.</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Välj namnet på den begärda webbformulärvyn</p> </li> 
       <li> <p><b>[!UICONTROL Auto login user]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill logga in användaren automatiskt. Välj <b>[!UICONTROL No]</b> om du vill begära inloggningsuppgifter. Standardvärdet är [!UICONTROL No].</p> </li> 
       <li> <p><b>[!UICONTROL Frame parent]</b> </p> <p>Ange eller mappa en kommaavgränsad lista över överordnade domänadresser där de returnerade URL:erna kan infogas. Om [!DNL Adobe Acrobat Sign]-sidorna är tomma kan de inte visas i iframe.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange det språk som du vill skapa vyn i. </p> </li> 
       <li> <p><b>[!UICONTROL No chrome flag]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill visa den inbäddade sidan utan ett navigeringssidhuvud eller en sidfot.</p> </li> 
       <li> <p>[!UICONTROL Personalized signing view configuration]</p> <p>Om du vill konfigurera en anpassad signeringsvy väljer du <b>[!UICONTROL Yes]</b> och fyller i följande fält:</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Email]</b> </p> <p>Ange e-postadressen till den person som tar emot det nya webbformuläret</p> </li> 
         <li> <p><b>[!UICONTROL Comment]</b> </p> <p>Ange en kommentar som beskriver hur API-anroparen etablerade undertecknarens identitet. Den här informationen visas i granskningsspåret [!DNL Adobe Acrobat Sign].</p> </li> 
         <li> <p><b>[!UICONTROL Expiration]</b> </p> <p>Ange ett förfallodatum för personaliseringen av det här webbformuläret. </p> <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Typtvång i [!DNL Adobe Workfront Fusion]</a>.</p> </li> 
         <li> <p><b>[!UICONTROL Reusable]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill att den avsedda signeraren ska kunna signera formuläret mer än en gång.</p> </li> 
        </ul> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Member share]</b> </p> <p>För varje medlem som du vill dela avtalet med klickar du på <b>[!UICONTROL Add item]</b> och anger medlemmens e-postadress och ett meddelande till medlemmen.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Custom API Call]**
Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en sökväg i förhållande till <code>https://api.[region].adobesign.com/api/rest/v6/</code></p> <p>Obs! En lista över tillgängliga slutpunkter finns i API-referensen för [!DNL Adobe Sign].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Ange frågesträngen för begäran.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a transient document]</td> 
   <td> <p>Om du vill överföra ett tillfälligt dokument anger du källfilen för dokumentet som du vill överföra.</p> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List records]**

Den här åtgärdsmodulen visar alla poster av den valda typen som kontot har åtkomst till.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill hämta relaterade poster för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td> <p>Ange användarens språkområde. Detta avgör språket i användargränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td>Ange eller mappa det externa ID:t (ett ID som tilldelats utanför [!DNL Adobe Acrobat Sign]) för de avtal som du vill returnera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td>Ange ID:t för gruppen som är associerad med de poster som du vill visa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show hidden (records)]</td> 
   <td>Aktivera det här alternativet om du vill inkludera dolda poster i dina resultat.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cursor] / [!UICONTROL Start index]</td> 
   <td> <p>Ange numret på den första posten som modulen ska returnera. </p> <p>Obs! Det här fältet kombineras med fältet [!UICONTROL Maximum number of returned records] för sidnumrering. Om [!UICONTROL Maximum number of returned events] till exempel är 100 och [!UICONTROL Start index] är 101, returnerar modulen posterna 101-200, eller den andra resultatsidan.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned records]</td> 
   <td> <p>Ange eller mappa det maximala antalet poster som du vill att modulen ska [åtgärd] under varje körningscykel för scenario.</p> <p>Obs! Det här fältet kombineras med fältet [!UICONTROL Cursor] eller [!UICONTROL Start Index] för sidnumrering. Om [!UICONTROL Maximum number of returned events] till exempel är 100 och [!UICONTROL Start index] är 101, returnerar modulen posterna 101-200, eller den andra resultatsidan.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent domain URLs]</td> 
   <td> <p>Ange eller mappa en kommaavgränsad lista över överordnade domänadresser där de returnerade URL:erna kan infogas. Om [!DNL Adobe Acrobat Sign]-sidorna är tomma kan de inte visas i iframe.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Read a record]**

Den här åtgärdsmodulen hämtar information från en enda post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill hämta relaterade poster för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>Ange eller mappa ID:t för den post som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Read related records]**

Läs ytterligare information om en enskild post.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill hämta relaterade poster för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID] (Exempel: [!UICONTROL Account ID])</td> 
   <td>Ange eller mappa ID:t för den post som du vill hämta relaterade poster för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td>Ange information i specifika fält baserat på posttyp och relaterade fält.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Update a record]**

Den här åtgärdsmodulen uppdaterar en enskild post i [!DNL Adobe Acrobat Sign].

>[!IMPORTANT]
>
>* Som en god praxis rekommenderar vi att du skapar ett nytt avtal i stället för att uppdatera det befintliga avtalet, om du förutser väsentliga ändringar i ett avtal.
>* Vissa uppdateringar har obligatoriska fält. När du konfigurerar uppdateringen måste du fylla i alla obligatoriska fält. Obligatoriska fält är feta i [!DNL Workfront Fusion] moduler.
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID] </td> 
   <td>Ange eller mappa ID:t för den post som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj den typ av post som du vill uppdatera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>Ange information i specifika fält baserat på posttyp och relaterade fält.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>Som en god praxis rekommenderar vi att du skapar ett nytt avtal i stället för att uppdatera det befintliga avtalet, om du förutser väsentliga ändringar i ett avtal.</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p>Markera de fält som du vill uppdatera och fyll sedan i de markerade fälten:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Status]</b> </p> <p>Välj den nya statusen för biblioteksdokumentet.</p> </li> 
       <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange eller mappa namnet på biblioteksmallen</p> </li> 
       <li> <p><b>[!UICONTROL Sharing mode]</b> </p> <p>Ange vem som ska ha åtkomst till biblioteksdokumentet.</p> </li> 
       <li> <p><b>[!UICONTROL Library template type]</b> </p> <p>För varje biblioteksmalltyp som du vill använda klickar du på <b>[!UICONTROL Add item]</b> och väljer malltypen.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p>Markera de fält som du vill uppdatera och fyll sedan i de markerade fälten:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL First name]</b> </p> <p>Ange användarens förnamn.</p> </li> 
       <li> <p><b>[!UICONTROL Last name]</b> </p> <p>Ange användarens efternamn</p> </li> 
       <li> <p><b>[!UICONTROL Company]</b> </p> <p>Ange namnet på användarens företag.</p> </li> 
       <li> <p><b>[!UICONTROL Phone]</b> </p> <p>Ange användarens telefonnummer</p> </li> 
       <li> <p><b>[!UICONTROL Primary group ID]</b> </p> <p>Ange den grupp som den nya användaren ska läggas till i. Om inget anges läggs användaren till i kontots standardgrupp.</p> </li> 
       <li> <p><b>[!UICONTROL Job title]</b> </p> <p>Ange användarens jobbtitel.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL widget])</b> </p> <p>Ange information i specifika fält baserat på posttyp och relaterade fält.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Update related record]**

Den här åtgärdsmodulen uppdaterar poster som är relaterade till ett specifikt objekt.

>[!IMPORTANT]
>
>* Som en god praxis rekommenderar vi att du skapar ett nytt avtal i stället för att uppdatera det befintliga avtalet, om du förutser väsentliga ändringar i ett avtal.
>* Vissa uppdateringar har obligatoriska fält. När du konfigurerar uppdateringen måste du fylla i alla obligatoriska fält. Obligatoriska fält är feta i [!DNL Workfront Fusion] moduler.
>



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td>Välj posttypen för den post som de relaterade fälten är kopplade till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Agreement]/[!UICONTROL Library document]/[!UICONTROL User]/[!UICONTROL Widget ID]</td> 
   <td>Ange eller mappa ID:t för objektet som du vill associera den skapade posten med.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Other fields]</td> 
   <td> <p>Ange information i specifika fält baserat på posttyp och relaterade fält.</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Agreement]</b> </p> <p>Som en god praxis rekommenderar vi att du skapar ett nytt avtal i stället för att uppdatera det befintliga avtalet, om du förutser väsentliga ändringar i ett avtal.</p> </li> 
     <li> <p><b>[!UICONTROL Library document]</b> </p> <p>Markera de fält som du vill uppdatera och fyll sedan i de markerade fälten:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>Välj den nya statusen för biblioteksdokumentet.</p> </li> 
       <li> <p><b>[!UICONTROL Note]</b> </p> <p>Ange eller mappa texten i anteckningen.</p> </li> 
       <li> <p><b>[!UICONTROL Visibility]</b> </p> <p>Välj om biblioteksdokumentet ska visas eller inte.</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL User]</b> </p> <p>Markera de fält som du vill uppdatera och fyll sedan i de markerade fälten:</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Group info list]</b> </p> <p>Fyll i följande fält</p> 
        <ul> 
         <li> <p><b>[!UICONTROL Status]</b> </p> <p>Välj ny status för användaren.</p> </li> 
         <li> <p><b>[!UICONTROL ID]</b> </p> <p>Ange gruppens unika ID</p> </li> 
         <li> <p><b>[!UICONTROL Is group admin]</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill göra den här användaren till en gruppadministratör.</p> </li> 
         <li> <p><b>Är primär grupp</b> </p> <p>Välj <b>[!UICONTROL Yes]</b> om du vill uppdatera den här gruppen till användarens primära grupp.</p> </li> 
         <li> <p><b>[!UICONTROL Created date]</b> </p> <p>Ange det datum då gruppen skapades.</p> <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">Typtvång i [!UICONTROL Adobe Workfront Fusion]</a>.</p> </li> 
         <li> <p><b>[!UICONTROL Name]</b> </p> <p>Ange eller mappa namnet på gruppen.</p> </li> 
         <li> <p><b>[!UICONTROL Library document creation visible]</b> </p> <p>Dessa inställningar avgör om användaren kan skapa biblioteksdokument</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Tillåt</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Ärv gruppinställning från grupp eller konto</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL Send restricted to workflows]</b> </p> <p>Dessa inställningar avgör om användaren kan skapa avtal enbart med hjälp av arbetsflöden.</p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Tillåt</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Ärv gruppinställning från grupp eller konto</p> </li> 
          </ul> </li> 
         <li> <p><b>[!UICONTROL User can send]</b> </p> 
          <ul> 
           <li> <p>[!UICONTROL Value]</p> <p>Tillåt</p> </li> 
           <li> <p>[!UICONTROL Inherited]</p> <p>Ärv gruppinställning från grupp eller konto</p> </li> 
          </ul> </li> 
        </ul> </li> 
      </ul> 
      <ul> 
       <li> <p><b>[!UICONTROL State]</b> </p> <p>Välj det nya tillståndet för användaren och ange en kommentar om varför du vill aktivera eller inaktivera användaren.</p> </li> 
       <li> <p><b>[!UICONTROL Locale]</b> </p> <p>Ange användarens språkområde. Detta avgör språket i användargränssnittet. </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Web form] ([!UICONTROL widget])</b> </p> <p>Ange information i specifika fält baserat på posttyp och relaterade fält.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Upload document]**

Överför ett tillfälligt dokument. Ett tillfälligt dokument är tillgängligt i 7 dagar efter att det har överförts.

>[!NOTE]
>
>Vi rekommenderar att du överför dokumentet för signering som ett tillfälligt dokument och sedan mappar det till fältet Arkiv för att skicka i modulen Skapa ett avtal.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record ID]</td> 
   <td>Ange eller mappa ID:t för den post som du vill uppdatera</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td>Ange mime-typen för den ursprungliga filen. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen <code>text/html</code> kommer att bearbetas i en annan webbläsare än en fil med MIME-typen <code>image/jpeg</code>.</td> 
  </tr> 
 </tbody> 
</table>

**Exempel:** I det här arbetsflödet överförs det dokument som ska signeras (som tidigare hämtats från Workfront) som ett tillfälligt dokument.

![](/help/workfront-fusion/references/apps-and-modules/assets/sign-example-1-350x308.png)

Modulen [!UICONTROL Upload document] ger dokumentet ett [!DNL Adobe Acrobat Sign]-ID som kan refereras i senare moduler. När avtalet skapas inkluderas det överförda dokumentets ID i fältet [!UICONTROL Files to send].

![](/help/workfront-fusion/references/apps-and-modules/assets/sign-example-2-350x356.png)

+++

### Sökningar

+++ **[!UICONTROL Search agreements]**

Den här sökmodulen söker efter avtal baserat på de villkor du anger.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Acrobat Sign]-konto till [!DNL Workfront Fusion] finns i <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Workfront Fusion] - grundläggande instruktioner</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text filter]</td> 
   <td> <p>Sök efter text i avtalsmetadata. </p> 
    <ul> 
     <li> <p><b>[!UICONTROL Find text]</b> </p> <p>Ange den text som du vill söka efter i avtalsmetadata. Varje ord behandlas som ett separat textobjekt. </p> </li> 
     <li> <p><b>[!UICONTROL Find text in]</b> </p> <p>Markera metadatafälten som du vill söka efter text i. Om du inte markerar något söks alla metadata igenom.</p> </li> 
    </ul> <p>Modulen returnerar alla avtal som innehåller någon av den angivna texten i något av de markerade fälten. Exempel: om du anger "vårkampanj" och väljer alternativen Titel och Anteckning returneras alla avtal med orden "vår" eller "Campaign" i antingen Titel eller Anteckning.</p> <p>Mer information om hur du söker efter fält i [!DNL Adobe Acrobat Sign] finns i"Hur textsökning fungerar" i <a href="https://helpx.adobe.com/sign/using/adobesign-search-users-agreements.html#HowSearchWorks">[!DNL Adobe Sign] Sök - Så fungerar det </a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Created date]</td> 
   <td>Välj datum. Modulen returnerar bara poster där det skapade datumet matchar det här villkoret.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expiration date]</td> 
   <td>Välj datum. Modulen returnerar bara poster där utgångsdatumet matchar det här villkoret.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL Modified date]</p> </td> 
   <td>Välj datum. Modulen returnerar bara poster där det ändrade datumet matchar det här villkoret.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL External ID]</td> 
   <td> <p> Externt ID är ett avsändartilldelat ID till avtalet som kan ha vilken form som helst, men vanligtvis i form av &lt;groupID&gt;:&lt;ID&gt;.</p> <p>För varje externt ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar det externa ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group ID]</td> 
   <td> <p>Grupp-ID är en identifierare som tilldelas när gruppen skapades.</p> <p>För varje externt ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar det externa ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>Detta är det ID som tilldelats det specifika avtalet. </p> <p>För varje externt ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar det externa ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Parent ID]</td> 
   <td> <p>Detta är det ID som tilldelats avtalets överordnade objekt. </p> <p>För varje externt ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar det externa ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Participant email]</td> 
   <td> <p>En deltagares e-postadress. </p> <p>För varje externt ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar det externa ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Role]</td> 
   <td>Välj roller som du vill att de returnerade resultaten ska inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort by]</td> 
   <td>Om du vill att modulen ska sortera resultaten markerar du det fält som du vill sortera resultaten efter.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort orde]r</td> 
   <td>Om du vill att modulen ska sortera resultaten väljer du om du vill sortera stigande eller fallande.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status]</td> 
   <td>Välj de statusar som du vill att de returnerade resultaten ska inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type]</td> 
   <td>Välj de avtalstyper som du vill att de returnerade resultaten ska inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subtypes]</td> 
   <td>Välj de avtalsundertyper som du vill att de returnerade resultaten ska inkludera. Endast biblioteksmallavtal har undertyper.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL User ID]</td> 
   <td> <p>Användar-ID för användaren som avtalet delas med.</p> <p>För varje användar-ID som du vill lägga till klickar du på <b>[!UICONTROL Add]</b> och anger eller mappar användar-ID:t.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Visibility]</td> 
   <td>Välj den synlighetsnivå som du vill att de returnerade resultaten ska inkludera.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start index]</td> 
   <td> <p>Ange positionen för det första resultatet som du vill returnera. Kombinera detta med [!UICONTROL maximum returned results] för att paginera resultat</p> <p>Exempel: Om du returnerar 100 resultat i taget, anger du 100 för att returnera resultatet 100-200.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td> <p>Ange eller mappa det maximala antalet poster som du vill att modulen ska [åtgärd] under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++
