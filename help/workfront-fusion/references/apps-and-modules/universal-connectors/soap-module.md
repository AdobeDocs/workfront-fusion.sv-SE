---
title: SOAP
description: Du kan använda modulen SOAP för att ansluta till SOAP API:er i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: bf9af473f08463c00578a1a8b07c800239225f09
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# modulen [!UICONTROL SOAP]

Du kan använda modulen [!UICONTROL SOAP] för att ansluta till [!UICONTROL SOAP] API:er i [!UICONTROL Adobe Workfront Fusion].

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
   <p>Gammalt licenskrav: [!UICONTROL [!DNL Workfront Fusion] för Automatisering och integrering av arbetet] </p>
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
* Anpassade XML-schemaelement definierade med hjälp av [[!UICONTROL SOAP]-kodningsscheman och element ](https://schemas.xmlsoap.org).

>[!INFO]
>
>**Exempel:**
>  
>Följande känns inte igen korrekt av [!UICONTROL Workfront Fusion]:
>
>```
><complexType name="ArrayOfFloat">
>     <complexContent>
>           <restriction base="soapenc:Array">
>                 <attribute ref="soapenc:arrayType"
>                       wsdl:arrayType="xsd:integer[]"/>
>           </restriction>
>     </complexContent>
></complexType>
>```
>
>I det här exemplet finns referenserna `soapenc:Array`, `soapenc:arrayType` och `wsdl:arrayType` som ännu inte stöds i [!UICONTROL Workfront Fusion].

## Tillfällig lösning

Om modulen [!UICONTROL SOAP] vägrar att bearbeta WSDL-filen eller genererar olika fel i modulens konfiguration kan du försöka med att använda den universella modulen **[!UICONTROL HTTP]>[!UICONTROL Make a request]** i stället:

1. Skapa ett nytt scenario i [!DNL Workfront Fusion].
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

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. Öppna ett nytt webbläsarfönster eller en ny flik.
1. Klistra in WSDL-URL:en i webbläsarens adressfält och hämta XML-filen.

   WSDL-URL:en avslutas vanligtvis med `?wsdl`, men inte nödvändigtvis, till exempel `http://voip.ms/api/v1/server.wsdl`.

1. Om WSDL-filen inte visas direkt i webbläsaren öppnar du den hämtade filen i en textredigerare.
1. Sök efter taggen `<service>` eller `<wsdl:service>`:

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. Kopiera URL-adressen från attributet `location` när den har hittats.
1. I [!DNL Workfront Fusion] klistrar du in URL-adressen i HTTP-modulens URL-fält.
1. Öppna [onlineklienten [!UICONTROL SOAP] ](https://wsdlbrowser.com/) i ett nytt webbläsarfönster/på en ny flik.
1. Klistra in WSDL-URL:en i WSDL-URL-fältet.
1. Klicka på **[!UICONTROL Browse]**.
1. Välj från listan med funktioner till vänster, till exempel `getLanguages`.
1. Kopiera innehållet i textområdet [!UICONTROL Request XML].
1. I [!UICONTROL Workfront Fusion] klistrar du in det kopierade innehållet i modulens URL-fält.
1. Ange värden för valda parametrar genom att ersätta frågetecknen med faktiska värden:

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. Stäng modulens konfiguration genom att klicka på **[!UICONTROL OK]**.
1. Kör scenariot eller modulen.
