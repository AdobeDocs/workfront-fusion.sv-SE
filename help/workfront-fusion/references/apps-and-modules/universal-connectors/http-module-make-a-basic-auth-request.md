---
title: HTTP > Gör en grundläggande autentiseringsbegäran-modul
description: Adobe Workfront Fusion kräver en Adobe Workfront Fusion-licens förutom en Adobe Workfront-licens.
author: Becky
feature: Workfront Fusion
exl-id: e544768e-7023-473f-8d51-631b04183743
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# [!UICONTROL HTTP] > [!UICONTROL Make a Basic Authorization request]-modulen

Med den här [!DNL Adobe Workfront Fusion]-modulen kan du konfigurera en HTTP-begäran med grundläggande HTTP-auktorisering och skicka den till en server. Det mottagna HTTP-svaret finns sedan i utdatapaketet.

>[!NOTE]
>
>Om du ansluter till en Adobe-produkt som inte har någon dedikerad anslutning rekommenderar vi att du använder Adobe Authenticator-modulen.
>
>Mer information finns i [Adobe Authenticator-modulen](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md).

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

## [!UICONTROL HTTP] > [!UICONTROL Make a Basic Authorization request] modulkonfiguration

När du konfigurerar modulen [!UICONTROL HTTP] > [!UICONTROL Make a Basic Authorization request] visar [!DNL Adobe Workfront Fusion] fälten som listas nedan. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan i [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Credentials]</td> 
   <td> <p>Välj nyckeln som innehåller dina grundläggande autentiseringsuppgifter eller klicka på <strong>[!UICONTROL Add]</strong> om du vill lägga till dina autentiseringsuppgifter i en ny nyckel. </p> <p>Obs! Du kan lägga till fler autentiseringsuppgifter för att enkelt växla mellan olika anslutningar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx )] </td> 
   <td> <p>Använd det här alternativet om du vill konfigurera felhantering.</p> <p>Mer information finns i <a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">Felhantering</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>Ange den URL som du vill skicka en begäran till, t.ex. en API-slutpunkt, webbplats osv.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt. Exempel: <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> Ange önskade nyckelvärdepar för frågan.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Body type]</p> </td> 
   <td> <p>HTTP-brödtexten är de databyte som skickas i ett HTTP-transaktionsmeddelande omedelbart efter rubrikerna om något ska användas.</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>Raw-brödtexttypen är vanligtvis lämplig för de flesta HTTP-innehållsbegäranden, även i situationer där utvecklardokumentationen inte anger vilka data som ska skickas.</p> <p>Ange en form av tolkning av data i fältet [!UICONTROL Content type].</p> <p>Trots att innehållstypen är vald, anges data i vilket format som helst som anges eller krävs av utvecklardokumentationen.</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>Den här brödtypen är till [!UICONTROL POST] data med <code>application/x-www-form-urlencoded</code>.</p> <p>För <code>[!UICONTROL application/x-www-form-urlencoded]</code> är brödtexten i HTTP-meddelandet som skickas till servern i princip en frågesträng. Nycklarna och värdena kodas i nyckelvärdepar avgränsade med <code>&amp;</code> och med en <code>=</code> mellan nyckeln och värdet. </p> <p>Använd <code>[!UICONTROL multipart/form-data]</code> i stället för binära data.</p> <p>För varje nyckelvärdepar som du vill lägga till klickar du i fältet Fält på <b>Lägg till objekt</b> och anger nyckel och värde.</p>
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>Exempel: </b></span></span> 
       <p>Exempel på det resulterande formatet för HTTP-begäran:</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>[!UICONTROL Multipart/form-data] är en HTTP-multipart-begäran som används för att skicka filer och data. Det används ofta för att överföra filer till servern.</p> <p>Lägg till fält som ska skickas i begäran. Varje fält måste innehålla nyckelvärdepar.</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>Ange nyckeln och värdet som ska skickas i begärandetexten.</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>Ange nyckeln och ange den källfil som du vill skicka i begärandetexten. Välj en källfil från en tidigare modul eller mappa filens namn och data.</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill analysera svar automatiskt och konvertera JSON- och XML-svar så att du inte behöver använda [!UICONTROL JSON] &gt; [!UICONTROL Parse JSON] eller [!UICONTROL XML] &gt; [!UICONTROL Parse XML]-moduler.</p> <p>Innan du kan använda tolkat JSON- eller XML-innehåll kör du modulen en gång manuellt, så att modulen kan identifiera svarsinnehållet och mappa det i efterföljande moduler.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>Ange timeout för begäran i sekunder (1-300). Standardvärdet är 40 sekunder.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> Aktivera det här alternativet om du vill dela cookies från servern med alla HTTP-moduler i ditt scenario.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>Så här lägger du till ett självsignerat certifikat:</p>
          <ol>
            <li value="1">
              <p>Klicka på <b>[!UICONTROL Extract]</b>.</p>
            </li>
            <li value="2">
              <p>Välj vilken typ av fil du extraherar.</p>
            </li>
            <li value="3">
              <p>Markera filen som innehåller certifikatet eller certifikatet.</p>
            </li>
            <li value="4">
              <p>Ange lösenordet för filen.</p>
            </li>
            <li value="5">
              <p>Klicka på <b>[!UICONTROL Save]</b> för att extrahera filen och återgå till modulinställningarna.</p>
            </li>
          </ol>
</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reject connections that are using unverified (self-signed) certificates] </td> 
   <td> <p>Aktivera det här alternativet om du vill avvisa anslutningar som använder overifierade TLS-certifikat.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow redirect]</td> 
   <td> <p> Aktivera det här alternativet om du vill följa URL-omdirigeringarna med 3xx-svar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow all redirects] </td> 
   <td> <p>Aktivera det här alternativet om du vill följa URL-omdirigeringarna med alla svarskoder.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Disable serialization of multiple same query string keys as arrays]</p> </td> 
   <td> <p>Som standard hanterar [!DNL Workfront Fusion] flera värden för samma URL-frågesträngsparameternyckel som matriser. <code>www.test.com?foo=bar&amp;foo=baz</code> konverteras till exempel till <code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>. Aktivera det här alternativet om du vill inaktivera funktionen. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> Aktivera det här alternativet om du vill begära en komprimerad version av webbplatsen.</p> <p>Lägger till ett <code>[!UICONTROL Accept-Encoding]</code>-huvud för att begära komprimerat innehåll.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>Aktivera det här alternativet om du vill använda ömsesidig TLS i HTTP-begäran.</p> <p>Mer information om ömsesidigt TLS finns i <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">Använd ömsesidigt TLS i HTTP-moduler</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>
