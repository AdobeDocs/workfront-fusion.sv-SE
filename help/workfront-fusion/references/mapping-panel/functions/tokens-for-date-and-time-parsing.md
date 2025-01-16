---
title: Token för datum- och tidanalys
description: Följande tokens för datum- och tidsanalys är tillgängliga på panelen  [!DNL Adobe Workfront Fusion mapping] .
author: Becky
feature: Workfront Fusion
exl-id: d3242af3-89e8-45ae-81a1-3b4dadf824fd
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Token för datum- och tidanalys

## Tokens för år, månad och dag

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Indata </th> 
   <th>Exempel </th> 
   <th> <p>Beskrivning</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>YYYY </code> </td> 
   <td><code>2014 </code> </td> 
   <td> <p>4- eller 2-siffrigt år</p> </td> 
  </tr> 
  <tr> 
   <td><code>YY</code></td> 
   <td><code>14</code></td> 
   <td> <p>Tvåsiffrigt år</p> </td> 
  </tr> 
  <tr> 
   <td><code>Y</code> </td> 
   <td><code>-25</code> </td> 
   <td> <p>[!UICONTROL Year with any number of digits and sign]</p> </td> 
  </tr> 
  <tr> 
   <td><code>Q</code> </td> 
   <td><code>1..4</code> </td> 
   <td> <p> Kvartal på året. Anger månad till första månaden i kvartal.</p> </td> 
  </tr> 
  <tr> 
   <td><code>M MM</code> </td> 
   <td><code>1..12</code> </td> 
   <td> <p> Månadsnummer</p> </td> 
  </tr> 
  <tr> 
   <td><code>MMM MMMM</code> </td> 
   <td><code>Jan..December</code> </td> 
   <td> <p> Månadsnamn</p> </td> 
  </tr> 
  <tr> 
   <td><code>D DD</code> </td> 
   <td><code>1..31</code> </td> 
   <td> <p> Dag i månaden</p> </td> 
  </tr> 
  <tr> 
   <td><code>Do </code> </td> 
   <td><code>1st..31st</code> </td> 
   <td> <p> Dag i månaden med ordningstal</p> </td> 
  </tr> 
  <tr> 
   <td><code>DDD DDDD</code> </td> 
   <td><code>1..365</code></td> 
   <td> <p> Dag på året</p> </td> 
  </tr> 
  <tr> 
   <td><code>X</code> </td> 
   <td><code>1410715640.579</code> </td> 
   <td> <p> Unix tidsstämpel</p> </td> 
  </tr> 
  <tr> 
   <td><code>x</code> </td> 
   <td><code>1410715640579</code> </td> 
   <td> <p> Unix ms-tidsstämpel</p> </td> 
  </tr> 
 </tbody> 
</table>

## Tokens för veckoår, vecka och veckodag

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Indata </th> 
   <th>Exempel </th> 
   <th> <p>Beskrivning</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>ddd dddd</code> </td> 
   <td><code>Mon...Sunday</code> </td> 
   <td> <p> Dag</p> </td> 
  </tr> 
  <tr> 
   <td><code>GGGG</code> </td> 
   <td><code>2014</code> </td> 
   <td> <p> ISO 4-siffrig vecka år</p> </td> 
  </tr> 
  <tr> 
   <td><code>GG </code> </td> 
   <td><code>14</code> </td> 
   <td> <p> Tvåsiffrig ISO-veckoår</p> </td> 
  </tr> 
  <tr> 
   <td><code>W WW</code> </td> 
   <td><code>1..53</code></td> 
   <td> <p> ISO-vecka på år</p> </td> 
  </tr> 
  <tr> 
   <td><code>E</code> </td> 
   <td><code>1..7</code> </td> 
   <td> <p> ISO-veckodag</p> </td> 
  </tr> 
 </tbody> 
</table>

## Token för timme, minut, sekund, millisekund och offset

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Indata </th> 
   <th>Exempel </th> 
   <th> <p>Beskrivning</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>H HH</code> </td> 
   <td><code>0..23</code></td> 
   <td> <p> Timmar (24-timmarstid)</p> </td> 
  </tr> 
  <tr> 
   <td><code>h hh</code> </td> 
   <td><code>1..12</code> </td> 
   <td> <p> Timmar (12 timmars tid använd med A.)</p> </td> 
  </tr> 
  <tr> 
   <td><code>k kk</code> </td> 
   <td><code>1..24</code> </td> 
   <td> <p> Timmar (24 timmars tid från 1 till 24)</p> </td> 
  </tr> 
  <tr> 
   <td><code>a A</code> </td> 
   <td><code>am pm</code> </td> 
   <td> <p> Post- eller ante-matrisdiem (observera att ett tecken a p också anses vara giltigt)</p> </td> 
  </tr> 
  <tr> 
   <td><code>m mm</code> </td> 
   <td><code>0..59</code> </td> 
   <td> <p> Minuter</p> </td> 
  </tr> 
  <tr> 
   <td><code>s ss</code> </td> 
   <td><code>0..59</code> </td> 
   <td> <p> Sekunder</p> </td> 
  </tr> 
  <tr> 
   <td><code>S SS SSS</code> </td> 
   <td><code>0..999</code> </td> 
   <td> <p> Fractionsekunder</p> </td> 
  </tr> 
  <tr> 
   <td><code>Z ZZ</code> </td> 
   <td><code>+12:00</code> </td> 
   <td> <p> Förskjutning från UTC som +-HH:mm, +-HHmm eller Z</p> </td> 
  </tr> 
 </tbody> 
</table>
