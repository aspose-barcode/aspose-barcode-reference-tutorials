---
category: general
date: 2026-11-23
description: Jak generovat obrázky čárových kódů v Pythonu s Aspose.BarCode. Naučte
  se vytvořit čárový kód Planet, upravit X‑rozměr a vytvořit PNG s prázdnými pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: cs
lastmod: 2026-11-23
og_description: Jak generovat čárový kód v Pythonu pomocí Aspose.BarCode. Tento tutoriál
  vás provede vytvořením Planet čárového kódu s prázdnými pruhy a jeho uložením jako
  PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Jak generovat čárový kód v Pythonu – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Jak generovat obrázky čárových kódů v Pythonu pomocí Aspose.BarCode
url: /cs/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat obrázky čárových kódů v Pythonu pomocí Aspose.BarCode

Generování obrázků čárových kódů v Pythonu je s knihovnou Aspose.BarCode jednoduché. Tento průvodce vám krok za krokem ukáže, jak vygenerovat čárový kód pomocí symbologie Planet, přizpůsobit X‑dimenzi a vytvořit PNG soubor ve stylu prázdných pruhů.

Uvidíte kompletní spustitelný skript, který můžete zkopírovat do svého projektu. Tutoriál také pokrývá běžné varianty – například přepnutí na jinou symbologii nebo výstupní formát – takže můžete řešení přizpůsobit svým požadavkům.

## Požadavky

* Python 3.8 nebo novější nainstalovaný.
* Přístup k terminálu nebo příkazovému řádku.
* Aktivní licence Aspose.BarCode pro Python (bezplatná zkušební verze funguje pro testování).
* Základní znalost správy balíčků v Pythonu (`pip`).

## Krok 1: Instalace balíčku Aspose.BarCode

Aspose distribuuje své Python API prostřednictvím PyPI. Nainstalujte jej pomocí standardního správce balíčků:

```bash
pip install asposebarcode
```

> **Tip:** Použijte virtuální prostředí (`python -m venv venv`), aby byly závislosti izolovány od ostatních projektů.

## Krok 2: Import požadovaných tříd Aspose.BarCode

Importní příkaz načte generátor, výčet symbologií a výčet formátů obrázků.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` vytváří objekt čárového kódu.
* `EncodeTypes` vypisuje všechny podporované symbologie – zde použijeme `Planet`.
* `BarCodeImageFormat` určuje typ výstupního souboru (PNG, JPEG, atd.).

## Krok 3: Vytvoření generátoru čárového kódu pro symbologii Planet

Instancujte generátor s požadovanou symbologií a daty, která chcete zakódovat.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Symbologie `Planet` vytváří kruhový vzor, který je ideální pro dekorativní nebo značkové účely.

## Krok 4: Úprava X‑dimenze (šířka modulu)

X‑dimenze řídí šířku nejmenšího pruhu (modulu). Nastavením na 4 pixely získáte čistý, vysoce rozlišený obrázek.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Změna X‑dimenze je užitečná, když potřebujete čárový kód, který se dobře škáluje pro tisk nebo zobrazení na obrazovce.

## Krok 5: Zakázání vyplněných pruhů pro styl prázdných pruhů

Čárový kód s prázdnými pruhy zobrazuje pouze obrysy pruhů, což může být užitečné pro aplikace zaměřené na design.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Když je `filled_bars` nastaveno na `False`, generátor kreslí duté tvary místo plných.

## Krok 6: Uložení obrázku čárového kódu jako PNG soubor

Nakonec zapište čárový kód na disk. PNG je bezztrátový a široce podporovaný.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

Metoda `save` automaticky vytvoří cílový adresář, pokud neexistuje.

## Kompletní příklad – kompletní spustitelný skript

Sestavením všech částí dohromady získáte samostatný program, který můžete spustit okamžitě:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Očekávaný výstup:** Po spuštění skriptu `output/PlanetEmptyBars.png` obsahuje 200 × 200 pixelový obrázek Planet čárového kódu s dutými pruhy. Otevřením souboru v libovolném prohlížeči obrázků se zobrazí kruhový vzor s číselnou hodnotou zakódovanou uvnitř.

## Běžné varianty a okrajové případy

### Přepnutí na jinou symbologii

Pokud potřebujete QR kód, Code 128 nebo jakýkoli jiný formát, nahraďte `EncodeTypes.Planet` odpovídající hodnotou výčtu:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Změna formátu obrázku

Aspose.BarCode podporuje PNG, JPEG, BMP a TIFF. Pro generování JPEG místo toho:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Úprava velikosti obrázku bez ztráty kvality

Můžete řídit celkové rozměry obrázku pomocí vlastnosti `resolution` nebo škálováním X‑dimenze a Y‑dimenze dohromady. Pro vysoce rozlišený tisk nastavte vyšší DPI:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Zpracování dlouhých řetězců dat

Symbologie Planet má omezenou kapacitu dat (až 8 znaků). Pokud se pokusíte zakódovat delší řetězec, generátor vyvolá výjimku. Ověřte délku před vytvořením čárového kódu:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Tipy a úskalí

* **Aktivace licence:** Pro produkční použití aplikujte soubor licence brzy ve skriptu pomocí `asposebarcode.License().set_license("Aspose.Total.lic")`. Přeskočení tohoto kroku vloží vodoznak do výstupního obrázku.
* **Bezpečnost vláken:** Instance `BarcodeGenerator` nejsou thread‑safe. Vytvořte samostatnou instanci pro každé vlákno, pokud generujete čárové kódy paralelně.
* **Výkon:** Opětovné použití generátoru pro více hodnot (voláním `barcode.value = "new data"`) je rychlejší než vytváření nového objektu pokaždé.
* **Cesty k souborům:** Používejte `os.path.join` pro tvorbu platformně nezávislých cest, zejména při nasazení na Linuxu nebo macOS.

## Závěr

Nyní víte, jak v Pythonu generovat obrázky čárových kódů pomocí Aspose.BarCode, přizpůsobit X‑dimenzi, vytvořit styl prázdných pruhů a výsledek uložit jako PNG. Kompletní příklad lze přizpůsobit jiným symbologiím, výstupním formátům a vizuálním stylům, což vám poskytne flexibilní základ pro jakoukoli funkci související s čárovými kódy ve vašich aplikacích.

**Další kroky:** Prozkoumejte další sekundární klíčová slova jako *Python barcode generation* vyzkoušením různých kódování, experimentujte s nastavením komprese *barcode image PNG*, nebo integrujte vygenerované obrázky do webové služby pomocí Flask nebo FastAPI. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}