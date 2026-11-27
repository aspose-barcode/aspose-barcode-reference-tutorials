---
category: general
date: 2026-11-27
description: Naučte se, jak upravit výšku čáry čárového kódu v generátoru DataBar
  Omni‑Directional. Krok za krokem ukazuje kód nastavení výšek na 30 px a 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: cs
lastmod: 2026-11-27
og_description: Upravte výšku čáry čárového kódu v generátoru DataBar Omni‑Directional
  pomocí Pythonu. Postupujte podle kompletního návodu, jak nastavit výšky, X‑rozměr
  a uložit PNG obrázky.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Upravit výšku pruhu čárového kódu v generátoru DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Jak nastavit výšku čáry čárového kódu v generátoru DataBar Omni‑Directional
url: /cs/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit výšku čáry čárového kódu v generátoru DataBar Omni‑Directional

Pokud potřebujete **upravit výšku čáry čárového kódu** pro DataBar Omni‑Directional čárový kód, tento návod vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad v Pythonu, který mění výšku čáry z 30 px na 60 px při zachování X‑dimension a formátu obrázku.

Změna vizuálních rozměrů čárového kódu je běžnou požadavkem, když musí čárový kód odpovídat konkrétní velikosti štítku nebo designovému návodu. Kromě výšky čáry můžete také chtít upravit **X‑dimension** (velikost modulu) nebo zvolit jiný **barcode image format**, například PNG nebo JPEG.

V tomto tutoriálu:

* Nainstalovat požadovanou knihovnu (GroupDocs.Barcode for Python)
* Vytvořit generátor čárového kódu DataBar Omni‑Directional
* Nastavit velikost modulu pomocí `XDimension`
* Dvakrát upravit vlastnost výšky čáry
* Uložit výsledné obrázky v požadovaném **BarCodeImageFormat**

Předchozí zkušenost s GroupDocs API není nutná – stačí základní znalost Pythonu.

## Požadavky

Před zahájením se ujistěte, že máte:

* Nainstalovaný Python 3.8 nebo novější
* balíček `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Oprávnění k zápisu do složky, kde budou uloženy PNG soubory

Pokud neznáte **DataBar Omni‑Directional barcode**, kóduje 14‑ciferný GTIN a je široce používán v maloobchodu pro skenování z libovolné orientace.

## Krok 1: Nastavení generátoru DataBar Omni‑Directional čárového kódu

Nejprve importujte potřebné třídy a vytvořte instanci generátoru s GTIN daty, která chcete zakódovat.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Proč je to důležité:* Konstantní `EncodeTypes.DatabarOmniDirectional` říká knihovně, aby vytvořila symbologii Omni‑Directional. Řetězec dat obsahuje AI `(01)`, který označuje hodnotu GTIN‑14.

## Krok 2: Definice X‑dimension (velikost modulu)

X‑dimension určuje šířku nejúzkější čáry. Běžná hodnota pro vykreslování na obrazovce je **2 px na modul**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Použití konzistentního **set XDimension** zajišťuje, že se čárový kód správně škáluje napříč různými tiskárnami a skenery.

## Krok 3: Úprava výšky čáry na 30 px a uložení obrázku

Nyní změníme vlastnost výšky čáry. První výška, kterou použijeme, je **30 px**, což je vhodné pro malé štítky.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Konstantní `BarCodeImageFormat.Png` vybírá **barcode image format** PNG, který zachovává bezztrátovou kvalitu.

### Očekávaný výsledek

Soubor `DatabarBarHeight30Pixels.png` obsahuje DataBar Omni‑Directional čárový kód, jehož čáry jsou vysoké 30 px. Níže je zástupná ukázka:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tip:** Pokud otevřete PNG v editoru obrázků, uvidíte přesnou výšku čáry. Úzké čáry mají šířku 2 px, jak bylo definováno dříve.

## Krok 4: Změna výšky čáry na 60 px pro vyšší čárový kód

Pro aplikace, které vyžadují větší vizuální stopu – například nákladní štítek – můžete zvýšit výšku čáry na **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Mění se pouze vlastnost `BarHeight`; X‑dimension a kódování zůstávají stejné, takže čárový kód zůstává čitelný.

## Krok 5: Uložení aktualizovaného obrázku čárového kódu

Nakonec zapíšete vyšší čárový kód do druhého PNG souboru.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Očekávaný výsledek

Soubor `DatabarBarHeight60Pixels.png` zobrazuje stejná zakódovaná data, ale každá čára je nyní vysoká 60 px. Vizualní rozdíl je znázorněn níže:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Kompletní, spustitelný příklad

Spojením všech částí získáte kompletní skript, který můžete zkopírovat a vložit do souboru pojmenovaného `adjust_barcode_height.py` a spustit přímo.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Run the script:

```bash
python adjust_barcode_height.py
```

Měli byste vidět dva PNG soubory ve složce `output`, z nichž každý odráží nastavenou výšku čáry.

## Často kladené otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Can I use JPEG instead of PNG?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. JPEG je ztrátový, takže pro přesné skenování upřednostněte PNG. |
| **What if I need a bar height that isn’t a multiple of 10?** | Vlastnost `BarHeight.Pixels` přijímá libovolnou celočíselnou hodnotu. Stačí přiřadit požadovaný počet pixelů (např. `45`). |
| **Does changing the bar height affect the encoded data?** | Ne. Mění se pouze vizuální reprezentace; podkladový řetězec dat zůstává stejný. |
| **How do I change the X‑dimension after saving the first image?** | Můžete upravit `gen.parameters.barcode.x_dimension.pixels` kdykoli před voláním `save()`. Změna se projeví u následných obrázků. |
| **Is the generator thread‑safe?** | Instance `BarcodeGenerator` není garantována jako thread‑safe. Vytvořte samostatnou instanci pro každý vlákný, pokud generujete čárové kódy souběžně. |

## Závěr

Nyní víte, jak **upravit výšku čáry čárového kódu** v generátoru DataBar Omni‑Directional čárového kódu pomocí Pythonu. Tutoriál pokryl vytvoření generátoru, nastavení **X‑dimension**, úpravu vlastnosti **barcode bar height** a ukládání obrázků v požadovaném **barcode image format**.

Odtud můžete experimentovat s dalšími výškami, různými velikostmi modulů nebo přejít na alternativní formáty obrázků, jako je JPEG nebo BMP. Můžete také prozkoumat další funkce **barcode generator python**, jako je přidání lidsky čitelného textu nebo změna barevných schémat.

Šťastné programování a ať jsou vaše čárové kódy ostré a dokonale velikostně nastavené!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}