---
title: Krypterare
description: Med Adobe Workfront Fusion Encryptor-modulerna kan du kryptera alla textdata. De stöder för närvarande meddelandekryptering via AES256 och PGP (OpenPGP).
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Krypterare

Med modulerna [!DNL Adobe Workfront Fusion] [!UICONTROL Encryptor] kan du kryptera textdata. De stöder för närvarande meddelandekryptering via AES256 och PGP ([!UICONTROL OpenPGP]).

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
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet], [!UICONTROL [!DNL Workfront Fusion] för Automatisering av arbete]</p>
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

## Meddelandekryptering och dekryptering med PGP

När du krypterar och dekrypterar via PGP måste du använda en nyckelring och skapa en privat eller offentlig nyckel (eller båda).

Mer information om offentliga och privata nycklar finns i [Adobe Workfront Fusion-ordlistan](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md). <!--For more information on keychains, see [Keys in [!DNL Adobe Workfront Fusion]]().-->

## [!UICONTROL Encryptor]-moduler och deras fält

När du konfigurerar [!UICONTROL Encryptor] moduler visas följande fält. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

### Kryptera ett PGP-meddelande

Med den här modulen kan du kryptera ett meddelande med offentliga och privata nycklar.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Ange avsändarens privata nyckel. Detta kan autentisera avsändarens identitet.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Ange mottagarens offentliga nyckel.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Ange meddelandet som du vill kryptera.</td>
    </tr>

### Dekryptera ett PGP-meddelande

Med den här modulen kan du dekryptera ett meddelande med offentliga och privata nycklar.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Ange mottagarens privata nyckel.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Ange mottagarens offentliga nyckel. Detta kan autentisera avsändarens identitet.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Mappa meddelandet som du vill dekryptera.</td>
    </tr>
</table>
