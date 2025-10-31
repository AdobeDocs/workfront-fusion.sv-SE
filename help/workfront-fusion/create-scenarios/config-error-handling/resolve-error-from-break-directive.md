---
title: Åtgärda fel som hanteras av direktivet Break
description: Ibland kan det vara användbart att köra en felande modul igen om det finns en möjlighet att orsaken till felet snabbt kan lösas.
author: Becky
feature: Workfront Fusion
exl-id: d568942c-2cd5-430c-bdbf-e1496da25b50
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# Åtgärda fel som hanteras av direktivet Break

När ett fel hanteras av direktivet Break skapas en post i mappen Ofullständiga körningar. Den här posten lagrar läget för scenariokörningen tillsammans med data från tidigare moduler. Posten refererar till modulen där felet uppstod och innehåller information om data som har tagits emot av modulen som indata. För varje datapaket som orsakar felet skapas en separat post.

Mer information finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

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

## Åtgärda fel som uppstår till följd av direktivet Break

Du kan lösa felet manuellt genom att uppdatera scenariot (om det behövs) och köra det en gång.

Du kan också konfigurera scenariot så att det automatiskt bearbetar en ofullständig körning genom att köra scenariot igen. Så här konfigurerar du modulen för att bearbeta ofullständiga körningar:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en tillfällig lösning.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Klicka på ikonen **Flödeskontroll** ![Flödeskontroll](assets/flow-control-icon.png) och välj **Brytning**.
1. Aktivera alternativet [!UICONTROL **Slutför körning automatiskt**] i Break-modulen.
1. I fältet **Antal försök** anger eller mappar du det maximala antalet försök som du vill att modulen ska göra om körningen

   Talet måste vara mellan 1 och 100.
1. Ange eller mappa antalet minuter mellan varje försök i fältet **Intervall mellan försök**.

När det här alternativet är aktiverat hämtas den ofullständiga körningen (efter den tid som anges i fältet [!UICONTROL Interval between attempts]) och körs med de ursprungliga indata. Detta upprepas tills körningen av modulen har slutförts utan fel eller tills det angivna antalet försök har uppnåtts.

>[!NOTE]
>
>Om det initiala försöket misslyckas, ökar intervallet mellan försöken exponentiellt varje annat försök.


När alternativet Automatiskt slutförd körning är aktiverat markeras scenariot som slutfört eftersom felhanterarens automatiska återförsök hanterar problemet automatiskt. I det här fallet får användarna inte något e-postmeddelande om den misslyckade körningen.

När körningsalternativet Automatiskt slutförd är inaktiverat markeras körningen som&quot;Varning&quot;.

Det finns vissa undantag från körningar som lagras under Ofullständiga körningar, och med vissa feltyper går det inte att utföra en scenariokörning automatiskt igen.

## Resurser

Mer information finns i [Tillåt lagring av ofullständiga körningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions) i artikeln Konfigurera scenarioinställningar.
