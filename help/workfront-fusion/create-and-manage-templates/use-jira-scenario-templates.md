---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: Använd mallar för att ansluta Adobe Workfront Fusion och Jira
description: Använd dessa mallar för att automatisera arbetsflöden mellan Adobe Workfront Fusion och Jira.
author: Becky
feature: Workfront Fusion
source-git-commit: 4ede5c7a75725a6540d6a8ff9cd056e6147d5c55
workflow-type: tm+mt
source-wordcount: '4171'
ht-degree: 0%

---

# Använd mallar för att ansluta Adobe Workfront Fusion och Jira

Adobe workfront Fusion innehåller mallar som kan automatisera vanliga arbetsflöden mellan Fusion och Jira.

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
   <p>Workfront: Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</p><p>Jira: Du måste ha en licens för Jira Cloud</p>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">Konfigurationer på åtkomstnivå</td> 
   <td> <p>Workfront: behörighet att skapa användare, anpassade formulär och anpassade fält.</p> <p>Jira: behörighet att skapa användare och anpassade fält samt att ändra skärmar och webbböcker.</td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Förutsättningar

### Workfront

* Du måste ha ett tekniskt konto på Adobe Developer Console.

  Mer information och instruktioner finns i [Konfiguration av tekniskt konto](https://developer.adobe.com/cloud-storage/guides/getting-started/technical-account-setup) i Adobe-dokumentationen.
* Du måste använda systemadministratörsbehörighet för det tekniska kontot i området Adobe Admin Console produktprofiler.

  Mer information och instruktioner finns i [Skapa systemadministratörer i Workfront med Adobe Admin Console](https://experienceleague.adobe.com/sv/docs/workfront/using/administration-and-setup/add-users/create-manage-users/admin-console#create-system-administrators-in-workfront-with-the-adobe-admin-console)

### Jira

Om du använder OAuth2-auktorisering för Jira (rekommenderas) måste du konfigurera ett OAuth2-program på [https://developer.atlassian.com/console](https://developer.atlassian.com/console). Mer information och instruktioner finns i [Skapa en OAuth2-anslutning till Jira](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#create-an-oauth2-connection-to-jira) i Jira-artikelmodulerna.

<!--

When configuring this application, you will need the following scopes:

* `read:jira-work` 
* `read:jira-user`
* `write:jira-work`

-->

## Antaganden

Dessa moduler förutsätter följande:

* Workfront är källan till sanning i det övergripande marknadsföringskampanjprojektet
* Jira används av tekniska team, vilket ingår i ett projekt som började i Workfront.
* Alla Jira-användare har inte tillgång till Workfront eller vice versa.
* Workfront och Jira ligger i molnet.

## Datamodell (fältmappningar)


| Workfront | Jira | Riktning | Anteckningar |
|---|---|---|---|
| ObjId | WF ID * | WF → Jira | Vid skapande av Jira-problem |
| Jira-tangenten * | Problemnyckel | Jira → WF | Vid skapande av Jira-problem |
| Jira URL * | – | Jira → WF | Användare klickbar länk i WF till Jira |
| – | WF-länk * | WF → Jira | Länk som kan klickas av användaren i Jira till WF |
| Namn | Sammanfattning | WF → Jira |  |
| Beskrivning | Beskrivning | WF → Jira |  |
| Status | WF-status | WF → Jira | WF-status |
| Jira-status * | Status | Jira → WF | Jira-status |
| Planerat slutförandedatum | Förfallodatum | WF → Jira | Planerat slutförandedatum |
| Anteckningar | Kommentar | WF ↔ Jira | Dubbelriktad kopia |
| Dokument | Bilaga | WF → Jira | Som bilagor när utgåvor skapas och kommentarer om nya dokument efter att de skapats. |

\* Dessa fält är konfigurerade som en del av den här integrationsinställningen. Instruktioner finns i [Konfigurera nödvändiga komponenter i Workfront, Jira och Workfront Fusion](/help/workfront-fusion/create-and-manage-templates/use-jira-scenario-templates.md#configure-prerequisites-in-workfront-jira-and-workfront-fusion).

## Konfigurera förutsättningar i Workfront, Jira och Workfront Fusion

Om du vill använda Jira-integrationsmallar måste du utföra följande konfigurationer:

* [Konfigurera Jira](#configure-jira)
* [Konfigurera Workfront](#configure-workfront)
* [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion)

### Konfigurera Jira

Om du vill använda dessa moduler måste följande skapas i Jira:

* En systemintegreringsanvändare
* Tre specifika anpassade fält

#### Skapa en systemintegreringsanvändare i Jira

1. I Jira skapar du en specifik användare som heter Systemintegreringsanvändare. Den här användaren bör endast användas av Workfront Fusion och bör inte representera en mänsklig användare. Den här användarens autentiseringsuppgifter används av Workfront Fusion-anslutningar.

#### Skapa nödvändiga anpassade fält i Jira

Den här integreringen förväntar sig tre specifika fält i det Jira-konto som den ansluter till. Utan dessa fält kommer integreringen att misslyckas

1. I Jira går du till **Inställningar** (kugghjulsikon) och väljer **Arbetsobjekt**.
1. Välj **Anpassade fält** i den vänstra navigeringen.
1. Klicka på **Skapa anpassat fält i skärmens övre högra hörn.**
1. Skapa följande fält:

   | Fältnamn | Fälttyp |
   |---|---|
   | WF ID | Textfält (en rad) |
   | WF-status | Textfält (en rad) |
   | WF-länk | URL-fält |

   Mer information om hur du skapar länkar i Jira finns i Jiras dokumentation om att skapa fält.
1. Lägg till de nya fälten på skärmen som är kopplad till ditt Jira-projekt.

   Mer information om skärmar i Jira finns i Jiras dokumentation om hur du ställer in skärmar för arbetsobjekt.


### Konfigurera Workfront

Om du vill använda dessa moduler måste följande skapas i Workfront:

* En systemintegreringsanvändare
* Ett eget formulär

#### Skapa en systemintegreringsanvändare i Workfront

1. Skapa en systemintegreringsanvändare i Workfront. Den här användaren används endast av Workfront Fusion och representerar inte en mänsklig användare. Aktiviteter som tilldelats den här användaren utlöser scenariot som synkroniserar Workfront med Jira.

   Instruktioner finns i [Lägga till användare](https://experienceleague.adobe.com/sv/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) i Workfront-dokumentationen.

#### Skapa ett anpassat formulär i Workfront

1. Börja skapa ett anpassat formulär i Workfront.

   Instruktioner finns i [Skapa ett anpassat formulär](https://experienceleague.adobe.com/sv/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) i Workfront-dokumentationen.
1. Namnge formuläret **JIRA-fält**.
1. Inkludera följande fält i det anpassade formuläret:

| Fältnamn | Fälttyp |
|---|---|
| Jira-tangenten | Enkelradigt textfält |
| Jira URL | Enkelradigt textfält |
| Jira-status | Enkelradigt textfält |

1. Lägg till ytterligare fält som du vill mappa mellan Jira och Workfront.
1. Spara det anpassade formuläret.

>[!NOTE]
>
>Vi rekommenderar att du begränsar det här formuläret från att redigeras av andra användare. Du kan uppnå detta genom att se till att alla användare som läggs till i det anpassade formuläret bara har åtkomst till Visa.
>
>Instruktioner finns i [Dela ett anpassat formulär](https://experienceleague.adobe.com/sv/docs/workfront/using/administration-and-setup/customize/custom-forms/manage-custom-forms/share-access-to-a-custom-form) i Workfront-dokumentationen.

### Konfigurera anslutningar i Workfront Fusion

Du måste ha skapat systemintegreringsanvändarna i Jira och Workfront innan du kan skapa anslutningar.

När du skapar de här anslutningarna måste du se till att använda autentiseringsuppgifterna för de systemintegreringsanvändare som har skapats.

Om du vill kan du skapa de här anslutningarna som en del av konfigurationen av mallarna.

* Instruktioner om hur du skapar en anslutning till Workfront finns i [Ansluta Workfront till Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#connect-workfront-to-workfront-fusion) i artikeln Workfront-moduler.
* Instruktioner om hur du skapar en anslutning till Jira finns i [Ansluta Jira till Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) i artikeln Jira Software modules.


## Scenarier

Åtta färdiga mallar för Jira hjälper till att replikera vanliga arbetsflöden och snabba upp implementeringen. Mallarna är helt anpassningsbara för att uppfylla specifika affärsbehov och kan utökas i takt med att behoven utvecklas.

Du behöver inte implementera alla scenarier. Den minimala implementeringen skulle kräva scenario 1, som skulle skapa en integrering i en riktning till ett JIRA-problem från ett uppdrag i Workfront.  Du kan lägga till ytterligare scenarier för att lägga till robusthet och mer dubbelriktad sammankoppling mellan Workfront och JIRA.  Du kan också skapa ytterligare scenarier för att hantera exempelvis projekt-till-episk integrering eller JIRA-problem för Workfront-problem eller uppgifter.

All användning av de här mallarna eller tilläggen av mallarna betraktas som anpassad konfiguration och vi rekommenderar att du använder Adobe Professional Services eller en Adobe-partner för support och implementering.

* **[Workfront till Jira: Skapa JIRA-problem från Workfront-aktivitet eller -problemtilldelning](#scenario-1-workfront-to-jira-create-jira-issue-from-workfront-task-or-issue-assignment)**
* [JIRA till Workfront: JIRA till Workfront: Skicka uppdateringar om problem och kommentarer tillbaka till Workfront från Jira](#scenario-2-jira-to-workfront-send-updates-on-issues-and-comments-back-to-workfront-from-jira)
* [Workfront till Jira: Ändringar i Workfront uppgift till JIRA-problem](#scenario-3-workfront-to-jira-changes-to-workfront-task-to-jira-issue)
* [Workfront till Jira: Ändringar i Workfront-utgåvan av JIRA-utgåvan](#scenario-4-workfront-to-jira-changes-to-workfront-issue-to-jira-issue)
* [Workfront till Jira: Skapa kommentar i JIRA när en ny anteckning om Workfront-aktivitet eller -problem](#scenario-5-workfront-to-jira-create-comment-in-jira-when-new-note-on-workfront-task-or-issue)
* [Workfront till Jira: Skapa kommentar i JIRA om borttagen anteckning om Workfront-aktivitet eller -problem](#scenario-6-workfront-to-jira-create-comment-in-jira-on-deleted-note-on-workfront-task-or-issue)
* [Workfront till Jira: Skapa kommentar i JIRA när ett nytt dokument om Workfront-aktivitet eller -problem skapas](#scenario-7-workfront-to-jira-create-comment-in-jira-when-new-document-on-workfront-task-or-issue)
* [Workfront till Jira: Skapa kommentar i JIRA om borttagna dokument om Workfront-aktivitet eller -problem](#scenario-8-workfront-to-jira-create-comment-in-jira-on-deleted-document-on-workfront-task-or-issue)

### Allmänna parametrar

Använd följande allmänna parametrar när du konfigurerar mallarna:

* **JiraBaseURL**: Bas-URL:en för Jira-instansen. Exempel: `https://myjira.atlassian.net/`
* **wfBaseURL**: Bas-URL:en för Workfront-instansen.  Vanligtvis: `https://<domain>.my.workfront.com` där `<domain>` är ditt speciella Workfront-domännamn.
* **defaultJIRAReporterID**: Det ID för användaren i JIRA som skapar problem. (Exempel: `557058:5aedf933-2312-40bc-b328-0c21314167f0`)
Du kan få detta ID genom att göra något av följande:
   * Klicka på användarens profil i JIRA och kontrollera URL:en i webbläsaren.
(Exempel `https://myjira.atlassian.net/jira/people/<JiraUserID>`)
   * Kör följande API-anrop på JIRA-instansen för att hämta ID:t för det specifika kontot i JIRA:
     `GET /rest/api/3/user/search?query=email@example.com`


### Scenario 1: Workfront till Jira: Skapa JIRA-problem från Workfront-aktivitet eller -tilldelning av utleveranser

Detta scenario skapar ett Jira-problem när en Workfront-aktivitet eller ett problem tilldelas systemintegreringsanvändaren. Scenariot fylls i fälten Sammanfattning, Beskrivning, Förfallodatum, WF-status och WF-ID. När problemet har skapats laddar det här scenariot även upp listan över bilagor och historiken över anteckningar som rör den ursprungliga uppgiften eller problemet i Workfront.

Om en Workfront-uppgift tilldelas är problemet i Jira en uppgift. Om ett Workfront-problem har tilldelats är Jira-problemet ett fel.

+++**Expandera om du vill visa instruktioner för hur du konfigurerar scenario 1:Workfront till Jira: Skapa JIRA-problem från Workfront-aktivitet eller -utleveranstilldelning**

#### Konfigurera utlösarmodulen

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Workfront till Jira: Skapa JIRA-problem från Workfront-aktiviteten eller mallen för utfärdandetilldelning**.

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. Välj den Workfront-anslutning som du skapade i [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion).
1. Välj **i fältet** Posttyp`Assignment`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder med alternativet **And**:

   | Fält | Operator | Värde |
   |---|---|---|
   | tilldelatToID | Lika med | (Ange Workfront-id:t för systemintegreringsanvändaren) |
   | AktivitetID | Finns |  |
   | projectID | Lika med | (Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på) |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj Endast ny post i fältet **Postens ursprung**.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. Fortsätt till [Anslut mallmoduler till Workfront och Jira](#connect-template-modules-to-workfront-and-jira)

#### Koppla mallmoduler till Workfront och Jira

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som du skapade i [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion) och klickar sedan på **OK** för att spara anslutningen till den modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Workfront-anslutning som du skapade i [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion) och klickar sedan på **OK** för att spara anslutningen till den modulen.
1. Fortsätt till [Uppdatera den allmänna parametermodulen](#update-the-general-parameters-module).

#### Uppdatera modulen Allmänna parametrar

1. Klicka på **Lägg till objekt** i den andra modulen i mallen (Ange miljöinformation) för var och en av följande variabler och ange variabelns namn och värde

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Ange ID:t för standardanvändaren när skaparanvändaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Ange bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Ange bas-URL:en för det Workfront-konto du ansluter till. |

1. Fortsätt till [Mappa anpassade fält i Jira](#map-custom-fields-in-jira)

<!--#### Map custom fields in Jira. 

Awaiting feedback-->

+++

### Scenario 2: JIRA till Workfront: Skicka uppdateringar om problem och kommentarer tillbaka till Workfront från Jira

Detta scenario skapar en Workfront-uppgift eller ett problem när ett problem skapas i Jira.

>[!NOTE]
>
>Det här scenariot kräver en OAuth2-anslutning för Jira.
>Om du vill använda OAuth2-auktorisering för Jira måste du konfigurera ett OAuth2-program på [https://developer.atlassian.com/console](https://developer.atlassian.com/console). Mer information och instruktioner finns i Jiras dokumentation.

+++**Expandera om du vill visa instruktioner för konfiguration av scenario 2: JIRA till Workfront: Skicka uppdateringar om problem och kommentarer tillbaka till Workfront från Jira**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på **Del 2: JIRA till Workfront: Skicka uppdateringar om problem och kommentarer tillbaka till Workfront från mallen Jira**.

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. Välj en anslutning som använder inloggningsuppgifterna för systemintegreringsanvändaren eller skapa en anslutning till Jira med inloggningsuppgifterna för systemintegrering.

* Instruktioner om hur du skapar en anslutning till Jira finns i [Ansluta Jira till Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion) i artikeln Jira Software modules.

1. Konfigurera webkrok-filtret

1. Fortsätt till [Konfigurera en webkrok i Jira](#configure-a-webhook-in-jira)

#### Konfigurera en webkrok i Jira

1. I Jira, skapa en webkrok.

   Instruktioner finns i [Webhooks](https://developer.atlassian.com/server/jira/platform/webhooks/) i Jiras dokumentation.

1. Använd följande värden när du konfigurerar webkroken:

   * **JQL**: project = &quot;yourProjectName&quot; (där yourProjectName = JIRA-projektets namn)
   * **Utgåva**: skapad, uppdaterad
   * **Kommentar**: har skapats, tagits bort


1. Fortsätt till [Anslut mallmoduler till Workfront och Jira (modul 2)](#connect-template-modules-to-workfront-and-jira-module-2)

#### Koppla mallmoduler till Workfront och Jira (modul 2)

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som du skapade i [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion) och klickar sedan på **OK** för att spara anslutningen till den modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Workfront-anslutning som du skapade i [Konfigurera anslutningar i Workfront Fusion](#configure-connections-in-workfront-fusion) och klickar sedan på **OK** för att spara anslutningen till den modulen.
   <!--#### Map custom fields-->

+++

### Scenario 3: Workfront till Jira: Ändringar i Workfront-aktiviteten till JIRA-problemet

+++**Expandera för att visa instruktioner om hur du konfigurerar scenario 3: WF-to-Jira-ändringar (uppgifter)**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Del 3: Workfront till Jira: Ändringar i Workfront-aktiviteten till mallen för JIRA-problem**.

   En vy av mallen öppnas med information och en animering av dataflödet.

1. Klicka på mallen för att öppna redigeraren.
1. Välj den organisation och det team som ska äga det här scenariot.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Task`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder med alternativet **And**:

   | Fält | Operator | Värde |
   |---|---|---|
   | tilldelatToID | Lika med | Ange Workfront-ID för systemintegreringsanvändaren |
   | projectID | Lika med | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |
   | DE: Jira Key | Finns |  |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`Updated record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. Ange följande variabler i modulen **Ange JIRA-variabler** och klicka sedan på **OK** för att spara modulen.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.

+++

### Scenario 4: Workfront till Jira: Ändringar i Workfront-utgåvan av JIRA-utgåvan

Det här scenariot skickar uppdateringar från Workfront-utgåvor till tidigare anslutna JIRA-utgåvor.

+++**Expandera om du vill visa instruktioner för hur du konfigurerar scenario 4: Workfront till Jira: Ändringar i Workfront-utgåvan av JIRA-problemet**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Scenario 4: WF-to-Jira Changes (Issues)** .

   En vy av mallen öppnas med information och en animering av dataflödet.

1. Klicka på mallen för att öppna redigeraren.
1. Välj den organisation och det team som ska äga det här scenariot.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Issues`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder med alternativet **And**:

   | Fält | Operator | Värde |
   |---|---|---|
   | tilldelatToID | Lika med | Ange Workfront-ID för systemintegreringsanvändaren |
   | projectID | Lika med | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |
   | DE: Jira Key | Finns |  |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`Updated record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. Ange följande variabler i modulen **Ange JIRA-variabler** och klicka sedan på **OK** för att spara modulen.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.

+++

### Scenario 5: Workfront till Jira: Skapa kommentar i JIRA när en ny anteckning om Workfront aktivitet eller problem

+++**Expandera om du vill visa instruktioner för att konfigurera scenario 5: Workfront till Jira: Skapa kommentar i JIRA när en ny anteckning om Workfront-aktivitet eller -problem**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Scenario 5: WF-to-Jira New notes (Tasks and Issues)** .

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Note`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder:

   | Fält | Operator | Värde |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |
   | ELLER |  |  |
   | projectID<br>AND<br>OpTaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`New record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. Ange följande variabler i modulen **Ange variabler** och klicka sedan på **OK** för att spara modulen.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.

+++

### Scenario 6: Workfront till Jira: Skapa kommentar i JIRA om borttagen anteckning om Workfront-aktivitet eller -problem

+++**Expandera om du vill visa instruktioner för hur du konfigurerar scenario 6: Workfront till Jira: Skapa kommentar i JIRA för borttagen anteckning om Workfront-aktivitet eller -problem**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Scenario 6: WF-to-Jira Remove notes (Tasks and Issues)** .

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Note`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder:

   | Fält | Operator | Värde |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |
   | ELLER |  |  |
   | projectID<br>AND<br>OpTaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`Deleted record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. Ange följande variabler i den andra modulen och klicka sedan på **OK** för att spara modulen.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.

+++

### Scenario 7: Workfront till Jira: Skapa kommentar i JIRA när ett nytt dokument om Workfront-aktivitet eller -problem

+++**Expandera om du vill visa instruktioner för att konfigurera scenario 7: Workfront till Jira: Skapa kommentar i JIRA när ett nytt dokument om Workfront-aktivitet eller -problem**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Scenario 7: WF-to-Jira New Attachments (Tasks and Issues)** .

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Document`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder med alternativet **And**:

   | Fält | Operator | Värde |
   |---|---|---|
   | tilldelatToID | Lika med | Ange Workfront-ID för systemintegreringsanvändaren |
   | projectID | Lika med | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |

1. Ange följande variabler i den andra modulen.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`New record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.

+++

### Scenario 8: Workfront till Jira: Skapa kommentar i JIRA om borttagna dokument om Workfront-aktivitet eller -problem

+++**Expandera om du vill visa instruktioner för att konfigurera scenario 8: Workfront till Jira: Skapa kommentar i JIRA för borttagna dokument för Workfront-uppgift eller -problem**

1. Klicka på ikonen **Mallar** ![Mallar](assets/templates-icon.png) i den vänstra navigeringspanelen.
1. Sök efter mallen med hjälp av sökfältet i skärmens övre vänstra hörn. Du kan söka efter mallnamn eller inkluderade program.
1. Klicka på mallen **Scenario 8: WF-to-Jira Remove Attachments (Tasks and Issues)** .

   En vy av mallen öppnas med information och en animering av dataflödet.
1. Börja lägga till en webkrok i den första modulen.
1. I anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering.
1. Välj **i fältet** Posttyp`Document`.
1. Välj **i fältet** Läge`New state`.
1. Konfigurera filtret med följande åtgärder:

   | Fält | Operator | Värde |
   |---|---|---|
   | projectID<br>AND<br>TaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |
   | ELLER |  |  |
   | projectID<br>AND<br>OpTaskID | Lika med <br><br>finns | Ange ID:t för det eller de projekt som du vill att webbkroken ska titta på. |

1. Ange följande variabler i modulen **Ange variabler**.

   | Variabelnamn | Variabelvärde |
   |---|---|
   | defaultJiraReporterID | Detta är standardanvändarens ID när den som skapade användaren inte finns i Jira. Du kan hitta detta användar-ID genom att klicka på användarens profil och kontrollera webbläsarens URL. Exempel: `https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | Bas-URL:en för det Jira-konto som du ansluter till. |
   | wfBaseURL | Bas-URL:en för det Workfront-konto du ansluter till. |

1. Aktivera alternativet **Uteslut uppdateringar som gjorts av anslutningen**.
1. Välj **i fältet** Postens ursprung`Deleted record only`.
1. Klicka på **Spara** för att spara webkroken och klicka sedan på **OK** för att spara utlösarmodulen.
1. I **each** Workfront-modulen i anslutningsfältet väljer du den Workfront-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.
1. I **each** Jira-modulen i anslutningsfältet väljer du den Jira-anslutning som använder inloggningsuppgifterna för systemintegrering och klickar sedan på **OK** för att spara modulen.


+++

