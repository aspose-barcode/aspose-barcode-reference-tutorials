---
category: general
date: 2026-10-24
description: Barcodegenerator‑voorbeeld dat laat zien hoe je een Planet‑barcode maakt
  en hoe je de barcodehoogte instelt met Python. Volg de stapsgewijze handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: nl
lastmod: 2026-10-24
og_description: Barcodegenerator-voorbeeld dat laat zien hoe je een Planet-barcode
  maakt en hoe je de barcodehoogte instelt in Python. Ontvang een volledige, uitvoerbare
  oplossing.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Voorbeeld van barcodegenerator – maak Planet- en RM4SCC-barcodes
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Barcodegenerator‑voorbeeld – maak Planet‑ en RM4SCC‑barcodes met aangepaste
  hoogte
url: /nl/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator voorbeeld – maak Planet- en RM4SCC-barcodes met aangepaste hoogte

Als je op zoek bent naar een **barcode generator voorbeeld**, biedt deze gids een complete, kant‑klaar oplossing. Je ziet **hoe je planet barcode** afbeeldingen maakt, leert **hoe je barcodehoogte instelt**, en begrijpt de kleine verschillen tussen automatische en handmatige afmetingen.

De tutorial doorloopt twee realistische scenario's: een Planet-barcode die de standaard (auto) hoogte gebruikt, en een RM4SCC-barcode waarbij de hoogte wordt geforceerd tot 100 px. Aan het einde kun je PNG‑bestanden genereren voor elk ondersteund barcode‑type met één consistente API.

## Vereisten

* Python 3.8 of nieuwer geïnstalleerd.
* Het `aspose-barcode`‑pakket (of een andere bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` levert). Installeer het met  

  ```bash
  pip install aspose-barcode
  ```
* Schrijfrechten voor een map waar de PNG‑bestanden worden opgeslagen.

Er zijn geen extra systeemeisen nodig.

## Overzicht van de oplossing

De kern van het **barcode generator voorbeeld** bestaat uit drie herbruikbare stappen:

1. **Instantiëren** van een `BarcodeGenerator` met de gewenste `EncodeTypes`‑waarde en de dataketen.
2. **Configureren** van de X‑dimensie (module‑breedte) en, indien nodig, de barcode‑hoogte.
3. **Opslaan** van de afbeelding op schijf in PNG‑formaat.

Beide voorbeelden delen stap 1 en 3; alleen stap 2 verschilt omdat de Planet-barcode vertrouwt op de automatische hoogterekenning van de bibliotheek, terwijl de RM4SCC-barcode **hoe je barcodehoogte instelt** handmatig demonstreert.

Below is a high‑level diagram that illustrates the flow:

![Barcode generator voorbeeld dat Planet- en RM4SCC-barcodes toont](barcode-example.png)

*Alt‑tekst: Barcode generator voorbeeld dat Planet- en RM4SCC-barcodes toont met verschillende hoogtes.*

## Hoe maak je een planet barcode – automatische hoogte

De Planet-barcode maakt deel uit van de postfamilie die door veel nationale postdiensten wordt gebruikt. In de meeste gevallen laat je de SDK de hoogte bepalen, wat de visuele verhoudingen correct houdt voor verschillende datalengtes.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Waarom dit werkt**

* `EncodeTypes.Planet` vertelt de bibliotheek om de Planet‑symbologie te gebruiken.
* Het instellen van `x_dimension.pixels` op 4 geeft elke module een breedte van 4 px, wat een veelvoorkomende standaard is voor afgedrukte etiketten.
* Er wordt geen expliciete hoogte ingesteld; de SDK berekent de optimale hoogte op basis van de data en de X‑dimensie, waardoor dit het eenvoudigste **barcode generator voorbeeld** voor postcodes is.

**Verwacht resultaat**

Een 2‑D PNG‑bestand met de naam `PostalPlanetBarHeightAuto.png` dat een scherpe Planet-barcode bevat. De hoogte zal ongeveer 30 px zijn (afhankelijk van de bibliotheekversie) en de breedte zal 4 px × aantal modules zijn.

## Hoe barcodehoogte instellen – aangepast RM4SCC‑voorbeeld

RM4SCC is een andere postbarcode die vaak een vaste hoogte vereist om te passen bij etiketsjablonen. Dit deel van de tutorial toont **hoe je barcodehoogte instelt** op een exact aantal pixels.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Waarom dit werkt**

* `EncodeTypes.RM4SCC` selecteert de RM4SCC‑symbologie.
* De X‑dimensie blijft op 4 px om de modulegrootte consistent te houden tussen beide barcodes.
* `bar_height.pixels = 100` dwingt de barcode om precies 100 px hoog te zijn, waardoor de automatische berekening wordt overschreven. Dit is de aanbevolen manier **hoe je barcodehoogte instelt** wanneer je lay-out een specifieke grootte vereist.

**Verwacht resultaat**

Een PNG‑bestand met de naam `PostalRM4SCCBarHeight100Pixels.png` dat een hoge RM4SCC-barcode weergeeft. De breedte wordt nog steeds bepaald door de X‑dimensie, terwijl de hoogte vast staat op 100 px, waardoor het geschikt is voor high‑resolution etikettenprinters.

## Volledig script – combineer beide voorbeelden

Als je de voorkeur geeft aan één script dat beide afbeeldingen genereert, kopieer dan de volgende code naar `generate_barcodes.py` en voer het uit.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Uitleg van het script**

* Twee hulpfuncties houden de code DRY (Don’t Repeat Yourself) en maken het gemakkelijk om het script uit te breiden voor andere symbologieën.
* De `if __name__ == "__main__":` guard maakt het mogelijk het bestand als module te importeren zonder de generatie‑logica uit te voeren, wat nuttig is voor unit‑testing.
* Alle parameters (dataketen, X‑dimensie, hoogte) zijn expliciet, zodat het script dient als referentie‑**barcode generator voorbeeld** voor toekomstige projecten.

## Veelgestelde vragen en randgevallen

| Vraag | Antwoord |
|----------|--------|
| *Wat als ik een andere X‑dimensie nodig heb?* | Verander `x_dimension.pixels` naar de gewenste modulebreedte. Grotere waarden vergroten de totale barcode‑grootte evenredig. |
| *Kan ik andere afbeeldingsformaten genereren?* | Ja. Vervang `BarCodeImageFormat.Png` door `Jpg`, `Bmp` of `Gif` afhankelijk van de enum van de bibliotheek. |
| *Wat gebeurt er als de dataketen ongeldige tekens bevat?* | De generator gooit een `ArgumentException`. Valideer de data tegen de tekenset van de symbologie voordat je de constructor aanroept. |
| *Is het mogelijk om een minimumhoogte in te stellen terwijl auto‑scaling behouden blijft?* | Gebruik `gen.parameters.barcode.bar_height.min_pixels = <value>` (als de SDK een `min_pixels`‑eigenschap exposeert). Dit voorkomt dat de barcode kleiner wordt dan een leesbare grootte. |
| *Moet ik de generator opruimen?* | De `BarcodeGenerator`‑klasse implementeert `IDisposable` in .NET; in Python wordt dit afgehandeld door de garbage collector, maar je kunt `gen.dispose()` aanroepen als je veel instanties in een lus maakt. |

## Tips voor productiegebruik

* **Pro tip:** Sla de X‑dimensie‑ en hoogte‑waarden op in een configuratie‑bestand zodat je ze kunt aanpassen zonder opnieuw te compileren.
* **Let op:** Een hoogte die te klein is voor de gekozen symbologie; scanners kunnen de barcode niet lezen.
* **Prestatienota:** Het genereren van een grote batch barcodes gaat sneller wanneer je één `BarcodeGenerator`‑instantie hergebruikt en alleen de `code_text`‑eigenschap wijzigt tussen opslagen.

## Conclusie

Dit **barcode generator voorbeeld** toont zowel **hoe je planet barcode** afbeeldingen maakt met automatische afmetingen als **hoe je barcodehoogte instelt** handmatig voor RM4SCC‑codes. Door de stap‑voor‑stap‑gids te volgen kun je barcode‑creatie integreren in elke Python‑applicatie, afmetingen aanpassen en PNG‑bestanden produceren die klaar zijn voor afdrukken of digitale weergave.

### Volgende stappen

* Verken extra symbologieën zoals `EncodeTypes.Postnet` of `EncodeTypes.Code128` – hetzelfde patroon geldt.
* Experimenteer met **hoe je barcodehoogte instelt** voor QR‑codes of DataMatrix‑symbolen; de meeste bibliotheken bieden een vergelijkbare `bar_height`‑eigenschap.
* Combineer de generator met een PDF‑bibliotheek om barcodes direct in facturen of verzendetiketten in te sluiten.

Voel je vrij om het script aan te passen, je resultaten te delen, en laat ons weten welke barcode‑typen je hierna toevoegt!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PNG op te slaan vanuit een barcode generator voorbeeld in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Hoe een planet barcode PNG te maken met Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Hoe een C# barcode generator te gebruiken om een Planet barcode te maken](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}