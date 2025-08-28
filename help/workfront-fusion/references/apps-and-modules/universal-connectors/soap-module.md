---
title: Modulen SOAP
description: Du kan använda SOAP-modulen för att ansluta till SOAP API:er i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: 95d52f8227c8a40c0db165eea9d2877e60446de9
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# modulen [!UICONTROL SOAP]

Du kan använda modulen [!UICONTROL SOAP] för att ansluta till [!UICONTROL SOAP] API:er i [!UICONTROL Adobe Workfront Fusion].

## SOAP-modulen och dess fält

SOAP-anslutningen innehåller endast en modul, åtgärden Kör SOAP

### Kör SOAP-åtgärd

Den här åtgärdsmodulen kör den angivna SOAP-åtgärden.



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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## SOAP-modulen och dess fält

När du konfigurerar SOAP-moduler visas fälten som listas nedan i Workfront Fusion.  En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Kör SOAP-åtgärd

Den här åtgärdsmodulen kör en SOAP-åtgärd baserat på den WSDL som du anger.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL WSDL]</td> 
   <td> Välj den WSDL som du vill att modulen ska använda. Om du vill skapa en WSDL klickar du på <b>Lägg till</b> bredvid fältet och fyller i fälten. </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL HTTP headers]</td> 
   <td> För varje HTTP-huvud som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger rubrikens namn och värde.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL SOAP headers]</td> 
   <td> För varje SOAP-rubrik som du vill lägga till klickar du på <b>Lägg till objekt</b> och anger rubrikens namn, värde, namnutrymme och XMLNS.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Force SOAP headers]</td> 
   <td> Aktivera det här alternativet om du vill konfigurera rubriker för SOAP 1.2. </td> 
  </tr> 
  </tbody> 
</table>

## Begränsningar för modulen [!UICONTROL SOAP]

>[!NOTE]
>
>Omdirigeringar inaktiveras under WDSL-inläsning. Det här är en säkerhetsfunktion, men det kan betyda att overifierade omdirigeringar blockeras när modulen körs.

Modulen [!UICONTROL SOAP] är för närvarande i betaversion och stöder inte:

* Omdefiniera element
* Begränsningar för bråktal
* Begränsningar för totalt antal siffror
* Begränsningar för tomt utrymme
* Flera delar i in- och utdatameddelanden. Endast meddelanden med en del stöds
* Anpassade XML-schemaelement som definieras med hjälp av SOAP Encoding-scheman och -element.

>[!BEGINSHADEBOX]

**Exempel:**

Följande känns inte igen korrekt av [!UICONTROL Workfront Fusion]:

```
<complexType name="ArrayOfFloat">
   <complexContent>
      <restriction base="soapenc:Array">
         <attribute ref="soapenc:arrayType"
            wsdl:arrayType="xsd:integer[]"/>
      </restriction>
   </complexContent>
</complexType>
```

I det här exemplet finns referenserna `soapenc:Array`, `soapenc:arrayType` och `wsdl:arrayType` som ännu inte stöds i [!UICONTROL Workfront Fusion].

>[!ENDSHADEBOX]

## Tillfällig lösning

Om modulen [!UICONTROL SOAP] vägrar att bearbeta WSDL-filen eller genererar olika fel i modulens konfiguration kan du försöka med att använda den universella modulen **[!UICONTROL HTTP]>[!UICONTROL Make a request]** i stället:

1. Skapa ett nytt scenario i Workfront Fusion.
1. Infoga modulen **[!UICONTROL HTTP]>[!UICONTROL Make a request]** i scenariot.
1. Öppna modulens konfiguration och fyll i följande fält:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method]</td> 
      <td> <p>[!UICONTROL POST]</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td> <p>[!UICONTROL Raw]</p> </td>
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td> <p>[!UICONTROL XML (application/xml)]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Parse response]</td> 
      <td>[!UICONTROL Enabled]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![Workaround](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. Öppna ett nytt webbläsarfönster eller en ny flik.
1. Klistra in WSDL-URL:en i webbläsarens adressfält och hämta XML-filen.

   WSDL-URL:en avslutas vanligtvis med `?wsdl`, men inte nödvändigtvis, till exempel `http://voip.ms/api/v1/server.wsdl`.

1. Om WSDL-filen inte visas direkt i webbläsaren öppnar du den hämtade filen i en textredigerare.
1. Sök efter taggen `<service>` eller `<wsdl:service>`:

   <!--![Service](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. Kopiera URL-adressen från attributet `location` när den har hittats.
1. I Workfront Fusion klistrar du in URL-adressen i HTTP-modulens URL-fält.
1. Ange värden för valda parametrar genom att ersätta frågetecknen med faktiska värden.

   >[!NOTE]
   >
   > Använd ett WSDL-visningsprogram online om du vill hämta specifika värden från WSDL-filen.

   <!--![Request](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. Stäng modulens konfiguration genom att klicka på **[!UICONTROL OK]**.
1. Kör scenariot eller modulen.
