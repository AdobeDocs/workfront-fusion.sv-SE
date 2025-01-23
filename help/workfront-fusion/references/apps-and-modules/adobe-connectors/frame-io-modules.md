---
title: Frame.io-moduler
description: Kontot  [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] .
author: Becky
feature: Workfront Fusion
exl-id: 121b145c-d04d-44b9-b673-ea2928e2346d
source-git-commit: 7f25a8a118a3dba3de3d834497e047bd1aeabf0a
workflow-type: tm+mt
source-wordcount: '2128'
ht-degree: 0%

---

# [!DNL Frame.io] moduler

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Frame.io] kan du övervaka, skapa, uppdatera, hämta eller ta bort resurser och kommentarer i ditt [!DNL Frame.io]-konto.

En videointroduktion till Frame.io-anslutningen finns i:

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

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

## Förutsättningar

Om du vill använda [!DNL Frame.io] moduler måste du ha ett [!DNL Frame.io]-konto

## API-information för Frame.io

För Frame.io-kopplingen används följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Bas-URL</td> 
   <td> https://api.frame.io/v2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-version</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## Anslut [!DNL Frame.io] till [!UICONTROL Adobe Workfront Fusion]

Du kan ansluta till [!DNL Frame.io] med en API-token eller med OAuth 2.0.

[Anslut till [!DNL Frame.io] med en API-token](#connect-to-frameio-using-an-api-token)

[Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE](#connect-to-frameio-using-oauth-20-pkce)

### Anslut till [!DNL Frame.io] med en API-token

Om du vill ansluta ditt [!DNL Frame.io]-konto till [!DNL Workfront Fusion] med en API-token måste du skapa API-token i ditt [!DNL Frame.io]-konto och infoga den i dialogrutan [!DNL Workfront Fusion] [!DNL Frame.io] [!UICONTROL Create a connection].

1. Logga in på ditt [!DNL Frame.io]-konto.
1. Gå till sidan **[!UICONTROL Tokens]** i [!DNL Frame.io] Developer.
1. Klicka på **[!UICONTROL New]**.
1. Ange namnet på token, markera de scope som du vill använda och klicka på **[!UICONTROL Create]**.
1. Kopiera angiven token.
1. Gå till [!DNL Workfront Fusion] och öppna dialogrutan **[!UICONTROL Create a connection]** för modulen [!DNL Frame.io].
1. Välj **[!DNL Frame.io]** i fältet **[!UICONTROL Connection type]**.
1. Ange den token som du har kopierat i steg 5 till fältet **[!UICONTROL Your [!DNL Frame.io] API Key]**
1. Klicka på **[!UICONTROL Continue]** för att upprätta anslutningen och återgå till modulen.

### Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE

Du kan skapa en anslutning till [!DNL Frame.io] med OAuth 2.0 PKCE med ett valfritt klient-ID. Om du vill inkludera ett klient-ID i anslutningen måste du skapa en OAuth 2.0-app i ditt [!DNL Frame.io]-konto.

* [Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE (utan klient-ID)](#connect-to-frameio-using-using-oauth-20-pkce-without-client-id)
* [Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE (med klient-ID)](#connect-to-frameio-using-using-oauth-20-pkce-with-client-id)

#### Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE (utan klient-ID)

1. Gå till [!DNL Workfront Fusion] och öppna dialogrutan **[!UICONTROL Create a connection]** för modulen [!DNL Frame.io].
1. Välj **[!UICONTROL [!DNL Frame.io] OAuth 2.0 PKCE]** i fältet **[!UICONTROL Connection type]**.
1. Ange ett namn för den nya anslutningen i fältet **[!UICONTROL Connection name]**.
1. Klicka på **[!UICONTROL Continue]** för att upprätta anslutningen och återgå till modulen.

#### Anslut till [!DNL Frame.io] med OAuth 2.0 PKCE (med klient-ID)

1. Skapa en OAuth 2.0-app i [!DNL Frame.io]. Instruktioner finns i [!DNL Frame.io]-dokumentationen för [!UICONTROL OAuth 2.0 Code Authorization Flow].

   >[!IMPORTANT]
   >
   >När du skapar OAuth 2.0-appen i [!DNL Frame.io]:
   >
   >* Ange följande som omdirigerings-URI:
   >   
   >     * **Amerika/APAC**: `https://app.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >     * **EMEA**: `https://app-eu.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >* Aktivera alternativet PCKE.


1. Kopiera angiven `client_id`.
1. Gå till [!DNL Workfront Fusion] och öppna dialogrutan **[!UICONTROL Create a connection]** för modulen [!DNL Frame.io].
1. Välj **[!UICONTROL [!DNL Frame.io] OAuth 2.0 PKCE]** i fältet **[!UICONTROL Connection type]**.
1. Ange ett namn för den nya anslutningen i fältet **[!UICONTROL Connection name]**.
1. Klicka på **[!UICONTROL Show advanced settings]**.
1. Ange `client_id` som du kopierade i steg 2 till fältet **[!UICONTROL Client ID]**.
1. Klicka på **[!UICONTROL Continue]** för att upprätta anslutningen och återgå till modulen.

## [!DNL Frame.io]-moduler och deras fält

När du konfigurerar [!DNL Frame.io] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Frame.io] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Assets](#assets)
* [Kommentar](#comments)
* [Projekt](#projects)
* [Övriga](#other)

### Assets

* [[!UICONTROL Create an Asset]](#create-an-asset)
* [[!UICONTROL Delete an Asset]](#delete-an-asset)
* [[!UICONTROL Get an Asset]](#get-an-asset)
* [[!UICONTROL List Assets]](#list-assets)
* [[!UICONTROL Update an Asset]](#update-an-asset)
* [[!UICONTROL Watch Asset Deleted]](#watch-asset-deleted)
* [[!UICONTROL Watch Asset Label Updated]](#watch-asset-label-updated)
* [[!UICONTROL Watch New Asset]](#watch-new-asset)

#### [!UICONTROL Create an Asset]

Den här åtgärdsmodulen skapar en ny resurs.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa teamet som äger projektet som du vill skapa en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet eller mappa ID:t för projektet som du vill skapa en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera mappen eller mappa ID:t för mappen som du vill skapa en resurs i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Välj om du vill skapa en mapp eller fil.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Ange namnet på den nya filen eller mappen.</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">File Type </td> 
    <td> <p>Select the type of file you want to upload.</p> </td> 
   </tr>
  --> <!--
   <tr> 
    <td role="rowheader">File Size </td> 
    <td> <p>The file size in bytes.</p> </td> 
   </tr>
  --> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>Om du skapar en fil anger du URL-adressen till filen som du vill överföra.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>Om du skapar en fil anger du en kort beskrivning av resursen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Label] </td> 
   <td> <p>Om du skapar en fil ska du välja om filen bearbetas, behöver granskas eller godkänns.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Asset]

Den här åtgärdsmodulen tar bort en angiven resurs.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Markera eller mappa teamet som äger projektet som innehåller resursen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Markera projektet eller det som innehåller resursen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera mappen som innehåller resursen som du vill ta bort</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera eller mappa resursen som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Asset]

Den här åtgärdsmodulen hämtar resursinformation.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa det team som äger projektet som innehåller resursen som du vill hämta information om.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Välj det projekt som innehåller resursen som du vill hämta information om.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Välj den mapp som innehåller resursen som du vill hämta information om.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera resursen eller mappa ID:t för resursen som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Assets]

Den här sökmodulen hämtar alla resurser i det angivna projektets mapp.

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa det team som äger projektet som innehåller mappen som du vill hämta resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Välj det projekt som innehåller mappen som du vill hämta resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Välj den mapp som du vill visa resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an Asset]

Med den här åtgärdsmodulen kan du uppdatera en befintlig resurs namn, beskrivning eller anpassade fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa teamet som äger projektet som du vill uppdatera en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet eller mappa ID:t för projektet som du vill uppdatera en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera mappen eller mappa ID:t för mappen som du vill uppdatera en resurs i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Ange eller mappa ID:t för resursen som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Ange namnet på den uppdaterade filen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>Ange en kort beskrivning av den uppdaterade resursen.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Asset Deleted]

Den här utlösarmodulen startar ett scenario när en resurs som hör till det angivna teamet tas bort.

Eftersom det här är en direktutlösare måste du välja eller skapa en webkrok som modulen ska använda.

Om du lägger till en webkrok anger du följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Ange ett namn för webkroken, till exempel"Resursen har tagits bort".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj teamet som den här webboken skapas för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Asset Label Updated]

Den här utlösarmodulen startar ett scenario när en etikett för en resurs som ägs av den angivna teamuppsättningen, ändras eller tas bort.

Eftersom det här är en direktutlösare måste du välja eller skapa en webkrok som modulen ska använda.

Om du lägger till en webkrok anger du följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Ange ett namn för webbokroken, till exempel"Resursstatus uppdaterad".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj teamet som den här webboken skapas för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch New Asset]

Denna utlösarmodul startar ett scenario när en ny resurs skapas för det angivna teamet.

Eftersom det här är en direktutlösare måste du välja eller skapa en webkrok som modulen ska använda.

Om du lägger till en webkrok anger du följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> Ange ett namn för webkroken, till exempel"Resursen har skapats".</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj teamet som den här webboken skapas för.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Kommentar

* [[!UICONTROL Create a Comment]](#create-a-comment)
* [[!UICONTROL Delete a Comment]](#delete-a-comment)
* [[!UICONTROL Get a Comment]](#get-a-comment)
* [[!UICONTROL List Comments]](#list-comments)
* [[!UICONTROL Update a Comment]](#update-a-comment)
* [[!UICONTROL Watch Comment Updated]](#watch-comment-updated)
* [[!UICONTROL Watch New Comment]](#watch-new-comment)

#### [!UICONTROL Create a Comment]

Den här åtgärdsmodulen lägger till en ny kommentar eller ett nytt svar till resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>Välj om du vill skapa en kommentar eller svara på en kommentar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Markera eller mappa teamet som äger projektet som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet eller mappa ID:t för projektet som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera mappen eller mappa ID:t för mappen som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera eller mappa resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Markera eller mappa kommentaren som du vill lägga till ett svar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Ange textinnehållet i kommentaren eller svaret.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Ange bildrutenumret i videon som kommentaren ska länkas till.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Comment]

Den här åtgärdsmodulen tar bort en befintlig kommentar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID]</td> 
   <td> <p> Markera eller mappa teamet som äger projektet som innehåller resursen som du vill ta bort en kommentar från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> Markera projektet eller mappa ID:t för projektet som innehåller resursen som du vill ta bort en kommentar från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p> Markera mappen som innehåller resursen som du vill ta bort en kommentar från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Ange eller mappa det ID för resursen som innehåller kommentaren som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Ange eller mappa ID:t för kommentaren som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Comment]

Denna åtgärdsmodul hämtar information om den angivna kommentaren.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa teamet som äger projektet som innehåller mappen som du vill hämta resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Välj det projekt som innehåller mappen som du vill hämta resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Välj den mapp som du vill visa resurser från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera resursen som innehåller kommentaren som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Markera kommentaren som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Comments]

Sökmodulen hämtar alla kommentarer för den angivna resursen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Markera eller mappa det team som äger projektet som innehåller mappen som du vill hämta kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Välj det projekt som innehåller mappen som du vill hämta kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera den mapp som innehåller resursen som du vill visa kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera den resurs som du vill visa kommentarer för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange eller mappa det maximala antal kommentarer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Comment]

Den här åtgärdsmodulen redigerar en befintlig kommentar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Markera eller mappa teamet som äger projektet som innehåller resursen som du vill uppdatera en kommentar för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet \ som innehåller resursen som du vill uppdatera en kommentar för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>Markera mappen som innehåller resursen som du vill uppdatera en kommentar för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera den resurs som du vill uppdatera en kommentar på.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Markera den kommentar som du vill uppdatera.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Ange textinnehållet i kommentaren.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Ange bildrutenumret i videon som kommentaren är länkad till.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Comment Updated]

Den här utlösarmodulen startar ett scenario när en kommentar redigeras.

Eftersom det här är en direktutlösare måste du välja eller skapa en webkrok som modulen ska använda.

Om du lägger till en webkrok anger du följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Ange namnet på webkroken, t.ex. Redigerad kommentar.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj teamet som den här webboken skapas för.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch New Comment]

Den här utlösarmodulen startar ett scenario när en ny kommentar eller ett nytt svar skapas.

Eftersom det här är en direktutlösare måste du välja eller skapa en webkrok som modulen ska använda.

Om du lägger till en webkrok anger du följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>Ange webbkrokens namn, t.ex. Ny kommentar.</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj teamet som den här webboken skapas för.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Projekt

#### [!UICONTROL List Projects]

Denna sökmodul hämtar alla projekt för det angivna teamet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>Välj eller mappa teamet som du vill hämta projekt för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>Ange eller mappa det maximala antalet projekt som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

#### [!UICONTROL Make an API Call]

Med den här modulen kan du utföra ett anpassat API-anrop.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>Ange en relativ sökväg till <code>https://api.frame.io</code>. Exempel: <code> /v2/teams</code></p> <p>Obs! En lista över tillgängliga slutpunkter finns i API-referensen för [!DNL Frame.io].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] lägger till auktoriseringshuvuden automatiskt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>Ange frågesträngen för begäran. För varje parameter som du vill ta med i frågesträngen klickar du på <b>[!UICONTROL Add item]</b> och anger fältets namn och önskat värde.</p> </td> 
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


<!-- 
**Example:** The following API call returns all teams and its details in your [!DNL Frame.io] account:

URL: `/v2/teams`

Method: `GET`

![](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

The result can be found in the module's Output under Bundle > Body.

In our example, the details of 1 team were returned:

![](/help/workfront-fusion/references/apps-and-modules/assets/api-call-output.png)

-->
