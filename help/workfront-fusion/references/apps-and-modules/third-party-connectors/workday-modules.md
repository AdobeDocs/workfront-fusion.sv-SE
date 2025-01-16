---
filename: workday-modules
title: Workday moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder  [!DNL Workday] och ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 77237a1b-2acd-4350-9cc0-ec43b8b08137
source-git-commit: 8bd08379fc88c4d4f31ba1faba922869d7957b4a
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 0%

---

# [!DNL Workday] moduler

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!DNL Workday] samt ansluta det till flera tredjepartsprogram och -tjänster.

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

Om du vill använda modulerna [!DNL Workday] måste du:

* Ha ett [!DNL Workday]-konto.

* Skapa ett OAuth-program i [!DNL Workday]. Instruktioner finns i dokumentationen för [!DNL Workday].

## Workday API-information

Workday Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td>https://{{connection.servicesUrl}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.6.4</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Workday] till [!DNL Workfront Fusion]

1. Klicka på [!UICONTROL Add] bredvid fältet [!UICONTROL Connection] i en [!DNL Workfront Fusion]-modul

2. Fyll i följande fält:

   <table style="table-layout:auto"> 
        <col/>
        <col/>
        <tbody>
            <tr>
                <td role="rowheader">
                    <p role="rowheader">[!UICONTROL Connection name]</p>
                </td>
                <td>Ange ett namn för anslutningen</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Workday host]</td>
                <td>Ange adressen till din [!DNL Workday]-värd utan <code>https://</code>. Till exempel: <code>mycompany.workday.com</code>.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Services URL]</td>
                <td>Ange adressen till dina [!DNL Workday]-webbtjänster utan <code>https://</code>. Till exempel: <code>mycompany-services.workday.com</code>.</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Tenant name]</td>
                <td>Ange klientorganisationen för det här [!DNL Workday]-kontot. Din klient är din organisations identifierare och kan visas på den URL du använder för att logga in på Workday. Exempel: i adressen <code>https://www.myworkday.com/mycompany</code> är klientorganisationen <code>mycompany</code>.</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Client ID]</td>
                <td>Ange klient-ID för det [!DNL Workday]-program som den här anslutningen använder. Du får detta när du skapar programmet i [!DNL Workday].</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Client Secret]</td>
                <td>Ange klienthemlighet för det [!DNL Workday]-program som den här anslutningen använder. Du får detta när du skapar programmet i [!DNL Workday].</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL Session timeout (min)]</td>
                <td >Ange antalet minuter som din auktoriseringstoken ska förfalla.</td>
            </tr>
        </tbody>
    </table>


3. Klicka på [!UICONTROL Continue] för att spara anslutningen och återgå till modulen

## [!DNL Workday]-moduler och deras fält

När du konfigurerar [!DNL Workday] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Workday] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Åtgärd](#action)

* [Sök](#search)


### Åtgärd

* [[!UICONTROL Create a record]](#create-a-record)

* [[!UICONTROL Delete a record]](#delete-a-record)

* [[!UICONTROL Make a custom API call]](#make-a-custom-api-call)

* [[!UICONTROL Update a record]](#update-a-record)


#### [!UICONTROL Create a record]

Den här åtgärdsmodulen skapar en enda post i [!DNL Workday].

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till Workfront Fusion finns i <a href="#Connect" class="MCXref xref" > Anslut [!DNL Workday] till [!DNL Workfront Fusion]</a>.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record Type]</td>
            <td>Välj den typ av post som du vill skapa.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>Ange eller mappa ID:t för den post som du vill skapa.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Subresource ID]</td>
            <td >Ange eller mappa ID:t för den underresurs som du vill skapa.</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL Delete a record]

Den här åtgärdsmodulen tar bort en enskild post i [!DNL Workday].

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till [!DNL Workfront Fusion] finns i <a href="#Connect" class="MCXref xref" >Anslut [!DNL Workday] till [!DNL Workfront Fusion]</a>.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record type]</td>
            <td>Välj den typ av post som du vill ta bort.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Specific record type]</td>
            <td>Välj den typ av post som du vill ta bort. Dessa baseras på den posttyp som du väljer.</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Subresource ID]</td>
            <td>Ange eller mappa ID:t för den underresurs som du vill ta bort.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >Ange eller mappa ID:t för den post som du vill ta bort.</td>
        </tr>
    </tbody>
</table>


### [!UICONTROL Make a custom API call]

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till API:t [!DNL Workday]. På så sätt kan du skapa en dataflödesautomatisering som inte kan utföras av de andra [!DNL Workday]-modulerna.

När du konfigurerar den här modulen visas följande fält.

Modulen returnerar statuskoden, tillsammans med rubrikerna och brödtexten för API-anropet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Connection]</p> </td> 
            <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till [!DNL Workfront Fusion] finns i <a href="#Connect" class="MCXref xref" >Anslut [!DNL Workday] till [!DNL Workfront Fusion]</a>.</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>Ange en relativ sökväg till <code style="color: #ff1493;">https://&lt;tenantHostname>/api/&lt;serviceName>/&lt;version>/&lt;tenant></code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran i [!DNL Adobe Workfront Fusion]</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
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

#### [!UICONTROL Update a record]

Den här åtgärdsmodulen uppdaterar en enskild post i [!DNL Workday].

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till Workfront Fusion finns i <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect [!DNL Workday] till Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record Type]</td>
            <td>Välj den typ av post som du vill uppdatera.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>Ange eller mappa ID:t för den post som du vill uppdatera.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Subresource ID]</td>
            <td >Ange eller mappa ID:t för den underresurs som du vill uppdatera.</td>
        </tr>
    </tbody>
</table>

### Sök

* [[!UICONTROL Read a record]](#read-a-record)

* [[!UICONTROL List records]](#list-records)


#### [!UICONTROL Read a record]

Den här åtgärdsmodulen läser en enda post.

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till Workfront Fusion finns i <a href="#Connect" class="MCXref xref" >[!UICONTROL Connect [!DNL Workday] till Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL Record type]</td>
            <td>Välj den typ av post som du vill ta bort.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL Specific record type]</td>
            <td>Välj den typ av post som du vill läsa. Dessa baseras på den posttyp som du väljer.</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >Ange eller mappa ID:t för den post som du vill ta bort.</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL List records]

Den här sökmodulen hämtar en lista med poster av den angivna typen.

<table style="table-layout:auto"> 
      <col/>
      <col/>
      <tbody>
          <tr>
              <td role="rowheader">[!UICONTROL Connection]</td>
              <td>Instruktioner om hur du ansluter ditt [!DNL Workday]-konto till [!DNL Workfront Fusion] finns i <a href="#Connect" class="MCXref xref" >Anslut [!DNL Workday] till [!DNL Workfront Fusion]</a></td>
          </tr>
          <tr>
              <td  role="rowheader">[!UICONTROL Record Type]</td>
              <td>Välj den typ av post som du vill hämta.</td>
          </tr>
          <tr>
              <td role="rowheader">[!UICONTROL Limit]</td>
              <td >
                  <p>Ange eller mappa det maximala antal poster som du vill att modulen ska hämta under varje körningscykel för scenario.</p>
              </td>
          </tr>
      </tbody>
  </table>
