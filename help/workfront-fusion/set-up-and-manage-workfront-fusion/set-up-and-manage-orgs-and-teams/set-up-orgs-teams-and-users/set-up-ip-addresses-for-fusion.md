---
title: Konfigurera IP-adresser för Fusion i din organisations tillåtelselista
description: Fusion använder specifika IP-adresser och domäner för webbkommunikation. Dessa måste läggas till i din organisations tillåtelselista innan du kan använda Workfront i din organisation.
author: Becky
feature: Workfront Fusion
exl-id: 406dd45c-0863-4270-a80e-c1c115e0b367
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Konfigurera IP-adresser för Fusion i din organisations tillåtelselista

Eftersom Adobe Workfront Fusion kommunicerar med din organisations nätverk måste din organisations brandvägg vara konfigurerad så att den kan kommunicera. Brandväggar är mycket effektiva säkerhetsåtgärder som fungerar genom att en organisations nätverk skiljs från internet. De ser till att endast utvalda data- och nätverkstrafik kan flyttas in i eller ut ur organisationens nätverk. Brandväggen tillåter eller blockerar data baserat på den webbplats som skickar eller tar emot data. Som Fusion-administratör måste du se till att data som skickas till eller från Fusion kan passera genom organisationens brandvägg.

Detta uppnås genom en tillåtelselista, som i huvudsak är en lista över webbplatser som&quot;tillåts&quot; att skicka eller ta emot data via brandväggen. Platserna kan identifieras på ett av två sätt:

* **IP-adress**: en serie siffror som 52.31.132.175
* **Domän**: del av en URL, till exempel `thisdomain` i `www.thisdomain.com`

Fusion använder specifika IP-adresser och domäner för webbkommunikation. Dessa måste läggas till i din organisations tillåtelselista innan du kan använda Workfront i din organisation.

Vanligtvis konfigureras en tillåtelselista av en nätverksadministratör. Samarbeta med organisationens nätverksadministratör för att säkerställa att brandväggen tillåter dessa IP-adresser. Om du inte vet vem din nätverksadministratör är kan din organisations IT-avdelning peka dig i rätt riktning.

>[!IMPORTANT]
>
>Som Fusion-administratör måste du se till att dessa IP-adresser och domäner läggs till i din organisations tillåtelselista. Detta gäller även om du inte själv lägger till dem. Fusion kan inte konfigurera din organisations tillåtelselista.

Du kan lägga till alla Fusion-IP-adresser och domäner på tillåtelselista, eller så kan du hitta ditt Fusion-kluster och bara lägga till IP-adresser och domäner för det klustret.

## Lägg till alla Fusion-IP-adresser och domäner

Lägg till följande IP-adresser i tillåtelselista:

* 52.30.133.50
* 54.220.93.204
* 34.254.76.122
* 54.244.142.219
* 52.39.217.230
* 44.241.82.96
* 100.20.126.137
* 34.223.32.4
* 52.39.176.220
* 20.36.133.48/28
* 20.81.156.240/28
* 172.172.84.48/28

Om din organisation använder utgående nätverksfiltrering lägger du till följande domän i tillåtelselista för att ge ditt system tillgång till Workfront Fusion.

* hook.app.workfrontfusion.com
* hook.app-eu.workfrontfusion.com
* hook.app-az.workfrontfusion.com

## Lägg endast till Fusion-IP-adresser och domäner för ditt kluster

### Identifiera ditt datacenter

IP-adresserna varierar beroende på var data lagras.

Om du kommer åt Fusion via en URL kan du leta rätt på ditt datacenter genom att undersöka URL:en.

| URL | Datacenter |
| --- | --- |
| `https://app.workfrontfusion.com` | Amerikanskt datacenter |
| `https://app-eu.workfrontfusion.com` | EU datacenter |
| `https://app-az.workfrontfusion.com` | Azure-kluster |

Om du ansluter till Fusion via `experience.adobe.com` kan du kontrollera nätverksfliken i webbläsaren för att identifiera datacentret.

| URL | Datacenter |
| --- | --- |
| Anrop till `https://fusion.adobe.com` | Amerikanskt datacenter |
| Anrop till `https://eu.fusion.adobe.com` | EU datacenter |
| Anrop till `https://az.fusion.adobe.com` | Azure-kluster |

### Lägg till IP-adresser och domäner för ditt datacenter

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront EU Datacenter</td> 
   <td> 
    <ul> 
     <li>52.30.133.50</li> 
     <li>54.220.93.204</li> 
     <li>34.254.76.122</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Adobe Workfront US Datacenter</p> </td> 
   <td> 
    <ul> 
     <li>54.244.142.219</li> 
     <li>52.39.217.230</li> 
     <li>44.241.82.96</li>
     <li>100.20.126.137</li>
     <li>34.223.32.4</li>
     <li>52.39.176.220</li>
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion på Microsoft Azure-klustret</td> 
   <td> 
    <ul> 
     <li>20.36.133.48/28</li> 
     <li>20.81.156.240/28</li> 
     <li>172.172.84.48/28</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Om din organisation använder utgående nätverksfiltrering lägger du till följande domän i tillåtelselista för att ge ditt system tillgång till Workfront Fusion. De här används för webbhooks

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront EU Datacenter</td> 
   <td> <p> hook.app-eu.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Adobe Workfront US Datacenter</p> </td> 
   <td> <p>hook.app.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Adobe Workfront Fusion på Microsoft Azure-klustret</p> </td> 
   <td> <p>hook.app-az.workfrontfusion.com </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Utgående nätverksfiltrering är ovanlig. Fråga nätverksadministratören om du behöver uppdatera tillåtelselista för att få plats.
