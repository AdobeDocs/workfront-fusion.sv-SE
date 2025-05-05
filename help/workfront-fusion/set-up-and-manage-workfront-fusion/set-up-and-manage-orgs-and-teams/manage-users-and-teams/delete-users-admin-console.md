---
content-type: reference
title: 'Konfigurera och hantera organisationer och team: artikelindex'
description: Det här avsnittet innehåller artiklar om hur du konfigurerar och hanterar organisationer och team i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Ta bort användare via [!DNL Adobe Admin Console]

Du kan bara ta bort en användare från [!DNL Adobe Workfront Fusion], lämna åtkomst till andra [!DNL Adobe]-produktprofiler, eller så kan du ta bort användaren helt från [!DNL Adobe Admin Console].

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara administratör för [!DNL Adobe Admin Console] för din organisation.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om [!DNL Adobe Workfront Fusion] licenser finns i [[!DNL Adobe Workfront Fusion] licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ta endast bort en användare från [!DNL Adobe Workfront Fusion]

Du kan ta bort en användare från Workfront Fusion utan att ändra Adobe övriga produktbehörigheter.

Instruktioner finns i&quot;Ta bort användare och användargrupper från en produkt&quot; i artikeln [Hantera produkter på Admin Console](https://helpx.adobe.com/se/enterprise/using/manage-products.html).

## Inaktivera en användare i alla produkter i [!DNL Adobe Admin Console]

Om du vill ta bort en användare måste du inaktivera användaren via [!DNL Adobe Admin Console].

En användare inaktiveras från [!DNL Adobe Admin Console] när något av följande gäller:

* Användaren flyttas ut från en produkt- eller produktprofil och tilldelas inte till någon annan produkt- eller produktprofil.
* Användaren tas bort från en grupp som är länkad till en produktprofil och ingår inte i någon annan grupp som är länkad till en produktprofil.
* Användaren tas bort från en produktprofil och tilldelas inte till någon annan produktprofil.
* Användaren tas bort eller inaktiveras i organisationen som innehåller Workfront Fusion.

  Instruktioner finns i avsnittet Ta bort användare i [Hantera användare individuellt](https://helpx.adobe.com/se/enterprise/using/manage-users-individually.html).

I [!DNL Workfront Fusion] påverkar inaktiveringen användaren på något av följande sätt:

* Om användaren bara finns i en organisation inaktiveras användaren.
* Om användaren finns i mer än en organisation tas användaren bort från organisationen som användaren ändrades i [!DNL Adobe Admin Console].
* Tänk på följande när du tar bort en användare.

### Att tänka på när du tar bort en användare i Workfront Fusion

Tänk på följande när du tar bort en användare.

* När en användare tas bort tas användarens anslutningar, nycklar och webbböcker bort.
* Alla scenarier som tillhör användaren överförs till organisationsägaren. Anslutningarna i dessa scenarier måste uppdateras eftersom anslutningarna som tillhör användaren inte längre är giltiga.
* Om den borttagna användaren äger något program eller publika mallar överförs programmen eller de publika mallarna till organisationens ägare. Om det inte finns någon organisationsägare överförs programmen eller de offentliga mallarna till en annan användare.
