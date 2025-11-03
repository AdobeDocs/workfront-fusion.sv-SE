---
title: Krypterare
description: Med Adobe Workfront Fusion Encryptor-modulerna kan du kryptera alla textdata. De stöder för närvarande meddelandekryptering via AES256 och PGP (OpenPGP).
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 0%

---

# Krypterare

Med Adobe Workfront Fusion [!UICONTROL Encryptor]-moduler kan du kryptera alla textdata. De stöder för närvarande meddelandekryptering via AES256 och PGP ([!UICONTROL OpenPGP]).

Dessa moduler kräver viss kunskap om krypteringsprocesser.

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



## Meddelandekryptering och dekryptering med PGP

När du krypterar och dekrypterar via PGP måste du använda en nyckelring och skapa en privat eller offentlig nyckel (eller båda).

Mer information om offentliga och privata nycklar finns i [Adobe Workfront Fusion-ordlistan](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md).

Mer information om nycklar finns i [Tangenter](/help/workfront-fusion/references/modules/keys.md).

## [!UICONTROL Encryptor]-moduler och deras fält

När du konfigurerar [!UICONTROL Encryptor] moduler visas följande fält. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

### AES-dekryptering (avancerat)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Markera den nyckel som du vill att modulen ska använda. Om du vill skapa en nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckel och kodningstyp.</td>
    </tr>
    <tr>
        <td>Bitar</td>
        <td>Välj om du vill att modulen ska använda 128- eller 256-bitarskryptering.</td>
    </tr>
    <tr>
        <td>Indatakodning</td>
        <td>Välj den typ av indatakodning som du vill använda:
        <ul>
        <li>binary</li>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Data</td>
        <td>Ange eller mappa de data som du vill dekryptera.</td>
    </tr>
    <tr>
        <td>Utdatakodning</td>
        <td>Välj den typ av utdatakodning som du vill använda:
        <ul>
        <li>ASCII</li>
        <li>binary</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Krypteringsalgoritm</td>
        <td>Välj den chifferalgoritm som du vill använda:
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Initiera vektorkodning</td>
        <td>Välj den initieringsvektorkodning som du vill använda:
        <ul>
        <li>UTF-8</li>
        <li>binary</li>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Kodning av autentiseringstaggar</td>
        <td>Välj den kodning för autentiseringstagg som du vill använda:
        <ul>
        <li>UTF-8</li>
        <li>binary</li>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
</table>

### AES-dekryptering (enkel)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Markera den nyckel som du vill att modulen ska använda. Om du vill skapa en nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckel och kodningstyp.</td>
    </tr>
   <tr>
        <td>Indatakodning</td>
        <td>Välj den typ av indatakodning som du vill använda:
        <ul>
        <li>binary</li>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Data</td>
        <td>Ange eller mappa de data som du vill dekryptera.</td>
    </tr>
    <tr>
        <td>Utdatakodning</td>
        <td>Välj den typ av utdatakodning som du vill använda:
        <ul>
        <li>ASCII</li>
        <li>binary</li>
        <li>UTF-8</li>
        </ul>
        </td>
     </tr>
    <tr>
        <td>Hemlig nyckel</td>
        <td>Ange eller mappa den hemliga nyckel som du vill använda.</td>
    </tr>
</table>

### AES-kryptering (avancerat)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Markera den nyckel som du vill att modulen ska använda. Om du vill skapa en nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckel och kodningstyp.</td>
    </tr>
    <tr>
        <td>Bitar</td>
        <td>Välj om du vill att modulen ska använda 128- eller 256-bitarskryptering.</td>
    </tr>
    <tr>
        <td>Indatakodning</td>
        <td>Välj den typ av indatakodning som du vill använda:
        <ul>
        <li>binary</li>
        <li>ASCII</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Data</td>
        <td>Ange eller mappa de data som du vill kryptera.</td>
    </tr>
    <tr>
        <td>Utdatakodning</td>
        <td>Välj den typ av utdatakodning som du vill använda:
        <ul>
        <li>ASCII</li>
        <li>binary</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Krypteringsalgoritm</td>
        <td>Välj den chifferalgoritm som du vill använda:
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Initiera vektorkodning</td>
        <td>Välj den kodning för autentiseringstagg som du vill använda:
        <ul>
        <li>UTF-8</li>
        <li>binary</li>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
</table>

### AES-kryptering (enkel)

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Key]</td>
        <td>Markera den nyckel som du vill att modulen ska använda. Om du vill skapa en nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckel och kodningstyp.</td>
    </tr>
   <tr>
        <td>Indatakodning</td>
        <td>Välj den typ av indatakodning som du vill använda:
        <ul>
        <li>binary</li>
        <li>ASCII</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Data</td>
        <td>Ange eller mappa de data som du vill kryptera.</td>
    </tr>
    <tr>
        <td>Utdatakodning</td>
        <td>Välj den typ av utdatakodning som du vill använda:
        <ul>
        <li>Bas 64</li>
        <li>binary</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Hemlig nyckel</td>
        <td>Ange eller mappa den hemliga nyckel som du vill använda.</td>
    </tr>
</table>


### Skapa digital signatur

Med den här modulen kan du dekryptera ett meddelande med offentliga och privata nycklar.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Välj den privata nyckel som ska användas för den här signaturen. Om du vill lägga till en privat nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckeltext och lösenfras.</td>
    </tr>
    <tr>
        <td>Algoritm </td>
        <td>Ange om du vill använda RSA-SHA1 eller RSA-SHA256. </td>
    </tr>
   <tr>
        <td>Indatakodning</td>
        <td>Välj den typ av indatakodning som du vill använda:
        <ul>
        <li>ASCII</li>
        <li>binary</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Utdatakodning</td>
        <td>Välj den typ av utdatakodning som du vill använda:
        <ul>
        <li>Bas 64</li>
        <li>Hexadecimal</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>Data</td>
        <td>Ange eller mappa data som du vill skapa signaturen från.</td>
    </tr>
</table>

### Dekryptera ett PGP-meddelande

Med den här modulen kan du dekryptera ett meddelande med offentliga och privata nycklar.

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Private key]</td>
        <td>Välj den privata nyckel som mottagaren ska använda för det här meddelandet. Om du vill lägga till en privat nyckel klickar du på <b>Lägg till</b> och anger nyckelns namn, nyckeltext och lösenfras.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Public key]</td>
        <td>Ange avsändarens offentliga nyckel. Detta kan autentisera avsändarens identitet.</td>
    </tr>
    <tr>
        <td>[!UICONTROL Message]</td>
        <td>Mappa meddelandet som du vill dekryptera.</td>
    </tr>
</table>

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
    </table>
