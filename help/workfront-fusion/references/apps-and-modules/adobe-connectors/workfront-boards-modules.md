---
title: Adobe Workfront Boards-moduler
description: Du kan använda Adobe Workfront Boards-kontakten för att automatisera processerna i Workfront Boards och koppla dem till program och tjänster från tredje part.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: dcc5044d-8fdf-4a74-b664-e965e714ce92
source-git-commit: a871a130a1ac023dcb4ce8da7241918da2431d3a
workflow-type: tm+mt
source-wordcount: '2694'
ht-degree: 0%

---

# Adobe Workfront Boards-moduler

>[!NOTE]
>
>The Boards Fusion Connector har betastatus. Detta innebär att stödet för den här kopplingen är begränsat och kan komma att ändras på grund av styrelsens framtida utveckling. Dessutom kan det finnas ändringar i GraphQL API utan föregående meddelande som kan påverka Fusion-anslutningsprocessen.

Adobe Workfront Boards är flexibla verktyg som ger teamsamarbete genom att ge åtkomst till en delad anslagstavla som innehåller kolumner och kort.

Du kan använda modulen Adobe Workfront Boards för att läsa eller uppdatera poster, göra ett API-anrop till Workfront Boards API eller utlösa ett scenario när en åtgärd utförs på en anslagstavla.

<!--For general information on Workfront Boards, see [Boards overview](/help/quicksilver/agile/boards-overview.md).-->

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
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Förutsättningar

Du måste ha konfigurerat en anslagstavla i Adobe Workfront innan du kan ansluta till den.

## API-information för Adobe Workfront Books

Adobe Workfront Boards-anslutningen använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.23.6</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till Workfront Boards

>[!NOTE]
>
>Du kan använda en Workfront-anslutning för att ansluta till Workfront Boards eller skapa en separat anslutning till Workfront Boards.

Så här skapar du en anslutning till Workfront Boards:

1. Klicka på [!DNL Adobe Workfront Boards] bredvid anslutningsrutan i någon **[!UICONTROL Add]**-modul.

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
          <td>Välj om du vill ansluta till ett tjänstkonto eller ett personligt konto.</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>(Valfritt)</p></td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>(Valfritt)</p></td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>(Valfritt)</p></td>
          <td>Ange den URL som din instans av Workfront ska använda för att autentisera anslutningen. <p>Standardvärdet är <code>https://oauth.my.workfront.com/integrations/oauth2</code>.</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>Ange värdprefixet.<p>Standardvärdet är <code>origin-</code>.</p>
        </tr>
      </tbody>
    </table>
1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## Adobe Workfront Books-moduler och deras fält

När du konfigurerar Workfront Boards-moduler visar Workfront Fusion de fält som listas nedan. Dessutom kan ytterligare fält för Workfront Boards visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Kort](#cards)
* [Varumärkena](#boards)
* [Kolumner](#columns)
* [Taggar](#tags)
* [Kommentar](#comments)
* [Övriga](#other)

### Kort

* [Lägg till checklisteobjekt](#add-checklist-item)
* [Lägg till underaktivitet](#add-subtask)
* [Skapa ett kort](#create-a-card)
* [Flytta ett kort](#move-a-card)
* [Läs ett kort](#read-a-card)
* [Uppdatera ett kort](#update-a-card)

#### Lägg till checklisteobjekt

Den här åtgärdsmodulen lägger till ett checklisteobjekt på det angivna kortet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill lägga till ett checklisteobjekt i.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Checklist items]</td> 
   <td>För varje objekt i checklistan som du vill lägga till klickar du på Lägg till objekt, anger namnet på objektet i checklistan och väljer om objektet har slutförts.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Lägg till underaktivitet

Den här åtgärdsmodulen lägger till en underaktivitet till ett kort i Boards. Kortet måste vara ett anslutet kort. Underaktiviteten läggs också till i den Workfront-uppgift som kortet representerar.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Parent card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill lägga till en underaktivitet i.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller kortet som du vill lägga till en underaktivitet i.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för den nya underaktiviteten.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Skapa ett kort

Den här åtgärdsmodulen skapar ett nytt kort på ett Workfront-kort.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den anslagstavla som du vill lägga till ett kort till.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column ID]</td> 
   <td>Ange eller mappa ID:t för den kolumn som du vill lägga till en underaktivitet i.<p>Du hittar kolumn-ID:t i informationen som returneras från modulen Läs en anslagstavla.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett namn för det nya kortet.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Flytta ett kort

Den här åtgärdsmodulen flyttar ett kort till en annan kolumn på samma anslagstavla.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill flytta.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller kortet som du vill flytta.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination column ID]</td> 
   <td>Ange eller mappa ID:t för kolumnen som du vill flytta kortet till.<p>Du hittar kolumn-ID:t i informationen som returneras från modulen Läs en anslagstavla.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To index]</td> 
   <td>Ange eller mappa positionen som du vill att kortet ska ha i den nya kolumnen.<p>Den översta positionen i kolumnen i index 0.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Läs ett kort

Den här åtgärdsmodulen hämtar information om ett specifikt kort.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill läsa.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller kortet som du vill läsa.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera ett kort

Den här åtgärdsmodulen uppdaterar information för ett kort som du anger.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill uppdatera.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den anslagstavla som innehåller kortet som du vill uppdatera.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>Ange eller mappa ett nytt namn för kortet.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Description]</td> 
   <td>Ange eller mappa en ny beskrivning för kortet.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Estimation]</td> 
   <td>Ange eller mappa en uppskattning av den tid som krävs för att slutföra kortet.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Due date]</td> 
   <td>Ange eller mappa förfallodatumet för kortet.</p>
   <p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p>
   </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Status]</td> 
   <td>Välj en ny status för kortet.</p></td> 
  </tr> 
 </tbody> 
</table>

### Varumärkena

* [Skapa en anslagstavla](#create-a-board)
* [Läs en anslagstavla](#read-a-board)

#### Skapa en anslagstavla

Den här åtgärdsmodulen skapar en styrelse i Workfront. Du kan ange vilken typ av anslagstavla du vill skapa.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board name]</td> 
   <td>Ange eller mappa ett namn för den nya ritytan.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Template]</td> 
   <td>Välj mallen för den typ av anslagstavla som du vill skapa.</td> 
  </tr> 
 </tbody> 
</table>

#### Läs en anslagstavla

Den här åtgärdsmodulen returnerar information om en enda anslagstavla, till exempel kort, kolumner, taggar och medlemmar.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den anslagstavla som du vill hämta information för.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
 </tbody> 
</table>

### Kolumner

* [Skapa en kolumn](#create-a-column)
* [Söka efter en kolumn](#search-for-a-column)
* [Uppdatera en kolumn](#update-a-column)

#### Skapa en kolumn

Den här åtgärdsmodulen skapar en ny kolumn på den angivna ritytan.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den anslagstavla som du vill lägga till en kolumn i.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column ID]</td> 
   <td>Ange eller mappa ID:t för den kolumn som du vill uppdatera.<p>Du hittar kolumn-ID:t i informationen som returneras från modulen Läs en anslagstavla.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column name]</td> 
   <td>Ange eller mappa ett nytt namn för kolumnen.</td> 
  </tr> 
 </tbody> 
</table>

#### Söka efter en kolumn

Sökmodulen returnerar information om kolumnen med det angivna namnet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller den kolumn som du vill hämta.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Name]</td> 
   <td>Ange eller mappa namnet på den kolumn som du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera en kolumn

Den här åtgärdsmodulen uppdaterar namnet eller PIA-gränsen för den angivna kolumnen.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller den kolumn som du vill hämta.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Name]</td> 
   <td>Ange eller mappa namnet på den kolumn som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL WIP Limit]</td> 
   <td>Ange eller mappa en ny PIA-gräns för kolumnen.</td> 
  </tr> 
 </tbody> 
</table>

### Taggar

* [Lägga till en tagg på ett kort](#add-a-tag-to-a-card)
* [Skapa en tagg](#create-a-tag)

#### Lägga till en tagg på ett kort

Den här åtgärdsmodulen lägger till en tagg på ett kort.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill lägga till en tagg i.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den bräda som innehåller kortet som du vill lägga till en tagg i.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag ID]</td> 
   <td>Ange eller mappa ID:t för taggen som du vill lägga till.<p>Du hittar tagg-ID:t i informationen som returneras från modulen Läs en anslagstavla.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en tagg

Den här åtgärdsmodulen skapar en ny tagg och tilldelar den en färg.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>Ange eller mappa ID:t för den anslagstavla som du vill skapa en tagg för.<p>Du kan hitta ID:t för anslagstavlan i URL:en när du tittar på anslagstavlan i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag name]</td> 
   <td>Ange eller mappa ett namn för den nya taggen.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag Color]</td> 
   <td>Välj färg för den här taggen.</td> 
  </tr> 
 </tbody> 
</table>

### Kommentar

* [Skapa en kommentar](#create-a-comment)
* [Läs kortkommentarer](#read-card-comments)

#### Skapa en kommentar

Den här åtgärdsmodulen skapade en kommentar på det angivna kortet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill lägga till en kommentar i.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>Ange eller mappa texten för kommentaren som du vill lägga till.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Läs kortkommentarer

Den här åtgärdsmodulen hämtar kommentarerna från det angivna kortet.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>Ange eller mappa ID:t för kortet som du vill hämta kommentarerna för.<p>Kortets ID finns i URL:en när du visar kortet i Workfront.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>Ange det maximala antal kommentarer som du vill att modulen ska returnera i en körningscykel.</p></td> 
  </tr> 
 </tbody> 
</table>

### Övriga

#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till Workfront Boards API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Ange en relativ sökväg till <code> https://&lt;WORKFRONT_DOMAIN&gt;/boards-service/graphql?</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran</a>.</p><p>För de flesta ritytor är metoden POST. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Detta avgör begärans innehållstyp.</p> <p>Exempel:<code> { "Content-type":"application/json-stringify()"}</code></p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>För Workfront Boards är det här avsnittet vanligtvis tomt.</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av en JSON-inbäddad Graphql </p> <p>Exempel:</p><p>I det här exemplet uppdateras ett kolumnnamn. Du kan inkludera <code>boardId</code> och <code>columnId</code> som GUID antingen hårdkodade eller mappade från en tidigare modul.<p><pre>{<br> "query": "mutation { updateColumn(boardId: \"\", columnId: \"\", updateColumnInput: { name: \"\" }) { id name }}"<br>}</pre><p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


#### Göra ett anpassat GraphQL API-anrop

Den här åtgärdsmodulen gör en anpassad GraphQL-begäran till Workfront Boards API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>Du kan använda en befintlig Workfront-anslutning för att ansluta till Workfront Boards eller använda en viss Workfront Boards-anslutning. </p><p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Skapa en anslutning till Workfront Boards</a> i den här artikeln.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj metod för anropet. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation name]</td> 
   <td> <p>Ange ett namn för den här åtgärden. Detta kan göra det enklare att spåra och felsöka samtalet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables data source]</td> 
   <td> <p>Välj om variablerna ska hämtas från ett formulär eller från en samling.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variables]</td> 
   <td> <p>För varje variabel som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger variabelns nyckel och värde.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
   </tr> 
 </tbody> 
</table>
