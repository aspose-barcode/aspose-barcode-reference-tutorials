---
category: general
date: 2026-11-27
description: Návod na generátor čárových kódů, který ukazuje, jak vygenerovat PNG
  čárového kódu, změnit jeho velikost a vytvořit Planet čárový kód v Pythonu s krok‑za‑krokem
  kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- how to generate barcode
- change barcode size
- create barcode png
- create planet barcode
language: cs
lastmod: 2026-11-27
og_description: Návod na generátor čárových kódů vás provede tím, jak vytvořit PNG
  čárového kódu, změnit jeho velikost a vytvořit Planet čárový kód pomocí Pythonu.
og_image_alt: Screenshot of a Planet barcode PNG generated in a barcode generator
  tutorial
og_title: Návod na generátor čárových kódů – vytvořte čárový kód Planet PNG
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Barcode generator tutorial that shows how to generate barcode PNG,
    change barcode size, and create a Planet barcode in Python with step‑by‑step code.
  headline: Barcode generator tutorial – create a Planet PNG barcode
  type: TechArticle
tags:
- barcode
- Python
- image-generation
title: Tutoriál generátoru čárových kódů – vytvořte Planet PNG čárový kód
url: /cs/python-java/general/barcode-generator-tutorial-create-a-planet-png-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Návod na generátor čárových kódů – vytvořte Planet PNG čárový kód

Pokud hledáte **návod na generátor čárových kódů**, tento průvodce vám přesně ukáže, jak vygenerovat Planet (POSTNET) čárový kód, změnit velikost čárového kódu a uložit jej jako PNG obrázek pomocí Pythonu. Ať už potřebujete čárové kódy pro poštovní štítky nebo sledování zásob, získáte kompletní, spustitelný příklad během několika kroků.

Tento návod pokrývá vše od instalace potřebné knihovny po přizpůsobení X rozměru a výšky čárového kódu. Na konci pochopíte **jak generovat čárový kód** obrázky programově a budete připraveni upravit kód pro jiné symboliky nebo výstupní formáty.

## Požadavky

* Python 3.8 nebo novější nainstalovaný.
* Přístup k internetu pro instalaci balíčku `aspose-barcode` (knihovna použitá v tomto návodu).
* Zapisovatelný adresář, kam bude vygenerovaný PNG uložen.

> **Tip:** Použijte virtuální prostředí (`python -m venv venv`) pro izolaci závislostí.

## Krok 1: Instalace knihovny Aspose.BarCode pro Python

Nejjednodušší způsob, jak pracovat s čárovými kódy v Pythonu, je oficiální balíček **Aspose.BarCode**, který podporuje symbologii Planet bez další konfigurace.

```bash
pip install aspose-barcode
```

Balíček obsahuje třídy `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`, které budete později potřebovat.

## Krok 2: Import požadovaných tříd a nastavení generátoru

Vytvořte nový soubor Pythonu (např. `planet_barcode.py`) a importujte potřebné symboly.

```python
# planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data to encode – Planet (POSTNET) expects a numeric string.
postal_code = "123456"
```

Konstanta `EncodeTypes.Planet` říká generátoru, aby použil symbologii **Planet**, což je ideální pro americké poštovní služby.

## Krok 3: Vytvoření generátoru čárového kódu (jak generovat čárový kód)

Instancujte generátor s požadovanými daty. Toto je jádro procesu **jak generovat čárový kód**.

```python
# Initialize the generator with Planet symbology and the data string.
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)
```

V tomto okamžiku `barcode_generator` obsahuje výchozí obrázek čárového kódu (obvykle šířka modulu 2 px a výška čáry 50 px). Aby byl obrázek vhodný pro tisk nebo digitální použití, budete chtít **změnit velikost čárového kódu**.

## Krok 4: Změna velikosti čárového kódu – úprava X rozměru a výšky čáry

### 4.1 Úprava X rozměru (šířka modulu)

X rozměr řídí šířku každé jednotlivé čáry (modulu). Nastavení na 4 pixely poskytuje jemnější, vyšší rozlišení čárového kódu.

```python
# Set the X dimension (module width) to 4 pixels.
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

### 4.2 Nastavení výšky čáry

Výška čáry určuje celkovou vertikální velikost čárového kódu. Výška 100 pixelů funguje dobře pro většinu skenovacích zařízení.

```python
# Set the bar height to 100 pixels.
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

Obě vlastnosti jsou součástí hierarchie `parameters.barcode`, která seskupuje všechna vizuální nastavení čárového kódu.

## Krok 5: Uložení čárového kódu jako PNG obrázek (vytvořit barcode png)

Jakmile je velikost nastavena, exportujte obrázek. Metoda `save` přijímá cestu k souboru a výčtový typ formátu obrázku.

```python
# Define the output path – adjust the directory as needed.
output_path = "output/PostalPlanetBarHeight100Pixels.png"

# Save the barcode as a PNG file.
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

Spuštěním skriptu se vygeneruje soubor s názvem `PostalPlanetBarHeight100Pixels.png` ve složce `output`. Obrázek obsahuje čistý Planet čárový kód připravený k tisku nebo vložení do PDF.

## Krok 6: Ověření vygenerovaného čárového kódu (vytvořit planet barcode)

Otevřete PNG v libovolném prohlížeči obrázků a ověřte, že čárový kód vypadá správně. Můžete jej také naskenovat pomocí mobilní aplikace pro skenování čárových kódů; měla by vrátit původní data (`123456`).

Pokud se čárový kód nedaří naskenovat:

* Ujistěte se, že X rozměr není nastaven příliš nízko (méně než 2 px může způsobit problémy s čitelností).
* Ověřte, že výška čáry je alespoň 50 px pro spolehlivé skenování.
* Zkontrolujte, že řetězec dat splňuje požadavky Planet (pouze číselný, správná délka).

## Kompletní skript – vše dohromady

Níže je kompletní, samostatný skript, který můžete okamžitě zkopírovat a spustit.

```python
# planet_barcode.py
"""
Barcode generator tutorial: create a Planet PNG barcode.
This script demonstrates how to generate a barcode, change barcode size,
and save the result as a PNG image using Aspose.BarCode for Python.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def main():
    # 1️⃣ Define the data to encode.
    postal_code = "123456"

    # 2️⃣ Create the generator for Planet symbology.
    barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)

    # 3️⃣ Change barcode size.
    #    - X dimension (module width) = 4 pixels for higher resolution.
    #    - Bar height = 100 pixels for a larger visual footprint.
    barcode_generator.parameters.barcode.x_dimension.pixels = 4
    barcode_generator.parameters.barcode.bar_height.pixels = 100

    # 4️⃣ Prepare the output directory.
    output_dir = "output"
    os.makedirs(output_dir, exist_ok=True)
    output_path = os.path.join(output_dir, "PostalPlanetBarHeight100Pixels.png")

    # 5️⃣ Save the barcode as PNG.
    barcode_generator.save(output_path, BarCodeImageFormat.Png)

    print(f"✅ Barcode generated and saved to: {output_path}")

if __name__ == "__main__":
    main()
```

Spuštěním `python planet_barcode.py` se vytvoří PNG zobrazený níže.

![PNG Planet čárový kód vygenerovaný v návodu na generátor čárových kódů](https://example.com/planet_barcode.png "PNG Planet čárový kód vygenerovaný v návodu na generátor čárových kódů")

*Text alt obrázku:* **PNG Planet čárový kód vygenerovaný v návodu na generátor čárových kódů** (odpovídá požadované délce alt textu).

## Běžné varianty a okrajové případy

| Situace | Co upravit | Proč je to důležité |
|-----------|----------------|----------------|
| **Různá délka dat** | Ujistěte se, že řetězec dat odpovídá požadovanému počtu číslic pro Planet (5, 9 nebo 11 číslic). | Neplatné délky způsobí `ArgumentException`. |
| **Výstup s vyšším DPI** | Nastavte `barcode_generator.parameters.image_resolution.dpi = 300`. | Zlepšuje kvalitu tisku na vysoce rozlišených tiskárnách. |
| **Jiné formáty obrázků** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. | Vyberte formát, který odpovídá následnému zpracování. |
| **Více čárových kódů v jednom obrázku** | Použijte `barcode_generator.save_multiple([...])` (k dispozici v novějších verzích). | Užitečné pro hromadnou tvorbu štítků. |

## Kontrolní seznam řešení problémů

* **Čárový kód se nezobrazuje** – Ověřte, že výstupní adresář existuje a máte oprávnění k zápisu.
* **Skenner nemůže čárový kód přečíst** – Zvyšte X rozměr nebo výšku čáry; nepřekračujte minimální čitelné limity.
* **ImportError** – Ověřte, že jste nainstalovali `aspose-barcode` ve stejném Python prostředí, ve kterém skript spouštíte.

## Závěr

Tento **návod na generátor čárových kódů** vás provedl celým procesem vytvoření Planet čárového kódu PNG, od instalace knihovny po **změnu velikosti čárového kódu** a uložení obrázku. Nyní máte pevný základ pro **jak generovat čárový kód** obrázky programově a můžete rozšířit kód na jiné symboliky, formáty nebo hromadné operace.

**Další kroky**

* Prozkoumejte další symboliky jako `EncodeTypes.Code128` nebo `EncodeTypes.QR` (pokrývá sekundární klíčové slovo *create barcode png* pro různé typy).
* Integrovat vygenerovaný PNG do PDF pomocí `reportlab` nebo `PyPDF2`.
* Automatizovat hromadnou generaci pro seznam poštovních kódů (navazuje na *create planet barcode* ve velkém měřítku).

Šťastné programování a ať se vaše čárové kódy vždy načtou na první pokus!

## Co byste se měli naučit dál?

Následující návody pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit Planet čárový kód PNG pomocí Pythonu](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Kompletní návod na generátor čárových kódů pro vytvoření Planet čárového kódu v Pythonu](/barcode/english/python-java/general/complete-barcode-generator-tutorial-for-creating-a-planet-ba/)
- [Jak uložit PNG z příkladu generátoru čárových kódů v Pythonu](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}