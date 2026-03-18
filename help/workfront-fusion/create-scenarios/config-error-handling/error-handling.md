---
title: Lägg till felhantering
description: När fel inträffar under körningen av ett scenario beror det oftast på att en tjänst inte är tillgänglig på grund av ett fel, att en tjänst svarar med oväntade data eller att valideringen av indata misslyckas.
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: d7072a2dca50bf47f20d1f25dba4d3fb819d3ddc
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 0%

---

# Lägg till felhantering

Fel kan uppstå när ett scenario körs.

Ett fel kan till exempel uppstå på grund av:

* En tjänst är inte tillgänglig på grund av ett fel
* En tjänst svarar med oväntade data
* Validering av indata misslyckas
* Andra orsaker

Om en modul påträffar ett fel under scenariokörningen och det inte finns någon felhanteringsväg som är kopplad till modulen eller dess väg, körs standardfelhanteringslogiken.

Genom att lägga till en felhanterare i en modul eller ett flöde kan du ersätta standardlogiken för felhantering med din egen. Adobe Workfront Fusion innehåller fem olika direktiv som kan infogas i slutet av felhanterarvägen.

Mer information om standardfelhantering finns i [Feltyper](/help/workfront-fusion/references/errors/error-processing.md).

Mer information om felhanteringsdirektiv finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

>[!NOTE]
>
>Workfront Fusion har stöd för felhantering på ruttnivå, vilket gör att du kan definiera felhanteringslogiken en gång per väg i stället för att koppla felhanterare till varje enskild modul.
>Eftersom felhantering på ruttnivå är ett mer skalbart, konsekvent och arkitektoniskt rent sätt att hantera fel, särskilt i avancerade automatiseringar med flera grenar, rekommenderar vi att felhantering på ruttnivå används som en bra metod.

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

## Felhanterarens plats och hierarki

Du kan lägga till felhanterare till enskilda moduler eller till routrar.

En felhanterare som är kopplad till en modul utlöses bara för fel som påträffas när den specifika modulen bearbetas.

En felhanterare som är kopplad till en router utlöser fel som påträffas av en modul på routerns väg. Detta inkluderar fel som påträffats på underordnade vägar som inte har någon felhanterare på sin egen router.

Fel hanteras av följande hierarki:

1. Modul
2. Router
3. Överordnad router
4. Standardfelhantering

>[!BEGINSHADEBOX]

### Exempel

Titta på följande exempelscenario:

![Exempel på scenario som visar vägar och felhanterare](assets/error-handling-route-example-with-numbers.png)

1. Modulen har en felhanterare. Alla fel i den här modulen hanteras av implementeringsdirektivet.
1. Den här modulen har ingen felhanterare. Om den här modulen påträffar ett fel hanteras felet av hanteraren på routern som skapade modulens väg. Alla fel i den här modulen hanteras av direktivet Rollback.
1. Den här modulen har ingen felhanterare, inte heller routern som skapade modulens väg, men det finns en felhanterare på nästa router upp. Alla fel i den här modulen hanteras av direktivet Break.

>[!NOTE]
>
>* Om en modul inte har någon felhanterare för modulen, dess router eller någon överordnad router hanteras eventuella fel i den modulen som standardfelhantering.
>* Om du vill skapa en global felhanterare skapar du en router nära början av ditt scenario och kopplar felhanteringen till den routern.


>[!ENDSHADEBOX]

## Lägga till en felhanterare

Du kan lägga till en felhanterare i en modul eller i en router.

* [Lägga till en felhanterare i en modul](#add-an-error-handler-to-a-module)
* [Lägga till en felhanterare till en router](#add-an-error-handler-to-a-router)

### Lägga till en felhanterare i en modul

Så här lägger du till en felhanterare i en modul:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en felhanteringsväg.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Högerklicka på den modul efter vilken du vill lägga till en felhanterarväg och välj **[!UICONTROL Add error handler]**:

   ![Felhanterarväg](assets/error-handler-route.png)

   En felhanterarväg läggs till i modulen. Om modulen är den sista modulen i ett flöde följer felhanteraren modulen direkt. Om modulen har fler moduler efter det läggs en separat felhanterarväg till.

   I felhanteringsmodulen visas en lista över direktiv samt de program som används i ditt scenario.

   ![Felflöde](assets/error-route.png)

1. Välj ett av direktiven.

   eller

   Lägg till en eller flera moduler i felhanterarflödet.

   Om du lägger till fler moduler i flödet används direktivet Ignorera som standard. Om ett fel uppstår behandlas efterföljande moduler på det flödet.

   Mer information om direktiv finns i [Felhanteringsdirektiv](#error-handling-directives) i den här artikeln.

1. (Valfritt) Lägg till ett filter i felhanteringsflödet. Instruktioner finns i [Lägga till filtrering och kapsling i felhanteringsflöden](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md).

>[!NOTE]
>
>Observera att en felhanterarväg består av genomskinliga cirklar, medan en vanlig väg består av heldragna cirklar.

### Lägga till en felhanterare till en router

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill lägga till en felhanteringsväg.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. Högerklicka på routern där du vill lägga till en felhanterarväg och välj **[!UICONTROL Add error handler]**:

   ![Felhanterarväg](assets/error-handler-on-router.png)

   En felhanterarväg läggs till i routern.

   I felhanteringsmodulen visas en lista över direktiv samt de program som används i ditt scenario.

   ![Felflöde](assets/error-handler-route-from-router.png)

1. Välj ett av direktiven.

   eller

   Lägg till en eller flera moduler i felhanterarflödet.

   Om du lägger till fler moduler i flödet används direktivet Ignorera som standard. Om ett fel uppstår behandlas efterföljande moduler på det flödet.

   Mer information om direktiv finns i [Felhanteringsdirektiv](#error-handling-directives) i den här artikeln.

1. (Valfritt) Lägg till ett filter i felhanteringsflödet. Instruktioner finns i [Lägga till filtrering och kapsling i felhanteringsflöden](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md).

## Felhanteringsdirektiv

Direktiven förklaras kortfattat nedan. Mer information finns i [Direktiv om felhantering](/help/workfront-fusion/references/errors/directives-for-error-handling.md).

Det finns fem direktiv som kan grupperas i följande kategorier baserat på om en scenariokörning fortsätter efter felet.

Följande direktiv ser till att en scenariokörning fortsätter:

* **[!UICONTROL Resume]**: Gör att du kan ange en ersättningsutmatning för modulen med felet. Scenariots körningsstatus har markerats som lyckad.
* **[!UICONTROL Ignore]**: ignorerar felet. Scenariots körningsstatus har markerats som lyckad.
* **[!UICONTROL Break]**: Lagrar indata till kön med ofullständiga körningar. Scenariots körningsstatus är markerad som varning.

  Mer information finns i [Visa och lösa ofullständiga körningar](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md).

Om en scenariokörning ska stoppas när ett fel inträffar, ska du använda något av följande direktiv:

* **[!UICONTROL Rollback]**: Stoppar scenariokörningen omedelbart och anger dess status som fel.
* **[!UICONTROL Commit]**: Stoppar scenariokörningen omedelbart och anger att den har lyckats.

## Resurser

Mer information om felhantering finns i:

* [Direktiv om felhantering i Adobe Workfront Fusion](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [Lägg till filtrering och kapsling i felhanteringsflöden](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)
