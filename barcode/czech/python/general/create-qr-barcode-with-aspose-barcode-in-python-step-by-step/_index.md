---
category: general
date: 2026-08-09
description: Vytvořte QR kód v Pythonu pomocí Aspose.BarCode. Naučte se, jak vytvořit
  rozšířený kódový text, upravit vzhled a uložit obrázek – vše v jednom tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: cs
lastmod: 2026-08-09
og_description: Vytvořte QR čárový kód v Pythonu s Aspose.BarCode. Tento průvodce
  ukazuje, jak vytvořit rozšířený kódový text, nastavit vizuální parametry a exportovat
  obrázek.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Vytvořte QR čárový kód pomocí Aspose.BarCode v Pythonu – kompletní příklad
  kódu
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Vytvořte QR kód pomocí Aspose.BarCode v Pythonu – krok za krokem
url: /cs/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření QR čárového kódu pomocí Aspose.BarCode v Pythonu – krok za krokem

Pokud potřebujete **vytvořit QR čárový kód** v Pythonu, tento tutoriál vás provede celým procesem pomocí knihovny Aspose.BarCode. Ať už kódujete ID produktů, vícejazyčný text nebo vlastní data, uvidíte, jak vytvořit rozšířený codetext, upravit vizuální nastavení a uložit finální obrázek v jediném spustitelném skriptu.

Příklad také ukazuje, jak zobrazit verzi knihovny, což vám pomůže ověřit, že používáte kompatibilní vydání. Na konci tohoto průvodce budete mít připravený QR čárový kód a jasné pochopení každé konfigurační možnosti.

## Prerequisites

- Python 3.8+ nainstalován.
- Balíček `aspose-barcode` (nainstalujte pomocí `pip install aspose-barcode`).
- Základní znalost syntaxe Pythonu.
- Oprávnění k zápisu do výstupního adresáře, kam bude soubor PNG uložen.

> **Tip:** Použijte virtuální prostředí, abyste se vyhnuli konfliktům verzí s ostatními projekty.

## Krok 1: Ověření verze knihovny Aspose.BarCode

Zobrazení verze knihovny zajišťuje, že používáte vydání, které podporuje rozšířený codetext a QR kódování.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Proč je to důležité:**  
Starší vydání mohou postrádat třídu `ExtCodetextBuilder`, která je potřebná pro smíšené plain a ECI segmenty. Ověření verze zabraňuje pozdějším chybám za běhu.

## Krok 2: Vytvoření řetězce rozšířeného codetextu

Rozšířený codetext vám umožňuje kombinovat plain ASCII data s Unicode (ECI) segmenty, což je nezbytné pro vícejazyčné QR kódy.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Proč je to důležité:**  
Metoda `add_plain_codetext` ukládá data jako standardní ASCII, zatímco `add_eci_codetext` přidává Unicode blok s odpovídajícím ECI designátorem. Tento přístup zajišťuje, že QR skenery interpretují japonský text správně a nedochází k poškozeným znakům.

### Běžné varianty

- **Více ECI segmentů:** Zavolejte `add_eci_codetext` několikrát pro smíchání několika jazyků.
- **Různé ECI identifikátory:** Použijte `27` pro ISO‑8859‑1, `28` pro ISO‑8859‑2 atd., podle cílového kódování.

## Krok 3: Generování QR čárového kódu pomocí rozšířeného codetextu

Nyní, když máme správně naformátovaný řetězec, můžeme vytvořit QR kód.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Proč je to důležité:**  
`EncodeTypes.QR` říká Aspose.BarCode, aby použil symbologii QR. Předání `extended_codetext` přímo propojí smíšená data s QR mřížkou a zachová jak plain, tak Unicode část.

## Krok 4: Úprava vizuálního vzhledu (volitelné, ale doporučené)

Doladění vizuálních parametrů čárového kódu zlepšuje spolehlivost skenování a odpovídá firemním směrnicím.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Proč je to důležité:**  
- **`x_dimension`** řídí velikost každého QR modulu; příliš malý může způsobit chyby čtení na nízkorozlišovacích zařízeních.  
- **`border_width`** přidává tichou zónu. Některé skenery vyžadují alespoň 4‑modulovou tichou zónu; knihovna ji přidá automaticky, ale můžete ji zvýšit pro extra bezpečnost.

### Řešení okrajových případů

- **Vysoká hustota dat:** Pokud jsou kódovaná data velká, možná budete muset zvýšit `x_dimension` nebo zvolit vyšší úroveň opravy chyb (pomocí `qr_generator.parameters.qr.error_correction_level`).  
- **Průhledné pozadí:** Nastavte `qr_generator.parameters.barcode.bg_color = Color.Transparent` pro PNG s alfa kanálem.

## Krok 5: Uložení QR čárového kódu jako obrázku

Nakonec zapíšeme obrázek na disk ve vámi preferovaném formátu.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Proč je to důležité:**  
Ukládání jako PNG zachovává bezztrátovou kvalitu, což je ideální pro QR kódy, které potřebují ostré hrany. Pokud potřebujete jiný formát pro webovou aplikaci, stačí změnit výčtový typ `BarCodeImageFormat`.

### Ověření výsledku

Otevřete uložený soubor v libovolném prohlížeči obrázků. Měli byste vidět QR kód, který po nascanování vrátí kombinovaný řetězec:

```
ABC12345
こんにちは
```

Většina moderních QR skenerů nejprve zobrazí plain segment a poté správně vykreslí japonské pozdravy.

---

## Kompletní spustitelný skript

Zkopírujte celý blok níže do souboru s názvem `create_qr_barcode.py` a spusťte jej pomocí `python create_qr_barcode.py`. Upravit `YOUR_DIRECTORY` na zapisovatelnou složku ve vašem počítači.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Spuštěním tohoto skriptu se vypíše verze, rozšířený codetext a potvrzení, že soubor PNG byl vytvořen.

---

## Závěr

Nyní víte, jak **vytvořit QR čárový kód** v Pythonu pomocí Aspose.BarCode. Tutoriál pokryl:

1. Ověření verze knihovny.  
2. Vytvoření rozšířeného codetextu s plain a ECI (Unicode) segmenty.  
3. Generování QR kódu.  
4. Přizpůsobení vizuálních parametrů, jako je velikost modulu a šířka okraje.  
5. Uložení finálního obrázku ve formátu PNG.

Odtud můžete dále zkoumat:

- Změna úrovně opravy chyb (`qr_generator.parameters.qr.error_correction_level`).  
- Přidání loga nebo obrázku pozadí (`qr_generator.parameters.qr.logo`).  
- Export do dalších formátů, jako je SVG pro škálovatelnou webovou grafiku.  
- Integrace generátoru do endpointu Flask nebo Django pro tvorbu QR kódu za běhu.

Experimentujte s různými datovými náklady a vizuálními nastaveními, aby vyhovovaly značce a požadavkům na skenování vaší aplikace. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak vytvořit rozšířený codetext pro dotcode pomocí Aspose.BarCode pro .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Vytvoření čárového kódu Aspose .NET – konfigurace textu DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}