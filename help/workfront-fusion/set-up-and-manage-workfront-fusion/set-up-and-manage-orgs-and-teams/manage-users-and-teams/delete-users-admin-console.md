---
content-type: reference
title: 'Konfigurera och hantera organisationer och team: artikelindex'
description: Det här avsnittet innehåller artiklar om hur du konfigurerar och hanterar organisationer och team i Adobe Workfront Fusion.
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: f7c1d5b1de74cc0c59e3a00938bed14b489500db
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Ta bort användare via [!DNL Adobe Admin Console]

Du kan bara ta bort en användare från Adobe Workfront Fusion, lämna åtkomst till alla andra [!DNL Adobe]-produktprofiler, eller så kan du ta bort användaren helt från [!DNL Adobe Admin Console].

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå</td> 
   <td> 
     <p>Du måste vara Adobe Admin Console-administratör för din organisation.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Ta endast bort en användare från Adobe Workfront Fusion

Du kan ta bort en användare från Workfront Fusion och samtidigt lämna övriga Adobe-produktbehörigheter intakta.

Instruktioner finns i&quot;Ta bort användare och användargrupper från en produkt&quot; i artikeln [Hantera produkter på Admin Console](https://helpx.adobe.com/se/enterprise/using/manage-products.html).

## Inaktivera en användare i alla produkter i [!DNL Adobe Admin Console]

Om du vill ta bort en användare måste du inaktivera användaren via [!DNL Adobe Admin Console].

En användare inaktiveras från [!DNL Adobe Admin Console] när något av följande gäller:

* Användaren flyttas ut från en produkt- eller produktprofil och tilldelas inte till någon annan produkt- eller produktprofil.
* Användaren tas bort från en grupp som är länkad till en produktprofil och ingår inte i någon annan grupp som är länkad till en produktprofil.
* Användaren tas bort från en produktprofil och tilldelas inte till någon annan produktprofil.
* Användaren tas bort eller inaktiveras i organisationen som innehåller Workfront Fusion.

  Instruktioner finns i avsnittet Ta bort användare i [Hantera användare individuellt](https://helpx.adobe.com/se/enterprise/using/manage-users-individually.html).

I Workfront Fusion påverkar inaktiveringen användaren på något av följande sätt:

* Om användaren bara finns i en organisation inaktiveras användaren.
* Om användaren finns i mer än en organisation tas användaren bort från organisationen som användaren ändrades i [!DNL Adobe Admin Console].
* Tänk på följande när du tar bort en användare.

### Att tänka på när du tar bort en användare i Workfront Fusion

Tänk på följande när du tar bort en användare.

* När en användare tas bort tas användarens anslutningar, nycklar och webbböcker bort.
* Alla scenarier som tillhör användaren överförs till organisationsägaren. Anslutningarna i dessa scenarier måste uppdateras eftersom anslutningarna som tillhör användaren inte längre är giltiga.
* Om den borttagna användaren äger något program eller publika mallar överförs programmen eller de publika mallarna till organisationens ägare. Om det inte finns någon organisationsägare överförs programmen eller de offentliga mallarna till en annan användare.
