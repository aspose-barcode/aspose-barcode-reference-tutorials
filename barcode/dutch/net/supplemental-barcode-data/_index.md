---
date: 2026-03-07
description: Leer hoe u een EAN‑2‑barcode maakt en barcodegeneratie in .NET uitvoert
  met Aspose.BarCode voor .NET. Beheers vandaag nog de aanpassing van aanvullende
  barcode‑gegevens!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Maak EAN‑2‑barcode met Aspose.BarCode voor .NET
url: /nl/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EAN-2 barcode maken met Aspose.BarCode voor .NET

## Inleiding

Als je een .NET‑ontwikkelaar bent die **een EAN-2 barcode** wil maken en de kracht van aanvullende barcode‑gegevens wil benutten, ben je op de juiste plek. In deze uitgebreide gids lopen we alles door wat je moet weten—van basisconfiguratie tot het fijn afstellen van de ruimte rond je symbolen. Of je nu een nieuw voorraadbeheersysteem bouwt of een bestaande point‑of‑sale‑applicatie verbetert, het beheersen van deze functies maakt je .NET‑projecten voor barcode‑generatie flexibeler en betrouwbaarder.

## Snelle antwoorden
- **Wat kan ik genereren?** EAN‑2 en EAN‑5 aanvullende barcodes.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoeveel code is er nodig?** Slechts een paar regels—Aspose.BarCode doet het zware werk.  
- **Kan ik de spatiëring aanpassen?** Ja, je kunt X‑dimension en supplement‑ruimte direct regelen.

## Wat zijn aanvullende barcode‑gegevens?

Aanvullende barcode‑gegevens verwijzen naar de kleine extra symbolen (EAN‑2, EAN‑5) die naast een primaire barcode verschijnen, meestal gebruikt voor uitgavenummers, prijsuitbreidingen of andere aanvullende informatie. Aspose.BarCode voor .NET stelt je in staat deze symbolen programmatisch te genereren, waardoor je volledige controle hebt over uiterlijk en plaatsing.

## Waarom Aspose.BarCode voor .NET gebruiken?

- **Volledige .NET‑integratie** – werkt met C#, VB.NET en F#.  
- **Hoge‑kwaliteit rendering** – produceert scanbare barcodes bij elke resolutie.  
- **Uitgebreide aanpassing** – van symbologie‑type tot X‑dimension, quiet zones en supplement‑ruimte.  
- **Geen externe afhankelijkheden** – pure managed library, eenvoudig te implementeren.

## Configuratie van aanvullende barcode‑gegevens

Laten we beginnen met het verkennen van de configuratie van aanvullende barcode‑gegevens. Aspose.BarCode voor .NET biedt je de tools om aanvullende barcodes moeiteloos te genereren, waardoor je volledige controle krijgt over EAN‑2 en EAN‑5 barcodes. Maar hoe begin je?

Allereerst download en installeer je Aspose.BarCode voor .NET. Je kunt een gratis proefversie uitproberen om de krachtige functies in actie te zien. Zodra je klaar bent, volg je onze stap‑voor‑stap‑gids, die je door het proces leidt en ervoor zorgt dat je de configuratie van aanvullende barcode‑gegevens gemakkelijk onder de knie krijgt.

Aan het einde van deze sectie heb je een solide begrip van hoe je EAN‑2 en EAN‑5 barcodes maakt, waardoor je een veelzijdigere .NET‑ontwikkelaar wordt.

## Hoe maak je een EAN-2 barcode? (Configuratiestappen)

1. **Instantieer de barcode‑generator** – kies de `BarcodeGenerator`‑klasse en stel de symbologie in op `EncodeTypes.EAN13` (of een ander primair type).  
2. **Schakel het aanvullende deel in** – stel de `SupplementData`‑eigenschap in op de gewenste numerieke tekenreeks (bijv. `"12"` voor een EAN‑2‑supplement).  
3. **Pas de visuele instellingen aan** – wijzig eventueel `XDimension`, `BarHeight` en `QuietZone` om aan je lay-outvereisten te voldoen.  
4. **Opslaan of renderen** – roep `Save` aan om de afbeelding naar een bestand of stream te schrijven.

> *Pro tip:* Houd de lengte van de aanvullende gegevens precies 2 cijfers voor EAN‑2 en 5 cijfers voor EAN‑5; anders kan de barcode onleesbaar worden.

## Aanpassing van de ruimte voor aanvullende barcode

In de wereld van barcodes is aanpasbaarheid cruciaal, en dat is waar Aspose.BarCode voor .NET schittert. Laten we nu focussen op de aanpassing van de ruimte voor aanvullende barcode. Dit aspect draait om het regelen van de X‑Dimension en de supplement‑ruimte in je barcodes.

Opnieuw begin je met het installeren van Aspose.BarCode voor .NET en maak je gebruik van de gratis proefversie. Vervolgens volg je onze aanwijzingen over hoe je de ruimte in je barcodes kunt aanpassen. Deze aanpassing kan buitengewoon nuttig zijn voor diverse toepassingen, van voorraadbeheer tot point‑of‑sale‑systemen.

De vrijheid om je barcodes aan te passen aan je specifieke behoeften is een waardevolle vaardigheid, en deze sectie zorgt ervoor dat je goed uitgerust bent.

## Hoe pas je de supplement‑ruimte aan?

- **X‑Dimension** – definieert de breedte van een enkele module; grotere waarden vergroten de totale barcode‑grootte.  
- **Supplement Space** – de ruimte tussen de primaire barcode en het aanvullende deel; pas aan via de `SupplementSpace`‑eigenschap.  
- **Quiet Zone** – de verplichte lege marge rond de volledige barcode; houd deze minimaal 10 X‑Dimension‑eenheden voor betrouwbare scanning.

Experimenteer met deze instellingen in een testproject totdat je de visuele balans bereikt die nodig is voor je scanner‑hardware.

## Veelvoorkomende gebruikssituaties

| Scenario | Waarom aanvullende gegevens helpen |
|----------|--------------------------------------|
| **Retail prijsuitbreidingen** | EAN‑5 kan prijsinformatie direct op het label coderen. |
| **Tijdschriftuitgavenummers** | EAN‑2 identificeert de uitgave, waardoor snel sorteren mogelijk is. |
| **Logistiek & tracking** | Het toevoegen van een klein supplement aan een primaire barcode geeft extra routeringsgegevens zonder de labelgrootte te vergroten. |

## Tutorials voor aanvullende barcode‑gegevens
### [Configuratie van aanvullende barcode‑gegevens](./supplemental-barcode-data-configuration/)
Genereer aanvullende barcode‑gegevens met Aspose.BarCode voor .NET. Pas EAN-2 en EAN-5 barcodes moeiteloos aan. Stapsgewijze gids voor .NET‑ontwikkelaars.
### [Aanpassing van de ruimte voor aanvullende barcode](./supplemental-barcode-space-customization/)
Pas barcodes eenvoudig aan met Aspose.BarCode voor .NET. Regel X‑Dimension en supplement‑ruimte. Probeer de gratis proefversie!

## Veelgestelde vragen

**Q: Kan ik zowel EAN‑2 als EAN‑5 genereren met dezelfde code?**  
A: Ja. Verander eenvoudig de lengte van `SupplementData` (2 cijfers voor EAN‑2, 5 cijfers voor EAN‑5) en de bibliotheek rendert de juiste symbologie.

**Q: Moet ik controlecijfers berekenen voor het supplement?**  
A: Nee. Aspose.BarCode berekent en voegt automatisch de vereiste controlecijfers toe.

**Q: Is er een limiet aan hoeveel barcodes ik in een lus kan genereren?**  
A: De bibliotheek is geoptimaliseerd voor bulkgeneratie; let wel op het geheugenverbruik bij het verwerken van zeer grote afbeeldingscollecties.

**Q: Hoe embed ik de barcode in een PDF‑ of Word‑document?**  
A: Sla de barcode op als afbeelding (PNG, JPEG, etc.) en voeg deze vervolgens in met je favoriete document‑generatie‑API (bijv. Aspose.PDF of Aspose.Words).

**Q: Wat als mijn scanner het aanvullende deel niet kan lezen?**  
A: Controleer of de `SupplementSpace` minimaal 2 X‑Dimension‑eenheden is en of de quiet zone voldoet aan de specificaties van de scanner.

---

**Laatst bijgewerkt:** 2026-03-07  
**Getest met:** Aspose.BarCode for .NET 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}