---
title: Körning av scenarier, cykler och faser
description: I den här artikeln beskrivs händelser som inträffar när ett  [!DNL Adobe Workfront Fusion] scenario körs, till exempel initiering, åtgärder, implementeringar och återställningar.
author: Becky
feature: Workfront Fusion
exl-id: abf41be5-df32-4eaf-b3f4-93ddf005bfe3
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# Körning av scenarier, cykler och faser

Varje scenariokörning börjar med initieringsfasen, fortsätter med minst en cykel bestående av operations- och implementerings-/återställningsfaserna och avslutas med slutförandefasen

* Initiering
* Cykel 1
   * Åtgärd (läsa eller skriva)
   * Verkställ eller återställ
* Cykel 2
   * Åtgärd (läsa eller skriva)
   * Verkställ eller återställ
* ...
* Bläddra #n
   * Åtgärd (läsa eller skriva)
   * Verkställ eller återställ
* Slutför

På en mindre skala följer varje modul även dessa faser. Information om modulfaserna finns i den bearbetade paketinformationen, som finns i den numrerade bubblan högst upp till höger i varje modul när scenariot har körts. Mer information om hur du hittar information om bearbetade paket finns i [Information om bearbetade paket](/help/workfront-fusion/references/scenarios/scenario-execution-flow.md#information-about-processed-bundles) i artikelscenariets körningsflöde.

Information om de större scenariofaserna finns i körningsinformationen.

## Scenario körningsfaser

### Initiering

Under initieringsfasen skapas och kontrolleras alla nödvändiga anslutningar (anslutning till en databas, e-posttjänst och så vidare) för att säkerställa att modulen kan utföra de avsedda åtgärderna.

### Cyklar

Varje cykel representerar en odelbar arbetsenhet som består av en serie åtgärder, där varje åtgärd är en implementering eller återställning.

Du kan ange maximalt antal cykler på panelen [!UICONTROL scenario settings]. Standardvärdet är 1.

* [Åtgärd](#operation)
* [Verkställ](#commit)
* [Återställning](#rollback)

#### Åtgärd

Under operationsfasen utförs en läs- eller skrivåtgärd

* En läsåtgärd består av att hämta data från en tjänst som sedan bearbetas av andra moduler enligt ett fördefinierat scenario. Modulen [!UICONTROL Workfront] >[!UICONTROL Watch records] returnerar till exempel nya paket (poster) som skapats sedan den senaste scenariokörningen.
* En skrivåtgärd består av att skicka data till en viss tjänst för vidare bearbetning. Modulen [!DNL Workfront] >[!UICONTROL Upload Document] överför till exempel en fil till Workfront.

#### Verkställ

Om operationsfasen lyckas börjar den implementeringsfas under vilken alla åtgärder som utförs av modulerna verkställs. Det innebär att [!DNL Workfront Fusion] skickar information till alla tjänster som är inblandade i operationsfasen om att åtgärden lyckades.

### Återställning

Om ett fel inträffar under operations- eller implementeringsfasen i en modul avbryts fasen och återställningsfasen startas, vilket gör alla åtgärder under den angivna cykeln void.

>[!IMPORTANT]
>
>Alla [!DNL Workfront Fusion]-moduler som stöder återställning (kallas även för transaktioner) markeras med ACID-taggen.
>
>![Acid-moduler](assets/acid-modules.png)
>
>Moduler som inte är markerade med den här taggen kan inte återställas till det ursprungliga läget när fel inträffar i andra moduler. Ett typiskt exempel på en modul som inte är en ACID-modul är åtgärden [!UICONTROL Email] >[!UICONTROL Send an Email]. När e-postmeddelandet har skickats kan du inte ångra det.

### Slutför

Under slutförandefasen stängs öppna anslutningar (till exempel FTP-anslutningar, databasanslutningar och så vidare) och scenariot slutförs.

## Resurs

Mer information finns i [Konfigurera scenarioinställningar](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md).
