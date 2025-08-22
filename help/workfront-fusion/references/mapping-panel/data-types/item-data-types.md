---
title: Artikeldatatyper
description: Dina Adobe Workfront Fusion-scenarier kan innehålla de typer av objekt som listas nedan i ett paket.
author: Becky
feature: Workfront Fusion
exl-id: 3ad65959-5c19-4727-bc9d-4ff1d238ad8b
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# Artikeldatatyper

Du kan innehålla de typer av objekt som listas nedan i ett paket.

Mer information om vilka typer av objekt som Workfront Fusion tillåter konvertering mellan varandra finns i [Typtvång](/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md).

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>Text</p> </td> 
   <td> <p>Den vanligaste artikeltypen. För vissa textobjekt kontrollerar Adobe Workfront Fusion om den högsta eller lägsta tillåtna längden uppfylls eller om objektet utför formatvalidering (e-post, URL eller filnamn).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Nummer</p> </td> 
   <td> <p>För vissa numeriska objekt kan Workfront Fusion validera indata för ett visst intervall (det lägsta eller högsta tillåtna värdet).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Boolean (Ja/Nej)</p> </td> 
   <td> <p>Den här typen används för objekt med endast två möjliga värden: true eller false. </p> <p>När du anger moduler kan den booleska typen visas i två olika former:</p> 
    <ul> 
     <li> <p>Den obligatoriska kryssrutan visas om fältet är obligatoriskt och måste fyllas i.</p> <p> <img src="assets/boolean-checkbox-350x158.jpg" style="width: 350;height: 158;"> </p> </li> 
     <li> <p>Valfria fält som kan lämnas tomma visas som en valruta, vilket gör att du kan välja mellan tre värden: <code>Yes</code>, <code>No</code> och <code>Not defined</code> (standard).</p> <p> <img src="assets/boolean-convert-file-350x129.jpg" style="width: 350;height: 129;"> </p> </li> 
    </ul> <p>Du kan klicka på <strong>[!UICONTROL Map]</strong> om du behöver mappa värdet till ett objekt från en annan modul.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Datum</p> </td> 
   <td> <p>Datum anges i ISO 8601-datumformat, till exempel <code>2015-09-18T11:58Z</code>. Du kan ändra tidszonen i dina profilinställningar. </p> <p>Om du klickar på ett fält som kräver ett datum visas en popup-kalender i modulinställningarna. Tiden krävs inte för vissa objekt.</p> <p>Värden för Date-objekt formateras med den lokala tidszonen och webbtidszonen som är vald i din profil. Du kan visa ISO 8601-versionen av ett datumobjekts värde genom att hålla markören över objektet.</p> <p>Obs! Om ISO-värdet inte visas är objektet förmodligen text, inte ett datum.</p> <p>Tiden anges i formatet <code>hours:minutes:seconds</code>, till exempel <code>14:03:52</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Buffert (binära data)</p> </td> 
   <td> <p>Filinnehåll skickas vanligtvis som bufferttypsinnehåll (bildinnehåll, videofil med flera). I vissa fall inkluderas textdata i den här typen (till exempel en textfil). Workfront Fusion kan automatiskt konvertera textdata i binär kod till text och text till textdata i binär kod. Mer information finns i <a href="/help/workfront-fusion/create-scenarios/map-data/map-files.md" class="MCXref xref">Mappa filer</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Samling</p> </td> 
   <td> <p>En samling är ett objekt som består av flera underposter. Avsändarobjektet i ett e-postmeddelande är ett exempel på en samling: det innehåller avsändarens namn (texttyp) och avsändarens e-postadress (texttyp).</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Markera (meny)</p> </td> 
   <td> <p>När du konfigurerar modulinställningarna kan du välja bland flera objekt av samma typ. Ett exempel är mappvalsmenyn i inställningarna för modulerna [!DNL Dropbox]. </p> <p>När du ställer in moduler kan urvalsmenyn visas i två former:</p> <p> <p>Om det går att markera flera objekt visas flera objekt med kryssrutor.</p> <p> <img src="assets/image-kb-type-list-multi-350x232.jpg" style="width: 350;height: 232;"> </p> </p> <p>Om bara ett alternativ är möjligt visas en listruta.</p> <p> <img src="assets/select-menu-dropdown-350x130.jpg" style="width: 350;height: 130;"> </p> <p>Om du behöver mappa ett objekt från en annan modul använder du knappen <strong>Karta</strong> . Med den här knappen öppnas ett textfält i stället för en markeringsmeny. Mer information om mappning finns i <a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md" class="MCXref xref">Mappningsöversikt</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Array</p> </td> 
   <td> <p>Du kan använda arraytypen för att arbeta med flera värden av samma typ, inklusive samlingar. Ett exempel är modulerna [!UICONTROL Email]: de returnerar en matris med bilagor och varje bifogad fil innehåller namn, innehåll, storlek och så vidare. Mer information finns i <a href="/help/workfront-fusion/create-scenarios/map-data/map-an-array.md" class="MCXref xref">Mappa en array eller ett arrayelement</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Validering</p> </td> 
   <td> <p>Workfront Fusion kan utföra validering för varje objekttyp. Om ett objekt inte godkänns i valideringen avbryts bearbetningen av modulen på grund av ett datafel. Mer information finns i <a href="/help/workfront-fusion/references/errors/error-processing.md" class="MCXref xref">Feltyper </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
