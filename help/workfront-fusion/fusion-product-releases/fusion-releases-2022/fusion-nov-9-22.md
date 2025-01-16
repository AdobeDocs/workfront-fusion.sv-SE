---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: 'Versionsaktivitet för Workfront Fusion: 7 november 2022'
description: Den här sidan beskriver alla förbättringar som gjorts i Adobe Workfront Fusion under veckan 7 november 2022.
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 9d58abd0-1fe7-43c8-a1ea-2fadea738590
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# Versionsaktivitet för Workfront Fusion: 7 november 2022

**Optimering av webbkrokkön**

Fusions webbkrokkkö har optimerats med den här versionen. Tjänsten som accepterar webhooks är nu skild från köer och andra processer. Den här ändringen gör det möjligt för Fusion att bearbeta webkrokköer med en snabbare och mer konsekvent hastighet.

Under implementeringen av den här ändringen kunde vi bättre förstå den förväntade loggbearbetningstiden för webkrofthändelser i kö. Fusions webbkrokvisningsprogramsida förväntas inte vara äldre än 1 minut.

Navigera till Webhooks i den vänstra navigeringen om du vill se webbkrockshändelser som står i kö. Lastikoner med ett nummer i täljaren anger köhändelser för den webkroken. Klicka på lastbilsikonen för att se de köade händelserna.


**Oanvända webbhooks kommer nu att inaktiveras eller tas bort**

Vi har gjort några ändringar i hur Workfront Fusion hanterar oanvända webbhooks. Nu inaktiveras webhooks automatiskt om något av följande gäller:

* Webbkroken har inte varit ansluten till något scenario på mer än fem dagar.
* Webkroken används bara i inaktiva scenarier, som har varit inaktiva i mer än 30 dagar.

Inaktiverade webhooks tas bort och avregistreras automatiskt om de inte är anslutna till några scenarier och har inaktiverats i över 30 dagar.
