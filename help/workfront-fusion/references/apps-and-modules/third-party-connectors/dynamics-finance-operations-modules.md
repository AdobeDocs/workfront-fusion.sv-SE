---
title: Microsoft Dynamics 365 - ekonomi- och driftmoduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Microsoft Dynamics 365 Finance och Operations samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 96f8d4f1-f97b-4da8-8d82-83cccb54ec68
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics 365 Finance and Operations modules]

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder [!DNL Microsoft Dynamics 365] samt ansluta det till flera tredjepartsprogram och -tjänster.

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365 Finance and Operations]-anslutningen stöder inte [!DNL Dynamics 365].
>
>Information om Microsoft Dynamics 365-moduler finns i [[!DNL Microsoft Dynamics 365 modules]](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md).



Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

## Skapa en anslutning

Så här skapar du en anslutning till dina Microsoft Dynamics 365-moduler för finans och drift:

1. Klicka på **[!UICONTROL Add]** bredvid anslutningsrutan i någon av Microsoft Dynamics 365-modulerna för finans och drift.

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
          <p>Ange om du skapar en Dynamics-anslutning för finans och drift, eller en anslutning med en auktoriseringskod.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>Ange ett namn för anslutningen.</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange Dynamics-ekonomi och åtgärder [!UICONTROL Client ID].</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange Dynamics-ekonomi och åtgärder [!UICONTROL Client Secret]. </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Tenant ID]</td>
        <td>Ange ditt ID för Dynamics Finance och Operations Tenant.</td>
        </tr>
        <tr>
        <td role="rowheader">Resurs</td>
        <td>Ange URL:en för ditt Dynamics-konto för finans och drift (utan https://)</td>
        </tr>
      </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.



## Microsoft Dynamics 365, ekonomi- och driftmodulerna samt deras områden

>[!IMPORTANT]
>
>Vilka datatabeller som är tillgängliga via Dynamics 365 F&amp;O API kan variera beroende på instans. Om du är osäker på vilka enheter som är tillgängliga via API:t är det praktiskt att titta igenom enheterna i din instans med hjälp av dataslutpunkten. Slutpunkten &quot;data&quot; i Dynamics 365 Finance and Operations är rot-URL:en för åtkomst till OData-tjänster. Den här slutpunkten gör att du kan interagera med olika datatabeller som exponeras av systemet med OData-standardprotokoll.
>
>Du kan hämta dessa enheter med den anpassade API-anropsmodulen.
>
><!--For more information -->



### Skapa enhetsobjekt

Den här åtgärdsmodulen skapar en ny enhetspost i Microsoft Dynamics 365 Finance and Operations.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter Microsoft Dynamics 365 Finance och Operations till Workfront Fusion finns i <a href="#create-a-connection" class="MCXref xref">Skapa en anslutning</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Entity]</td>
     <td>Ange eller mappa Dynamics Finance- och Operations-entitetstypen som du vill skapa.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Body]</td>
     <td> <p>Ange eller mappa en JSON-brödtext som innehåller de data som du vill inkludera i det nya enhetsobjektet.</p> </td> 
  </tr> 
 </tbody> 
</table>



### Ta bort enhetsobjekt

Den här åtgärdsmodulen tar bort en entitetsobjekt från Dynamics Finance och Operations. Objektet identifieras av dess primärnyckelfält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter Microsoft Dynamics 365 Finance och Operations till Workfront Fusion finns i <a href="#create-a-connection" class="MCXref xref">Skapa en anslutning</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Entity]</td>
     <td>Ange eller mappa den Dynamics Finance- och Operations-enhetstyp som du vill ta bort.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Primary key fields]</td>
     <td> Primärnyckelfälten identifierar objektet. För varje primärnyckelfält som du vill ange klickar du på <b>Lägg till objekt</b> och anger eller mappar den unika nyckel och det unika värde som identifierar det objektet. </td> 
  </tr> 
 </tbody> 
</table>

### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Dynamics finans- och drifts-API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
    <td> <p>Instruktioner om hur du ansluter Microsoft Dynamics 365 Finance och Operations till Workfront Fusion finns i <a href="#create-a-connection" class="MCXref xref">Skapa en anslutning</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Ange en sökväg som är relativ till Dynamics ekonomi- och Operations-URL:en.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Detta avgör begärans innehållstyp.</p> <p>Exempel:<code> {"Content-type":"application/json"}</code></p> <p>Obs! Om du får felmeddelanden och det är svårt att fastställa deras ursprung bör du överväga att ändra rubrikerna baserat på Workfront-dokumentationen. Om ditt anpassade API-anrop returnerar ett 422 HTTP-begärandefel kan du försöka med att använda en <code>"Content-Type":"text/plain"</code>-rubrik.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query string]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> <p>Tips! Vi rekommenderar att du skickar information via JSON-brödtexten i stället för som frågeparametrar.</p> </td> 
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



### Läs enhetsobjekt

Den här åtgärdsmodulen returnerar data från ett entitetsobjekt. Objektet identifieras av dess primärnyckelfält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter Microsoft Dynamics 365 Finance och Operations till Workfront Fusion finns i <a href="#create-a-connection" class="MCXref xref">Skapa en anslutning</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Entity]</td>
     <td>Ange eller mappa Dynamics Finance- och Operations-entitetstypen som du vill läsa.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Primary key fields]</td>
     <td> Primärnyckelfälten identifierar objektet. För varje primärnyckelfält som du vill ange klickar du på <b>Lägg till objekt</b> och anger eller mappar den unika nyckel och det unika värde som identifierar det objektet. </td> 
  </tr> 
 </tbody> 
</table>

### Uppdatera enhetsobjekt

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter Microsoft Dynamics 365 Finance och Operations till Workfront Fusion finns i <a href="#create-a-connection" class="MCXref xref">Skapa en anslutning</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Entity]</td>
     <td>Ange eller mappa Dynamics Finance- och Operations-entitetstypen som du vill uppdatera.</td> 
  </tr>  
  <tr> 
    <td>[!UICONTROL Primary key fields]</td>
     <td> Primärnyckelfälten identifierar objektet. För varje primärnyckelfält som du vill ange klickar du på <b>Lägg till objekt</b> och anger eller mappar den unika nyckel och det unika värde som identifierar det objektet. </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Body]</td>
     <td> <p>Ange eller mappa en JSON-brödtext som innehåller de data som du vill inkludera i det nya enhetsobjektet.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Sök

Sökmodulen returnerar resultat baserat på villkor som du anger.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Entity]</td> 
   <td>Ange eller mappa Dynamics Finance- och Operations-entitetstypen som du vill söka efter.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Ange fältet som du vill söka efter, operatorn som du vill använda i frågan och värdet som du söker efter i fältet.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Sort by]</td> 
   <td> <p>Ange eller mappa fältet som du vill sortera resultaten efter.</p> </td> 
  </tr> 
 </tbody> 
</table>


<!--

### List All

This module lists all records for a given entity.  The item is identified by its Primary key fields.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>
     <td>Choose the Dynamics Finance and Operations entity type that you want the module to list.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>
     <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Watch Record

This trigger module starts a scenario when a record of the given type is created or updated.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to watch.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

-->
