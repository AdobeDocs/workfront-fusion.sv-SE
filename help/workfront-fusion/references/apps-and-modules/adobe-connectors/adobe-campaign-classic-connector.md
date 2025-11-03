---
title: Adobe Campaign v7/v8-moduler
description: Med  [!DNL Adobe Campaign] modulerna kan du starta ett Adobe Workfront Fusion-scenario baserat på händelser i ditt [!DNL Adobe Campaign] konto, skapa, läsa eller uppdatera avtal och andra poster, söka efter poster med villkor som du anger och överföra dokument.
author: Becky
feature: Workfront Fusion
exl-id: 9fdff26c-c7c0-4eb8-a36f-4aeaf432b333
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 0%

---

# [!DNL Adobe Campaign] moduler

Med modulerna [!DNL Adobe Campaign] kan du starta ett Adobe Workfront Fusion-scenario baserat på händelser i ditt [!DNL Adobe Campaign v7/v8]-konto, skapa, läsa eller uppdatera poster, söka efter poster med villkor som du anger och utföra anpassade API-anrop.

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

Du måste lägga till Fusion-IP-adresserna till [!DNL Adobe Campaign].

* Instruktioner om hur du lägger till IP-adresser i Campaign-tillåtelselista finns i [Lägga till IP-adresser i tillåtelselista](https://experienceleague.adobe.com/en/docs/control-panel/using/sftp-management/ip-range-allow-listing#adding-ip-addresses-allow-list) i Adobe Campaign-dokumentationen.
* En lista över IP-adresser som ska läggas till i tillåtelselista finns i [Konfigurera IP-adresser för Fusion i din organisations tillåtelselista](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md).

## Adobe Campaign API-information

Adobe Campaign Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.7.22</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Adobe Campaign] till Adobe Workfront Fusion

>[!IMPORTANT]
>
>Vi rekommenderar att du skapar en server-till-server-anslutning. Adobe Campaign har uppdaterat sitt API så att det endast accepterar server-till-server-anslutningar. Om du ansluter till Campaign version 8 eller senare måste du **skapa en server-till-server-anslutning**.
>
>Mer information om Campaigns nya anslutningskrav finns i [Migrering av tekniska operatorer för Campaign till Adobe Developer Console](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/ims-migration.html) i dokumentationen för Campaign.

1. Klicka på [!DNL Adobe Campaign] bredvid fältet **[!UICONTROL Add]** i någon [!UICONTROL Connection]-modul.
1. Fyll i följande fält:
   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection type]</td>
          <td>
            <p>Ange om du skapar en grundläggande anslutning eller en server-till-server-anslutning.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>Ange ett namn för anslutningen.</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Base URL]</td>
          <td>Ange den bas-URL som du använder för att ansluta till din [!DNL Adobe Campaign]-instans.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Username]</td>
          <td>Om du skapar en grundläggande anslutning anger du ditt Adobe Campaign-användarnamn.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Password]</td>
          <td>Om du skapar en grundläggande anslutning anger du ditt Adobe Campaign-lösenord.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]</td>
          <td>Om du skapar en server-till-server-anslutning anger du din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Om du skapar en server-till-server-anslutning anger du din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
        </tr>
     </tbody>
    </table>
1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

## [!DNL Adobe Campaign]-moduler och deras fält

När du konfigurerar [!DNL Adobe Campaign]-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare [!DNL Adobe Campaign] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<!--* [Triggers](#triggers)-->
* [Åtgärder](#actions)
* [Sökningar](#searches)

<!--### Triggers

#### [!UICONTROL Watch records]

This scheduled trigger module starts a scenario when a record changes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Campaign], see <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Create a connection to [!DNL Adobe Campaign]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Select whether you want to watch for new records, updated records, or both.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Select the resource that you want to watch for.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output]</td> 
   <td>Select the fields that you want to include in the module's output.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>For each custom field that you want to include in output, click <b>[!UICONTROL Add]</b> and enter the name of the custom field.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> 
  </tr> 
 </tbody> 
</table>-->


### Åtgärder

* [[!UICONTROL Create a record]](#create-a-record)
* [[!UICONTROL Delete a record]](#delete-record)
* [[!UICONTROL Make a custom API call]](#make-a-custom-api-call)
* [[!UICONTROL Perform an action]](#perform-an-action)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Subscribe or unsubscribe]](#subscribe-or-unsubscribe)
* [[!UICONTROL Update a record]](#update-record)

#### [!UICONTROL Create a record]

Den här åtgärdsmodulen skapar en ny post i [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Välj den typ av [!DNL Adobe Campaign]-post som du vill skapa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>Markera de fält som du vill ange värden för när posten skapas och fyll sedan i värdena för dessa fält. Fälten varierar beroende på vilken typ av post du väljer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> För varje anpassat fält som du vill lägga till i den nya posten klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar fältets namn och värde. </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Record]

Den här åtgärdsmodulen tar bort en post från [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Välj den typ av resurs som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>Ange eller mappa ID:t för resursen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make a custom API call]

Den här modulen gör ett anpassat API-anrop till API:t [!DNL Adobe Campaign]

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Action]</td>
      <td><p>Välj den åtgärd som du vill att API-anropet ska utföra.</p>
      <p>[!UICONTROL Execute query]</p>
      <p>[!UICONTROL Write]</p>
      <p>[!UICONTROL Get entity if more recent]</p>
      <p>[!UICONTROL Select all]</p>
      <p>[!UICONTROL Push event]</p>
    </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p>
        <p>Exempel: <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion lägger automatiskt till tokenhuvudet [!UICONTROL x-security].</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL XML Body]</td>
   <td> <p>Lägg till brödtexten för API-anropet i XML, utan sessionselementet. </td>     </tr>
  </tbody>
</table>


#### [!UICONTROL Perform an action]

Den här åtgärdsmodulen utför en markerad åtgärd på ett objekt i API:t [!DNL Adobe Campaign].

Mer information om specifika åtgärder och fält finns i [[!DNL Adobe Campaign] - API-dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td><p>Välj vilken åtgärd som ska utföras på objektet.</p>
   <ul>
   <li><p><b>[!DNL List]</b></p><p> Information om tillgängliga fält finns i <a href="#search" class="MCXref xref" >[!UICONTROL Search]</a> i den här artikeln. </p></li>
     <li><p><b>[!UICONTROL Get]</b></p><p> Information om tillgängliga fält finns i <a href="#search" class="MCXref xref" >[!UICONTROL Search]</a> i den här artikeln. </p></li> 
   <li><p><b>[!UICONTROL Create]</b></p><p> Information om tillgängliga fält finns i <a href="#create-a-record" class="MCXref xref" >[!UICONTROL Create a record]</a> i den här artikeln. </p></li>
   <li><p><b>[!UICONTROL Update]</b></p><p> Information om tillgängliga fält finns i <a href="#update-record" class="MCXref xref" >[!UICONTROL Update a record]</a> i den här artikeln. </p></li>
   <li><p><b>[!UICONTROL Delete]</b></p><p> Information om tillgängliga fält finns i <a href="#delete-record" class="MCXref xref" >[!UICONTROL Delete a record]</a> i den här artikeln. </p></li>
   </ul>
   </td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser en post från [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Välj den typ av [!DNL Adobe Campaign]-post som du vill läsa.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>Ange på kartan ID för den post som du vill läsa.</td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output] </td> 
   <td>Markera de fält som du vill inkludera i modulens utdata.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>För varje anpassat fält som du vill ta med i utdata klickar du på <b>[!UICONTROL Add]</b> och anger namnet på det anpassade fältet.</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL Subscribe or unsubscribe]

Den här åtgärdsmodulen prenumererar på eller avbryter en användares prenumeration på en informationstjänst.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe or unsubscribe]</td> 
   <td>Välj om du vill prenumerera eller avbryta prenumerationen på informationstjänsten.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Service name]</td> 
   <td>Välj den tjänst som du vill prenumerera på eller avbryta prenumerationen på.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Recipient email address] </td> 
   <td>Ange eller mappa e-postadressen till den användare som du vill prenumerera på eller avbryta prenumerationen på informationstjänsten.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update record]

Den här åtgärdsmodulen uppdaterar en enskild post i [!DNL Adobe Campaign].

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Välj den typ av [!DNL Adobe Campaign]-post som du vill skapa.</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>Ange på kartan ID:t för den post som du vill uppdatera.</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL Fields] </td> 
   <td>Markera de fält som du vill uppdatera värden för och fyll sedan i värdena för dessa fält. Fälten varierar beroende på vilken typ av post du väljer.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> För varje anpassat fält som du vill uppdatera klickar du på <b>[!UICONTROL Add item]</b> och anger eller mappar fältets namn och värde. </td> 
  </tr> 
 </tbody> 
</table>

### Sökningar

#### [!UICONTROL Search]

Sökmodulen returnerar poster baserat på angivna villkor.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Adobe Campaign] finns i <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Skapa en anslutning till [!DNL Adobe Campaign]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Välj den typ av [!DNL Adobe Campaign]-post som du vill skapa.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>Ange de fält och värden som du vill att sökningen ska använda. Fälten beror på vald resurs.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>
