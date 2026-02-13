---
title: Mappa data med egna funktioner
description: När du mappar objekt kan du använda funktioner för att skapa enkla eller komplexa formler.
author: Becky
feature: Workfront Fusion
source-git-commit: 109ea8a6b3c37918110dc930a19ac85ef3e6d764
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---

# Mappa data med egna funktioner

Du kan skapa anpassade funktioner under Funktioner i Fusion. Sedan lägger du till dessa funktioner i dina scenarier i form av en Adobe App Builder-modul.

Eftersom anpassade funktioner fungerar i Adobe App Builder måste ni ha en Adobe App Builder-licens för att använda dem.

Anpassade funktioner, precis som de flesta scenarioelement, ägs av team.

Workfront Fusion innehåller även inbyggda funktioner som gör att du kan skapa enkla eller komplexa formler. Funktionerna omfattar en mängd olika användningsområden, bland annat funktioner för arrayer, strängar, tal och data från tidigare moduler.

Mer information och instruktioner om inbyggda funktioner finns i [Mappa ett objekt med inbyggda funktioner](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md).

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
   <p><ul><li>Om ni har ett Select- eller Prime Workfront-paket som inte innehåller Workfront Automation and Integration måste ni köpa Adobe Workfront Fusion.</li><li>Du måste ha en licens för Adobe App Builder för att kunna använda anpassade funktioner.</ul>
   </td> 
  </tr>
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

+++

## Konfigurera en anpassad funktion

Anpassade funktioner konfigureras under Funktioner i Workfront Fusion. När en funktion har konfigurerats kan du lägga till den i ett scenario med hjälp av Adobe App Builder-anslutningen.

### Initiera körningsmiljön

Innan du kan skapa anpassade funktioner måste du initiera körningsmiljön. Detta behöver bara göras om ditt team inte har några anpassade funktioner.

>[!IMPORTANT]
>
>Initieringen kan bara utföras av en användare med tillgång till Adobe App Builder, antingen en utvecklare eller en systemadministratör i IMS-organisationen.
>
>När initieringen är klar kan alla användare i det team där initieringen utfördes skapa och använda funktioner.

1. Klicka på fliken **Funktioner** ![Funktioner ](assets/functions-icon.png) i den vänstra panelen.

   Om du ännu inte har konfigurerat runtime-modulen visas meddelandet&quot;Körningsmiljön har inte konfigurerats&quot;.
1. Klicka på **Initiera körningsmiljö**.

   Efter en stund visas en funktionslista med två exempelfunktioner.

### Skapa en anpassad funktion

När körningsmiljön har konfigurerats kan du börja skapa anpassade funktioner.

>[!IMPORTANT]
>
>* Din anpassade funktion **måste** vara en JavaScript-funktion.
>* Den anpassade funktionen **måste** returnera ett objekt.
>* När du har skapat en anpassad funktion kan du inte:
>
>   * Ändra namnet
>   * Visa standardparametervärden

1. Klicka på fliken **Funktioner** ![Funktioner ](assets/functions-icon.png) i den vänstra panelen.
1. Klicka på **Lägg till funktion**.
1. Ange ett namn för den anpassade funktionen.

   Du kan inte ändra det här namnet senare.
1. Ange koden för funktionen.
1. För varje standardparametervärde som du vill lägga till klickar du på **Lägg till parameter** och anger parameternamnet och standardvärdet.

   Du kan åsidosätta standardparametrar när du lägger till funktionen i ett scenario.
1. Klicka på **Spara**

## Lägga till en anpassad funktion i ett scenario

Om du vill lägga till en anpassad funktion i ett scenario använder du Adobe App Builder-anslutningen.

Instruktioner finns i [Adobe App Builder-modulen](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md).

