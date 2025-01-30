---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: Skapa ett grundläggande scenario
description: Lär dig skapa ett enkelt automatiseringsscenario med Adobe Workfront Fusion. Automatiseringsscenarier automatiserar Workfront-processer, inklusive datamanipulering och -omvandling. Det här exemplet tar dig genom processen att skapa ett scenario som söker efter en [!DNL Workfront] aktivitet i Workfront och konverterar den till ett projekt.
author: Becky
feature: Workfront Fusion
exl-id: 5284dee1-e890-4357-a28d-29e09ac02822
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 0%

---

# Skapa ett grundläggande scenario

Rollen för [!DNL Adobe Workfront Fusion] är att automatisera dina processer så att du kan koncentrera dig på nya uppgifter i stället för att upprepa samma uppgifter om och om igen. Det fungerar genom att länka åtgärder inom och mellan program och tjänster för att skapa ett scenario som överför och omvandlar data automatiskt. Scenariot du skapar letar efter data i en app eller tjänst och bearbetar data för att ge det resultat du vill ha.

I det här exemplet går du igenom processen att skapa ett scenario som söker efter en begäran i Workfront och konverterar den till ett projekt.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] licens</td> 
   <td> <p>Nytt: [!UICONTROL Standard]</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] licens**</td> 
   <td>
   <p>Aktuell: Inga [!DNL Workfront Fusion]-licenskrav.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] [!DNL Workfront]: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</li><li>[!UICONTROL Ultimate] [!DNL Workfront] plan: [!DNL Workfront Fusion] ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa [!DNL Adobe Workfront Fusion].</p>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

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

1. Välj **[!DNL Adobe Workfront]**. Om sökfältet inte visas klickar du på sökfältet längst ned i listan, skriver&quot;Workfront&quot; och markerar det när det visas i listan.

   Listan ändras till att visa alla [!DNL Workfront] moduler som du kan använda.

1. Klicka på modulen **[!UICONTROL Search]**.

   Modulkonfigurationsfönstret öppnas.

1. I rutan [!UICONTROL Connection] väljer du din Workfront-anslutning.

   Om du inte har någon Workfront-anslutning kan du läsa [Skapa en anslutning](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)
1. Välj **[!UICONTROL Issue]** i rutan [!UICONTROL Record Type]. Detta anger att modulen endast ska söka efter problem, som omfattar förfrågningar.

   Du kan hitta **[!UICONTROL Issue]** i listan om du börjar skriva ordet [!UICONTROL Issue].

1. Välj **[!UICONTROL First Matching Record]** i rutan **[!UICONTROL Result Set]**.

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

   Namnet visas precis nedanför modulen. Under det finns en kort beskrivning av den typ av åtgärd som har utförts av modulen i [!DNL Workfront Fusion].

   ![Modulen har bytt namn](assets/module-renamed-wf.png)

1. Fortsätt med [Lägg till och konfigurera den andra modulen](#add-and-configure-the-second-module).

## Lägg till och konfigurera den andra modulen

1. Håll pekaren över den partiella cirkeln till höger om modulen och klicka sedan på **[!UICONTROL Add another module]**.
1. Välj [!DNL Adobe Workfront] i listan med program och välj sedan modulen **[!UICONTROL Convert object]**.
1. I fältet [!UICONTROL Connection] väljer du samma Workfront-anslutning som du använde i den tidigare modulen.
1. I fältet **[!UICONTROL Record type]** väljer du **[!UICONTROL issue]** eftersom modulen kommer att konvertera ett problem.
1. Välj **Projekt** i fältet **[!UICONTROL Convert to]**.
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

1. I [!DNL Workfront Fusion] klickar du på **[!UICONTROL Save]** i det nedre vänstra hörnet för att spara förloppet för scenariot.

   >[!IMPORTANT]
   >
   >Spara ofta när du finslipar ett scenario.

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
>     När du har lagt till en anteckning i ett scenario visas en orange punkt på **[!UICONTROL Notes]**-ikonen ![Anteckningsikonen med en punkt ](assets/notes-icon-w-dot.png) längst ned i scenarioredigeraren.
>
>1. Klicka på ikonen **[!UICONTROL Notes]** ![Anteckningar med punkt ](assets/notes-icon-w-dot.png) om du vill visa anteckningarna.
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
