---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Skapa ett grundläggande scenario
description: Lär dig skapa ett enkelt automatiseringsscenario med Adobe Workfront Fusion. Automatiseringsscenarier automatiserar Workfront-processer, inklusive datamanipulering och -omvandling. I det här exemplet går du igenom processen att skapa ett scenario som söker efter en Workfront-uppgift i Workfront och konverterar den till ett projekt.
author: Becky
feature: Workfront Fusion
exl-id: 5284dee1-e890-4357-a28d-29e09ac02822
source-git-commit: 6269db7454a63e80de3d770ab1012162d5080565
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 0%

---

# Skapa ett grundläggande scenario

Adobe Workfront Fusions roll är att automatisera processerna så att ni kan koncentrera er på nya uppgifter istället för att upprepa samma uppgifter om och om igen. Det fungerar genom att länka åtgärder inom och mellan program och tjänster för att skapa ett scenario som överför och omvandlar data automatiskt. Scenariot du skapar letar efter data i en app eller tjänst och bearbetar data för att ge det resultat du vill ha.

I det här exemplet går du igenom processen att skapa ett scenario som söker efter en begäran i Workfront och konverterar den till ett projekt.

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

## Skapa ett övningsscenario

### Börja skapa scenariot

1. Klicka på **Skapa ett nytt scenario** i området **Scenarier**.

   Information om hur du hittar scenområdet finns i [Navigera i Workfront Fusion](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/navigate-workfront-fusion.md).

   Scenarioredigeraren visas och innehåller en tom modul i mitten.

1. Markera platshållarnamnet **[!UICONTROL New scenario]** i det övre vänstra hörnet och ange sedan ett namn.
1. Fortsätt med [Lägg till och konfigurera den första modulen](#add-and-configure-the-first-module).

### Lägg till och konfigurera den första modulen

1. Klicka på den tomma modulen för att välja det program du vill välja en modul från.

   En lista över program visas till höger om modulen.

1. Välj **Adobe Workfront**. Om sökfältet inte visas klickar du på sökfältet längst ned i listan, skriver&quot;Workfront&quot; och markerar det när det visas i listan.

   Listan ändras och visar alla Workfront-moduler som du kan använda.

1. Klicka på modulen **[!UICONTROL Search]**.

   Modulkonfigurationsfönstret öppnas.

1. I rutan [!UICONTROL Connection] väljer du din Workfront-anslutning.

   Om du inte har någon Workfront-anslutning kan du läsa [Skapa en anslutning](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)
1. Välj [!UICONTROL Record Type] i rutan **[!UICONTROL Issue]**. Detta anger att modulen endast ska söka efter problem, som omfattar förfrågningar.

   Du kan hitta **[!UICONTROL Issue]** i listan om du börjar skriva ordet [!UICONTROL Issue].

1. Välj **[!UICONTROL Result Set]** i rutan **[!UICONTROL First Matching Record]**.

   Detta ställer in modulen så att endast den första posten som uppfyller villkoren returneras.
1. Konfigurera villkoren i området **[!UICONTROL Search criteria]** för att returnera den specifika aktiviteten.

   1. I den första rutan under [!UICONTROL Search Criteria] markerar du det fält som du vill ta med i sökningen. I det här exemplet väljer du **[!UICONTROL Name]**.

      Du kan hitta **[!UICONTROL Name]** i listan om du börjar skriva ordet [!UICONTROL name].
   1. För operatorn klickar du på listrutepilen bredvid **Exist** och ändrar den till [!UICONTROL **Innehåller (skiftlägesokänslig)**].

      Detta gör att modulen kan hitta projekt med de valda orden i namnet, även om du inte anger hela namnet eller anger namnet med fel skiftläge (till exempel versaler).
   1. I det sista fältet under [!UICONTROL Search Criteria] anger du ett ord eller en fras som du vet finns i namnet på den uppgift du söker efter.

1. I listan **[!UICONTROL Outputs]** markerar du de fält som du vill att modulen ska visa. I det här exemplet väljer du fälten **[!UICONTROL ID]** och **[!UICONTROL Name]**.

   >[!TIP]
   >
   >Du kan använda **Cmd+F** ([!DNL Mac] OS) eller **Ctrl-F** ([!DNL Windows] OS) för att snabbt hitta ett fält.

1. Klicka på **[!UICONTROL OK]** för att spara modulkonfigurationen.

1. Högerklicka på modulen, klicka på **[!UICONTROL Rename]**, skriv ett namn som beskriver vad du vill att modulen ska göra (till exempel&quot;Sök efter begäranden&quot;) och klicka sedan på **[!UICONTROL OK]**.

   Namnet visas precis nedanför modulen. Nedan finns en kort beskrivning av vilken typ av åtgärd som utförts i modulen i Workfront Fusion.

   ![Modulen har bytt namn](assets/module-renamed-wf.png)

1. Fortsätt med [Lägg till och konfigurera den andra modulen](#add-and-configure-the-second-module).

## Lägg till och konfigurera den andra modulen

1. Håll pekaren över den partiella cirkeln till höger om modulen och klicka sedan på **[!UICONTROL Add another module]**.
1. Välj Adobe Workfront i listan över program och välj sedan modulen **[!UICONTROL Convert object]**.
1. I fältet [!UICONTROL Connection] väljer du samma Workfront-anslutning som du använde i den tidigare modulen.
1. I fältet **[!UICONTROL Record type]** väljer du **[!UICONTROL issue]** eftersom modulen kommer att konvertera ett problem.
1. Välj **[!UICONTROL Convert to]** Projekt **i fältet**.
1. Klicka på mappningsväxeln bredvid fältet Aktivitets-ID för att aktivera det.

   Växeln blir blå när den är aktiverad. Detta gör att du kan mappa uppgifts-ID:t från föregående modul.

   ![Växla karta](assets/map-toggle.png)
1. Klicka på fältet **[!UICONTROL Task ID]**.

   En panel öppnas där du kan välja vad som ska användas som ID för uppgiften som du vill konvertera till ett projekt. Eftersom du har aktiverat mappning innehåller panelen utdata från tidigare moduler. Du har valt ID som utdata från föregående modul, så det är nu tillgängligt på panelen.

   Panelen kallas för mappningspanelen. Mer information om mappningspanelen finns i [Mappningsöversikt](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md).
1. Välj **ID** på mappningspanelen.

   Ett ID-block visas i ID-fältet. Här visas numret på den modul som modulen mappas från och fältet som mappas.

   ![Mappnings-ID](assets/map-id.png)

1. Klicka på fältet **Mall-ID**, börja skriva namnet på den Workfront-mall som du vill använda för det här projektet och markera den när den visas i listan.
1. Klicka på **[!UICONTROL OK]** för att spara modulkonfigurationen.

1. Högerklicka på modulen, klicka på **[!UICONTROL Rename]**, skriv ett namn som beskriver vad du vill att modulen ska göra (till exempel&quot;Konvertera till projekt&quot;) och klicka sedan på **[!UICONTROL OK]**.

1. Fortsätt till [Testa scenariot](#test-the-scenario).

## Testa scenariot

Innan du aktiverar ditt scenario är det viktigt att du testar det genom att köra det minst en gång och visa resultatet. Detta hjälper er att förstå hur data flödar genom scenariot och hitta eventuella fel.

I det här scenariot skulle ett lyckat test resultera i att begäran lokaliseras och konverteras till ett projekt.

1. Klicka på **[!UICONTROL Run once]** i det nedre vänstra hörnet i scenarioredigeraren.
1. När scenariot är klart klickar du på bubblan ovanför den första modulen för att visa information om det datapaket som modulen har bearbetat, inklusive data som hämtats från den begäran som modulen returnerade.

1. Klicka på exekveringspanelen ovanför den andra modulen för att visa indata (begäran) och utdata (det konverterade projektet).

   Mer information om data i inspektionsbubblorna finns i:

   * Allmän information finns i [Körningsflöde för scenario](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md).
   * Mer information om bearbetade paket finns i [Scenariokörning, cykler och faser](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md).

1. I Workfront Fusion klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.

   >[!IMPORTANT]
   >
   >Spara ofta när du finslipar ett scenario. Du kan behöva skapa ett nytt problem i ditt Workfront-konto för att utlösa scenariot.

>[!TIP]
>
>Vi rekommenderar den valfria men användbara metoden att lägga till anteckningar om varje modul.
>
>1. Högerklicka på en modul och välj sedan **[!UICONTROL Add a note]**.
>1. Skriv en översikt för modulen i anteckningen som visas.
>
>    Du kan lägga till flera anteckningar för en modul.
>
>1. Stäng området **[!UICONTROL Notes]**.
>
>     När du har lagt till en anteckning i ett scenario visas en punkt på ikonen **[!UICONTROL Notes]** ![Anteckningar med en punkt &#x200B;](assets/notes-icon-w-dot.png) längst ned i scenarioredigeraren.
>
>1. Klicka på ikonen **[!UICONTROL Notes]** ![Anteckningar med punkt &#x200B;](assets/notes-icon-w-dot.png) om du vill visa anteckningarna. När anteckningar är öppna visas en cirkel runt anteckningsikonen.
>

## Aktivera scenariot

Det sista steget i att skapa ett scenario är att aktivera det.

Eftersom det här scenariot söker efter ett specifikt problem behöver det inte aktiveras. När du aktiverar ett scenario körs det enligt ett schema eller när en viss åtgärd inträffar i ett program. När du har aktiverat ett scenario körs det som standard var 15:e minut. Du kan ändra detta genom att definiera när och hur ofta du vill att det ska köras.

Mer information om att aktivera scenarier finns i [Aktivera eller inaktivera ett scenario](/help/workfront-fusion/manage-scenarios/activate-deactivate-scenarios.md).

Mer information om scheman finns i [Schemalägg ett scenario](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md).

## Nästa steg

* [Lägg till en utlösarmodul](/help/workfront-fusion/build-practice-scenarios/add-a-webhook-to-basic-scenario.md) så att scenariot regelbundet kan söka efter nya begäranden och konvertera dem till projekt.
* [Lägg till en webkrok](/help/workfront-fusion/build-practice-scenarios/add-a-webhook-to-basic-scenario.md) så att scenariot kan köras varje gång en begäran anges.
* [Lägg till ett filter](/help/workfront-fusion/build-practice-scenarios/add-filter-basic-scenario.md) för att säkerställa att endast vissa begäranden konverteras till projekt.
* [Lägg till en funktion](/help/workfront-fusion/build-practice-scenarios/use-function-to-build-practice-scenario.md) som anpassar namnet på det nya projektet.
