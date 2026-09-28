---
category: general
date: 2026-07-30
description: Maak een Databar Stacked Omnidirectional barcode in Python. Volg deze
  stapsgewijze handleiding om de beeldverhouding, XDimension in te stellen en een
  PNG te exporteren met een Python barcodegenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: nl
lastmod: 2026-07-30
og_description: Maak een Databar Stacked Omnidirectional barcode in Python. Deze tutorial
  laat zien hoe je XDimension instelt, de DataBar-aspectverhouding aanpast en opslaat
  als PNG met BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Maak Databar Stacked Omnidirectionele barcode – Python‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Maak een gestapelde omnidirectionele Databar-barcode in Python
url: /nl/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Databar Stacked Omnidirectional Barcode in Python

Heb je ooit een **databar stacked omnidirectional** barcode in Python moeten **maken**, maar wist je niet waar je moest beginnen? Je bent niet de enige—veel ontwikkelaars lopen tegen die muur aan wanneer ze voor het eerst met de `BarcodeGenerator`-klasse werken. Het goede nieuws is dat het hele proces heel eenvoudig is zodra je de belangrijkste eigenschappen begrijpt.

In deze gids lopen we een volledig, uitvoerbaar voorbeeld door dat een **python barcode generator** gebruikt om de XDimension in te stellen, de DataBar-aspectverhouding aan te passen, en uiteindelijk twee PNG‑bestanden te exporteren. Aan het einde heb je een goed begrip van hoe je hoogwaardige stacked omnidirectional‑symbolen kunt genereren voor elk voorraad‑ of logistiekproject.

## Wat je zult leren

- Hoe je een **databar stacked omnidirectional** generator instantieert met een GTIN‑14 payload.  
- Waarom de **XDimension pixel size** belangrijk is voor scanbetrouwbaarheid.  
- De impact van de **DataBar aspect ratio** op de breedte versus hoogte van de rij.  
- Hoe je het resultaat opslaat als een **BarCodeImageFormat PNG**‑bestand.  
- Tips om hetzelfde generatorobject opnieuw te gebruiken om meerdere varianten te produceren zonder extra geheugenoverhead.

### Vereisten

- Python 3.8+ (de bibliotheek die we gebruiken is pure‑Python, geen gecompileerde wheels nodig).  
- Het `barcode-generator`‑pakket (installeren via `pip install barcode-generator`).  
- Een map waarin je kunt schrijven – het script zal daar twee PNG‑afbeeldingen wegschrijven.

Als je vertrouwd bent met basis‑Python‑imports en objectgeoriënteerde code, ben je klaar om te beginnen.

## Maak Databar Stacked Omnidirectional Barcode – Stappenoverzicht

Hieronder splitsen we de workflow op in zes hapklare stappen. Elke stap is een zelfstandige code‑blok die je kunt copy‑pasten in een REPL of scriptbestand. Voel je vrij om te experimenteren—het wijzigen van de aspect ratio of XDimension geeft je direct een andere visuele stijl.

---

## Stap 1: Maak Databar Stacked Omnidirectional Generator

Het eerste wat we doen is een **databar stacked omnidirectional** generator‑instantie maken, waarbij we de juiste `EncodeTypes`‑enum en de gegevensreeks doorgeven.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Waarom dit belangrijk is:** De `EncodeTypes.DatabarStackedOmniDirectional`‑vlag vertelt de bibliotheek om een stacked omnidirectional‑symbool te produceren, de enige DataBar‑variant die tot 14 cijfers kan coderen en toch vanuit elke hoek leesbaar is.

---

## Configureer XDimension Pixelgrootte

De **XDimension pixel size** bepaalt de kleinste module (de dunste zwarte balk). Een waarde van `2` pixels werkt goed voor de meeste scherm‑weergaves.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** Als je van plan bent de barcode bij hoge DPI te printen, verhoog deze waarde naar 3 of 4 om wazige randen te voorkomen.

---

## Pas DataBar Aspect Ratio aan (15)

De **DataBar aspect ratio** bepaalt hoe breed elke rij is ten opzichte van de hoogte. Een aspect ratio van `15` levert bredere rijen op, wat veel scanners verkiezen voor snelle bewegingsvastlegging.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Waarom 15?** De officiële GS1‑specificatie beveelt een ratio tussen 10 en 20 aan voor stacked omnidirectional‑symbolen. We kiezen `15` als een evenwichtige standaard.

---

## Exporteer Barcode als PNG met BarCodeImageFormat

Nu de generator geconfigureerd is, slaan we de afbeelding op. De `BarCodeImageFormat.Png`‑enum zorgt voor verliesvrije output, perfect voor verdere verwerking.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Wat je zult zien:** Open de resulterende PNG; je zou een schone, hoog‑contrast barcode moeten zien met relatief brede rijen.

---

## Verander DataBar Aspect Ratio naar 30

Soms heb je hogere rijen nodig in plaats van bredere—misschien om op een smalle label te passen. Het wijzigen van de **DataBar aspect ratio** naar `30` maakt elke rij hoger.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Randgeval:** Zeer hoge ratio's (bijv. >40) kunnen ervoor zorgen dat de barcode de typische labelhoogtes overschrijdt, test daarom op een echte printer voordat je het definitief maakt.

---

## Exporteer Barcode opnieuw met nieuwe Aspect Ratio

Tot slot hergebruiken we hetzelfde `barcode_generator`‑object om een tweede PNG te schrijven. Het is niet nodig de generator opnieuw te maken—wijzig gewoon de eigenschap en roep `Save` opnieuw aan.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Resultaat:** Je hebt nu twee PNG‑bestanden—een met brede rijen (`AR15`) en een andere met hoge rijen (`AR30`). Vergelijk ze naast elkaar om te bepalen welke het beste werkt voor jouw scanner‑opstelling.

---

## Volledig Werkend Voorbeeld

Alles bij elkaar genomen, hier is het volledige script dat je direct kunt uitvoeren. Vervang `YOUR_DIRECTORY` door een absoluut pad op jouw machine.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Verwachte output** (in je console):

```
✅ Two PNG files created – AR15 and AR30
```

En twee afbeeldingsbestanden verschijnen in de doelmap, klaar voor scan‑tests.

---

## Conclusie

We hebben zojuist **databar stacked omnidirectional** barcodes in Python **gemaakt**, de **XDimension pixel size** aangepast, geëxperimenteerd met twee verschillende **DataBar aspect ratio**‑instellingen, en de resultaten geëxporteerd als **BarCodeImageFormat PNG**‑bestanden. De volledige workflow past in een handvol regels, maar geeft je volledige controle over de visuele kenmerken die het belangrijkst zijn voor scanners.

Wat is het volgende? Probeer de payload te vervangen door een andere GTIN, speel met kleuren door de PNG naar een palet‑gebaseerde afbeelding te converteren, of genereer een PDF‑rapport dat beide PNG's naast elkaar embedt. De `BarcodeGenerator`‑klasse is flexibel genoeg om al deze scenario's aan te kunnen, dus voel je vrij om te experimenteren.

Heb je vragen over een specifiek gebruiksscenario of loop je tegen een fout aan? Laat een reactie achter hieronder, en ik help je graag. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}