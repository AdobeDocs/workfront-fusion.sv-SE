---
title: Veeva Vault-moduler
description: I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Veeva Vault samt ansluta det till flera tredjepartsprogram och -tjänster.
author: Becky
feature: Workfront Fusion
exl-id: 2ef967b6-0a69-4801-8574-5f17c9ce991d
source-git-commit: 323e7d10795991bbcb6c1439db0af90e4331e687
workflow-type: tm+mt
source-wordcount: '3681'
ht-degree: 0%

---

# Veeva Vault-moduler

I ett Adobe Workfront Fusion-scenario kan du automatisera arbetsflöden som använder Veeva Vault samt ansluta det till flera tredjepartsprogram och -tjänster.

Instruktioner om hur du skapar ett scenario finns i artiklarna under [Skapa scenarier: artikelindex](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md).

Mer information om moduler finns i artiklarna under [Moduler: artikelindex](/help/workfront-fusion/references/modules/modules-toc.md).

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

## Förutsättningar

Om du vill använda Veeva Vault-moduler måste du ha ett Veeva Vault-konto.

## Connect Veeva Vault till Workfront Fusion

Du kan skapa en anslutning till ditt Vevavaultkonto direkt från en Vevavaultmodul.

När du skapar en anslutning kan du välja om du vill använda ett lösenord eller om OAuth2-autentisering ska användas.

### Anslut till Veeva Vault med ett användarnamn och lösenord

1. Klicka på **Lägg till** intill anslutningsfältet i valfri Vevavaultmodul.
1. Välj **i fältet** Anslutningstyp`Veeva Username Password`.
1. Fyll i följande fält.

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">Anslutningsnamn</td> 
       <td> <p>Ange ett namn för anslutningen.</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">Användarnamn</td>
        <td>
          <p>Ange användarnamnet för Veeva Vault-kontot.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Lösenord</td>
        <td>
          <p>Ange lösenordet för Veeva Vault-kontot.</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">Valv-DNS</td> 
       <td>Ange veeva-valvets DNS (domännamn).</p><p>Om du vill hitta DNS:en för ditt veeva-valv kontrollerar du den URL som du använder för att komma åt veeva-valvet.</p>I URL:en <code>https://my-dns.veevavault.com</code> är till exempel DNS <code>my-dns</code>. Du behöver inte ange hela URL:en.</td> 
      </tr> 
     </tbody> 
    </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.

### Anslut till Veeva Vault med OAuth2-autentisering

1. Klicka på **Lägg till** intill anslutningsfältet i valfri Vevavaultmodul.
1. Välj **i fältet** Anslutningstyp`Veeva Oauth 2`.
1. Fyll i följande fält.

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">Anslutningsnamn</td> 
       <td> <p>Ange ett namn för anslutningen.</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader">Leverantör av auktoriseringsserver</td> 
       <td> <p>Välj den provider som du vill använda för den här autentiseringen.</p> 
       <p><b>OBS!</b> Veeva Vault använder Azure AD-klientautentiseringsuppgifter när Azure väljs som auktoriseringsserverleverantör.</p>
       </td> 
      </tr> 
      <tr> 
       <td role="rowheader">Ping-värd</td> 
       <td> <p>Om du använder PingFederate anger du ping-värden.</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">Omfång</td>
        <td>
          <p>Ange omfattningen för den här anslutningen. Omfånget måste formateras som <code>{Application ID URI}/.default</code>. Program-ID-URI:n måste tillhöra resursen eller appen som visar behörigheter.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Klient-ID</td>
        <td>
          <p>Om du använder Azure AD/Microsoft Entra ID för din auktoriseringsserverleverantör anger du klientorganisations-ID för den här anslutningen.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Klient-ID</td>
        <td>
          <p>Ange klient-ID:t för Veeva Vault-programmet som den här anslutningen ska använda.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Klienthemlighet</td>
        <td>
          <p>Ange klienthemlighet för Veeva-valverappen som den här anslutningen ska använda.</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">Profil-ID</td>
        <td>
          <p>Ange ID för din OAuth2-/Open ID-anslutningsprofil.</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">Valv-DNS</td> 
       <td>Ange veeva-valvets DNS (domännamn).</p><p>Om du vill hitta DNS:en för ditt veeva-valv kontrollerar du den URL som du använder för att komma åt veeva-valvet.</p>I URL:en <code>https://my-dns.veevavault.com</code> är till exempel DNS <code>my-dns.veevavault.com</code>. </td> 
      </tr> 
      <tr>
        <td role="rowheader">Förfallotid för din session i minuter</td>
        <td>
          <p>Ange sessionens förfallotid i minuter.</p>
        </td>
      </tr>
     </tbody> 
    </table>

1. Klicka på **[!UICONTROL Continue]** för att skapa anslutningen och gå tillbaka till modulen.


## Veeva Vault-moduler och deras fält

När du konfigurerar Veeva Vault-moduler visas fälten som listas nedan i Workfront Fusion. Dessutom kan ytterligare Veeva Vault-fält visas, beroende på faktorer som din åtkomstnivå i appen eller tjänsten. En rubrik med fet stil i en modul visar ett obligatoriskt fält.

Om du ser kartknappen ovanför ett fält eller en funktion kan du använda den för att ange variabler och funktioner för det fältet. Mer information finns i [Mappa information från en modul till en annan](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md).

![Växla karta](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [Dokument](#document)
* [Objekt](#object)
* [Övriga](#other)

### Dokument

* [Skapa ett enstaka dokument](#create-a-single-document)
* [Skapa en dokumentrelation](#create-a-single-document-relationship)
* [Skapa flera anteckningar](#create-multiple-annotations)
* [Skapa flera dokument](#create-multiple-documents)
* [Skapa flera dokumentrelationer](#create-multiple-document-relationships)
* [Ta bort ett enstaka dokument](#delete-a-single-document)
* [Ta bort en dokumentrelation](#delete-a-single-document-relationship)
* [Ta bort flera anteckningar](#delete-multiple-annotations)
* [Ta bort flera dokumentrelationer](#delete-multiple-document-relationships)
* [Hämta en fil](#download-file)
* [Exportera dokument](#export-documents)
* [Skaffa ett enda dokument](#get-a-single-document)
* [Hämta dokumentanteckningar](#get-document-annotations)
* [Hämta dokumentrelationer](#get-document-relationships)
* [Initiera användaråtgärd](#initiate-user-action)
* [Visa dokument](#list-documents)
* [Hämta dokumentexportresultat](#retrieve-document-export-results)
* [Uppdatera ett enstaka dokument](#update-a-single-document)
* [Uppdatera flera anteckningar](#update-multiple-annotations)
* [Uppdatera flera dokument](#update-multiple-documents)

#### Skapa ett enstaka dokument

I den här modulen skapas ett dokument, en bindare eller en mall.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa ett dokument, en bindare eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Markera fält</p> </td> 
   <td> <p>Markera de fält som du vill ange data för och ange sedan data i dessa fält.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa en dokumentrelation

Denna åtgärdsmodul skapar en relation mellan två dokument

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Dokument-ID</p> </td> 
   <td> <p>Ange eller mappa ID:t för det dokument där du vill att relationen ska ha sitt ursprung.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Version</p> </td> 
   <td> <p>Markera eller mappa ID:t för den version som du vill skapa en relation för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Måldokument-ID</p> </td> 
   <td> <p>Ange ID:t för dokumentet som relationen pekar på.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Huvudmålversion</p> </td> 
   <td> <p>Ange måldokumentets huvudversion. Detta är talet före punkten.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Delversion av mål</p> </td> 
   <td> <p>Ange måldokumentets huvudversion. Detta är numret efter punkten.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Relationstyp</p> </td> 
   <td> <p>Ange eller mappa den typ av relation som du vill skapa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Skapa flera anteckningar

I den här åtgärdsmodulen kan du skapa upp till 500 anteckningar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Anteckningar</p> </td> 
   <td> <p>För varje anteckning som du vill lägga till klickar du på <b>Lägg till objekt</b> och fyller i de data som beskrivs i <a href="#annotation-fields" class="MCXref xref">Anteckningsfält</a> i den här artikeln.</p> </td> 
  </tr> 
 </tbody> 
</table>

##### Anteckningsfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anteckningstyp </td> 
   <td> <p>Välj den typ av anteckning som du vill skapa.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Ange eller mappa den typ av märkning som du vill använda för den här anteckningen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Sidnummer</p> </td> 
   <td> <p>Ange eller mappa sidnumret där du vill att den här anteckningen ska visas.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>X-koordinat</p> </td> 
   <td> <p>Ange eller mappa placeringsmarkeringens X-koordinat.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Y-koordinat</p> </td> 
   <td> <p>Ange eller mappa placeringsmarkeringens Y-koordinat.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Bredd</p> </td> 
   <td> <p>Ange eller mappa bildens bredd.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Höjd</p> </td> 
   <td> <p>Ange eller mappa placeringsmärket.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Stil</p> </td> 
   <td> <p>Ange eller mappa placeringsmarkeringens format.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Referens</p> </td> 
   <td> <p>En referens gör att anteckningen kan referera till en extern källa. För varje referens som du vill lägga till i anteckningen klickar du på <b>Lägg till objekt</b> och anger referensens typ, dokumentversions-ID och en anteckning.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Markera fält</p> </td> 
   <td> <p>Markera de fält som du vill ange värden för och ange sedan värdena i varje fält. Vilka fält som är tillgängliga beror på anteckningstypen.</p> </td> 
  </tr> 
 </tbody> 
</table>


#### Skapa flera dokument

I den här modulen skapas flera dokument eller mallar med hjälp av en CSV-fil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa mallar eller dokument.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Fildata</p> </td> 
   <td> <p>Mappa den CSV-fil som ska användas för att skapa dokumenten.</td> 
  </tr> 
 </tbody> 
</table>

#### Skapa flera dokumentrelationer

Den här åtgärdsmodulen konfigurerar flera dokumentrelationer.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Indatatyp</p> </td> 
   <td> <p>Välj den typ av indata som du anger för att skapa dessa relationer.</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Fildata</p> </td> 
   <td> <p>Om du använder en CSV-fil anger eller mappar du CSV-filens data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Relationsdata</p> </td> 
   <td> <p>Om du använder JSON, för varje relation som du vill lägga till, klickar du på <b>Lägg till objekt</b> och fyller i de data som beskrivs i <a href="#relationship-fields" class="MCXref xref">Relationsfält</a> i den här artikeln.</p> </td> 
  </tr> 
 </tbody> 
</table>

##### Relationsfält

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Source-dokument-ID </td> 
   <td> <p>Ange eller mappa ID:t för det dokument där du vill att relationen ska ha sitt ursprung.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Source huvudversion</p> </td> 
   <td> <p>Ange huvudversionen av källdokumentet. Detta är talet före punkten.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Source delversion</p> </td> 
   <td> <p>Ange huvudversionen av källdokumentet. Detta är numret efter punkten.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Måldokument-ID</p> </td> 
   <td> <p>Ange ID:t för dokumentet som relationen pekar på.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Huvudmålversion</p> </td> 
   <td> <p>Ange måldokumentets huvudversion. Detta är talet före punkten.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Delversion av mål</p> </td> 
   <td> <p>Ange måldokumentets huvudversion. Detta är numret efter punkten.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader"> <p>Relationstyp</p> </td> 
   <td> <p>Ange eller mappa den typ av relation som du vill skapa.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort ett enstaka dokument

Den här modulen tar bort ett enstaka dokument, en bindare eller en mall.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill ta bort ett dokument, en bindare eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokument-ID / Binder-ID / Mallnamn</p> </td> 
   <td> <p>Markera det objekt som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en dokumentrelation

Den här åtgärdsmodulen tar bort en relation från ett dokument

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Dokument-ID</p> </td> 
   <td> <p>Ange eller mappa ID:t för källdokumentet för relationen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Version</p> </td> 
   <td> <p>Markera eller mappa ID:t för den version som du vill ta bort en relation för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Relation-ID</p> </td> 
   <td> <p>Ange eller mappa ID för relationen som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort flera anteckningar

Den här åtgärdsmodulen tar bort anteckningar. Användaren måste ha behörighet att ta bort anteckningar i Veeva Vault. Du kan ta bort upp till 500 anteckningar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Anteckningar</p> </td> 
   <td> <p>För varje anteckning som du vill ta bort klickar du på <b>Lägg till objekt</b> och anger följande fält.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID</p> </td> 
   <td> <p>Ange eller mappa ID:t för anteckningen som du vill ta bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokumentversions-ID</p> </td> 
   <td> <p>Ange eller mappa dokumentets versionsnummer som innehåller den anteckning som du vill ta bort.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort flera dokumentrelationer

Den här åtgärdsmodulen tar bort relationer från flera dokument

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Indatatyp</p> </td> 
   <td> <p>Välj den typ av indata som du anger för att ta bort dessa relationer.</p> <ul><li>CSV</li><li>JSON</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Fildata</p> </td> 
   <td> <p>Om du använder en CSV-fil anger eller mappar du CSV-filens data.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Relationsdata</p> </td> 
   <td> <p>Om du använder JSON klickar du på <b>Lägg till objekt</b> för varje relation som du vill lägga till och anger relations-ID:t.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### Hämta fil

Den här modulen hämtar ett dokument, en dokumentversion eller en mall från Veeva Vault.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill hämta ett dokument eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Hämtningstyp</p> </td> 
   <td> <p>Välj om du vill hämta ett dokument eller en dokumentversion.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokument-ID / mallnamn</p> </td> 
   <td> <p>Ange eller mappa ID:t för dokumentet eller namnet på mallen som du vill hämta.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Checka ut dokument</p> </td> 
   <td> <p>Om du hämtar ett dokument aktiverar du det här alternativet för att checka ut dokumentet innan du hämtar det.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Version</p> </td> 
   <td> <p>Om du hämtar en dokumentversion väljer du den version du vill hämta.</td> 
  </tr> 
 </tbody> 
</table>

#### Exportera dokument

Den här modulen exporterar dokument som du anger, inklusive källor, återgivningar och text.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill ta bort ett dokument, en bindare eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Källa</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera källfiler i exporten.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Återgivningar</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera återgivningsfiler i exporten.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Alla versioner</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera alla versioner av dokumentfilerna i exporten.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Text</p> </td> 
   <td> <p>Aktivera det här alternativet om du vill inkludera källdokumentstext i exporten.</p></td> 
  </tr> 
 </tbody> 
</table>

#### Skaffa ett enda dokument

Den här modulen hämtar metadata för ett enstaka dokument, en bindare eller en mall.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill hämta data för ett dokument, en bindare eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokument-ID / Binder-ID / Mallnamn</p> </td> 
   <td> <p>Markera de fält som du vill hämta data för.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta dokumentanteckningar

Den här modulen hämtar anteckningar från en specifik dokumentversion. Du kan hämta alla anteckningar eller välja att bara hämta vissa anteckningstyper.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Dokument-ID</p> </td> 
   <td> <p>Markera eller mappa dokumentet som du vill hämta anteckningar för. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Version</p> </td> 
   <td> <p>Markera eller mappa ID:t för den version som du vill hämta anteckningar för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade anteckningar</td> 
   <td>Ange eller mappa det maximala antal anteckningar som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta dokumentrelationer

Den här modulen hämtar alla relationer för ett dokument.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Dokument-ID</p> </td> 
   <td> <p>Markera eller mappa dokumentet som du vill hämta relationer för. </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Version</p> </td> 
   <td> <p>Markera eller mappa ID:t för den version som du vill hämta relationer för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade relationer</td> 
   <td>Ange eller mappa det maximala antalet relationer som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Initiera användaråtgärd

Den här modulen initierar åtgärder för dokument och bindare, som att skicka ett dokument för granskning eller ändra dess tillstånd.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill utföra en åtgärd på ett dokument eller en bindare.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokument/Binder</p> </td> 
   <td> <p>Markera dokumentet eller bindaren som du vill utföra åtgärden på.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Dokumentversion/ Binder-version</p> </td> 
   <td> <p>Markera dokumentet eller bindaren som du vill utföra åtgärden på.</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>Åtgärd</p> </td> 
   <td> <p>Välj den åtgärd som ska utföras på dokumentet eller bindaren.</td> 
  </tr> 
 </tbody> 
</table>

#### Visa dokument

I den här modulen visas alla dokument av den valda typen.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill lista dokument, pärmar eller mallar.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta dokumentexportresultat

Den här modulen returnerar resultatet av en tidigare begärd dokumentexport.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Jobb-ID</p> </td> 
   <td> <p>Ange eller mappa ID:t för jobbet som du vill returnera resultat för. </p> </td> 
  </tr> 
  </tbody> 
</table>

#### Uppdatera flera anteckningar

Den här åtgärdsmodulen uppdaterar upp till 500 anteckningar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Anteckningar</p> </td> 
   <td> <p>För varje anteckning som du vill uppdatera klickar du på <b>Lägg till objekt</b> och fyller i de data som beskrivs i <a href="#annotation-fields" class="MCXref xref">Anteckningsfält</a> i den här artikeln.</p> </td> 
  </tr> 
  </tbody> 
</table>

#### Uppdatera flera dokument

Den här modulen uppdaterar flera dokument eller mallar med hjälp av en CSV-fil.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa mallar eller dokument</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Fildata</p> </td> 
   <td> <p>Mappa den CSV-fil som ska användas för att skapa dokumenten.</td> 
  </tr> 
 </tbody> 
</table>

#### Uppdatera ett enstaka dokument

Den här modulen uppdaterar ett enstaka dokument, en bindare eller en mall.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa ett dokument, en dokumentversion, en bindare eller en mall.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID / Namn</p> </td> 
   <td> <p>Om du uppdaterar en mall anger du ett nytt namn för mallen.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Nytt mallnamn</p> </td> 
   <td> <p>Ange eller mappa ID:t eller namnet på objektet som du vill uppdatera.</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">  <p>Markera fält</p> </td> 
   <td> <p>Markera de fält som du vill ange data för och ange sedan data i dessa fält.</td> 
  </tr> 
 </tbody> 
</table>

### Objekt

* [Skapa en objektspost](#create-a-single-object-record)
* [Ta bort en objektpost](#delete-a-single-object-record)
* [Hämta ett enskilt objekt](#get-a-single-object)
* [Listobjektsposter](#list-objects-records)
* [Uppdatera en objektpost](#update-a-single-object-record)

#### Skapa en objektspost

Den här modulen skapar, kopierar eller djup kopierar en enstaka objektpost.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa eller kopiera en post eller om en post ska djupkopieras.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Migreringsläge</td> 
   <td>Om du skapar eller kopierar en post aktiverar du det här alternativet för att skapa eller uppdatera objektposter i ett icke-initialt läge och med minimal validering, skapa inaktiva poster och ange standardfält och systemhanterade fält som <code>createdby_v</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Inga utlösare</td> 
   <td>Om värdet är true och migreringsläget är aktiverat, kringgår modulen alla system-, standard-, anpassade SDK-utlösare och Action Triggers.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Objektnamn</td> 
   <td>Ange eller mappa objektnamnet__v, till exempel <code>product__v</code>, <code>country__v</code> eller <code>custom_object__c</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Post-ID</td> 
   <td>Om du kopierar en post djupt markerar du den post som ska kopieras.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Postfält</td> 
   <td>Om du kopierar en post djupt markerar du de fält som du vill ange värden för och anger sedan dessa värden.</td> 
  </tr> 
 </tbody> 
</table>

#### Ta bort en objektpost

Den här modulen tar bort eller tar bort en enstaka objektpost. När du tar bort en post tas posten och alla dess underordnade objekt bort.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om en post ska tas bort eller om en post ska tas bort.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Objektnamn</td> 
   <td>Markera det objekt som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Post-ID</td> 
   <td>Markera ID:t för den post som du vill ta bort.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Externt ID</td> 
   <td>I stället för post-ID kan du använda det här användardefinierade dokumentets externa ID.</td> 
  </tr> 
 </tbody> 
</table>

#### Hämta ett enskilt objekt

Den här modulen hämtar metadata som konfigurerats för en specifik objektpost i ditt valv.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Objektnamn</td> 
   <td>Markera det objekt som du vill hämta metadata för.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Post-ID</td> 
   <td>Markera ID:t för den post som du vill hämta metadata för.</td> 
  </tr> 
 </tbody> 
</table>

#### Listobjektsposter

Den här modulen hämtar alla vaultobjekt i det autentiserade valvet.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Hämta lokaliserade etiketter</p> </td> 
   <td> <p>Välj Ja om du vill hämta lokaliserade (översatta) strängar för objektfälten label och label_plural.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>

<!--#### Update a single object record-->

Den här modulen uppdaterar fält i en befintlig objektpost.

Den här modulen skapar, kopierar eller djup kopierar en enstaka objektpost.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa eller kopiera en post eller om en post ska djupkopieras.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Migreringsläge</td> 
   <td>Aktivera det här alternativet om du vill skapa eller uppdatera objektposter i ett icke-initialt läge och med minimal validering, skapa inaktiva poster och ange standardfält och systemhanterade fält som <code>createdby_v</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Inga utlösare</td> 
   <td>Om migreringsläget är aktiverat kan du aktivera det här alternativet för att kringgå alla system-, standard-, anpassade SDK-utlösare och Action Triggers.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Objektnamn</td> 
   <td>Ange eller mappa objektnamnet__v, till exempel <code>product__v</code>, <code>country__v</code> eller <code>custom_object__c</code>.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Post-ID</td> 
   <td>Markera ID:t för den post som ska uppdateras.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Läge</td> 
   <td>Ange postens livscykeltillstånd när <code>X-VaultAPI-MigrationMode</code> har värdet true.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Tillståndsetikett</td> 
   <td>Ange postens livscykeltillståndstyp när <code>X-VaultAPI-MigrationMode</code> har värdet true. Använd formatet <code>base:object_lifecycle:</code> följt av objektets tillståndstyp.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Postfält</td> 
   <td>Om du kopierar en post djupt markerar du de fält som du vill ange värden för och anger sedan dessa värden.</td> 
  </tr> 
 </tbody> 
</table>

### Övriga

* [Göra ett anpassat API-anrop](#make-a-custom-api-call)
* [Gör en VQL-fråga](#make-a-vql-query)
* [Läs loggar](#read-logs)

#### Göra ett anpassat API-anrop

Den här åtgärdsmodulen gör ett anpassat anrop till veeva Vault API.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning</td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>Ange en relativ sökväg till <code>baseurl/api/v</code>.  Till exempel: <code>/objects/documents</code>. Inkludera inte <code>baseurl/api/v/</code> eftersom det redan ingår.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Metod</td> 
   <td> <p>Välj den HTTP-förfrågningsmetod som du behöver för att konfigurera API-anropet. Mer information finns i <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">Metoder för HTTP-begäran</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Sidhuvuden</td> 
   <td> <p>Lägg till rubrikerna för begäran i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion lägger till auktoriseringsrubrikerna åt dig.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Frågesträng</td> 
   <td> <p>Lägg till frågan för API-anropet i form av ett standard-JSON-objekt.</p> <p>Exempel: <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Brödtext</td> 
   <td> <p>Lägg till brödinnehållet för API-anropet i form av ett standard-JSON-objekt.</p> <p>Obs!  <p>När du använder villkorssatser som <code>if</code> i JSON placerar du citattecknen utanför villkorssatsen.</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Gör en VQL-fråga

Den här modulen skapar en fråga med VQL (Vault Query Language).

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Typ</p> </td> 
   <td> <p>Välj om du vill skapa mallar eller dokument</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>Fildata</p> </td> 
   <td> <p>Mappa den CSV-fil som ska användas för att skapa dokumenten.</td> 
  </tr> 
 </tbody> 
</table>

#### Läs loggar

Den här modulen returnerar data från granskningsspår

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Anslutning </td> 
   <td> <p>Instruktioner om hur du ansluter ditt Vevaevavalskonto till Workfront Fusion finns i <a href="#connect-veeva-vault-to-workfront-fusion" class="MCXref xref">Anslut Vevajevault till Workfront Fusion</a> i den här artikeln.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Granskningstyp</p> </td> 
   <td> <p>Välj den granskningstyp som du vill hämta data för.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Startdatum</p> </td> 
   <td> <p>Ange eller mappa startdatumet för de granskningar som du vill hämta.</p><p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Slutdatum</p> </td> 
   <td> <p>Ange eller mappa slutdatumet för granskningarna som du vill hämta.</p><p>En lista över vilka datum- och tidsformat som stöds finns i <a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">Typtvång</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Resultat-URL </p> </td> 
   <td> <p>Välj CSV om du vill hämta en URL för att hämta en CSV-fil med resultatet.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Maximalt antal returnerade resultat</td> 
   <td>Ange eller mappa det maximala antal poster som du vill att modulen ska returnera under varje körningscykel för scenario.</td> 
  </tr> 
 </tbody> 
</table>
