---
title: Adobe Workfront moduler
description: Du kan använda Adobe Workfront Fusion Adobe Workfront-kontakten för att automatisera processerna i Workfront. Om du har en Workfront Fusion for Work Automation- och Integration-licens kan du också använda den för att ansluta till program och tjänster från tredje part.
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 93c27cf6-38b0-466c-87bb-926c4817eae7
source-git-commit: 6fa7ab493112351d9480b21b23b3b6b7b14f2230
workflow-type: tm+mt
source-wordcount: '7292'
ht-degree: 0%

---

# Adobe Workfront moduler

Du kan använda Adobe Workfront Fusion Adobe Workfront-kontakten för att automatisera processerna i Workfront. Du kan även ansluta Workfront till andra program och tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md). Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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
   <p>Äldre: Alla </p>
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


>[!NOTE]
>
>* Om din organisation använder det äldre licenspaketet (baserat på anslutningar) måste den ha en Workfront Fusion for Work Automation- och Integration-licens för att kunna ansluta till program och tjänster från tredje part. Workfront Connector räknar inte med antalet aktiva appar som är tillgängliga för din organisation. Alla scenarier, även om de bara använder Workfront-appen, räknas av mot organisationens totala antal scenarier.

+++

## Anslut Workfront till Workfront Fusion

Workfront-anslutningen använder OAuth 2.0 för att ansluta till Workfront.

Du kan skapa en anslutning till ditt Workfront-konto direkt inifrån en Workfront Fusion-modul.

1. Klicka på **Lägg till** bredvid anslutningsfältet i en Adobe Workfront-modul.
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
          <p>Ange ett namn för den nya anslutningen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>
          <p>Välj om du ansluter till en produktionsmiljö eller icke-produktionsmiljö.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>Ange om du ansluter till ett tjänstkonto eller ett personligt konto.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>Ange ditt Workfront klient-ID. Detta finns under OAuth2-program under Konfigurera i Workfront. Öppna det program du ansluter till för att se klient-ID:t.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>Ange din Workfront-klienthemlighet. Detta finns under OAuth2-program under Konfigurera i Workfront. Om du inte har någon klienthemlighet för OAuth2-programmet i Workfront kan du generera en annan. Instruktioner finns i dokumentationen för Workfront.</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>Detta kan vara standardvärdet eller så kan du ange URL:en för din Workfront-instans följt av <code>/integrations/oauth2</code>. <p>Exempel: <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Host prefix]</td>
        <td>I de flesta fall bör det här värdet vara <code>origin</code>.
      </tr>
    </tbody>
    </table>

1. Klicka på **[!UICONTROL Continue]** för att spara anslutningen och återgå till modulen.

   Om du inte är inloggad på Workfront dirigeras du till en inloggningsskärm. När du har loggat in kan du tillåta anslutningen.

>[!NOTE]
>
>* OAuth 2.0-anslutningar till Workfront API är inte längre beroende av API-nycklar.
>* Om du vill skapa en anslutning till en Workfront Sandbox-miljö måste du skapa ett OAuth2-program i den miljön och sedan använda det klient-ID och klienthemlighet som genereras av det programmet i anslutningen.

## Workfront-moduler och deras fält

När du konfigurerar Workfront-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Workfront-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).


![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* Om du inte ser de mest aktuella fälten i en Workfront-modul kan det bero på problem med cachelagring. Vänta en timme och försök igen.
>* HTTP 429-statuskoder från Adobe Workfront bör inte orsaka inaktiveringar, utan i stället utlösa en kort körningspaus i scenariot.

* [Utlösare](#triggers)
* [Åtgärder](#actions)
* [Sökningar](#searches)

### Utlösare

<!--
* [Watch Events](#watch-events) 
* [Watch Record](#watch-record) 
* [Watch Field](#watch-field)
-->

+++ **[!UICONTROL Watch Events]**

Denna utlösarmodul kör ett scenario i realtid när objekt av en viss typ läggs till, uppdateras eller tas bort i Workfront

Modulen returnerar alla standardfält som är associerade med posten, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

1. Klicka på **[!UICONTROL Add]** till höger om rutan **Webkrok**.

1. Konfigurera webkroken i rutan **[!UICONTROL Add a hook]** som visas.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook name]</td> 
      <td>Ange ett namn för webkroken</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Connection]</td> 
      <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Type]</td> 
      <td>Markera den typ av Workfront-post som du vill att modulen ska bevaka.</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL State]</td> 
      <td>Välj om du vill titta på det gamla eller nya läget.<ul><li><p><b>[!UICONTROL New state]</b></p><p>Utlös ett scenario när posten ändras till <b></b> för ett givet värde.</p><p>Om läget till exempel är inställt på [!UICONTROL New State] och filtret är inställt på [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress] utlöser webkroken ett scenario när [!UICONTROL Status] ändras till [!UICONTROL In Progress], oavsett vilken status som var tidigare. </p></li><li><p><b>[!UICONTROL Old state]</b></p><p>Utlös ett scenario när posten ändrar <b> från</b> ett givet värde.</p><p>Om läget till exempel är inställt på [!UICONTROL Old State] och filtret är inställt på [!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress] utlöser webkroken ett scenario när en [!UICONTROL Status] som för närvarande är [!UICONTROL In Progress] ändras till en annan status. </p></li></ul></td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL Events filters]</p> </td> 
      <td> <p>Du kan ställa in filter så att endast poster som uppfyller de villkor du väljer bevakas.</p> <p>För varje filter anger du fältet som du vill att filtret ska utvärderas, operatorn och värdet som du vill att filtret ska tillåta. Du kan använda mer än ett filter genom att lägga till OCH-regler.</p> <p><b>Obs!</b> Du kan inte redigera filter i befintliga Workfront-webbböcker. Om du vill ställa in olika filter för Workfront-händelseprenumerationer tar du bort den aktuella webbkroken och skapar en ny.</p> <p>Mer information om händelsefilter finns i <a href="#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Evenemangsprenumerationsfilter i Workfront &gt; [!UICONTROL Watch Events] moduler</a> i den här artikeln.</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>Uteslut händelser som har gjorts i den här anslutningen</td> 
      <td>Aktivera det här alternativet om du vill exkludera händelser som har skapats eller uppdaterats med samma koppling som den här utlösarmodulen använder. Detta kan förhindra situationer där ett scenario kan utlösa sig självt och få det att upprepas i en oändlig slinga.<p><b>Obs!</b> Tilldelningsposttypen innehåller inte det här alternativet.</p></td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Record Origin]</td> 
      <td>
       <p>Välj om du vill att scenariot ska bevaka [!UICONTROL New Records Only], [!UICONTROL Updated Records Only], [!UICONTROL New and Updated Records] eller [!DNL Deleted Records Only].</p>
       <p><b>Obs!</b> Om du väljer [!UICONTROL New and Updated Records] skapar webkroken 2 händelseprenumerationer (för samma webkrok-adress).</p>
       </td> 
     </tr> 
    </tbody> 
   </table>



   <!--Markdown 0032 placeholder-->

När webbkroken har skapats kan du visa adressen till slutpunkten som händelser skickas till.

Mer information finns i avsnittet [Exempel på händelsenyttolaster](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-api#examples-of-event-payloads) i artikeln Event Subscription API (Händelseprenumerations-API) i Workfront-dokumentationen.

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Watch Field]**

Den här utlösarmodulen kör ett scenario när ett fält som du anger uppdateras. Modulen returnerar både det gamla och det nya värdet för det angivna fältet. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Markera den typ av Workfront-post som du vill att modulen ska bevaka.</p> <p>Välj till exempel [!UICONTROL Task] om du vill börja köra scenariot varje gång ett postfält uppdateras i en uppgift.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Field]</td> 
   <td>Markera det fält som du vill att modulen ska bevaka för uppdateringar. Dessa fält återspeglar de fält som din Workfront-administratör har ställt in för spårning.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td>Markera de objektfält som du vill ska ingå i utdatapaketet för den här modulen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Watch Record]**

Den här utlösarmodulen kör ett scenario när objekt av en viss typ läggs till, uppdateras eller både och. Modulen returnerar alla standardfält som är associerade med posten eller posterna, tillsammans med anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

I utdata anger modulen om varje post är ny eller uppdaterad.

Poster som både lagts till och uppdaterats sedan det senaste scenariot kördes returneras som nya poster.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Välj om du vill att scenariot ska bevaka [!UICONTROL New Records Only], [!UICONTROL Updated Records Only] eller [!UICONTROL New and Updated Records].</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record Type]</td> 
   <td> <p>Markera den typ av Workfront-post som du vill att modulen ska bevaka.</p> <p>Om du till exempel vill starta scenariot varje gång ett nytt projekt skapas, väljer du [!UICONTROL Project]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reference]</td> 
   <td> <p>Markera de referensfält som du vill ska ingå i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Markera de samlingsfält som du vill ska ingå i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Optional Filter]</td> 
   <td> <p>(Avancerat) Ange en API-kodsträng för att definiera eventuella ytterligare parametrar eller kod som förfinar villkoren. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++


### Åtgärder

<!--
* [Convert object](#convert-object) 
* [Create a record (attaching custom forms)](#create-a-record-attaching-custom-forms) 
* [Create a record](#create-a-record) 
* [Custom API Call](#custom-api-call) 
* [Delete Record](#delete-record) 
* [Download Document](#download-document) 
* [Misc Action](#misc-action) 
* [Read a Record](#read-a-record) 
* [Update Record](#update-record) 
* [Upload Document](#upload-document)
-->

+++ **[!UICONTROL Convert object]**

Den här åtgärdsmodulen gör någon av följande konverteringar:

* Konvertera problem till projekt
* Konvertera problem till aktivitet
* Konvertera aktivitet till projekt

>[!NOTE]
>
>Från och med juli 2024 kan anpassade formulär inkluderas när ett objekt konverteras.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Object type]</td> 
   <td> <p>Markera den typ av objekt som du vill konvertera. Detta är den typ som objektet har före konverteringen.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Convert to]</td> 
   <td>Markera det objekt som du vill konvertera det till. Detta är den typ som objektet har efter konverteringen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL <Object> ID]</td> 
   <td> <p>Ange objektets ID. </p> <p>Obs! När du anger ID:t för ett objekt kan du börja skriva namnet på objektet och sedan markera det i listan. Modulen anger sedan rätt ID i fältet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Template ID]</td> 
   <td> <p>Om du konverterar till ett projekt väljer du det mall-ID som du vill använda för projektet.</p> <p>Obs! När du anger ID:t för ett objekt kan du börja skriva namnet på objektet och sedan markera det i listan. Modulen anger sedan rätt ID i fältet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Custom forms]</td> 
   <td>Markera de anpassade formulär som du vill lägga till i det nyligen konverterade objektet och ange värden för fälten i det anpassade formuläret.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Options]</td> 
   <td> <p>Aktivera de alternativ du vill ha när du konverterar objektet. Alternativen är tillgängliga beroende på vilket objekt du konverterar till eller från.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Copy native fields]</td> 
   <td> <p>Aktivera det här alternativet om du vill kopiera inbyggda fält från det ursprungliga objektet till det nya objektet.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Copy custom forms]</td> 
   <td> <p>Aktivera det här alternativet om du vill kopiera inbyggda fält från det ursprungliga objektet till det nya objektet.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a record]**

I den här åtgärdsmodulen skapas ett objekt, t.ex. ett projekt, en uppgift eller ett problem i Workfront, och du kan lägga till ett anpassat formulär i det nya objektet. I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

Se till att du anger det minsta antalet inmatningsfält. Om du till exempel vill skapa ett problem måste du ange ett giltigt överordnat projekt-ID i fältet Projekt-ID för att ange var problemet ska finnas i Workfront. Du kan använda mappningspanelen för att mappa den här informationen från en annan modul i ditt scenario, eller ange den manuellt genom att skriva in namnet och sedan välja den i listan.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av Workfront-post som du vill att modulen ska skapa.</p> <p>Om du till exempel vill skapa ett projekt väljer du [!UICONTROL Project] i listrutan.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td> <p>Markera de fält som du vill ska vara tillgängliga för datainmatning. På så sätt kan du använda de här fälten utan att behöva bläddra igenom de fält du inte behöver. Du kan sedan ange eller mappa data till dessa fält.</p> <p>Använd fältet <b>[!UICONTROL Attach Custom Form]</b> för fält i anpassade formulär.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Attach Custom Form]</td> 
   <td>Markera de anpassade formulär som du vill lägga till i det nya objektet och ange eller mappa värden för fälten.</td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* När du anger ID:t för ett objekt kan du börja skriva namnet på objektet och sedan markera det i listan. Modulen anger sedan rätt ID i fältet.
>* När du anger text för ett anpassat fält eller ett [!UICONTROL Note]-objekt (kommentar eller svar) kan du använda HTML-taggar i fältet [!UICONTROL Note Text] för att skapa RTF, till exempel fet eller kursiv text.
>

+++

+++ **[!UICONTROL Create Record (Legacy)]**

>[!IMPORTANT]
>
>Den här modulen har ersatts med modulen Skapa en post. Vi rekommenderar att du använder den modulen i nya scenarier.
>Befintliga scenarier som använder den här modulen fortsätter att fungera som förväntat. Den här modulen tas bort från modulväljaren i maj 2025.

Den här åtgärdsmodulen skapar ett objekt, till exempel ett projekt, en uppgift eller ett problem i Workfront. I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

Se till att du anger det minsta antalet inmatningsfält. Om du till exempel vill skapa ett problem måste du ange ett giltigt överordnat projekt-ID i fältet Projekt-ID för att ange var problemet ska finnas i Workfront. Du kan använda mappningspanelen för att mappa den här informationen från en annan modul i ditt scenario, eller ange den manuellt genom att skriva in namnet och sedan välja den i listan.

Den här modulen kopplar inte anpassade formulär när objektet skapas. Använd modulen [!UICONTROL Create a record (attaching custom forms)] om du vill bifoga anpassade formulär när du skapar ett objekt.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av Workfront-post som du vill att modulen ska skapa.</p> <p>Om du till exempel vill skapa ett projekt väljer du [!UICONTROL Project] i listrutan.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td>Markera de fält som du vill ska vara tillgängliga för datainmatning. På så sätt kan du använda de här fälten utan att behöva bläddra igenom de fält du inte behöver.</td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* När du anger ID:t för ett objekt kan du börja skriva namnet på objektet och sedan markera det i listan. Modulen anger sedan rätt ID i fältet.
>* När du anger text för ett anpassat fält eller ett [!UICONTROL Note]-objekt (kommentar eller svar) kan du använda HTML-taggar i fältet [!UICONTROL Note Text] för att skapa RTF, till exempel fet eller kursiv text.

+++

+++ **[!UICONTROL Custom API Call]**

Med den här åtgärdsmodulen kan du göra ett anpassat autentiserat anrop till Workfront API. På så sätt kan du skapa en dataflödesautomatisering som inte kan uppnås med andra Workfront-moduler.

Modulen returnerar följande information:

* **[!UICONTROL Status Code]** (tal): Detta anger om HTTP-begäran lyckades eller misslyckades. Det här är standardkoder som du kan söka efter på Internet.
* **[!UICONTROL Headers]** (objekt): En mer detaljerad kontext för svars-/statuskoden som inte relaterar till utdatatexten. Alla sidhuvuden som visas i en svarshuvud är inte svarshuvuden, så en del kanske inte är användbara för dig.

  Svarshuvuden beror på den HTTP-begäran du valde när du konfigurerade modulen.

* **[!UICONTROL Body]** (objekt): Beroende på den HTTP-begäran du valde när du konfigurerade modulen kan du få tillbaka data. Dessa data, till exempel data från en GET-begäran, finns i det här objektet.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>Ange en relativ sökväg till <code> https://&lt;WORKFRONT_DOMAIN&gt;/attask/api/&lt;API_VERSION&gt;/</code>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>Välj den version av Workfront API som du vill att modulen ska använda.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Metoder för HTTP-begäran i Adobe Workfront Fusion</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Detta avgör begärans innehållstyp.</p> <p>Exempel:<code> {"Content-type":"application/json"}</code></p> <p>Obs! Om du får felmeddelanden och det är svårt att fastställa deras ursprung bör du överväga att ändra rubrikerna baserat på Workfront-dokumentationen. Om ditt anpassade API-anrop returnerar ett 422 HTTP-begärandefel kan du försöka med att använda en <code>"Content-Type":"text/plain"</code>-rubrik.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> <p>Tips! Vi rekommenderar att du skickar information via JSON-brödtexten i stället för som frågeparametrar.</p> </td> 
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

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Delete Record]**

Den här åtgärdsmodulen tar bort ett objekt, till exempel ett projekt, en uppgift eller ett problem i Workfront.

Du anger postens ID.

Modulen returnerar postens ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Force delete]</td> 
   <td>Aktivera det här alternativet om du vill vara säker på att posten tas bort, även om användargränssnittet i Workfront begär att du bekräftar borttagningen.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Async delete]</td> 
   <td>Aktivera det här alternativet om du vill tillåta att modulen tas bort asynkront.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>ID</td> 
   <td> <p>Ange det unika Workfront-ID:t för den post som du vill ta bort modulen.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td>Markera den typ av Workfront-post som du vill ta bort modulen.</td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>Vi rekommenderar följande scenariokonfiguration för att undvika möjligheten att poster inte tas bort på grund av asynkrona åtgärder.
>
>1. Ta bort posten synkront.
>1. Lägg till felhantering i modulen Ta bort post för att ignorera felet som orsakas av timeout på 40 sekunder.


+++

+++ **[!UICONTROL Download Document]**

Denna åtgärdsmodul hämtar ett dokument från Workfront.

Du anger postens ID.

Modulen returnerar dokumentets innehåll, filnamn, filtillägg och filstorlek. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Document ID]</td> 
   <td> <p>Mappa eller ange det unika Workfront-id:t för dokumentet som du vill att modulen ska hämta.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Misc Action]**

Med den här åtgärdsmodulen kan du utföra åtgärder mot API:t.

>[!NOTE]
>
>Från och med juli 2024 innehåller åtgärden `convertToProject` fältet `copyCategories`. När värdet är `TRUE` inkluderas alla anpassade formulär i projektet som utgåvan konverteras till.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av Workfront-post som du vill att modulen ska interagera med.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Action]</td> 
   <td> <p>Välj den åtgärd som du vill att modulen ska utföra.</p> <p>Du kan behöva fylla i ytterligare fält, beroende på vilken [!UICONTROL Record Type] och [!UICONTROL Action] du väljer. Vissa kombinationer av dessa två inställningar kan endast kräva ett post-ID, medan andra (till exempel Projekt för <strong>[!UICONTROL Record Type]</strong> och [!UICONTROL Attach Template] för <strong>[!UICONTROL Action]</strong>) kräver ytterligare information (till exempel ett objekt-ID och ett mall-ID).</p><p>Tillgängliga alternativ för vissa åtgärder finns i <a href="#misc-action-options" class="MCXref xref">Alternativ för andra åtgärder</a> i den här artikeln.</p> <p>Mer information om enskilda fält finns i <a href="http://developer.workfront.com/">dokumentationen för Workfront-utvecklare</a>. <p><strong>Obs!</strong> Utvecklarens dokumentationswebbplats innehåller endast information via API-version 14, men innehåller fortfarande värdefull information för API-anrop. </p> 
    <ol> 
     <li value="1"> <p>Välj posttyp i den vänstra navigeringen på dokumentationssidan för Workfront-utvecklare. Följande typer har egna sidor:</p> 
      <ul> 
       <li> <p>[!UICONTROL Projects]</p> </li> 
       <li> <p>[!UICONTROL Tasks]</p> </li> 
       <li> <p>[!UICONTROL Issues]</p> </li> 
       <li> <p>[!UICONTROL Users]</p> </li> 
       <li> <p>[!UICONTROL Documents]</p> </li> 
      </ul> <p>För alla andra posttyper väljer du <b>[!UICONTROL Other objects and endpoints]</b> och letar upp posttypen på de alfabetiskt sorterade sidorna.</p> </li> 
     <li value="2"> <p>På sidan med rätt posttyp söker du efter åtgärden (Ctrl-F eller Cmd-F).</p> </li> 
     <li value="3"> <p>Visa beskrivningar för tillgängliga fält under den valda åtgärden.</p> </li> 
    </ol> <p>Obs!  <p>När du skapar ett korrektur med Workfront [!UICONTROL Misc Action]-modulen är det bästa sättet att skapa ett korrektur utan några avancerade alternativ och sedan uppdatera korrekturet med SOAP-API:t i [!DNL Workfront Proof] .</p><p>Mer information om hur du skapar ett korrektur med Workfront API (som används i den här modulen) finns i <a href="https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/tips-troubleshooting-apis/api-create-proof-options-json" class="MCXref xref">Lägga till avancerade korrekturalternativ när du skapar ett korrektur via Adobe Workfront API</a></p> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td>Ange eller mappa det unika Workfront-ID:t för den post som du vill att modulen ska interagera med.<p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p></td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

#### Alternativ för diverse åtgärder

##### Uppgift

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Åtgärd</th> 
   <th>Alternativ</th> 
  </tr> 
  <tr> 
   <td>Kopiera</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearConstraints</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Raderar ekonomiska data</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Rensar påminnelsemeddelanden</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Flytta</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearDocuments</li>
   <li>clearConstraints</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Raderar ekonomiska data</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Rensar påminnelsemeddelanden</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

##### Problem

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Åtgärd</th> 
   <th>Alternativ</th> 
  </tr> 
  <tr> 
   <td>Kopiera</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearPermissions</li>
   <li>clearProgress</li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Konvertera till uppgift</td> 
   <td>
   <ul>
   <li>preserveIssue<p>Behåll det ursprungliga problemet och knyt lösningen till den här uppgiften</p></li>
   <li>preservePrimaryContact<p>Tillåt åtkomst till den primära kontakten för den här aktiviteten</p></li>
   <li>preserveCompletionDate<p>Behåll det planerade slutförandedatumet för problemet</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Konvertera till projekt</td> 
   <td>
   <ul>
   <li>preserveIssue<p>Behåll det ursprungliga problemet och knyt lösningen till den här uppgiften</p></li>
   <li>preservePrimaryContact<p>Tillåt åtkomst till den primära kontakten för den här aktiviteten</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



##### Projekt

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>Åtgärd</th> 
   <th>Alternativ</th> 
  </tr> 
  <tr> 
   <td>Kopiera</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Raderar ekonomiska data</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>Rensar påminnelsemeddelanden</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>Bifoga mall/Spara som mall</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearBillingRates</li>
   <li>clearConstraints</li>
   <li>clearDeliverables<p>Rensar mål</p></li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>Raderar ekonomiska data</p></li>
   <li>clearHourTypes</li>
   <li>clearIssueSetup<p>Rensar köegenskaper och inställningar för utleveranser</p></li>
   <li>clearPredecessors</li>
   <li>clearRisks</li>
   <li>clearSharingOptions</li>
   <li>clearTimedNotifications<p>Rensar påminnelsemeddelanden</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



+++

+++ **[!UICONTROL Read a Record]**

Den här åtgärdsmodulen hämtar data från en enda post.

Du anger postens ID. Du kan också ange vilka relaterade poster som du vill att modulen ska läsa.

Om posten som modulen läser till exempel är ett projekt kan du ange att du vill att projektets uppgifter ska läsas.

Modulen returnerar en array med data från de utdatafält som du har angett.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>Välj den Workfront-objekttyp som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Output Custom Form]</td>
     <td> <p>Välj de anpassade formulär som du vill inkludera i utdatapaketet för den här modulen och välj sedan de specifika fält från de anpassade formulär som du vill inkludera i utdata.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>Markera de referensfält som du vill ta med i utdata.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>Markera de referensfält som du vill ta med i utdata.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>Ange det unika Workfront-ID:t för den post som du vill att modulen ska läsa.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Read a Record (Legacy)]**

>[!IMPORTANT]
>
>Den här modulen har ersatts med modulen Läs en post. Vi rekommenderar att du använder den modulen i nya scenarier.
>Befintliga scenarier som använder den här modulen fortsätter att fungera som förväntat. Den här modulen tas bort från modulväljaren i maj 2025.

Den här åtgärdsmodulen hämtar data från en enda post.

Du anger postens ID. Du kan också ange vilka relaterade poster som du vill att modulen ska läsa.

Om posten som modulen läser till exempel är ett projekt kan du ange att du vill att projektets uppgifter ska läsas.

Modulen returnerar en array med data från de utdatafält som du har angett.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>

<td>Välj den Workfront-objekttyp som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>

<td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>Markera de referensfält som du vill ta med i utdata.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>Markera de referensfält som du vill ta med i utdata.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>Ange det unika Workfront-ID:t för den post som du vill att modulen ska läsa.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **Uppdatera nyttolastversion för händelser**

Workfront har nyligen släppt en ny version av sin abonnemangstjänst. Den nya versionen är inte en ändring av Workfront API, utan snarare en ändring av prenumerationsfunktionen för evenemang. Den här åtgärdsmodulen uppdaterar den händelsenyttolastversion som används för det här scenariot.

Mer information om den nya händelseprenumerationsversionen finns i [Versionshantering för händelseteckning](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning) i Workfront-dokumentationen

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Version]</td> 
   <td> Välj den version av händelseprenumerationen som du vill använda för denna nyttolast. </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **Uppdatera en post**


Den här åtgärdsmodulen uppdaterar ett objekt, t.ex. ett projekt, en uppgift eller ett problem. I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen.

Du anger postens ID.

Modulen returnerar objektets ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Ange det unika Workfront-ID:t för den post som du vill att modulen ska uppdatera.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>Markera den typ av Workfront-post som du vill att modulen ska uppdatera.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>Markera de fält som du vill ska vara tillgängliga för datainmatning. På så sätt kan du använda de här fälten utan att behöva bläddra igenom de fält du inte behöver. Du kan sedan ange eller mappa data till dessa fält.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Attach Custom Form]</td> 
   <td>Välj de anpassade formulär som du vill ange fältvärden för på den nya posten. När du har valt formuläret anger du data för fälten i det formuläret.<p> Om du vill ange fältvärden för ett formulär som du bifogar i den här modulen, inkluderar du det anpassade formulär-ID:t i fälten som ska mappas.</td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
> När du anger text för ett anpassat fält eller ett [!UICONTROL Note]-objekt (kommentar eller svar) kan du använda HTML-taggar i fältet [!UICONTROL Note Text] för att skapa RTF, till exempel fet eller kursiv text.


+++

+++ **[!UICONTROL Update Record (Legacy)]**

>[!IMPORTANT]
>
>Den här modulen har ersatts med modulen Uppdatera en post. Vi rekommenderar att du använder den modulen i nya scenarier.
>Befintliga scenarier som använder den här modulen fortsätter att fungera som förväntat. Den här modulen tas bort från modulväljaren i maj 2025.

Den här åtgärdsmodulen uppdaterar ett objekt, t.ex. ett projekt, en uppgift eller ett problem. I modulen kan du välja vilka av objektets fält som är tillgängliga i modulen.

Du anger postens ID.

Modulen returnerar objektets ID och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Ange det unika Workfront-ID:t för den post som du vill att modulen ska uppdatera.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>Markera den typ av Workfront-post som du vill att modulen ska uppdatera.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>Markera de fält som du vill ska vara tillgängliga för datainmatning. På så sätt kan du använda de här fälten utan att behöva bläddra igenom de fält du inte behöver. Du kan sedan ange eller mappa data till dessa fält.</td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* När du anger ID:t för ett objekt kan du börja skriva namnet på objektet och sedan markera det i listan. Modulen anger sedan rätt ID i fältet.
>* När du anger text för ett anpassat fält eller ett [!UICONTROL Note]-objekt (kommentar eller svar) kan du använda HTML-taggar i fältet [!UICONTROL Note Text] för att skapa RTF, till exempel fet eller kursiv text.

+++

+++ **[!UICONTROL Upload Document]**

Den här åtgärdsmodulen överför ett dokument till ett Workfront-objekt, t.ex. ett projekt, en uppgift eller ett problem. Den här modulen överför dokumentet i segment, vilket gör överföringsprocessen smidigare för Workfront.

Den här modulen kan hantera större filer än den äldre modulen och är en del av en fasad utrullning till organisationer med ett Ultimate Workfront-paket.

Du anger platsen för dokumentet, filen som du vill överföra och ett valfritt nytt namn för filen.

Modulen returnerar ID:t för dokumentet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>Ange det unika Workfront-id för den post som du vill överföra dokumentet till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>Välj den typ av Workfront-post där du vill att modulen ska överföra dokumentet.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>Beroende på vilken typ av relaterad post det är kan du behöva ange eller mappa ett mapp-ID.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

+++ **[!UICONTROL Upload Document (Legacy)]**

Den här åtgärdsmodulen överför ett dokument till ett Workfront-objekt, t.ex. ett projekt, en uppgift eller ett problem. Hela dokumentet överförs samtidigt.

Du anger platsen för dokumentet, filen som du vill överföra och ett valfritt nytt namn för filen.

Modulen returnerar ID:t för dokumentet och eventuella associerade fält, tillsammans med eventuella anpassade fält och värden som anslutningen har åtkomst till. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>Ange det unika Workfront-id för den post som du vill överföra dokumentet till.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>Välj den typ av Workfront-post där du vill att modulen ska överföra dokumentet.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>Beroende på vilken typ av relaterad post det är kan du behöva ange eller mappa ett mapp-ID.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Välj en källfil från en tidigare modul eller mappa källfilens namn och data.</p> </td> 
  </tr> 
 </tbody> 
</table>

Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i [Workfront-objekttyper som är tillgängliga för varje Workfront-modul](#workfront-object-types-available-for-each-workfront-module).

+++

### Sökningar

<!--
* [Read Related Records](#read-related-records) 
* [Search](#search)
-->

+++ **[!UICONTROL Read Related Records]**

Den här sökmodulen läser poster som matchar den sökfråga du anger, i ett visst överordnat objekt.

Du anger vilka fält som ska inkluderas i utdata. Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av överordnad post (Workfront-objekt) vars associerade poster du vill läsa.</p> <p>Se en lista över de Workfront-objekttyper som du kan använda den här modulen för i <a href="#object-types-available-for-each-workfront-search-module" class="MCXref xref">Workfront-objekttyper som är tillgängliga för varje Workfront-modul</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Parent Record ID]</td> 
   <td> <p>Ange eller mappa ID:t för den överordnade post vars associerade poster du vill läsa.</p> <p>Om du vill hämta ID:t öppnar du Workfront-objektet i webbläsaren och kopierar texten i slutet av URL:en efter "ID=.". Exempel: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Markera eller mappa den typ av underordnad post som du vill att modulen ska läsa.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Välj den information som du vill inkludera i utdatapaketet för den här modulen.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search]**

Den här sökmodulen söker efter poster i ett objekt i Workfront som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av Workfront-post som du vill att modulen ska söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Custom forms list]</td> 
   <td> <p>Välj minst ett anpassat formulär. Fält från dessa anpassade formulär är tillgängliga för sökfrågan.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Välj ett alternativ för att ange om du vill att modulen ska få det första resultatet som matchar dina sökvillkor eller alla resultat som matchar det.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>Markera de fält som du vill använda som sökvillkor. Dessa fält är sedan tillgängliga i listrutan Sökvillkor.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Ange fältet som du vill söka efter, operatorn som du vill använda i frågan och värdet som du söker efter i fältet.</p> <p>Obs! Använd inte <code>username </code> i sökvillkoren. Om <code>username </code> inkluderas i en API-fråga till Workfront loggas användaren in i Workfront och sökningen kommer inte att lyckas.</p> <p>Obs! <code>In</code> och <code>NotIn</code>fungerar med arrayer. Indata ska vara i matrisformat.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i utdata för den här modulen.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Markera de referensfält som du vill ta med i sökningen.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Markera de samlingar som du vill lägga till i sökningen.</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search (Legacy)]**

>[!IMPORTANT]
>
>Den här modulen har ersatts med modulen Sök efter poster. Vi rekommenderar att du använder den modulen i nya scenarier.
>Befintliga scenarier som använder den här modulen fortsätter att fungera som förväntat. Den här modulen tas bort från modulväljaren i maj 2025.

Den här sökmodulen söker efter poster i ett objekt i Workfront som matchar den sökfråga du anger.

Du kan mappa den här informationen i efterföljande moduler i scenariot.

När du konfigurerar den här modulen visas följande fält.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>Instruktioner om hur du ansluter din Workfront-app till Workfront Fusion finns i <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Ansluta Workfront till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Välj den typ av Workfront-post som du vill att modulen ska söka efter.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Välj ett alternativ för att ange om du vill att modulen ska få det första resultatet som matchar dina sökvillkor eller alla resultat som matchar det.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria fields]</td> 
   <td> <p>Markera de fält som du vill använda som sökvillkor. Dessa fält är sedan tillgängliga i listrutan Sökvillkor.</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Ange fältet som du vill söka efter, operatorn som du vill använda i frågan och värdet som du söker efter i fältet.</p> <p>Obs! Använd inte <code>username </code> i sökvillkoren. Om <code>username </code> inkluderas i en API-fråga till Workfront loggas användaren in i Workfront och sökningen kommer inte att lyckas.</p> <p>Obs! <code>In</code> och <code>NotIn</code>fungerar med arrayer. Indata ska vara i matrisformat.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Markera de fält som du vill inkludera i utdata för den här modulen.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Markera de referensfält som du vill ta med i sökningen.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Markera de samlingar som du vill lägga till i sökningen.</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--not visible Jan 6, 2025

+++ **[!UICONTROL Search (Legacy)]**

This search module looks for records in an object in Workfront that match the search query you specify.

You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to search for.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Select an option to specify whether you want the module to get the first result that matches your search criteria or all the results that match it.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Select the fields that you want to include in the output for this module.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Select any reference fields that you want to include in the search.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Select any collections that you want to add to the search.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

+++-->

## Workfront objekttyper som är tillgängliga för varje Workfront-modul

<!-- [Object types available for each Workfront trigger module](#object-types-available-for-each-workfront-trigger-module) 
* [Object types available for each Workfront action module](#object-types-available-for-each-workfront-action-module) 
* [Object types available for each Workfront search module](#object-types-available-for-each-workfront-search-module)-->

+++**Objekttyper tillgängliga för varje Workfront-utlösarmodul**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col>         
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Watch Record]</th> 
   <th>[!UICONTROL Watch Field]</th> 
   <th>[!UICONTROL Watch Events]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Godkännandeprocess</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tilldelning</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Baslinje</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Faktureringspost </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Faktureringstakt</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Företag</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Kontrollpanel</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokument</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokumentmapp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Dokumentförfrågan</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Dokumentversion</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Utgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Utgiftstyp</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Grupp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Timme</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Timtyp</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problem</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Upprepning</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Jobbroll</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Journalpost</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Milstolpe</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Sökväg för milstolpe</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Anteckning</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Anteckningstagg</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portfolio</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Program</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Projekt</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Projektanvändare</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Bevis godkännande</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Reserverad tid* </td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Rapport</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>risk</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Risktyp</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Steggodkännare</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Uppgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Team</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Mall</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Malluppgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tidrapport</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Användare</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Uppdatera</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Objekttyper tillgängliga för varje Workfront-åtgärdsmodul**

>[!NOTE]
>
>Modulen [!UICONTROL Download Document] ingår inte i den här tabellen eftersom Workfront-objekttyper inte ingår i konfigurationen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Create a record]</th> 
   <th>[!UICONTROL Update a record]</th> 
   <th>[!UICONTROL Delete a record]</th> 
   <th>[!UICONTROL Upload Document]</th> 
   <th>[!UICONTROL Read a record]</th> 
   <th>[!UICONTROL Custom API Call]</th> 
   <th>[!UICONTROL Misc Action]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Godkännandeprocess</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tilldelning</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Baslinje</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
   <tr> 
   <td>Faktureringspost</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Faktureringstakt</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Företag</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokument</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokumentmapp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokumentversion</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Växelkurs</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Utgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Utgiftstyp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Externt dokument</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Grupp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Timme</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Timtyp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problem</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Upprepning</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Jobbroll</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Journalpost</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Milstolpe</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Sökväg för milstolpe</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Anteckning</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Anteckningstagg</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portfolio</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Program</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Projekt</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Projektanvändare</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Reserverad tid* </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>risk</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Risktyp</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Steggodkännare</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Uppgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Team</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Mall</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Malluppgift</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tidrapport</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Användare</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Uppdatera</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**Objekttyper tillgängliga för varje Workfront-sökmodul**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL Search]</th> 
   <th>[!UICONTROL Read Related Records]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>Godkännandeprocess</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Tilldelning</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Faktureringspost</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Faktureringstakt</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Företag</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokument</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokumentmapp</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Dokumentversion</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Utgift</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Utgiftstyp</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Grupp</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Timme</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Timtyp</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Problem</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Upprepning</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Jobbroll</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Journalpost</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Milstolpe</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Sökväg för milstolpe</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Anteckning</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Anteckningstagg</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Portfolio</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Program</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Projekt</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Projektanvändare</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Reserverad tid* </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>risk</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Risktyp</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Steggodkännare</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Uppgift</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Team</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Mall</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Malluppgift</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tidrapport</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Användare</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>Användardelegering</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

Vi rekommenderar att du kontrollerar att det här fungerar som du tänkt dig.

+++

## Evenemangsprenumerationsfilter i Workfront > [!UICONTROL Watch Events] moduler

>[!NOTE]
>
>Vi rekommenderar att du använder händelseprenumerationsfilter i dina [!UICONTROL Watch Events]-moduler.

Workfront [!UICONTROL Watch Events]-modulen utlöser scenarier baserat på en webkrok som skapar en händelseprenumeration i Workfront API. Händelseprenumerationen är en uppsättning data som avgör vilka händelser som skickas till webbkroken. Om du t.ex. har konfigurerat en [!UICONTROL Watch Events]-modul som bevakar problem, skickar händelseprenumerationen endast händelser som rör problem.

Genom att använda händelseprenumerationsfilter kan Fusion-användare skapa händelseprenumerationer som passar bättre för deras användningsfall. Du kan till exempel konfigurera en händelseprenumeration i Workfront API så att endast problem som finns i ett visst projekt skickas till webbhoven, vilket säkerställer att modulen [!UICONTROL Watch Events] bara aktiveras för problem i det projektet. Möjligheten att skapa smalare utlösare förbättrar scenariodesignen genom att minska antalet irrelevanta utlösare.

Detta skiljer sig från hur du ställer in ett filter i Workfront Fusion-scenariot. Utan ett händelseprenumerationsfilter får din webkrok alla händelser som hör till den objekttyp du väljer. De flesta av dessa händelser skulle vara irrelevanta för scenariot och måste filtreras bort innan scenariot kan fortsätta.

Följande operatorer är tillgängliga i Workfront > filtret Bevakningshändelser:

* Lika med
* Inte lika med
* Större än
* Mindre än
* Större än eller lika med
* Mindre än eller lika med
* Innehåller
* Finns
   * Den här operatorn kräver inget värde och värdefältet saknas.
* Finns inte
   * Den här operatorn kräver inget värde och värdefältet saknas.
* Ändrad
   * Den här operatorn kräver inget värde och värdefältet saknas.
   * Den här operatorn ignorerar tillståndsfältet.
   * När du använder `Changed` väljer du **Endast uppdaterade händelser** i fältet **Postursprung**.

>[!IMPORTANT]
>
>Du kan inte redigera filter i befintliga Workfront-webbplatser. Om du vill ställa in olika filter för Workfront-händelseprenumerationer tar du bort den aktuella webbkroken och skapar en ny.

>[!INFO]
>
>**Exempel:** Överväg ett scenario som bearbetar nya problem som har tilldelats en viss användare, Ana.
>
>### Filtrera händelser med ett händelseprenumerationsfilter (rekommenderas)
>
>Med hjälp av händelsefiltret kan du ställa in webkroken för att utlösa scenariot när ett problem tilldelas Ana när problemet skapas. Ana har användar-ID b378489d8f7cd3cee0539260720a84b7.
>
>![Händelsefilter](/help/workfront-fusion/references/apps-and-modules/assets/event-filter-watch-events-350x277.png)
>
>Om 100 utgåvor skapas per dag, men bara två av dem tilldelas till Ana, körs scenariot två gånger.
>
>### Filtrera händelser i scenariot (rekommenderas inte)
>
>Om du vill filtrera händelser så att endast ärenden som tilldelats Ana behandlas, kan du skapa ett filter efter modulen [!UICONTROL Watch Events].
>
>![Utan händelsefilter](/help/workfront-fusion/references/apps-and-modules/assets/watch-events-non-event-filter-350x206.png)
>
>Om 100 utgåvor skapas per dag, men bara två av dem tilldelas till Ana, körs scenariot 100 gånger. 98 av körningarna stoppades vid filtret, men utlösarmodulen använder fortfarande data och utför åtgärder i alla körningar.

Mer information om Workfront-händelseprenumerationer finns i [Vanliga frågor och svar - Händelseprenumerationer](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-faq).

Mer information om webbhooks finns i [Direktutlösare (webbhooks) i Adobe Workfront Fusion](/help/workfront-fusion/references/modules/webhooks-reference.md)

Mer information om filter i scenarier finns i [Lägga till ett filter i ett scenario](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md).
