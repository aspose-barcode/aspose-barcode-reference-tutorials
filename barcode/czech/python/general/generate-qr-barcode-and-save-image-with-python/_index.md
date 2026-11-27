---
category: general
date: 2026-11-27
description: Vygenerujte QR kód v Pythonu pomocí Aspose.Barcode a naučte se rychle
  uložit obrázek čárového kódu na disk.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: cs
lastmod: 2026-11-27
og_description: Vygenerujte QR kód v Pythonu pomocí Aspose.Barcode a okamžitě uložte
  obrázek čárového kódu. Postupujte podle kompletního příkladu pro vytvoření, přizpůsobení
  a uložení QR kódů.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Generujte QR kód a uložte obrázek pomocí Pythonu – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Vygenerujte QR kód a uložte obrázek pomocí Pythonu
url: /cs/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování QR čárového kódu a uložení obrázku pomocí Pythonu

Pokud potřebujete **generovat QR čárový kód** v aplikaci Python, tento návod vám ukáže, jak to provést pomocí knihovny Aspose.Barcode. Také se naučíte správný způsob **uložení obrázku čárového kódu** do místní složky, jak získat podrobnosti o verzi knihovny a jak pracovat s rozšířenými segmenty codetextu.

Vytváření QR kódů je běžnou potřebou pro systémy vstupenek, mobilní platby a sledování produktů. Na konci tohoto tutoriálu budete mít připravený skript, který vygeneruje soubor s obrázkem QR čárového kódu a vypíše informace o verzi pro ladění nebo účely shody.

## Požadavky

Než začnete, ujistěte se, že máte:

* Python 3.8 nebo novější nainstalovaný.
* Balíček `aspose-barcode`. Nainstalujte jej pomocí `pip install aspose-barcode`.
* Oprávnění k zápisu do adresáře, kde bude obrázek čárového kódu uložen.

Žádné další externí služby nejsou vyžadovány; celý proces probíhá lokálně.

## Krok 1: Vytvoření rozšířeného codetextu pomocí `ExtCodetextBuilder`

Rozšířený codetext vám umožňuje kombinovat prostý text a segmenty ECI (Extended Channel Interpretation) v jediném QR kódu. To je užitečné, když potřebujete vložit znaky z různých znakových sad, například znak eura.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Proč je tento krok důležitý:**  
`ExtCodetextBuilder` sestaví finální řetězec, který QR enkodér zpracuje. Bez vytvoření rozšířeného codetextu by čárový kód obsahoval jen prosté ASCII znaky a nemohl by reprezentovat lokálně specifické symboly.

## Krok 2: Získání kombinovaného řetězce rozšířeného codetextu

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Výstup vypadá takto:

```
Extended codetext: ABC123[ECI3]€123
```

Závorkový marker `[ECI3]` říká QR enkodéru, aby přepnul na určenou znakovou sadu pro následující znaky.

## Krok 3: Generování QR čárového kódu pomocí rozšířeného codetextu

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Vysvětlení:**  
`BarcodeGenerator` přijímá dva argumenty: typ čárového kódu (`QR`) a data k zakódování (`extended_codetext`). Generátor připraví všechny interní struktury potřebné pro vykreslení.

## Krok 4: Uložení vygenerovaného obrázku čárového kódu

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Proč použít tento přístup:**  
Volání `save` přímo zapíše obrázek na disk ve formátu odvozeném od přípony souboru. Metoda podporuje PNG, JPEG, BMP a TIFF, což vám dává flexibilitu pro různé následné spotřebitele.

### Ověření uloženého obrázku

Otevřete soubor `output/qr_extended.png` libovolným prohlížečem obrázků. Měli byste vidět QR kód, který po naskenování vrátí řetězec `ABC123€123`. Většina moderních mobilních QR skenerů automaticky zpracuje ECI segment.

## Krok 5: Dotaz na informace o verzi Aspose.BarCode (volitelné, ale užitečné)

Znalost přesné verze knihovny Aspose.BarCode pomáhá při hlášení chyb nebo ověřování kompatibility.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typický výstup:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Kompletní skript – zkopírujte, vložte a spusťte

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Spuštěním skriptu se vytvoří obrázek QR kódu a do konzole se vypíše jak rozšířený codetext, tak podrobnosti o verzi.

## Běžné varianty a okrajové případy

| Situace | Doporučená úprava |
|-----------|------------------------|
| **Jiná znaková sada** | Změňte identifikátor ECI předávaný do `add_eci_codetext`. Pro UTF‑8 použijte `5`. |
| **Vyšší úroveň opravy chyb** | Nastavte `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` před voláním `save`. |
| **Vlastní velikost obrázku** | Použijte `barcode.parameters.image_width` a `barcode.parameters.image_height` pro nastavení rozměrů v pixelech. |
| **Výstup jiný než PNG** | Změňte příponu souboru v `output_path` na `.jpg` nebo `.bmp`. Knihovna automaticky vybere správný enkodér. |

## Profesionální tipy

* **Vytvořte výstupní složku** programově, pokud nemusí existovat:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Ověřte QR kód** po vygenerování jeho načtením pomocí `aspose.barcode.BarcodeReader`. Tím zajistíte, že zakódovaná data odpovídají očekáváním, zejména při použití ECI segmentů.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Tip pro výkon** – znovu použijte jedinou instanci `BarcodeGenerator`, pokud potřebujete generovat mnoho QR kódů ve smyčce. Resetujte vlastnost `code_text` místo vytváření nového objektu v každé iteraci.

## Závěr

Nyní víte, jak **generovat QR čárový kód** v Pythonu pomocí Aspose.Barcode, jak vytvořit rozšířený codetext, který kombinuje prostý text a ECI segmenty, a jak **správně uložit obrázek čárového kódu** na disk. Skript také ukazuje, jak získat informace o verzi knihovny pro řešení problémů.

Další kroky, které můžete prozkoumat, zahrnují:

* Přidání loga nebo vlastních barev do QR kódu.
* Vložení QR čárového kódu přímo do PDF pomocí Aspose.PDF.
* Automatizaci hromadného generování pro velké datové sady.

Neváhejte experimentovat s různými datovými náklady, úrovněmi opravy chyb a formáty obrázků. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}