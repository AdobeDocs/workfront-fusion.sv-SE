---
title: Frame.io-moduler (Beta)
description: Kontot  [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] .
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: cc1ce10fccf159a0c17a3bba978d88c0d1013cbf
workflow-type: tm+mt
source-wordcount: '2604'
ht-degree: 0%

---

# [!DNL Frame.io] Beta-moduler (V4)

>[!IMPORTANT]
>
>I den här artikeln beskrivs den nya (beta) versionen av Frame.io-kopplingen. Den här kopplingen används för att ansluta till Frame.io version 4.
>
>Instruktioner om den äldre versionen av Frame.io-kopplingen finns i [Frame.io Legacy-koppling](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md).

Med modulerna [!DNL Adobe Workfront Fusion] [!DNL Frame.io] kan du övervaka, skapa, uppdatera, hämta eller ta bort resurser och kommentarer i ditt [!DNL Frame.io]-konto.

Workfront har två Frame.io-anslutningar, baserat på den version av Frame.io som du ansluter till.

| Koppling | Frame.io-version |
|---|---|
| Frame.io (Beta) | V4 |
| Frame.io (äldre) | V3 |

Instruktioner om den äldre versionen av Frame.io-kopplingen finns i [Frame.io Legacy-koppling](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md).


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
   <p>Aktuell: Inga Workfront Fusion-licenser krävs</p>
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
   <td> https://api.frame.io/v4</td> 
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

Du kan ansluta automatiskt med inloggningsuppgifter, manuellt skapa en anslutning för inloggningsuppgifter eller skapa en server-till-server-anslutning.

* [Anslut automatiskt med inloggningsuppgifter](#connect-automatically-with-user-credentials#)
* [Skapa en anslutning för användarautentiseringsuppgifter manuellt](#create-a-user-credentials-connection-manually)
* [Skapa en server-till-server-anslutning](#create-a-server-to-server-connection)

### Anslut automatiskt med inloggningsuppgifter

Den här metoden skapar en anslutning automatiskt om du är inloggad på Frame.io, eller ansluter dig till inloggningssidan Frame.io så att du kan logga in.

1. Klicka **[!UICONTROL Add]** bredvid anslutningsrutan i någon av modulerna Frame.io Beta.
1. Ange ett namn för anslutningen.
1. Klicka på **Fortsätt**.
1. Om du uppmanas att logga in på ditt Frame.io-konto gör du det.
1. Om du är en del av mer än en Frame.io-organisation väljer du den organisation som du vill använda för den här anslutningen.

Anslutningen skapas.

### Skapa en anslutning för användarautentiseringsuppgifter manuellt

Du kan skapa en anslutning för användarautentiseringsuppgifter genom att logga in i Frame.io eller genom att ange ett klient-ID eller klienthemlighet.

Om du vill skapa en server-till-server-anslutning måste du först konfigurera ett program i Adobe Developer Console.

* [Skapa inloggningsuppgifter i Adobe Developer Console](#create-user-credentials-in-the-adobe-developer-console)
* [Konfigurera en anslutning för användarautentisering](#configure-a-user-authentication-connection)

#### Skapa inloggningsuppgifter i Adobe Developer Console

Om du inte redan har inloggningsuppgifter för server-till-server i ett Adobe Developer Console-projekt kan du skapa dem.

1. Öppna [Adobe Developer Console](https://developer.adobe.com/).
1. Välj ett befintligt projekt i Adobe Developer Console som ska användas för anslutningen

   eller

   Skapa ett nytt projekt i Adobe Developer Console. Instruktioner finns i [Skapa ett tomt projekt](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. Klicka på **Lägg till API** på sidan Projektöversikt eller på sidan Kom igång med ditt nya projekt.
1. Leta reda på och klicka på **API:t Frame.io** på sidan som öppnas.
1. Välj **Användarverifiering** på sidan Välj autentiseringstyp och klicka på **Nästa**.
1. Välj **OAuth-webbapp** på sidan Lägg till inloggningsuppgifter för användarautentisering och klicka på **Nästa**.
1. Ange följande på inloggningssidan för Konfigurera OAuth-webbprogrammet:   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Default redirect URI]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Redirect URI pattern]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. Klicka på **Nästa**.
1. Klicka på **Spara konfigurerat API**.
1. På produktsidan klickar du på kortet för de inloggningsuppgifter som du nyss skapade.

   Här hittar du ditt klient-ID och din klienthemlighet.

>[!NOTE]
>
> Vi rekommenderar att du lämnar det här fönstret öppet när du börjar konfigurera anslutningen i Adobe Workfront Fusion. Du kan kopiera klient-ID:t och hämta och kopiera klienthemlighet från den här sidan för att klistra in i anslutningsfälten.


#### Konfigurera en anslutning för användarautentisering

1. Klicka **[!UICONTROL Add]** bredvid anslutningsrutan i någon av modulerna Frame.io Beta.
1. Klicka på **Visa avancerade inställningar** i rutan Skapa en anslutning.

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
            <p>Välj <b>IMS-användarautentisering</b>.</p>
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
          <td>Ange din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du skapar inloggningsuppgifter finns i <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Skapa inloggningsuppgifter i Adobe Developer Console</a> i den här artikeln.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du skapar inloggningsuppgifter finns i <a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">Skapa inloggningsuppgifter i Adobe Developer Console</a> i den här artikeln.</p>
        </tr>
       </tbody>
    </table>
1. Om du uppmanas att logga in på ditt Frame.io-konto gör du det.
1. Om du är en del av mer än en Frame.io-organisation väljer du den organisation som du vill använda för den här anslutningen.

Anslutningen skapas.


### Skapa en server-till-server-anslutning

Om du vill skapa en server-till-server-anslutning måste du först konfigurera ett program i Adobe Developer Console.

* [Skapa serverreferenser i Adobe Developer Console](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [Konfigurera en server-till-server-anslutning](#configure-a-server-to-server-connection)

#### Skapa serverreferenser i Adobe Developer Console

Om du inte redan har inloggningsuppgifter för server-till-server i ett Adobe Developer Console-projekt kan du skapa dem.

1. Öppna [Adobe Developer Console](https://developer.adobe.com/).
1. Välj ett befintligt projekt i Adobe Developer Console som ska användas för anslutningen

   eller

   Skapa ett nytt projekt i Adobe Developer Console. Instruktioner finns i [Skapa ett tomt projekt](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty).

1. Klicka på **Lägg till API** på sidan Projektöversikt eller på sidan Kom igång med ditt nya projekt.
1. Leta reda på och klicka på **API:t Frame.io** på sidan som öppnas.
1. På sidan Välj autentiseringstyp väljer du **Server-till-server-autentisering** och klickar på **Nästa**.
1. Ange ett namn för autentiseringsuppgifterna. På så sätt kan du identifiera inloggningsuppgifterna senare i API-autentiseringsuppgifterna i Adobe Admin Console.
1. Klicka på **Nästa**.
1. På sidan Välj produktprofiler väljer du den produktprofil som innehåller det Frame.io-konto som du vill ansluta till.
1. Klicka på **Spara konfigurerat API**.
1. På produktsidan klickar du på kortet för de inloggningsuppgifter som du nyss skapade.

   Här hittar du ditt klient-ID och din klienthemlighet.

>[!NOTE]
>
> Vi rekommenderar att du lämnar det här fönstret öppet när du börjar konfigurera anslutningen i Adobe Workfront Fusion. Du kan kopiera klient-ID:t och hämta och kopiera klienthemlighet från den här sidan för att klistra in i anslutningsfälten.


#### Konfigurera en server-till-server-anslutning

1. Klicka **[!UICONTROL Add]** bredvid anslutningsrutan i någon av modulerna Frame.io Beta.

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
            <p>Välj <b>IMS-server till server</b>.</p>
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
          <td>Ange din [!DNL Adobe] [!UICONTROL Client ID]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du skapar autentiseringsuppgifter finns i <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Skapa server-till-server-autentiseringsuppgifter i Adobe Developer Console</a> i den här artikeln.</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>Ange din [!DNL Adobe] [!UICONTROL Client Secret]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].<p>Instruktioner om hur du skapar autentiseringsuppgifter finns i <a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">Skapa server-till-server-autentiseringsuppgifter i Adobe Developer Console</a> i den här artikeln.</p>
        </tr>
       </tbody>
    </table>
1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.




## [!DNL Frame.io]-moduler och deras fält

När du konfigurerar [!DNL Frame.io] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL Frame.io] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Assets](#assets)
* [Kommentar](#comments)
* [Mappar](#folders)
* [Projekt](#projects)
* [Aktier](#shares)
* [Arbetsytor](#workspaces)
* [Övriga](#other)

### Assets

* [[!UICONTROL Create an asset]](#create-an-asset)
* [[!UICONTROL Delete an asset]](#delete-an-asset)
* [[!UICONTROL Get an asset]](#get-an-asset)
* [[!UICONTROL List assets]](#list-assets)
* [[!UICONTROL Update an asset]](#update-an-asset)

#### [!UICONTROL Create an asset] <!--different for v4-->

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller projektet som du vill skapa en resurs för.</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera arbetsytan eller mappa ID:t för arbetsytan som innehåller projektet som du vill skapa en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet eller mappa ID:t för projektet som du vill skapa en resurs för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Välj den sökväg där du vill skapa en resurs.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>Ange namnet på filen som du vill använda för resursen.</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">Filstorlek </td> 
    <td> <p>Ange eller mappa filstorleken i byte.</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>Om du skapar en fil anger du URL-adressen till filen som du vill överföra.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
   <td> <p>Välj medietyp för resursen.</p> </td> 
  </tr> 
  </tbody> 
</table>

#### [!UICONTROL Delete an asset]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller resursen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera eller mappa resursen som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an asset]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller resursen som du vill hämta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Markera eller mappa resursen som du vill hämta.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List assets]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller de resurser som du vill visa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned assets] </td> 
   <td> <p>Ange eller mappa det maximala antalet resurser som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Kommentar

* [[!UICONTROL Create a Comment]](#create-a-comment)
* [[!UICONTROL Delete a Comment]](#delete-a-comment)
* [[!UICONTROL Get a Comment]](#get-a-comment)
* [[!UICONTROL List Comments]](#list-comments)
* [[!UICONTROL Update a Comment]](#update-a-comment)

#### [!UICONTROL Create a comment]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för det konto som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för arbetsytan som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera projektet eller mappa ID:t för projektet som innehåller resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Markera sökvägen till resursen som du vill lägga till en kommentar i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> Ange textinnehållet i kommentaren eller svaret.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>Ange bildrutenumret i videon som kommentaren ska länkas till.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page] </td> 
   <td> <p>Om resursen är en PDF-fil anger eller mappar du den sida som kommentaren ska kopplas till.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a comment]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller kommentarer som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Ange eller mappa ID:t för kommentaren som du vill ta bort.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a comment]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera kontot eller mappa ID:t för kontot som innehåller kommentarer som du vill hämta information om.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>Markera kommentaren som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List comments]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa det konto som innehåller resursen som du vill hämta kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera eller mappa arbetsytan som innehåller resursen som du vill hämta kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Välj det projekt som innehåller resursen som du vill hämta kommentarer från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Välj den sökväg som leder till resursen som du vill visa kommentarer från.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments] </td> 
   <td> <p>Ange eller mappa det maximala antal kommentarer som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a comment]

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa kontot som innehåller projektet som innehåller resursen som du vill uppdatera en kommentar för.</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Page] </td> 
   <td> <p>Om resursen är en PDF-fil anger eller mappar du den sida som kommentaren är kopplad till.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Mappar

#### Skapa en mapp

Den här åtgärdsmodulen skapar en ny mapp i Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa kontot där du vill skapa en mapp.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera eller mappa arbetsytan där du vill skapa en mapp.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Välj var du vill skapa en mapp.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Path] </td> 
   <td> <p>Välj den sökväg där du vill skapa en mapp.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn </td> 
   <td> <p>Ange eller mappa ett namn för den nya mappen.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Projekt

* [Skapa ett projekt](#create-a-project)
* [Visa projekt](#list-projects)

#### Skapa ett projekt

Denna åtgärdsmodul skapar ett nytt projekt i Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Välj eller mappa kontot där du vill skapa ett projekt.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera eller mappa arbetsytan där du vill skapa ett projekt.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn </td> 
   <td> <p>Ange eller mappa ett namn för det nya projektet.</p> </td> 
  </tr> 
 </tbody> 
</table>

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
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa det konto som innehåller resursen som du vill hämta projekt från.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera eller mappa arbetsytan som innehåller resursen som du vill hämta projekt från.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned projects] </td> 
   <td> <p>Ange eller mappa maximalt antal projekt
   du vill att modulen ska returneras under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Aktier

* [Lägga till en resurs i en delningslänk](#add-an-asset-to-a-share-link)
* [Skapa en delningslänk](#create-a-share-link)

#### Lägga till en resurs i en delningslänk

Den här åtgärdsmodulen lägger till en resurs i en delningslänk i Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa kontot som innehåller resurslänken som du vill lägga till en resurs i.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share link ID] </td> 
   <td> <p>Markera eller mappa delningslänken som du vill lägga till en resurs i.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>Ange eller mappa-ID för resursen som du vill lägga till i delningslänken.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en delningslänk

Den här åtgärdsmodulen skapar en ny delningslänk i Frame.io.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa kontot där du vill skapa en delningslänk.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>Markera eller mappa arbetsytan där du vill skapa en delningslänk.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>Markera eller mappa projektet där du vill skapa en delningslänk.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Åtkomst </td> 
   <td> <p>Ange om den här länken har offentlig eller begränsad åtkomst.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Assets </td> 
   <td> <p>För varje resurs som du vill lägga till i resurslänken klickar du på <b>Lägg till objekt</b> och anger resursens ID.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Beskrivning </td> 
   <td> <p>Ange eller mappa en beskrivning för delningslänken.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn </td> 
   <td> <p>Ange eller mappa utgångsdatumet för länken.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn </td> 
   <td> <p>Ange eller mappa ett namn för den nya delningslänken.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">Namn </td> 
   <td> <p>Ange eller mappa en lösenfras för delningslänken.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Arbetsytor

#### Skapa en arbetsyta

Den här åtgärdsmodulen skapar en ny arbetsyta i bildruta.io

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa kontot där du vill skapa en arbetsyta.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>Ange eller mappa ett nytt namn för arbetsytan.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Listarbetsytor

Den här modulen visar alla arbetsytor i ett konto.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>Instruktioner om hur du skapar en anslutning till [!DNL Frame.io] finns i <a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref"> Ansluta [!DNL Frame.io] till [!DNL Adobe Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account ID] </td> 
   <td> <p>Markera eller mappa det konto som innehåller resursen som du vill hämta arbetsytor från.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned workspaces] </td> 
   <td> <p>Ange eller mappa maximalt antal arbetsytor
   du vill att modulen ska returneras under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Övriga

#### [!UICONTROL Make a custom API call]

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
   <td> <p>Ange en relativ sökväg till <code>https://api.frame.io</code>. Exempel: <code> /v4/me</code></p> <p>Obs! En lista över tillgängliga slutpunkter finns i API-referensen för [!DNL Frame.io].</p> </td> 
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
   <td role="rowheader">[!UICONTROL Query string] </td> 
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

![API call example](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

The result can be found in the module's Output under Bundle > Body.

In our example, the details of 1 team were returned:

![API call output](/help/workfront-fusion/references/apps-and-modules/assets/api-call-output.png)

-->
