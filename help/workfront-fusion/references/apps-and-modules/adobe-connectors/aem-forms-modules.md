---
title: Adobe Experience Manager Forms moduler
description: Med  [!DNL Adobe Experience Manager Forms] connector for Adobe Workfront Fusion kan du starta ett scenario baserat på händelser i ditt [!DNL Adobe Experience Manager Forms] konto, skapa, överföra och uppdatera resurser samt kopiera eller flytta mappar och resurser.
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: e0d7a655-1353-4d24-83d4-7da73d859a63
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager Forms] moduler

Med [!DNL Adobe Experience Manager Forms]-anslutningen för Adobe Workfront Fusion kan du starta ett scenario baserat på händelser i ditt [!DNL Adobe Experience Manager Forms]-konto genom att skapa en webkrok.

Du kan konfigurera ett formulär i [!DNL Adobe Experience Manager Forms] för att skicka formuläröverföringar till den här webkroken.

## Åtkomstkrav

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront-plan*</td>
  <td> <p>[!UICONTROL Pro] eller högre</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens*</td>
   <td> <p>[!UICONTROL Plan], [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuellt licenskrav: Inga Workfront Fusion-licenskrav.</p>
   <p>eller</p>
   <p>Gammalt licenskrav: [!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Aktuellt produktkrav: Om du har Adobe Workfront-planen [!UICONTROL Select] eller [!UICONTROL Prime] måste din organisation köpa Adobe Workfront Fusion samt Adobe Workfront för att kunna använda de funktioner som beskrivs i den här artikeln. Workfront Fusion ingår i Workfront-planen för [!UICONTROL Ultimate].</p>
   <p>eller</p>
   <p>Krav för äldre produkter: Din organisation måste köpa Adobe Workfront Fusion och Adobe Workfront för att kunna använda de funktioner som beskrivs i den här artikeln.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Kontakta Workfront-administratören om du vill veta vilken plan, licenstyp eller åtkomst du har.

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

## Förutsättningar

* Du måste ha ett [!DNL Adobe Experience Manager Forms]-konto för att kunna använda den här modulen.

## Adobe Experience Manager Assets API-information

Adobe Experience Manager Assets Connector använder följande:

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API-tagg</td> 
   <td>v1.2.27</td> 
  </tr>
 </tbody> 
 </table>

## Skapa en anslutning till Adobe Experience Manager Forms

Så här skapar du en anslutning för dina [!DNL Adobe Experience Manager Forms]-moduler:

1. Klicka på **[!UICONTROL Add]** bredvid rutan Anslutning i någon av modulerna.

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
        <td>
          <p>Välj om den här anslutningen ska ansluta till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>
          <p>Ange om det här kontot är ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance URL without a trailing slash]</td>
        <td>
          <p>Ange den URL som du använder för att komma åt kontot, utan det sista snedstrecket.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL IMS endpoint]</td>
        <td>
          <p><code>https://ims-na1.adobelogin.com</code></p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange ditt klient-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din [!DNL Adobe]-klienthemlighet. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Org ID]</td>
        <td>Ange ditt organisations-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>Ange ditt tekniska konto-ID för [!DNL Adobe]. Detta finns i avsnittet [!UICONTROL Credentials details] i [!DNL Adobe Developer Console].
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>Ange lämpliga metaomfång       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>Ange den privata nyckel som skapades när dina autentiseringsuppgifter skapades i [!DNL Adobe Developer Console]. </p>
          <p>Så här extraherar du din privata nyckel eller ditt certifikat:</p>
          <ol>
            <li value="1">
              <p>Klicka på <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Välj vilken typ av fil du extraherar.</p>
            </li>
            <li value="3">
              <p>Markera filen som innehåller den privata nyckeln eller certifikatet.</p>
            </li>
            <li value="4">
              <p>Ange lösenordet för filen.</p>
            </li>
            <li value="5">
              <p>Klicka på <b>[!UICONTROL Save]</b> för att extrahera filen och återgå till anslutningsinställningarna.</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

## Adobe Experience Manager Forms-modulen och dess fält

För närvarande finns det bara en modul i Adobe Experience Manager Forms-anslutningen.

### Håll utkik efter formulärhändelser

Med denna direktutlösare (webkrok) kan du starta ett scenario när en Skicka-åtgärd inträffar i ett Adobe Experience Manager-formulär.

>[!IMPORTANT]
>
>Den här modulen kräver även konfiguration i Adobe Experience Manager. När du har konfigurerat den här webbokroken måste du öppna Adobe Experience Manager och konfigurera formuläret så att du kan skicka material till webkroken.
>
><!--For instructions on the required form configuration, see insert url here-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p>Ange ett namn för webkroken</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter ditt [!DNL Adobe Experience Manager]-konto till Workfront Fusion finns i <a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/aem-forms-modules.md#create-a-connection-to-adobe-experience-manager-forms" class="MCXref xref">Skapa en anslutning till [!DNL Adobe Experience Manager Forms]</a></p> </td> 
  </tr>

Modulen skapar en webbkrok och ger dig webbkrokadressen som du kan ange i dialogrutan för att skicka formulär i [!DNL Adobe Experience Manager Forms].
