---
date: 2026-09-28
description: Leer hoe u een aangepaste barcode-ruimte kunt creëren voor GS1-coupons
  met Aspose.BarCode voor .NET en de leesbaarheid van barcodes verbetert. Volg onze
  stapsgewijze gids.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 Coupon Supplement Ruimteconfiguratie
og_description: Leer hoe u een aangepaste barcode-ruimte kunt creëren voor GS1-coupons
  met Aspose.BarCode voor .NET en de leesbaarheid van barcodes verbetert. Stapsgewijze
  code en tips inbegrepen.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Maak aangepaste barcode-ruimte voor GS1 coupon supplement – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Hoe een aangepaste barcode-ruimte te maken voor GS1-couponaanvulling
url: /nl/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1-coupon supplementruimte configuratie

In deze tutorial zult u **barcode aangepaste ruimte** creëren voor de GS1 Coupon Supplement Space met Aspose.BarCode voor .NET. Het aanpassen van de supplementruimte is essentieel wanneer u de **leesbaarheid van barcodes** moet verhogen op scanners met lage resolutie of moet voldoen aan door de retailer opgelegde marges. Aan het einde van deze gids begrijpt u waarom de supplementruimte belangrijk is, hoe u deze programmatically instelt, en hoe u afbeeldingen genereert met verschillende pixelwaarden.

## Snelle antwoorden
- **Wat regelt de supplementruimte?** Het definieert het lege gebied (in pixels) tussen de coupongegevens en de rest van de barcode.  
- **Welk barcode-type wordt gebruikt?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Kan ik de grootte van de ruimte wijzigen?** Ja – stel `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` in op een geheel getal.  
- **Heb ik een licentie nodig voor deze functie?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke uitvoerformaten worden ondersteund?** PNG, JPEG, BMP, GIF, TIFF, en meer via `BarCodeImageFormat`.

## Wat is GS1-coupon supplementruimte?
De GS1 Coupon Supplement Space is een gedefinieerd leeg gebied dat voorkomt in GS1‑Databar coupon barcodes. Retailsystemen gebruiken deze ruimte om de scanbetrouwbaarheid te verbeteren en te voldoen aan branchespecificaties die een minimale marge rond de aanvullende gegevens vereisen.

## Waarom de supplementruimte configureren?
De supplementruimte verhoogt direct de **leesbaarheid van barcodes** en helpt u te voldoen aan strikte retailerrichtlijnen. Door extra pixels toe te voegen vermindert u de kans op foutieve scans op scanners met lage resolutie, zorgt u voor consistente scanning over verschillende labelgroottes, en krijgt u visuele flexibiliteit om de barcode in een afgedrukt ontwerp in balans te brengen.

## Voorwaarden

Voordat we ingaan op het configureren van de GS1 Coupon Supplement Space met Aspose.BarCode voor .NET, zorg ervoor dat u het volgende heeft:

1. **Visual Studio** – De primaire IDE voor .NET-ontwikkeling.  
2. **Aspose.BarCode voor .NET** – Download de bibliotheek van de [Aspose.BarCode voor .NET documentatie](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework of .NET 5+** – Bekendheid met C# en de .NET-runtime is vereist.

Nu de omgeving klaar is, gaan we verder met de implementatie.

## Namespaces importeren

De `Aspose.BarCode.Generation` namespace bevat de `BarcodeGenerator` klasse en gerelateerde instellingen.

```csharp
using Aspose.BarCode;
```

## Stap 1: pad definiëren

Kies een map waarin de gegenereerde afbeeldingen worden opgeslagen. Het pad moet eindigen met de juiste mapseparator voor uw besturingssysteem.

```csharp
string path = "Your Directory Path";
```

## Stap 2: GS1-coupon supplementruimte configuratie genereren

De volgende code maakt een barcode, stelt de X‑dimensie in, en past de supplementruimte aan.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

In dit voorbeeld doen we:

1. **Aanmaken** van een `BarcodeGenerator` instantie voor het `UpcaGs1DatabarCoupon` type.  
2. **Instellen** van de X‑dimensie op 2 pixels, wat de smalste balkbreedte bepaalt.  
3. **Aanpassen** van de `SupplementSpace.Pixels` eigenschap naar 30 px, een afbeelding genereren, en vervolgens herhalen met 50 px.  

Voel u vrij om te experimenteren met andere pixelwaarden om uw afdrukworkflow aan te passen.

## Veelvoorkomende problemen & tips
- **Ongeldig pad** – Zorg ervoor dat de `path` variabele eindigt met een backslash (`\`) of forward slash (`/`) die geschikt is voor uw besturingssysteem.  
- **Onvoldoende rechten** – Voer Visual Studio uit als Administrator of kies een map waarin de applicatie schrijfrechten heeft.  
- **Onjuist gegevensformaat** – De gegevensreeks moet de GS1-syntaxis volgen (`(8110)` duidt de supplementidentificatie aan).  

## Waarom dit belangrijk is voor uw bedrijf
Aspose.BarCode ondersteunt **meer dan 60 barcode-symbologieën** en kan afbeeldingen renderen tot **10.000 × 10.000 pixels** zonder het geheugen uit te putten. Voor grootschalige retailimplementaties betekent dit dat u high‑resolution GS1-coupons in batchmodus kunt genereren, terwijl de verwerkingstijd onder een seconde per afbeelding blijft op typische serverhardware.

## Veelgestelde vragen

**Q: Wat is het doel van de GS1 Coupon Supplement Space in barcodes?**  
A: Het voegt een verplichte lege marge toe rond de aanvullende gegevens, verbetert de scannerbetrouwbaarheid en voldoet aan de door de retailer gespecificeerde minimumbreedtes.

**Q: Kan ik de breedte van de GS1 Coupon Supplement Space aanpassen met Aspose.BarCode voor .NET?**  
A: Ja, stel `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` in op een geheel getal; de bibliotheek past de wijziging direct toe op de gegenereerde afbeelding.

**Q: Waar kan ik extra documentatie en ondersteuning vinden voor Aspose.BarCode voor .NET?**  
A: Raadpleeg de [Aspose.BarCode voor .NET documentatie](https://reference.aspose.com/barcode/net/) en bezoek het [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) voor community‑ondersteuning.

**Q: Is Aspose.BarCode voor .NET geschikt voor zowel beginners als ervaren ontwikkelaars?**  
A: Absoluut. De API biedt eenvoudige methoden voor snelle taken en geavanceerde opties voor fijn afgestemde barcode‑generatie.

**Q: Kan ik een tijdelijke licentie verkrijgen voor Aspose.BarCode voor .NET om de functies te evalueren?**  
A: Ja, vraag een proeflicentie aan via de [Aspose tijdelijke licentie website](https://purchase.aspose.com/temporary-license/).

## Conclusie

Door de bovenstaande stappen te volgen weet u nu hoe u **barcode aangepaste ruimte** kunt **creëren** voor de GS1 Coupon Supplement Space, een belangrijke techniek om de **leesbaarheid van barcodes** te verhogen en aan retailnormen te voldoen. Integreer de code in uw bestaande scansystemen, experimenteer met verschillende pixelwaarden, en verken andere barcode‑types die Aspose.BarCode voor .NET biedt.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Gerelateerde tutorials

- [Genereer Aspose.BarCode Databar barcode met .NET API – Rij‑ en kolomconfiguratie](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Hoe DataMatrix barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}