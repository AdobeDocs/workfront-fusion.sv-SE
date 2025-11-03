---
title: Microsoft SQL Server-moduler
description: Du kan använda Adobe Workfront Fusion för att ansluta till Microsoft SQL Server.
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# [!DNL Microsoft SQL Server] moduler

Du kan ansluta till [!UICONTROL Microsoft SQL Server] med Adobe Workfront Fusion.

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
   <td role="rowheader">Adobe Workfront Fusion-licens</td> 
   <td>
   <p>Operationsbaserad: Ingen Workfront Fusion-licens krävs</p>
   <p>Kopplingsbaserad (äldre): Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Ansluta tjänsten [!DNL Microsoft SQL Server] till Workfront Fusion

Instruktioner om hur du ansluter ditt [!DNL Microsoft SQL Server]-konto till [!UICONTROL Workfront Fusion] finns i [Skapa en anslutning till [!UICONTROL Adobe Workfront Fusion] - grundläggande instruktioner](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>Vissa Microsoft-program använder samma anslutning, som är kopplad till individuella användarbehörigheter. När du skapar en anslutning visas därför alla behörigheter som tidigare har beviljats användarens anslutning, förutom de nya behörigheter som krävs för det aktuella programmet.
>
>Om en användare till exempel har behörighet att läsa tabell som beviljats via Excel-anslutningen och sedan skapar en anslutning i Outlook-anslutningen för att läsa e-post, visar tillståndsskärmen både den behörighet som redan har beviljats för att läsa tabell och den behörighet som nyligen har krävts för att skriva e-post.

## Använder [!DNL Microsoft SQL Server] moduler

Du kan köra din anpassade logik direkt på databasservern via lagrade procedurer. Adobe Workfront Fusion läser in gränssnittet för in-/utdataparametrar och postmängder dynamiskt så att varje parameter eller värde kan mappas individuellt. Innan du börjar konfigurera ditt scenario bör du kontrollera att kontot som du använder för att ansluta till databasen har läsåtkomst till `INFORMATION_SCHEMA.ROUTINES`- och `INFORMATION_SCHEMA.PARAMETERS`-vyer.

När [!DNL Fusion] upprättar anslutningen till [!DNL SQL server]-målet identifierar användaren [!DNL Fusion] värden (domännamnet eller IP-adressen där servern finns) och porten. [!DNL Fusion] kan ansluta till alla tillgängliga värdar och portar.

Mer information om IP-adresser som används av Workfront Fusion finns i [IP-adresser för åtkomst till Adobe Workfront Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)

Mer information om hur du skapar en lagrad procedur finns i [!DNL Microsoft SQL Server]-dokumentationen.

>[!NOTE]
>
>Workfront Fusion stöder inte flera postmängder. Endast den första bearbetas.

## Felsökningsfel [!UICONTROL ER_LOCK_WAIT_TIMEOUT: Lock wait timeout exceeded; try restarting transaction]

Det här felet inträffar när du ändrar samma data med flera moduler. Den orsakas av SQL-transaktioner.

När en SQL-modul körs startar den en transaktion. Transaktionen avslutas när scenariot har slutförts.

Om en annan modul försöker få åtkomst till samma data måste den vänta tills den föregående transaktionen är klar. Eftersom den första transaktionen slutförs efter att scenariot har slutförts kan den andra transaktionen aldrig påbörjas.

### Lösning:

Aktivera Automatisk implementering. Den automatiska implementeringen slutför (verkställer) alla transaktioner omedelbart efter att modulen har körts.

1. Klicka på ikonen [!UICONTROL Scenario settings] ![Scenarioinställningar](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png) längst ned på skärmen.
1. Klicka i kryssrutan **[!UICONTROL Auto commit]**.
1. Klicka på **[!UICONTROL OK]** om du vill spara scenarioinställningarna.
