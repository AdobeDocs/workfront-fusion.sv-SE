---
title: Mappa en fil mellan moduler
description: Vissa moduler kan bearbeta filer. Dessa moduler kan antingen returnera en utdatafil som ska skickas för vidare bearbetning eller kräva att en fil skickas till dem för bearbetning. Innan dessa moduler kan användas tillsammans för att bearbeta filer måste de mappas till varandra.
author: Becky
feature: Workfront Fusion
exl-id: 25c632f4-169e-4d3c-989a-f57b398bd3f0
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Mappa en fil mellan moduler

Vissa moduler kan bearbeta filer. Dessa moduler kan antingen returnera en utdatafil som ska skickas för vidare bearbetning eller kräva att en fil skickas till dem för bearbetning. Filer kan mappas så att en fil som skrivs ut från en modul kan bearbetas av en annan.

## Åtkomstkrav

+++ Expandera om du vill visa åtkomstkrav för funktionerna i den här artikeln.

Du måste ha följande åtkomst för att kunna använda funktionerna i den här artikeln:

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront package</td> 
   <td> <p>Alla</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront-licens</td> 
   <td> <p>Nytt: Standard</p><p>eller</p><p>Aktuell: [!UICONTROL Work] eller högre</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion-licens**</td> 
   <td>
   <p>Aktuell: Inga Workfront Fusion-licenser krävs.</p>
   <p>eller</p>
   <p>Äldre: Alla </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Produkt</td> 
   <td>
   <p>Nytt:</p> <ul><li>[!UICONTROL Select] eller [!UICONTROL Prime] Workfront-plan: Din organisation måste köpa Adobe Workfront Fusion.</li><li>[!UICONTROL Ultimate] Workfront: Workfront Fusion ingår.</li></ul>
   <p>eller</p>
   <p>Aktuell: Din organisation måste köpa Adobe Workfront Fusion.</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">Konfigurationer på åtkomstnivå*</td> 
   <td> 
     <p>Du måste vara Workfront Fusion-administratör för din organisation.</p>
     <p>Du måste vara Workfront Fusion-administratör för ditt team.</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

Mer information om informationen i den här tabellen finns i [Åtkomstkrav i dokumentationen](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md).

Mer information om Adobe Workfront Fusion-licenser finns i [Adobe Workfront Fusion-licenser](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md).

+++

## Mappa filer från källmoduler till målmoduler

Modulerna kan bearbeta filer och kräver två informationsdelar:

* Filnamn
* Filinnehåll (data)

Om någon tidigare modul genererar en fil kan du välja källmodulen och namnet och data för den modulens utdata mappas till målmodulen.

Du kan också ange det här namnet och data manuellt eller mappa det från tidigare moduler. Detta kan vara praktiskt när du t.ex. byter namn på en fil.

>[!NOTE]
>
>Om du behöver bearbeta en fil från en URL rekommenderar vi att du använder modulen `HTTP > Get a File` för att hämta filen från URL:en och sedan mappar filen från modulen `HTTP > Get a File` till fältet för den önskade modulen i ditt scenario.
>
>![Mappningsfil](assets/map-source-file.png)

Så här mappar du en fil:

1. Klicka på fliken **[!UICONTROL Scenarios]** i den vänstra panelen.
1. Välj det scenario där du vill mappa en fil.
1. Klicka någonstans i scenariot för att öppna Scenarioredigeraren.
1. I målmodulen, som är det mål som du mappar till, letar du reda på **Source-filområdet**.
1. Om du vill mappa en fils utdata från en tidigare modul markerar du modulen som utdata från filen.

   ![Workfront nedladdningsdokument](assets/wf-download-document.png)

1. Om du vill mappa namn och data manuellt väljer du Karta och anger eller mappar sedan filens namn och data.

   ![Använd kartalternativet](assets/use-the-map-option.png)

1. Fortsätt konfigurera modulen eller klicka på **OK**.
