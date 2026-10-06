---
category: general
date: 2026-08-19
description: Jak generovat čárový kód s ECI pomocí Aspose.Barcode pro Python. Naučte
  se, jak přidat ECI data, kombinovat prostý text a uložit obrázek v jednom přehledném
  návodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: cs
lastmod: 2026-08-19
og_description: Jak generovat čárový kód s ECI pomocí Aspose.Barcode pro Python. Sledujte
  tento tutoriál, abyste se naučili, jak přidat ECI data, přizpůsobit vzhled a uložit
  výsledek.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Jak vygenerovat čárový kód s ECI pomocí Aspose.Barcode v Pythonu – krok
  za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Jak vygenerovat čárový kód s ECI pomocí Aspose.Barcode v Pythonu
url: /cs/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód s ECI pomocí Aspose.Barcode Python

Pokud potřebujete vědět **jak generovat čárový kód**, který obsahuje jak obyčejné znaky, tak data kódovaná pomocí ECI, tento návod ukazuje celý proces. Uvidíte přesně **jak přidat eci** sekce, upravit velikost a zapsat obrázek na disk pomocí jediného spustitelného skriptu.

Návod pokrývá:

* Získání verze knihovny Aspose.Barcode (volitelné, ale užitečné pro ladění).  
* Vytvoření rozšířeného řetězce codetext, který kombinuje obyčejné a ECI‑kódované znaky.  
* Vytvoření generátoru čárových kódů pro symbologii, která podporuje rozšířený codetext.  
* Přizpůsobení rozměrů čárového kódu a uložení finálního PNG souboru.

Externí dokumentace není potřeba; zkopírujte kód, spusťte jej a získáte obrázek čárového kódu, který obsahuje čínské znaky kódované pomocí ECI 26 (UTF‑8).

## Požadavky

Předtím, než začnete, ujistěte se, že máte:

* Nainstalovaný Python 3.8 nebo novější.  
* Nainstalovaný balíček `aspose-barcode` (`pip install aspose-barcode`).  
* Oprávnění k zápisu do složky, kam chcete uložit PNG soubor.

Pokud používáte virtuální prostředí, nejprve jej aktivujte, aby byly závislosti izolovány.

## Krok 1: Ověřte verzi Aspose.Barcode (volitelné)

Znalost přesné verze knihovny pomáhá, když potřebujete hlásit chyby nebo porovnávat funkce mezi verzemi.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Proč je to důležité*: Výstup verze potvrzuje, že běhové prostředí odpovídá dokumentaci, kterou používáte. Různé verze mohou podporovat různé hodnoty ECI, takže je to rychlá kontrola.

## Krok 2: Vytvořte rozšířený codetext s obyčejnými a ECI‑kódovanými částmi

Aspose.Barcode poskytuje `ExtCodetextBuilder` pro spojení obyčejných dat a ECI‑kódovaných segmentů. V tomto příkladu kombinujeme číselný řetězec s čínskými znaky.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Vysvětlení*:  
* `add_plain_codetext` vloží data, která symbologie čárového kódu považuje za běžné znaky.  
* `add_eci_codetext` říká generátoru, aby před dodaný text přidal indikátor ECI (zde **26**, který odpovídá UTF‑8). To je přesně **jak přidat eci** data do čárového kódu.

Můžete volat `add_eci_codetext` vícekrát pro vložení několika různých jazykových bloků. Builder automaticky zpracuje potřebné únikové sekvence.

## Krok 3: Vyberte symbologii, která podporuje rozšířený codetext

Ne každý typ čárového kódu může ukládat ECI segmenty. Code 128, QR a Data Matrix jsou běžné volby. Příklad používá Code 128, protože je široce podporován a dobře funguje pro smíšená alfanumerická data.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Proč Code 128?*: Přijímá celý rozsah ASCII a ECI únikové sekvence generované builderem, což ho činí ideálním pro scénář „jak generovat čárový kód“, který kombinuje obyčejný i kódovaný text.

## Krok 4: Upravit vzhled čárového kódu

Můžete řídit velikost, výšku, okraje a mnoho dalších vizuálních aspektů pomocí objektu `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tip*: Pokud plánujete tisk čárového kódu, zvyšte `x_dimension` a `bar_height` úměrně, aby byla zachována čitelnost při cílovém DPI.

## Krok 5: Uložit obrázek čárového kódu

Nakonec zapište vygenerovaný obrázek do souboru. Aspose.Barcode podporuje PNG, JPEG, BMP a mnoho dalších formátů.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Ujistěte se, že složka `output` existuje, nebo ji vytvořte pomocí `os.makedirs("output", exist_ok=True)` před voláním `save`.

### Očekávaný výsledek

Když otevřete `extended_codetext.png`, měli byste vidět Code 128 čárový kód, který kóduje číselný řetězec `1234567890` následovaný čínskými znaky „特殊字符“. Skenování čárového kódu moderním skenerem, který respektuje ECI, vrátí původní smíšený řetězec.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Čárový kód vygenerovaný příkladem jak generovat čárový kód"}

## Časté otázky a okrajové případy

### Co když potřebuji jinou znakovou sadu?

Vyberte vhodnou hodnotu ECI z tabulky ISO/IEC 18004. Například ECI 27 představuje ISO‑8859‑1 (Latin‑1). Nahraďte číselný identifikátor v `add_eci_codetext` odpovídajícím způsobem.

### Mohu vložit více než jeden ECI blok?

Ano. Zavolejte `add_eci_codetext` vícekrát. Builder vloží potřebné ECI přepínací kódy mezi bloky a zachová pořadí, ve kterém je přidáte.

### Podporuje generátor QR kódy s ECI?

Rozhodně. Nahraďte `barcode.Symbology.CODE_128` za `barcode.Symbology.QR` a upravte případné QR‑specifické parametry (např. úroveň opravy chyb) pomocí `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Jak zacházet s velmi dlouhými řetězci dat?

Pro lineární čárové kódy jako Code 128 je maximální délka přibližně 80 znaků při použití rozšířeného codetextu. Pokud tuto délku překročíte, zvažte přechod na dvourozměrnou symbologii, jako je QR nebo Data Matrix, která může uložit tisíce znaků.

## Kompletní spustitelný skript

Níže je kompletní program, který můžete zkopírovat a vložit do souboru s názvem `generate_extended_barcode.py` a spustit přímo.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která navazují na techniky předvedené v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat obrázek čárového kódu s přizpůsobením doplňkového prostoru pomocí Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Jak generovat obrázek čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Jak generovat DataMatrix čárový kód s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}