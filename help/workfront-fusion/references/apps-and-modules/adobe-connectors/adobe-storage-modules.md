---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe lagringsmoduler
description: I ett [!DNL Adobe Workfront Fusion] scenario kan du skapa och hantera projekt i Adobe Admin Console.
author: Becky
feature: Workfront Fusion
exl-id: 78ee905f-4713-44a4-bffb-c64cdb3665c2
source-git-commit: 61a523398f00a9d9439b9e74bfbd1ae3f94b0749
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 0%

---

# Adobe lagringsmoduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du skapa och hantera projekt i Adobe Admin Console.

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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
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

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Skapa en anslutning till Adobe Storage

För att skapa en anslutning till Adobe Storage krävs viss konfiguration i Adobe Developer Console och Fusion.

### Konfigurera projektet i Adobe Developer Console

Du måste lägga till API:t i ditt projekt i Adobe Developer Console.

1. Öppna ditt projekt i Adobe Developer Console.
1. Klicka på **Lägg till i projekt** och välj **API**.
1. I listan över tillgängliga API:er väljer du **Adobe Cloud Platform och Collaboration API**.
1. På skärmen Välj autentiseringstyp väljer du **OAuth Server-till-server** och klickar på **Nästa**.
1. Lägg till ett namn för autentiseringsuppgifterna.
1. Klicka på **Nästa** och sedan på **Spara konfigurerad API**.
1. Observera de angivna inloggningsuppgifterna som du kommer att använda när du konfigurerar anslutningen i Workfront Fusion.
1. Fortsätt till [Gör ditt tekniska konto till administratör i Adobe Admin Console](#make-your-technical-account-an-admin-in-the-adobe-admin-console).

### Gör ditt tekniska konto till administratör i Adobe Admin Console

På Adobe Admin Console-sidan väljer du fliken Produkter i det övre navigeringsfältet och sedan Workfront Fusion

1. Leta upp och kopiera e-postadressen till den tekniska kontoanvändaren i organisationen.
1. Om en lista visas väljer du länken längst upp.
1. Det här är din produktionsinstans där dina användare arbetar.
1. I den lista som visas, med fliken Produktprofiler markerad, klickar du på namnet på länken Workfront produktprofil.

   Den här listan innehåller alla användare som redan är tilldelade till din Production-instans av Workfront.

1. Välj fliken **Administratörer** ovanför listan över användare.
1. Välj **Lägg till administratör**.
1. Ange e-postadresserna till det tekniska kontot i rutan Lägg till produktprofiladministratörer och välj sedan **Spara**.

   Det tekniska kontot är en administratör.

1. Fortsätt till [Skapa anslutningen i Workfront Fusion](#create-the-connection-in-workfront-fusion).

### Skapa anslutningen i Workfront Fusion

Så här skapar du en anslutning för dina [!DNL Adobe Storage]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning i någon av modulerna.

1. Fyll i följande fält:

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>Välj <code>Server to server</code>.</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange din [!UICONTROL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credential details] i projektet i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credential details] i projektet i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS Organization ID]</td>
        <td>Ange eller mappa ditt Adobe IMS-organisations-ID. Detta är en sträng med formen <code> 123abc@AdobeOrg</code>, där avsnittet före @ är ett hexadecimalt tal. Du kan hitta det här värdet som en del av URL-sökvägen för din organisation i Adobe Admin Console eller i Adobe.IO-konsolen för användarhanteringsintegrering.</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## Adobe lagringsmoduler och deras fält

När du konfigurerar Adobe-moduler för användarhantering visas de fält som listas nedan i Workfront Fusion. Dessutom kan ytterligare fält för användarhantering i Adobe visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ESM-butiker](#esm-stores)
* [Inbjudningar](#invitations)
* [Övriga](#other)

### ESM-butiker

* [Skapa en ESM-butik](#create-an-esm-store)
* [Ta bort en ESM-butik](#delete-an-esm-store)
* [Ignorera en ESM-butik](#discard-an-esm-store)
* [Återställ ett ESM-arkiv](#restore-an-esm-store)

#### Skapa en ESM-butik

Den här åtgärdsmodulen konfigurerar en ny lagringsplats (ESM) för Enterprise Storage Management för att organisera och hantera affärskritiska resurser.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Projektnamn</td> 
   <td>Ange eller mappa ett namn för det nya projektet.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en ESM-butik

Den här åtgärdsmodulen tar permanent bort ett befintligt ESM-arkiv och alla associerade data. Det går inte att ångra den här åtgärden.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Butiks-ID</td> 
   <td>Ange eller mappa ID:t för den butik som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Ignorera en ESM-butik

Den här åtgärdsmodulen markerar ett EMS-arkiv för borttagning, vilket ger en respitperiod innan permanent borttagning.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Butiks-ID</td> 
   <td>Ange eller mappa ID:t för den butik som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Återställ ett ESM-arkiv

Den här åtgärdsmodulen återställer ett tidigare borttaget ESM-arkiv och återställer åtkomsten till dess data och konfigurationer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Butiks-ID</td> 
   <td>Ange eller mappa ID:t för den butik som du vill återställa.</td> 
  </tr> 
 </tbody> 
</table>

### Inbjudningar

#### Bjud in användare

Den här åtgärdsmodulen skickar en inbjudan som ger en ny användare åtkomst till ett specifikt ESM-arkiv, vilket möjliggör samarbete och filhantering.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">E-postadress</td> 
   <td>Ange eller mappa e-postadressen till användaren som du vill bjuda in till butiken.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångs-ID</td> 
   <td>Ange eller mappa ID:t för resursen som du vill bjuda in användaren till.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Roll</td> 
   <td>Välj den roll som du vill att den nyinbjudna användaren ska ha för resursen.<ul><li>Ägare</li><li>Redigerare</li><li>Visningsprogram</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kan kommentera</td> 
   <td>Aktivera det här alternativet om du vill tillåta användaren att kommentera resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Kan dela</td> 
   <td>Aktivera det här alternativet om du vill att användaren ska kunna dela resursen med en annan användare.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Godkännande krävs</td> 
   <td>Aktivera det här alternativet för att se till att användaren måste acceptera inbjudan innan han/hon kan samarbeta med resursen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Använd montage</td> 
   <td>Aktivera det här alternativet om en monteringspunkt till resursen måste skapas för den som bjuder in. Det obligatoriska alternativet Godkännande måste vara aktiverat för att det här alternativet ska kunna aktiveras.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Meddelandetyp</td> 
   <td>Ange eller mappa den meddelandetyp för Adobe som du vill använda för att meddela användaren om inbjudan. Om detta lämnas tomt baseras meddelandetypen på tillgångens mime-typ.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mallnamn</td> 
   <td>Ange eller mappa Adobe Post Office-ID:t för mallen som du vill använda för e-postinbjudan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Språk</td> 
   <td>Ange användarens språkområde i form av en språkkod och en landskod. <p>Exempel: <code>en-us</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Extern</td> 
   <td>Ange det här alternativet till true om du vill skicka meddelanden via ett system som inte är tillgängligt för tjänsten Adobe Invitations. Extern avisering stöds bara när godkännande inte krävs.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillgångstyp</td> 
   <td>Ange eller mappa resurstypen.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Meddelande</td> 
   <td>Ange eller mappa ett meddelande som ska inkluderas i e-postmeddelandet med inbjudan.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Mål-URL</td> 
   <td>Ange eller mappa den URL som den som bjuder in kan använda för att visa resursen.</td> 
  </tr> 
 </tbody> 
</table>

### Övriga

#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör en anpassad HTTP-begäran till Adobe Storage API.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">Anslutning</td>
   <td>Instruktioner om hur du skapar en anslutning till Adobe Storage finns i <a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >Skapa en anslutning till Adobe Storage</a> i den här artikeln.</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>Ange en sökväg i förhållande till <code>https://ccprojects.adobe.io/api/v3/.</code></p>
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
