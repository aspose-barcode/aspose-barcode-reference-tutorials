---
category: general
date: 2026-10-24
description: Exempel på streckkodsgenerator som visar hur man skapar Planet‑streckkod
  och hur man ställer in streckkodens höjd med Python. Följ steg‑för‑steg‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: sv
lastmod: 2026-10-24
og_description: Exempel på streckkodsgenerator som visar hur man skapar Planet-streckkod
  och hur man ställer in streckkodens höjd i Python. Få en komplett, körbar lösning.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Exempel på streckkodsgenerator – skapa Planet- och RM4SCC-streckkoder
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
title: Exempel på streckkodsgenerator – skapa Planet- och RM4SCC-streckkoder med anpassad
  höjd
url: /sv/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exempel på streckkodsgenerator – skapa Planet- och RM4SCC-streckkoder med anpassad höjd

Om du letar efter ett **barcode generator example**, ger den här guiden dig en komplett, färdig‑att‑köra lösning. Du kommer att se **how to create planet barcode**‑bilder, lära dig **how to set barcode height**, och förstå de små skillnaderna mellan automatisk och manuell storleksinställning.

Handledaren går igenom två realistiska scenarier: en Planet-streckkod som använder standardhöjden (auto) och en RM4SCC-streckkod där höjden tvingas till 100 px. I slutet kan du generera PNG‑filer för vilken stödd streckkodstyp som helst med ett enda, konsekvent API.

## Förutsättningar

* Python 3.8 eller nyare installerat.
* `aspose-barcode`‑paketet (eller något bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`). Installera det med  

  ```bash
  pip install aspose-barcode
  ```
* Skrivbehörighet till en mapp där PNG‑filerna kommer att sparas.

Inga ytterligare systemberoenden krävs.

## Översikt av lösningen

Kärnan i **barcode generator example** består av tre återanvändbara steg:

1. **Instantiate** en `BarcodeGenerator` med önskat `EncodeTypes`‑värde och datasträngen.
2. **Configure** X‑dimensionen (modulbredd) och, vid behov, streckkodens höjd.
3. **Save** bilden till disk i PNG‑format.

Båda exemplen delar steg 1 och 3; endast steg 2 skiljer sig eftersom Planet‑streckkoden förlitar sig på bibliotekets automatiska höjdkalkyl, medan RM4SCC‑streckkoden visar **how to set barcode height** manuellt.

Nedan är ett hög‑nivå diagram som illustrerar flödet:

![Exempel på streckkodsgenerator som visar Planet- och RM4SCC-streckkoder](barcode-example.png)

*Alt text: Exempel på streckkodsgenerator som visar Planet- och RM4SCC-streckkoder med olika höjder.*

## Hur man skapar planet‑streckkod – automatisk höjd

Planet‑streckkoden är en del av postfamiljen som används av många nationella posttjänster. I de flesta fall låter du SDK:n bestämma höjden, vilket behåller de visuella proportionerna korrekta för varierande datalängder.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Varför detta fungerar**

* `EncodeTypes.Planet` talar om för biblioteket att använda Planet‑symbologi.
* Att sätta `x_dimension.pixels` till 4 ger varje modul en bredd på 4 px, vilket är en vanlig standard för tryckta etiketter.
* Ingen explicit höjd anges; SDK:n beräknar den optimala höjden baserat på data och X‑dimensionen, vilket är varför detta är det enklaste **barcode generator example** för postkoder.

**Förväntat resultat**

En 2‑D PNG‑fil med namnet `PostalPlanetBarHeightAuto.png` som innehåller en skarp Planet‑streckkod. Höjden blir omkring 30 px (beroende på biblioteksversion) och bredden blir 4 px × antalet moduler.

## Hur man sätter streckkodshöjd – anpassat RM4SCC‑exempel

RM4SCC är en annan poststreckkod som ofta kräver en fast höjd för att matcha etikettsmallar. Denna del av handledningen visar **how to set barcode height** till ett exakt antal pixlar.

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

**Varför detta fungerar**

* `EncodeTypes.RM4SCC` väljer RM4SCC‑symbologi.
* X‑dimensionen förblir på 4 px för att hålla modulstorleken konsekvent över båda streckkoderna.
* `bar_height.pixels = 100` tvingar streckkoden att bli exakt 100 px hög, vilket åsidosätter den automatiska beräkningen. Detta är det rekommenderade sättet **how to set barcode height** när din layout kräver en specifik storlek.

**Förväntat resultat**

En PNG‑fil med namnet `PostalRM4SCCBarHeight100Pixels.png` som visar en hög RM4SCC‑streckkod. Bredden styrs fortfarande av X‑dimensionen, medan höjden är fast på 100 px, vilket gör den lämplig för högupplösta etikettskrivare.

## Fullt skript – kombinera båda exemplen

Om du föredrar ett enda skript som genererar båda bilderna, kopiera följande kod till `generate_barcodes.py` och kör det.

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

**Förklaring av skriptet**

* Två hjälpfunktioner håller koden DRY (Don’t Repeat Yourself) och gör det enkelt att utöka skriptet för andra symbologier.
* `if __name__ == "__main__":`‑skyddet gör att filen kan importeras som en modul utan att köra genereringslogiken, vilket är användbart för enhetstestning.
* Alla parametrar (datasträng, X‑dimension, höjd) är explicita, så skriptet fungerar som ett referens‑**barcode generator example** för framtida projekt.

## Vanliga frågor och specialfall

| Fråga | Svar |
|----------|--------|
| *Vad händer om jag behöver en annan X‑dimension?* | Ändra `x_dimension.pixels` till önskad modulbredd. Större värden ökar den totala streckkodsstorleken proportionellt. |
| *Kan jag generera andra bildformat?* | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpg`, `Bmp` eller `Gif` beroende på bibliotekets enum. |
| *Vad händer om datasträngen innehåller ogiltiga tecken?* | Generatorn kastar ett `ArgumentException`. Validera data mot symbologins teckenuppsättning innan du anropar konstruktorn. |
| *Är det möjligt att sätta en minsta höjd samtidigt som auto‑skalning behålls?* | Använd `gen.parameters.barcode.bar_height.min_pixels = <value>` (om SDK:n exponerar en `min_pixels`‑egenskap). Detta förhindrar att streckkoden blir mindre än en läsbar storlek. |
| *Behöver jag avyttra generatorn?* | `BarcodeGenerator`‑klassen implementerar `IDisposable` i .NET; i Python hanteras det av skräpsamlaren, men du kan anropa `gen.dispose()` om du skapar många instanser i en loop. |

## Tips för produktionsanvändning

* **Pro tip:** Spara X‑dimensionen och höjdvärden i en konfigurationsfil så att du kan justera dem utan att kompilera om.
* **Watch out for:** Att använda en höjd som är för liten för den valda symbologin; skannrar kan misslyckas med att läsa streckkoden.
* **Performance note:** Att generera en stor mängd streckkoder går snabbare när du återanvänder en enda `BarcodeGenerator`‑instans och bara ändrar dess `code_text`‑egenskap mellan sparningar.

## Slutsats

Detta **barcode generator example** demonstrerar både **how to create planet barcode**‑bilder med automatisk storlek och **how to set barcode height** manuellt för RM4SCC‑koder. Genom att följa den steg‑för‑steg‑guiden kan du integrera streckkodsskapande i vilken Python‑applikation som helst, anpassa dimensioner och producera PNG‑filer redo för utskrift eller digital visning.

### Nästa steg

* Utforska ytterligare symbologier såsom `EncodeTypes.Postnet` eller `EncodeTypes.Code128` – samma mönster gäller.
* Experimentera med **how to set barcode height** för QR‑koder eller DataMatrix‑symboler; de flesta bibliotek exponerar en liknande `bar_height`‑egenskap.
* Kombinera generatorn med ett PDF‑bibliotek för att bädda in streckkoder direkt i fakturor eller fraktetiketter.

Känn dig fri att anpassa skriptet, dela dina resultat, och låt oss veta vilka streckkodstyper du lägger till härnäst!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man sparar PNG från ett barcode generator example i Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Hur man skapar planet‑streckkod PNG med Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Hur man använder en C# barcode generator för att skapa en Planet‑streckkod](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}