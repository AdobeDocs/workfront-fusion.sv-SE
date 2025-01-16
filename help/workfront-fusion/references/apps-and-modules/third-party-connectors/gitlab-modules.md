---
title: GitLab-moduler
description: Adobe Workfront Fusion kräver en Adobe Workfront Fusion-licens förutom en Adobe Workfront-licens.
author: Becky
feature: Workfront Fusion
exl-id: fabbadce-5669-4363-834e-6d7428520f62
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '3554'
ht-degree: 0%

---

# [!UICONTROL GitLab] moduler

Adobe Workfront Fusion kräver en Adobe Workfront Fusion-licens förutom en Adobe Workfront-licens.

I ett [!DNL Adobe Workfront Fusion]-scenario kan du automatisera arbetsflöden som använder [!UICONTROL GitLab] samt ansluta det till flera tredjepartsprogram och -tjänster.

>[!NOTE]
>
>Den här artikeln förväntar sig viss kunskap om API-dokumentation och om funktionen [!DNL GitLab] i allmänhet.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

## Anslut [!DNL GitLab] till [!DNL Workfront Fusion] {#connect-gitlab-to-workfront-fusion}

1. Klicka på **[!UICONTROL Add]** bredvid anslutningsfältet i en [!DNL Workfront Fusion] [!DNL Gitlab]-modul.
1. Konfigurera följande fält:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td> <p>Ange ett namn för anslutningen.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL [!DNL GitLab] URL]</td> 
      <td>Ange URL:en för din [!DNL GitLab]-instans.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Access Token]</td> 
      <td><p>Ange din [!UICONTROL Private Token] eller [!UICONTROL Personal Access Token].</p><p>Mer information om hur du hittar eller skapar en personlig åtkomsttoken i [!DNL GitLab] finns i"Skapa en personlig åtkomsttoken" i <a href="https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html">Personliga åtkomsttoken</a> i [!DNL GitLab]-dokumentationen.</p></td> 
     </tr> 
    </tbody> 
   </table>


1. Klicka på **[!UICONTROL Continue]**.
1. Klicka på **[!UICONTROL Authorize]** för att skapa anslutningen och återgå till modulen.

## [!DNL GitLab]-moduler och deras fält

När du konfigurerar [!DNL GitLab] moduler visar [!DNL Workfront Fusion] fälten som listas nedan. Dessutom kan ytterligare [!DNL GitLab] fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### Utlösare

+++**[!UICONTROL Watch build status]**

Den här snabbutlösarmodulen startar ett scenario när statusen för ett bygge ändras.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för ändringar av byggstatus</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commit/MR/issue/snippet comments]**

Den här snabbutlösarmodulen startar ett scenario när en kommentar görs i ett implementerings-, sammanfogningsbegäran-, utgåva- eller kodfragment.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för kommentarer</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commits (pushes)]**

Den här snabbutlösarmodulen startar ett scenario när en implementering överförs till en databas. Den här modulen startar inte ett scenario när en tagg överförs.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska kontrollera implementeringar</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issue comment]**

Den här snabbutlösarmodulen startar ett scenario när en kommentar görs i ett problem.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska titta på för att få kommentarer</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issues]**

Modulen [!UICONTROL instant trigger] startar ett scenario när ett problem skapas eller när ett befintligt problem uppdateras, stängs eller öppnas igen.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för problem</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge requests]**

Den här snabbutlösarmodulen startar ett scenario när något av följande inträffar:

* En ny sammanfogningsbegäran skapas
* En befintlig kopplingsbegäran uppdateras, sammanfogas eller stängs
* En implementering läggs till i källgrenen


<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för sammanfogningsbegäranden</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge request comments]**

Den här snabbutlösarmodulen startar ett scenario när en kommentar görs i en kopplingsbegäran.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för kommentarer om sammanfogningsbegäran</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch pipeline status]**

Den här snabbutlösarmodulen startar ett scenario när statusen för en pipeline ändras.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkopplingen ska bevaka för statusändringar för pipeline</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch projects]**

Den schemalagda utlösarmodulen startar ett scenario när ett nytt projekt läggs till, där den autentiserade användaren är medlem.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL GitLab]-konto till [!DNL Workfront] Fusion finns i <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Anslut [!DNL GitLab] till [!DNL Workfront] Fusion</a> i den här artikeln.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Maximalt antal resultat</td> 
   <td> <p>Ange eller mappa det maximala antalet poster som modulen ska bevaka under varje körningscykel för scenario.</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository branches]**

Denna schemalagda utlösarmodul startar ett scenario när en ny gren läggs till i en databas.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL GitLab]-konto till [!DNL Workfront] Fusion finns i <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Anslut [!DNL GitLab] till [!DNL Workfront] Fusion</a> i den här artikeln.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">Maximalt antal resultat</td> 
   <td> <p>Ange eller mappa det maximala antalet poster som modulen ska bevaka under varje körningscykel för scenario.</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository tags]**

Denna snabbutlösarmodul startar ett scenario när en tagg skapas eller tas bort i en databas.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för taggar</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch snippet comments]**

Den här snabbutlösarmodulen startar ett scenario när en ny kommentar görs i ett fragment.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för kommentarer</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch todos]**

Den schemalagda utlösarmodulen startar ett scenario när en ny åtgärd läggs till. När inget filter används körs utlösaren när en ny väntande åtgärd läggs till.

Mer information om fält finns i [Hämta en lista med uppgifter](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Watch wiki page]**

Den här snabbutlösarmodulen startar ett scenario när en wiki-sida skapas eller redigeras.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>Välj den webkrok som du vill använda för den här utlösaren eller lägg till en ny webkrok. </p><p>Om du vill lägga till en ny webbkrok <ol><li>Klicka på <b>[!UICONTROL Add]</b> bredvid fältet [!UICONTROL webhook].</li><li>Ange följande: <ul><li>Ett namn för webkroken</li><li>Anslutningen som du vill använda för den här webkroken</li><li>Det projekt som du vill att webbkroken ska bevaka för wiki-sidor</li></ul></li><li>Klicka på <b>[!UICONTROL Save]</b> för att spara webkroken och återgå till modulen. </td> 
   </tr> 
   </tbody> 
</table>

+++

### Åtgärder

+++**[!UICONTROL Accept merge request]**

Den här åtgärdsmodulen sammanfogar skickade ändringar med den angivna sammanfogningsbegäran.

Mer information om fält finns i [Godkänn sammanfogningsbegäran](https://docs.gitlab.com/ee/api/merge_requests.html#accept-mr) i [!DNL GitLab] -dokumentationen.

+++

+++**[!UICONTROL Cancel a build]**

Den här åtgärdsmodulen avbryter en enskild version av ett projekt.

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Instruktioner om hur du ansluter ditt [!DNL GitLab]-konto till [!DNL Workfront] Fusion finns i <a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">Anslut [!DNL GitLab] till [!DNL Workfront] Fusion</a> i den här artikeln.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Markera eller mappa projektet som innehåller det bygge som du vill avbryta.</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td>Markera eller mappa det bygge som du vill avbryta.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge commit message]</td> 
   <td> Ange eller mappa ett implementeringsmeddelande för sammanfogningen.
    </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Should remove source branch]</td> 
   <td>Välj om du vill ta bort källgrenen när sammanfogningen är klar.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge when build succeeds]</td> 
   <td>Välj om sammanfogningsbegäran ska sammanfogas så snart som bygget är slutfört.</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL SHA]</td> 
   <td>Om det finns måste SHA-värdet matcha HEAD i källgrenen. Om den inte matchar misslyckas sammanfogningen.</td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Cancel a pipeline's builds]**

Den här åtgärdsmodulen avbryter byggnaderna för en enskild pipeline.

Mer information om fält finns i [Avbryt en pipelines jobb](https://docs.gitlab.com/ee/api/pipelines.html#cancel-a-pipelines-jobs) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Cancel merge when pipeline succeeds]**

Om en sammanfogningsbegäran är inställd på att sammanfogas när en pipeline lyckas avbryts åtgärden av den här åtgärdsmodulen.

Mer information om fält finns i [Avbryt sammanfogning när pipeline lyckas](https://docs.gitlab.com/ee/api/merge_requests.html) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Cherry pick a commit]**

Den här åtgärdsmodulens körsbärsprogram väljer en bindning till en viss gren.

Mer information om fält finns i [Körsbär välja en implementering](https://docs.gitlab.com/ee/api/commits.html#cherry-pick-a-commit) i [!DNL GitLab] -dokumentationen.

+++

+++**[!UICONTROL Create a new label]**

Den här åtgärdsmodulen skapar en ny etikett för den angivna databasen.

Mer information om fält finns i [Skapa en ny etikett](https://docs.gitlab.com/ee/api/labels.html#create-a-new-label) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a new pipeline]**

Den här åtgärdsmodulen skapar en ny pipeline för det aktuella projektet.

Mer information om fält finns i [Skapa en ny pipeline](https://docs.gitlab.com/ee/api/pipelines.html#create-a-new-pipeline) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a new release]**

Den här åtgärdsmodulen lägger till versionsinformation till den befintliga Git-taggen.

Mer information om fält finns i [Skapa en release](https://docs.gitlab.com/ee/api/releases/#create-a-release) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a new tag]**

Den här åtgärdsmodulen skapar en ny tagg i databasen som pekar på den angivna referensen.

Mer information om fält finns i [Skapa en ny tagg](https://docs.gitlab.com/ee/api/tags.html#create-a-new-tag) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a todo]**

Den här åtgärdsmodulen skapar en åtgärd för den aktuella användaren i det valda problemet. Den aktuella användaren är den användare som identifieras av autentiseringsuppgifterna för anslutningen som används för den här modulen.

Mer information om fält finns i [Skapa en att göra](https://docs.gitlab.com/ee/api/issues.html#create-a-todo) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a todo on a merge request]**

Den här åtgärdsmodulen skapar en åtgärd för den aktuella användaren på den valda sammanfogningsbegäran. Den aktuella användaren är den användare som identifieras av autentiseringsuppgifterna för anslutningen som används för den här modulen.

Mer information om fält finns i [Skapa en att göra](https://docs.gitlab.com/ee/api/merge_requests.html#create-a-todo) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create merge request]**

Den här åtgärdsmodulen skapar en ny kopplingsbegäran för ett projekt.

Mer information om fält finns i [Skapa sammanfogningsbegäran](https://docs.gitlab.com/ee/api/merge_requests.html#create-mr) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create new file in repository]**

Den här åtgärdsmodulen skapar en ny fil i den valda databasen.

Mer information om fält finns i [Skapa ny fil i databasen](https://docs.gitlab.com/ee/api/repository_files.html#create-new-file-in-repository) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create new issue note]**

Den här åtgärdsmodulen skapar en problemanteckning för ett enstaka projektproblem.

Mer information om fält finns i [Skapa ny problemanteckning](https://docs.gitlab.com/ee/api/notes.html#create-new-issue-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create new merge request note]**

Den här åtgärdsmodulen skapar anteckning för en enda sammanfogningsbegäran.

Mer information om fält finns i [Skapa ny begärandeanteckning för sammanfogning](https://docs.gitlab.com/ee/api/notes.html#create-new-merge-request-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create a new milestone]**

Den här åtgärdsmodulen skapar en ny milstolpe för ett projekt.

Mer information om fält finns i [Skapa ny milstolpe](https://docs.gitlab.com/ee/api/milestones.html#create-new-milestone) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create new snippet note]**

Den här åtgärdsmodulen skapar en ny anteckning för ett enskilt fragment. Utdragsanteckningar är kommentarer som användare kan skicka till ett utdrag.

Mer information om fält finns i [Skapa ny utdragsanteckning](https://docs.gitlab.com/ee/api/notes.html#create-new-snippet-note) i [!DNL GitLab] -dokumentationen.

+++

+++**[!UICONTROL Create repository branch]**

Den här åtgärdsmodulen skapar en enskild databasgren.

Mer information om fält finns i [Skapa databasgren](https://docs.gitlab.com/ee/api/branches.html#create-repository-branch) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Create build variable]**

Den här åtgärdsmodulen skapar en ny byggvariabel.

Mer information om fält finns i [Skapa variabel](https://docs.gitlab.com/ee/api/project_level_variables.html#create-variable) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Delete a merge request]**

Den här åtgärdsmodulen är endast avsedd för administratörer och projektägare. Den tar bort den aktuella sammanfogningsbegäran

Mer information om fält finns i [Ta bort en sammanfogningsbegäran](https://docs.gitlab.com/ee/api/merge_requests.html#delete-a-merge-request) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Delete existing file in repository]**

Den här åtgärdsmodulen tar bort en befintlig fil från databasen.

Mer information om fält finns i [Ta bort befintlig fil i databasen](https://docs.gitlab.com/ee/api/repository_files.html#delete-existing-file-in-repository) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Delete repository branch]**

Den här åtgärdsmodulen tar bort en gren från databasen.

Mer information om fält finns i [Ta bort databasgren](https://docs.gitlab.com/ee/api/branches.html#delete-repository-branch) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Edit issue]**

Den här åtgärdsmodulen uppdaterar ett befintligt projektproblem. Det här samtalet används även för att markera ett problem som stängt.

Mer information om fält finns i [Redigera problem](https://docs.gitlab.com/ee/api/issues.html#edit-issue) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Edit Milestone]**
Den här åtgärdsmodulen uppdaterar en befintlig projektmilstolpe.

Mer information om fält finns i [Redigera milstolpe](https://docs.gitlab.com/ee/api/milestones.html#edit-milestone) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Erase a build]**

Den här åtgärdsmodulen raderar ett bygge av ett projekt (tar bort jobbartefakter och jobblogg).

Mer information om fält finns i [Radera ett jobb](https://docs.gitlab.com/ee/api/jobs.html#erase-a-job) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a list of todos]**

Den här sökmodulen hämtar en lista med att göra-objekt.

Mer information om fält finns i [Hämta en lista med uppgifter](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a single build]**

Den här åtgärdsmodulen hämtar ett enstaka jobb i ett projekt.

Mer information om fält finns i [Hämta ett enskilt jobb](https://docs.gitlab.com/ee/api/jobs.html#get-a-single-job) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a single repository tag]**

Den här åtgärdsmodulen hämtar en specifik databastagg som bestäms av dess namn.

Mer information om fält finns i [Hämta en enda databastagg](https://docs.gitlab.com/ee/api/tags.html#get-a-single-repository-tag) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a specific deployment]**

Den här åtgärdsmodulen hämtar en specifik distribution.

Mer information om fält finns i [Hämta en specifik distribution](https://docs.gitlab.com/ee/api/deployments.html#get-a-specific-deployment) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get all issues assigned to a single milestone]**

Den här sökmodulen hämtar alla utgåvor som tilldelats en enskild projektmilstolpe.

Mer information om fält finns i [Hämta alla utgåvor som tilldelats en enskild milstolpe](https://docs.gitlab.com/ee/api/milestones.html#get-all-issues-assigned-to-a-single-milestone) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get file from repository]**

Den här åtgärdsmodulen hämtar information om en fil i databasen, t.ex. namn, storlek eller innehåll.

Mer information om fält finns i [Hämta fil från databas](https://docs.gitlab.com/ee/api/repository_files.html#get-file-from-repository) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get project users]**

Den här sökmodulen hämtar användarna av projektet.

Mer information om fält finns i [Hämta projektanvändare](https://docs.gitlab.com/ee/api/projects.html#get-project-users) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a single issue]**

Den här åtgärdsmodulen hämtar information om problem.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Mer information om hur du skapar en ny anslutning finns i <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] till Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td> <p>Välj det projekt som innehåller problemet som du vill hämta information om.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID]</td> 
   <td> <p>Ange eller mappa namnet på det problem som du vill hämta information om.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Get single issue note]**

Den här åtgärdsmodulen hämtar en enda anteckning för ett specifikt projektproblem.

Mer information om fält finns i [Få en problemanteckning](https://docs.gitlab.com/ee/api/notes.html#get-single-issue-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single merge request]**

Den här åtgärdsmodulen hämtar information om en enda sammanfogningsbegäran.

Mer information om fält finns i [Hämta en sammanfogningsbegäran](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single merge request changes]**

Den här sökmodulen hämtar information om sammanfogningsbegäran, inklusive filer och ändringar.

Mer information om fält finns i [Få ändringar av enskilda sammanfogningsbegäranden](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-changes) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single merge request commits]**

Den här åtgärdsmodulen hämtar en lista över implementeringar av sammanslagningsbegäranden.

Mer information om fält finns i [Få implementeringar av enskilda sammanfogningsbegäranden](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single merge request note]**

Den här åtgärdsmodulen returnerar en enda anteckning för en given kopplingsbegäran.

Mer information om fält finns i [Få meddelande om begäran om enskild sammanslagning](https://docs.gitlab.com/ee/api/notes.html#get-single-merge-request-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a Milestone]**

Den här åtgärdsmodulen hämtar information om milstolpe.

Mer information om fält finns i [Hämta en milstolpe](https://docs.gitlab.com/ee/api/milestones.html#get-single-milestone) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single project]**

Den här åtgärdsmodulen hämtar projektinformation.

Mer information om fält finns i [Hämta ett projekt](https://docs.gitlab.com/ee/api/projects.html#get-single-project) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get single repository branch]**

Den här åtgärdsmodulen hämtar information om databasgrenar.

Mer information om fält finns i [Hämta en enskild databasgren](https://docs.gitlab.com/ee/api/branches.html#get-single-repository-branch) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get snippet note]**

Den här modulen hämtar en anteckning för ett visst kodavsnitt.

Mer information om fält finns i [Få en enda utdragsanteckning](https://docs.gitlab.com/ee/api/notes.html#get-single-snippet-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get the comments of a commit]**

Den här sökmodulen hämtar kommentarer från en implementering i ett projekt.

Mer information om fält finns i [Hämta kommentarer från en implementering](https://docs.gitlab.com/ee/api/commits.html#get-the-comments-of-a-commit) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get the diff of a commit]**

Den här åtgärdsmodulen hämtar skillnaden mellan en implementering i ett projekt.

Mer information om fält finns i [Hämta skillnaden för en implementering](https://docs.gitlab.com/ee/api/commits.html#get-the-diff-of-a-commit) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Keep artifacts]**

Förhindrar att artefakter tas bort när förfallodatum har angetts.

Mer information om fält finns i [Behåll artefakter](https://docs.gitlab.com/ee/api/job_artifacts.html#keep-artifacts) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List all merge request notes]**

Den här sökmodulen hämtar en lista med alla anteckningar för en enda sammanfogningsbegäran.

Mer information om fält finns i [Visa alla anteckningar för sammanfogningsbegäran](https://docs.gitlab.com/ee/api/notes.html#list-all-merge-request-notes) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List all snippet notes]**

Den här modulen hämtar en lista med alla anteckningar för ett enskilt kodfragment. Utdragsanteckningar är kommentarer som användare kan skicka till ett utdrag.

Mer information om fält finns i [??](https://docs.gitlab.com/ee/api/notes.html#list-all-snippet-notes) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List commit builds]**

Den här sökmodulen returnerar en lista med byggen för en specifik implementering i ett projekt.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Mer information om hur du skapar en ny anslutning finns i <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] till Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Välj det projekt som innehåller den implementering som du vill lista byggen för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> Om du vill begränsa sökningen till att bygga med en viss status väljer du status. Om du lämnar det här fältet tomt returneras alla byggen av implementeringen.  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL List issues]**

Den här sökmodulen returnerar alla utgåvor av de angivna filterinställningarna.

Mer information om fält finns i [Lista problem](https://docs.gitlab.com/ee/api/issues.html#list-issues) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List Issues That Close on Merge]**

Den här sökmodulen hämtar alla problem som skulle stängas genom att sammanfoga den angivna sammanfogningsbegäran.

Mer information om fält finns i [Lista problem som stängs vid sammanslagning](https://docs.gitlab.com/ee/api/merge_requests.html#list-issues-that-will-close-on-merge) i dokumentationen för [!DNL GitLab].

+++

+++**[!UICONTROL List Labels]**

Den här sökmodulen hämtar alla etiketter i projektet.

Mer information om fält finns i [Listetiketter](https://docs.gitlab.com/ee/api/labels.html#list-labels) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List merge requests]**

Den här sökmodulen hämtar alla sammanfogningsbegäranden från filterinställningarna.

Mer information om fält finns i [Visa sammanfogningsbegäranden](https://docs.gitlab.com/ee/api/merge_requests.html#list-merge-requests) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List Owned Projects]**

Den här sökmodulen hämtar projekt där den autentiserade användaren har angetts som ägare.

Mer information om fält finns i [Visa användarprojekt](https://docs.gitlab.com/ee/api/projects.html#list-all-projects) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project builds]**

Den här sökmodulen hämtar en lista med byggen i ett projekt.

Mer information om fält finns i [Visa projektjobb](https://docs.gitlab.com/ee/api/jobs.html#list-project-jobs) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project deployments]**

Den här sökmodulen hämtar en lista över distributioner i ett projekt.

Mer information om fält finns i [Visa projektdistributioner](https://docs.gitlab.com/ee/api/deployments.html#list-project-deployments) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project issue notes]**

Den här sökmodulen hämtar en lista med alla anteckningar för ett enskilt problem.

Mer information om fält finns i [Visa information om projektproblem](https://docs.gitlab.com/ee/api/notes.html#list-project-issue-notes) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project issues]**

Den här sökmodulen returnerar alla utgåvor i ett visst projekt.

Mer information om fält finns i [Visa projektproblem](https://docs.gitlab.com/ee/api/issues.html#list-project-issues) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project milestones]**

Den här sökmodulen hämtar alla milstolpar i projektet.

Mer information om fält finns i [Visa projektmilstolpar](https://docs.gitlab.com/ee/api/milestones.html#list-project-milestones) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project pipelines]**

Med den här sökmodulen hämtas alla rörledningar för projektet.

Mer information om fält finns i [Visa projektpipelines](https://docs.gitlab.com/ee/api/pipelines.html#list-project-pipelines) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project repository tags]**

Den här sökmodulen hämtar en lista med databastaggar från ett projekt, sorterade efter namn i omvänd alfabetisk ordning.

Mer information om fält finns i [Visa projektdatabastaggar](https://docs.gitlab.com/ee/api/tags.html#list-project-repository-tags) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List project variables]**

Den här sökmodulen hämtar en lista över ett projekts variabler.

Mer information om fält finns i [Visa projektvariabler](https://docs.gitlab.com/ee/api/project_level_variables.html#list-project-variables) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List projects]**

Den här sökmodulen hämtar alla projekt där den autentiserade användaren är medlem.

Mer information om fält finns i [Visa alla projekt](https://docs.gitlab.com/ee/api/projects.html#list-all-projects) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List repository branches]**

Den här modulen söker efter databasgrenar efter söktermen.

Mer information om fält finns i [Visa databasgrenar](https://docs.gitlab.com/ee/api/branches.html#list-repository-branches) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List repository commits]**

Den här sökmodulen hämtar en lista över databasimplementeringar i ett projekt.

Mer information om fält finns i [Visa databasimplementeringar](https://docs.gitlab.com/ee/api/commits.html#list-repository-commits) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List repository contributors]**

Den här sökmodulen hämtar en lista över databasdeltagare.

Mer information om fält finns i [Medarbetare](https://docs.gitlab.com/ee/api/repositories.html#contributors) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL List repository tree]**

Den här sökmodulen hämtar en lista med databasfiler och kataloger i ett projekt.

Mer information om fält finns i [Visa databasträd](https://docs.gitlab.com/ee/api/repositories.html#list-repository-tree) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Mark a todo as done]**

Den här åtgärdsmodulen markerar ett enskilt väntande att göra-objekt som anges av dess ID för den aktuella användaren som gjort.

Mer information om fält finns i [Markera en att göra-uppgift som färdig](https://docs.gitlab.com/ee/api/todos.html#mark-a-todo-as-done) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Modify existing issue note]**

Ändrar en befintlig anteckning av ett problem.

Mer information om fält finns i [Ändra befintlig problemanteckning](https://docs.gitlab.com/ee/api/notes.html#modify-existing-issue-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Modify existing merge request note]**

Ändrar den befintliga anteckningen för en sammanfogningsbegäran.

Mer information om fält finns i [Ändra befintlig förfrågan om sammanfogning](https://docs.gitlab.com/ee/api/notes.html#modify-existing-merge-request-note) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Modify existing snippet note]**

Den här åtgärdsmodulen ändrar en befintlig anteckning av ett fragment.

Mer information om fält finns i [Ändra befintlig utdragsanteckning](https://docs.gitlab.com/ee/api/notes.html#modify-existing-snippet-note) i [!DNL GitLab] -dokumentationen.

+++

+++**[!UICONTROL New issue]**

Den här åtgärdsmodulen skapar ett nytt projektproblem.

Mer information om fält finns i [Nytt problem](https://www.integromat.com/en/help/app/gitlab) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Play a build]**

Den här åtgärdsmodulen utlöser en manuell åtgärd för att starta ett jobb.

Mer information om fält finns i [Spela upp ett jobb](https://docs.gitlab.com/ee/api/jobs.html#play-a-job) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Post comment to commit]**

Den här åtgärdsmodulen lägger till en kommentar i en implementering.

Mer information om fält finns i [Publicera kommentar som ska verkställas](https://docs.gitlab.com/ee/api/commits.html#post-comment-to-commit) i [!DNL GitLab] -dokumentationen.

+++

+++**[!UICONTROL Remove variable]**

Den här åtgärdsmodulen tar bort ett projekts variabel.

Mer information om fält finns i [Ta bort variabel](https://docs.gitlab.com/ee/api/project_level_variables.html#remove-variable) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Retry a build]**

Den här åtgärdsmodulen försöker återskapa en enda programversion i en implementering.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>Mer information om hur du skapar en ny anslutning finns i <a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab] till Workfront Fusion]</a> i den här artikeln.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>Välj det projekt som innehåller det bygge som du vill försöka igen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td> Välj det bygge som du vill försöka igen. </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Retry Failed Jobs in a Pipeline]**

Den här åtgärdsmodulen försöker återskapa misslyckade byggen i en pipeline.

Mer information om fält finns i [Försök igen i en pipeline](https://docs.gitlab.com/ee/api/pipelines.html#retry-jobs-in-a-pipeline) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Get a Variable]**

Den här modulen hämtar information om ett projekts specifika variabel.

Mer information om fält finns i [Visa variabelinformation](https://docs.gitlab.com/ee/api/project_level_variables.html#show-variable-details) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Update a release]**

Den här åtgärdsmodulen uppdaterar en release.

Mer information om fält finns i [Uppdatera en release](https://docs.gitlab.com/ee/api/releases/#update-a-release) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Update merge request]**

Den här åtgärdsmodulen uppdaterar en befintlig kopplingsbegäran. Du kan ändra målgrenen, titeln eller till och med stänga MR-filen.

Mer information om fält finns i [Uppdatera sammanfogningsbegäran](https://docs.gitlab.com/ee/api/merge_requests.html#update-mr) i [!DNL GitLab]-dokumentationen.

+++

+++**[!UICONTROL Update a Variable]**

Den här åtgärdsmodulen uppdaterar ett projekts variabel.

Mer information om fält finns i [Uppdatera variabel](https://docs.gitlab.com/ee/api/project_level_variables.html#update-variable) i [!DNL GitLab]-dokumentationen.

+++
