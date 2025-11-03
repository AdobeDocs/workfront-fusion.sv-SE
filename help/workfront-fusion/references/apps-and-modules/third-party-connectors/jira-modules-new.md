---
title: Jira-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Jira Software, samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: b74a3618-c4a1-4965-a88d-1643bfab12db
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: tm+mt
source-wordcount: '1749'
ht-degree: 0%

---

# Jira-moduler

>[!NOTE]
>
>Dessa instruktioner gäller den nya versionen av Jira-anslutningen, som helt enkelt heter Jira. Instruktioner om de äldre Jira Cloud- och Jira Server-anslutningarna finns i [Jira-programmoduler](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-software-modules.md).

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Jira, samt ansluta det till flera tredjepartsprogram och -tjänster.

Jira-anslutningen kan användas för både Jira Cloud och Jira Data Server.

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

För att kunna använda Jira-moduler måste du ha ett Jira-konto.

## Anslut Jira till Workfront Fusion

### Skapa nödvändiga autentiseringsuppgifter

Om du vill skapa anslutningar till Jira behöver du följande:

| Anslutningstyp | Kontotyp | Autentiseringsuppgifter krävs |
|---|---|---|
| OAuth 2 | Alla | Klient-ID och klienthemlighet |
| Grundläggande | Jira Cloud | Jira API-token |
| Grundläggande | Jira Data Center | Jira Personal Access Token (PAT) |

Instruktioner om hur du skapar något av dessa finns i Jiras dokumentation.

När du skapar dessa autentiseringsuppgifter behöver du följande information:

* För OAuth 2:

  | Fusion datacenter | Omdirigeringsadress |
  |---|---|
  | USA | `https://app.workfrontfusion.com/oauth/cb/workfront-jira2` |
  | EU | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira2` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira2` |



* För personliga åtkomsttoken (PAT):

  | Fusion datacenter | Omdirigeringsadress |
  |---|---|
  | USA | `https://app.workfrontfusion.com/oauth/cb/workfront-jira` |
  | EU | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira` |

  >[!IMPORTANT]
  >
  >Om du vill använda en PAT-fil måste du aktivera följande i filerna `jira/bin/WEB-INF/classes` i filen `jira-config.properties`:
  >
  >* `jira.rest.auth.allow.basic = true`
  >* `jira.rest.csrf.disabled = true`
  >
  >Om filen inte finns måste du skapa den.

### Skapa anslutningen till Jira i Workfront Fusion

Så här skapar du en anslutning i Workfront Fusion:

1. Klicka på **Lägg till** bredvid anslutningsfältet i en Jira-modul.
1. Konfigurera följande fält:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>Anslutningstyp</p> </td> 
      <td> <p>Ange om du skapar en grundläggande anslutning eller en OAuth 2-anslutning.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>Anslutningsnamn</p> </td> 
      <td> <p>Ange ett namn för den nya anslutningen.</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">Tjänst-URL</td>
      <td>Ange din Jira-instans-URL. Det här är den URL du använder för att komma åt Jira.</td>
     </tr>
     <tr>
      <td role="rowheader">Jira-kontotyp</td>
       <td>Välj om du ansluter till Jira Cloud eller Jira Data Center.</td>
     </tr>
     <tr> 
      <td role="rowheader">Klient-ID</td> 
      <td> <p>Om du skapar en OAuth 2-anslutning anger du ditt Jira Client-ID</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Klienthemlighet</td> 
      <td> <p>Om du skapar en OAuth 2-anslutning anger du din Jira-klienthemlighet</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">E-post</td> 
      <td>Om du skapar en grundläggande anslutning till Jira Cloud anger du din e-postadress.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API-token</td> 
      <td>Om du skapar en grundläggande anslutning till Jira Cloud anger du din API-token.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Personlig åtkomsttoken</td> 
      <td>Om du skapar en grundläggande anslutning till Jira Data Center anger du din personliga åtkomsttoken.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API-version</td> 
      <td>Välj den Jira API-version som du vill att anslutningen ska ansluta till.</td> 
     </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.


## Jira-moduler och deras fält

När du konfigurerar Jira-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Jira-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

#### Håll utkik efter poster

Denna utlösarmodul startar ett scenario när en post läggs till, uppdateras eller tas bort.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Webkrok</td> 
   <td> <p>Välj den webkrok som du vill använda för att bevaka poster, eller skapa en ny webkrok. </p> <p>Så här skapar du en ny webbkrok:</p> 
    <ol> 
     <li>Klicka på <strong>Lägg till</strong></li> 
     <li>Ange ett namn för webkroken.</li> 
     <li> Välj den anslutning som du vill använda för din webkrok. <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </li> 
     <li> <p>Välj den posttyp som du vill att programmet ska bevaka:</p> 
      <ul> 
       <li>Problem</li> 
       <li>Kommentar </li> 
       <li>Arbetslogg </li> 
       <li>Projekt </li> 
       <li>Sprint</li> 
       <li>Bilaga </li> 
      </ul> </li> 
     <li>Välj en eller flera händelsetyper som ska utlösa det här scenariot.</li> 
     <li>Ange ett Jira-frågespråkfilter för den här modulen.<p>Mer information om JQL finns i <a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a> på hjälpwebbplatsen för Atlassian. </p></li>
     <li>Klicka på <b>Spara</b> för att spara webkroken. 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Åtgärder

* [Lägg till utgåva i utskrift](#add-issue-to-sprint)
* [Skapa en post](#create-a-record)
* [Anpassat API-anrop](#custom-api-call)
* [Ta bort en post](#delete-a-record)
* [Hämta en bifogad fil](#download-an-attachment)
* [Läsa en post](#read-a-record)
* [Uppdatera en post](#update-a-record)

#### Lägg till utgåva i utskrift

Den här åtgärdsmodulen lägger till en eller flera utgåvor i en utskrift.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sprint-ID</td> 
   <td>Ange eller mappa Sprint-ID:t för den utskrift som du vill lägga till ett problem i.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Problem-ID eller nycklar</td> 
   <td>Klicka på <b>Lägg till objekt</b> för varje problem eller nyckel som du vill lägga till i skrivaren och ange ID eller nyckel för problemet. Du kan ange upp till 50 i en modul.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en post

Denna åtgärdsmodul skapar en ny post i Jira.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska skapa.</p> 
    <ul> 
     <li>Bilaga</li> 
     <li>Kommentar</li> 
     <li>Problem</li> 
     <li>Projekt</li> 
     <li>Sprint </li> 
     <li>Arbetslogg</li> 
     <li>Användare</li> 
     <li>Styrelse</li> 
     <li>Kategori</li> 
     <li>Filter</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Andra fält</td> 
   <td> Fyll i andra fält. Fälten är tillgängliga beroende på den valda posttypen. </td> 
  </tr> 
 </tbody> 
</table>

#### Anpassat API-anrop

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till Jira API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Ange en sökväg i förhållande till<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">Metod</td> 
   td&gt; <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sidhuvuden</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Frågesträng</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Brödtext</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en post

Den här åtgärdsmodulen tar bort den angivna posten.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska ta bort. </p> 
    <ul> 
     <li>Kommentar</li> 
     <li>Problem</li> 
     <li>Projekt</li> 
     <li>Sprint </li> 
     <li>Arbetslogg</li> 
     <li>Bilaga</li> 
     <li>Styrelse</li> 
     <li>Kategori</li> 
     <li>Filter</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">(Posttyp)ID</td> 
   <td>Ange eller mappa ID:t eller nyckeln för den post som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta en bifogad fil

Den här åtgärdsmodulen hämtar den angivna bifogade filen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td>Ange eller mappa ID:t för den bifogade fil som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### Läsa en post

Den här åtgärdsmodulen läser data från den angivna posten i Jira.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj den typ av Jira-post som du vill att modulen ska läsa.</p> 
    <ul> 
     <li>Bilaga</li> 
     <li>Kommentar</li> 
     <li>Problem</li> 
     <li>Projekt</li> 
     <li>Sprint </li> 
     <li>Arbetslogg</li> 
     <li>Användare</li> 
     <li>Styrelse</li> 
     <li>Kategori</li> 
     <li>Filter</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Utdata</td> 
   <td>Välj de utdata som du vill ta emot. Utdataalternativen är tillgängliga baserat på vilken typ av post som har valts i fältet Posttyp.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">(Posttyp)-ID</td> 
   <td> <p>Ange eller mappa det unika Jira-ID:t för den post som du vill att modulen ska läsa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en post

Den här åtgärdsmodulen uppdaterar en befintlig post, t.ex. ett problem eller ett projekt.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska uppdatera. När du väljer en posttyp visas andra fält som är specifika för den posttypen i modulen.</p> 
    <ul> 
     <li>Kommentar</li> 
     <li>Problem</li> 
     <li>Projekt</li> 
     <li>Sprint </li> 
     <li>Övergångsproblem</li> 
     <li>Kategori </li> 
     <li>Filter </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID eller nyckel</td> 
   <td>Ange eller mappa ID:t eller nyckeln för den post som du vill uppdatera.</td> 
  <tr> 
   <td role="rowheader">Andra fält</td> 
   <td> Fyll i andra fält. Fälten är tillgängliga beroende på den valda posttypen. </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

>[!IMPORTANT]
>
>Sökmodulen som används av den äldre Jira-anslutningen kan resultera i följande fel:
>
>`[410] The requested API has been removed. Please migrate to the /rest/api/3/search/jql API. A full migration guideline is available at https://developer.atlassian.com/changelog/#CHANGE-2046`
>
>Detta beror på en tillbakagång på Jiras sida.
>
>Om du råkar ut för det här felet kan du ersätta sökmodulen för den äldre Jira-anslutningen med sökmodulen för den nya anslutningen. Observera att den nya anslutningen gör att du kan välja vilken API-version som ska användas. Var noga med att välja V3 när du skapar anslutningen.
>
> ![API-versionsalternativ i ny Jira-anslutning](/help/workfront-fusion/references/apps-and-modules/assets/jira-version-option.png)
>
>Observera att:
>
>* Endast sökmodulen påverkas. För närvarande påverkas inte andra Jira API-slutpunkter som används av Fusion-anslutningen av den här borttagningen.
>
>* Geografisk utrullning kan orsaka inkonsekvenser. Atlassian rullar ut den här ändringen regionalt, vilket innebär att vissa Jira Cloud-instanser fortfarande har tillfälligt stöd för äldre slutpunkter. Detta kan leda till inkonsekvent beteende i olika miljöer.

#### Sök efter poster

Den här sökmodulen söker efter poster i ett objekt i Jira som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Anvisningar om hur du ansluter ditt Jira-konto till Workfront Fusion finns i <a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Ansluta Jira till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Posttyp</td> 
   <td> <p>Välj den typ av post som du vill att modulen ska söka efter. När du väljer en posttyp visas andra fält som är specifika för den posttypen i modulen.</p> 
    <ul> 
     <li>Problem</li> 
     <li>Projekt</li> 
     <li>Användare</li> 
     <li>Sprint</li> 
     <li>Styrelse</li> 
     <li>Arbetslogg</li> 
     <li>Kommentar</li> 
     <li>Övergångsproblem</li> 
     <li>Kategori</li> 
    </ul> </td> 
  <tr> 
   <td role="rowheader"> <p>Maximalt antal resultat</p> </td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska hämta under varje körningscykel för scenario.</p> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">Förskjutning</td> 
    <td> Ange eller mappa ID:t för det första objektet som du vill hämta information för. Detta är ett sätt att numrera posterna. Om du anger det 5000:e objektet som förskjutning returnerar modulen objekten 5000-9999.</td> 
   </tr>
  <tr> 
   <td role="rowheader">Andra fält</td> 
   <td> Fyll i andra fält. Fälten är tillgängliga beroende på den valda posttypen. </td> 
  </tr> 
 </tbody> 
</table>
