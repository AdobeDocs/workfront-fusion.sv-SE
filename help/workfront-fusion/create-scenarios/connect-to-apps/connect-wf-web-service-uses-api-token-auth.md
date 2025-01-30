---
title: Anslut Adobe Workfront Fusion till en webbtjänst som använder API-tokenauktorisering
description: Vissa tjänster tillåter inte integreringslösningar som Adobe Workfront Fusion att skapa en app som du enkelt kan använda i ditt scenario.
author: Becky
feature: Workfront Fusion
exl-id: 4a8ac816-52de-41e8-96d7-1c8cde2ebe32
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Anslut Adobe Workfront Fusion till en webbtjänst som använder API-tokenauktorisering

Vissa tjänster tillåter inte integreringslösningar som Adobe Workfront Fusion att skapa en app som du enkelt kan använda i ditt scenario.

Du kan lösa problemet genom att ansluta den önskade tjänsten (appen) till Workfront Fusion med HTTP > Gör en begäran-modul.

I den här artikeln beskrivs hur du ansluter nästan alla webbtjänster till Workfront Fusion med hjälp av en API-nyckel/API-token.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package 
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
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>Select or Prime Workfront Plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>Ultimate Workfront Plan: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ansluta till en webbtjänst som använder en API-token

Proceduren för att ansluta tjänsten via en API-token liknar den för de flesta webbtjänster.

1. Skapa ett program på webbtjänstens webbplats, enligt beskrivningen i avsnittet [Skapa ett nytt program och hämta API-token](#create-a-new-application-and-obtain-the-api-token) i den här artikeln.
1. Hämta API-nyckeln eller API-token.
1. Lägg till Workfront Fusions HTTP > Gör en Request-modul i ditt scenario.
1. Konfigurera modulen enligt webbtjänstens API-dokumentation och kör scenariot, vilket förklaras i avsnittet [Konfigurera HTTP-modulen](#set-up-the-http-module) i den här artikeln.

>[!NOTE]
>
>Det här exemplet ansluter till meddelandetjänsten för push-over.

## Skapa ett nytt program och hämta API-token

>[!NOTE]
>
>Det finns många olika sätt att skapa och distribuera API-nycklar eller API-tokens i webbtjänster. Instruktioner om hur du hämtar en API-nyckel och -token för den önskade webbtjänsten finns på tjänstens webbplats och söker efter &quot;API-nyckel&quot; eller &quot;API-token&quot;.
>
>Vi inkluderar instruktioner om hur du får en Pushover API-nyckel som exempel på vad du kan hitta.

1. Logga in på ditt Pushover-konto.
1. Klicka på **Skapa en program-/API-token** längst ned på sidan.
1. Fyll i programinformationen och klicka på **Skapa ett program**.
1. Lagra den angivna API-token på en säker plats. Du behöver det för Workfront Fusion HTTP > Make a Request-modulen för att ansluta till önskad webbtjänst (Pushover, i det här fallet).

## Konfigurera HTTP-modulen

Om du vill ansluta en webbtjänst till ditt Workfront Fusion-scenario måste du använda HTTP > Gör en begäran-modul i scenariot och konfigurera modulen enligt webbtjänstens API-dokumentation.

1. Lägg till HTTP > Gör en begäran-modul i ditt scenario.
1. Om du vill skicka ett meddelande med Workfront Fusion ställer du in HTTP-modulen enligt följande.

   >[!NOTE]
   >
   >De här modulinställningarna motsvarar dokumentationen för webbtjänsten Pushover API. Inställningarna kan vara annorlunda för andra webbtjänster. API-token kan till exempel infogas i huvudet och inte i fältet Brödtext.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> URL</td> 
      <td> <p><code>https://api.pushover.net/1/messages.json</code> </p> <p>URL-fältet innehåller slutpunkten som du hittar i webbtjänstens API-dokumentation.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> Metod</td> 
      <td> <p><code>POST</code> </p> <p>Vilken metod som används beror på motsvarande slutpunkt. Pushover-slutpunkten för push-meddelanden använder metoden POST.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Sidhuvuden</p> </td> 
      <td> <p>Vissa webbtjänster kan använda rubriker för att ange API-tokenautentisering eller andra parametrar. Detta är inte fallet i vårt exempel eftersom Pushover-slutpunkten för push-meddelanden använder Body (se nedan) för alla typer av begäranden.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Frågesträng</p> </td> 
      <td> <p>Vissa webbtjänster kan använda en frågesträng för att ange andra parametrar. Detta är inte fallet i vårt exempel eftersom webbtjänsten Pushover använder Body (se nedan) för alla typer av förfrågningar.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Typ av brödtext</p> </td> 
      <td> <p><code>Raw</code> </p> <p>Med den här inställningen kan du välja JSON-innehållstypen i fältet Innehållstyp nedan.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Innehållstyp</p> </td> 
      <td> <p><code>JSON (application/json)</code> </p> <p>JSON är den innehållstyp som krävs av Pushover-appen. Detta kan skilja sig från andra webbtjänster.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> Begär innehåll</p> </td> 
      <td> <p>Ange innehållet i Body request i JSON-format. Du kan använda modulen JSON &gt; Skapa JSON så som beskrivs i <a href="#map-the-json-body-using-the-json--create-json-module" class="MCXref xref">Mappa JSON-brödtexten med JSON &gt; Skapa JSON-modul</a> i den här artikeln. Du kan också ange JSON-innehållet manuellt, vilket förklaras i <a href="#enter-the-json-body-manually" class="MCXref xref">Ange JSON-brödtexten manuellt</a> i den här artikeln.</p> <p>I webbtjänstens API-dokumentation finns information om vilka parametrar som krävs för den webbtjänsten.</p> </td>

   </tr> 
    </tbody> 
   </table>

## Ange JSON-brödtexten manuellt

Ange parametrar och värden i JSON-format.

>[!BEGINSHADEBOX]

**Exempel:**

```
{"user":"12345c2ecu1hq42ypqzhswbyam34",
"token":"123459evz8aepwtxydndydgyumbfx",
"message":"Hello World!",
"title":"The Push Notification"}
```

>[!ENDSHADEBOX]

Det här exemplet innehåller följande information.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p> användare</p> </td> 
   <td> <p>Din USER_KEY. Detta finns på din Pushover-kontrollpanel.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> token </td> 
   <td> <p>Din API-token/API-nyckel som genererades när du skapade Pushover-appen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> message </td> 
   <td> <p>Textinnehållet i push-meddelandet som skickas till enheten/enheterna.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> title </td> 
   <td> <p>(Valfritt) Meddelandets titel. Om inget värde anges används appens namn. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mappa JSON-brödtexten med modulen JSON > Skapa JSON

Modulen Skapa JSON gör det enklare att ange JSON. Det ger dig också möjlighet att definiera värden dynamiskt.

Mer information om JSON-modulerna finns i [JSON-moduler](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/json-modules.md).

1. Ange eller mappa de värden som du vill skapa JSON från.

   ![JSON-värden](/help/workfront-fusion/create-scenarios/connect-to-apps/assets/json-values-350x288.png)

1. Anslut JSON > Create JSON-modulen till HTTP > Make a Request module.
1. Mappa JSON-strängen från modulen Create JSON till innehållsfältet Request i HTTP > Make a Request module.

När du kör scenariot skickas push-meddelandet till den enhet som har registrerats i ditt Pushover-konto.
