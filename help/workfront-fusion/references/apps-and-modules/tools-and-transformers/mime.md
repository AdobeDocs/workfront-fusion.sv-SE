---
title: MIME-moduler
description: Du kan använda MIME-typer i Adobe Workfront Fusion. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen text/html kommer att bearbetas i en annan webbläsare än en fil med MIME-typen image/jpeg. MIME-typer fungerar oberoende av operativsystem och maskinvara.
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# [!UICONTROL MIME] moduler

Du kan använda MIME-typer i Adobe Workfront Fusion. MIME-typer (Multipurpose Internet Mail Extension) är etiketter som gör att program kan identifiera olika typer av data som delas på Internet. Webbservrar och webbläsare använder MIME-typen för att avgöra vad som ska göras med en fil. En fil med till exempel MIME-typen `text/html` kommer att bearbetas i en annan webbläsare än en fil med MIME-typen `image/jpeg`. MIME-typer fungerar oberoende av operativsystem och maskinvara.

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



## [!UICONTROL MIME]-moduler och deras fält

* [Skaffa ett filtillägg](#get-a-file-extension)
* [Hämta en MIME-typ](#get-a-mime-type)

### [!UICONTROL Get a file extension]

Denna transformatormodul returnerar det ursprungliga filtillägget för en viss MIME-typ.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME type]</td> 
   <td> <p>Ange eller mappa den MIME-typ som du vill bestämma filtillägget för. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Get a MIME type]

Den här transformatormodulen returnerar den MIME-typ som är associerad med ett visst filnamn, sökväg eller tillägg.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL File]</td> 
   <td> <p>Ange eller mappa filen som du vill bestämma MIME-typen för. </p> <p>Du kan ange filen med:</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File path]</strong> </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>/file/image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File name]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>image.jpeg</p> </li> 
     <li><strong>[!UICONTROL File extension]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>Exempel: </b></span></span>jpeg</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
