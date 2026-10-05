---
category: general
date: 2026-08-12
description: Vytvořte omni‑directionální databar pomocí Pythonu a naučte se, jak vytvořit
  obrázek čárového kódu v Pythonu pomocí Aspose.BarCode. Postupujte podle krok‑za‑krokem
  průvodce pro kompletní řešení.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: cs
lastmod: 2026-08-12
og_description: Vytvořte omnidirekční databar pomocí Pythonu a během několika minut
  vygenerujte obrázek čárového kódu v Pythonu. Tento tutoriál ukazuje kompletní, spustitelný
  příklad.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Vytvořte všesměrový datový panel – kompletní průvodce Pythonem
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Vytvořte všesměrový databar a obrázek čárového kódu v Pythonu
url: /cs/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření omni‑directional databar a obrázku čárového kódu v Pythonu

Pokud potřebujete **vytvořit omni directional databar** v Python projektu, tento návod vám ukáže, jak na to, a také jak **vytvořit obrázek čárového kódu v Pythonu** pomocí knihovny Aspose.BarCode. Získáte připravený skript, který vygeneruje dva PNG soubory s různými poměry stran.

Generování DataBaru podle specifikace Omni‑directional je běžnou požadavkem v maloobchodních a logistických aplikacích. Tutoriál pokrývá instalaci, nastavení X‑dimenze, úpravu poměru stran a uložení finálních obrázků. Nepotřebujete žádné externí služby; vše běží lokálně.

## Co budete potřebovat

Než začnete, ujistěte se, že máte:

* Python 3.8 nebo novější nainstalovaný na vašem počítači.  
* Přístup k terminálu nebo příkazovému řádku.  
* Oprávnění k zápisu do složky, kam budou obrázky čárových kódů uloženy.

Jedinou třetí stranou závislostí je **Aspose.BarCode for Python via .NET**, která podporuje typ Omni‑directional DataBar přímo z krabice.

## Krok 1: Instalace Aspose.BarCode pro Python

Aspose.BarCode poskytuje třídu `BarcodeGenerator`, která se používá v ukázkovém kódu. Nainstalujte balíček pomocí `pip`:

```bash
pip install aspose-barcode
```

Balíček obsahuje potřebná .NET runtime vazby, takže není nutné instalovat .NET SDK samostatně.

## Krok 2: Import knihovny a vytvoření generátoru

První řádek skriptu vytvoří generátor pro vrstvený Omni‑directional DataBar. Jako ukázková data se používá hodnota GTIN‑14 `(01)12345678901231`.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Proč je tento krok důležitý*: Konstantní `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` říká knihovně, aby kódovala hodnotu jako Omni‑directional DataBar, což je formát požadovaný mnoha pokladními skenery.

## Krok 3: Nastavení X‑dimenze (šířka modulu)

X‑dimenze určuje šířku nejmenšího modulu čáry. Hodnota `2` pixelů vytváří čistý, čitelný čárový kód bez nadměrné velikosti souboru.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Proč je tento krok důležitý*: Úprava X‑dimenze vám umožní vyvážit čitelnost a rozměry obrázku. Příliš malá X‑dimenze může vést k špatnému vykreslení na nízkorozlišovacích tiskárnách.

## Krok 4: Konfigurace poměru stran a uložení prvního obrázku

Poměr stran ovlivňuje celkovou výšku DataBaru vzhledem k jeho šířce. Poměr `15` vytváří kompaktní vizuální styl.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Tip**: Použijte `pathlib.Path` pro vytvoření výstupní cesty, který automaticky vytvoří chybějící adresáře.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Krok 5: Změna poměru stran pro druhý vizuální styl a uložení dalšího obrázku

Změna poměru stran na `30` vytvoří vyšší čárový kód, který může být vyžadován specifickým hardwarem skeneru.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Proč je tento krok důležitý*: Různí prodejci a skenovací zařízení mají odlišná omezení velikosti. Poskytnutí obou poměrů stran v jednom skriptu vám umožní vygenerovat požadovaný styl bez duplikace kódu.

## Kompletní skript – vytvoření omni directional databar a obrázku čárového kódu v Pythonu

Níže je kompletní, spustitelný příklad, který zahrnuje všechny předchozí kroky. Uložte jej jako `generate_databar.py` a spusťte pomocí `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Očekávaný výstup

Po spuštění skriptu se vytvoří následující soubory:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Oba obrázky zobrazují platný Omni‑directional DataBar, který lze načíst standardním maloobchodním vybavením.

![example of create omni directional databar barcode image in Python](example_databar.png "create omni directional databar barcode image python")

*Výše uvedený obrázek je jen zástupný a ilustruje dva uložené PNG soubory.*

## Řešení běžných problémů

| Problém | Důvod | Řešení |
|---------|-------|--------|
| `ImportError: No module named aspose` | Aspose.BarCode není nainstalován nebo je nainstalován v jiném prostředí. | Aktivujte správné virtuální prostředí a spusťte `pip install aspose-barcode`. |
| `PermissionError` při ukládání | Skript nemá oprávnění k zápisu do cílové složky. | Vyberte adresář, ke kterému máte přístup, nebo spusťte skript s potřebnými oprávněními. |
| Čárový kód se nenačte | X‑dimenze je příliš malá nebo poměr stran nevyhovuje skeneru. | Zvyšte `x_dimension.pixels` na 3 nebo 4 a vyzkoušejte různé hodnoty `aspect_ratio` (např. 20, 25). |
| Chybí .NET runtime | Aspose.BarCode závisí na .NET runtime na Windows/Linux. | Nainstalujte nejnovější .NET runtime z webu Microsoft; dokumentace balíčku poskytuje platformně specifické pokyny. |

## Rozšíření příkladu

Můžete upravit skript tak, aby generoval jiné varianty DataBaru (např. `DATABAR_STACKED`, `DATABAR_EXPANDED`). Nahraďte konstantu `EncodeTypes` odpovídající hodnotou:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Pokud potřebujete vložit čárový kód do PDF, Aspose.PDF pro Python dokáže importovat PNG soubor přímo, nebo můžete použít metodu `save` s parametrem `BarCodeImageFormat.Pdf`.

## Závěr

Tento tutoriál ukázal, jak **vytvořit omni directional databar** a jak **vytvořit obrázek čárového kódu v Pythonu** pomocí Aspose.BarCode. Nyní máte kompletní, reprodukovatelný skript, který generuje dva PNG soubory s různými poměry stran, řeší běžné problémy a lze jej rozšířit na další formáty čárových kódů.

Dále můžete zkoumat generování QR kódů, přidávání čárových kódů do PDF faktur nebo automatizaci hromadného zpracování velkých katalogů produktů. Všechny tyto témata staví na stejném vzoru `BarcodeGenerator`, který byl zde předveden. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}