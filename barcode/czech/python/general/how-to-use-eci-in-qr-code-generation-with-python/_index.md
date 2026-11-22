---
category: general
date: 2026-11-20
description: Naučte se, jak používat ECI, generovat QR z textu, vymazat builder a
  uložit QR obrázek pomocí knihovny Python barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: cs
lastmod: 2026-11-20
og_description: Jak použít ECI k vygenerování QR z textu, vymazat QR builder a uložit
  QR obrázek – kompletní průvodce krok za krokem.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Jak použít ECI při generování QR kódu v Pythonu
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Jak použít ECI při generování QR kódu v Pythonu
url: /cs/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat ECI při generování QR kódu v Pythonu

Pokud potřebujete **how to use eci** při vytváření QR kódů, tento průvodce ukazuje přesné kroky. Uvidíte, jak generovat QR z textu, vyčistit builder a nakonec uložit QR obrázek – vše pomocí několika řádků Pythonu.

QR kódy, které obsahují vícejazyčná data, často vyžadují segment Extended Channel Interpretation (ECI), aby skenery věděly, jakou znakovou sadu použít. Tento tutoriál vás provede vytvářením rozšířeného codetextu, vymazáním builderu při jeho opětovném použití a uložením výsledku jako PNG souboru.

## Požadavky

- Nainstalovaný Python 3.8+.
- Balíček Aspose.BarCode for Python via .NET (nebo jakákoli kompatibilní knihovna `barcode`, která poskytuje `ExtCodetextBuilder` a `BarcodeGenerator`).
- Základní znalost konceptů QR kódu.

Nainstalujte knihovnu pomocí pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Použijte virtuální prostředí, abyste se vyhnuli konfliktům verzí.

## Krok 1: Importujte požadované třídy

Primární třídy, se kterými budete pracovat, jsou `ExtCodetextBuilder` pro vytváření rozšířeného codetextu a `BarcodeGenerator` pro vykreslení QR kódu.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Tyto importy vám poskytují přístup k metodám builderu (`add_plain_codetext`, `add_eci_codetext` atd.) a funkcím generátoru `set_code_text`, `set_symbology` a `save`.

## Krok 2: Vytvořte a nakonfigurujte ExtCodetextBuilder

Vytvoření nové instance builderu je první konkrétní příklad **how to use eci**. Builder můžete také později vymazat, pokud jej potřebujete znovu použít.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Volání `clear()` zajistí, že builder začne v čistém stavu, což je nezbytné při generování více QR kódů ve smyčce.

## Krok 3: Přidejte plain (non‑ECI) codetext

Plain text nepotřebuje ECI segment. Použijte `add_plain_codetext` pro ASCII‑kompatibilní řetězce.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Builder nyní obsahuje plain segment "HelloWorld".

## Krok 4: Přidejte ECI‑kódovaný segment

Zde je jádro **how to use eci**: zadáte hodnotu ECI (26 pro UTF‑8) a poskytnete Unicode řetězec, který chcete zakódovat. To umožní QR kódu nést ruštinu, čínštinu nebo jakýkoli jiný jazyk, který není zahrnut v výchozí sadě ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** Bez indikátoru ECI by scanner interpretoval bajty pomocí výchozí znakové sady a zobrazil by poškozené znaky pro non‑ASCII text.

## Krok 5: Získejte spojený rozšířený řetězec codetext

Po přidání všech požadovaných segmentů načtěte finální řetězec, který bude předán generátoru QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Vytisknutá hodnota vypadá například takto:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Přesný formát závisí na knihovně, ale důležitá část je, že ECI marker (`[ECI26]`) předchází UTF‑8 payloadu.

## Krok 6: Generujte QR kód pomocí spojeného textu

Nyní můžete **generate QR from text** předáním rozšířeného codetextu do `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Když otevřete `qr_extended.png`, objeví se QR kód, který kóduje jak plain anglický řetězec, tak ruský pozdrav. Naskenováním moderním QR scannerem se správně zobrazí „HelloWorld“ a „Привет“.

### Proč byste měli volat `clear()` před opětovným použitím builderu

Pokud generujete více QR kódů ve smyčce, zapomenutí vymazat builder spojí staré segmenty s novými, což vytvoří neplatný kód. Zde je rychlý vzor:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Tento úryvek ilustruje **how to clear builder** a **how to generate QR from text** opakovaně.

## Okrajové případy a běžné úskalí

| Situace | Na co si dát pozor | Jak postupovat |
|-----------|-------------------|---------------|
| **Nepodporovaná hodnota ECI** | Knihovna vyhodí `InvalidArgumentException`. | Používejte pouze hodnoty ECI uvedené ve specifikaci (např. 26 pro UTF‑8, 20 pro Shift‑JIS). |
| **Velmi dlouhý spojený text** | Verze QR může překročit maximální kapacitu. | Zvyšte verzi QR automaticky (`qr_generator.set_qr_version(QRVersion.AUTO)`) nebo rozdělte data mezi více QR kódů. |
| **Chyby oprávnění souborového systému** | `save` selže s `IOError`. | Ujistěte se, že cílový adresář existuje a proces má oprávnění k zápisu. |
| **Nesprávné zobrazení znakové sady** | Scanner zobrazuje poškozené znaky. | Ověřte, že správná hodnota ECI odpovídá skutečnému kódování řetězce. |

## Kompletní spustitelný příklad

Níže je samostatný skript, který můžete zkopírovat, vložit a spustit. Obsahuje všechny importy, zpracování chyb a komentáře pro přehlednost.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Spuštěním tohoto skriptu vznikne `output/qr_extended.png`, QR kód, který správně kóduje jak anglický, tak ruský text.

## Závěr

Nyní víte **how to use eci** při vytváření QR kódů, jak **clear the QR builder** před opětovným použitím, jak **generate QR from text**, a přesné kroky k **save QR image** v Pythonu. Dodržením výše uvedeného vzoru můžete vložit libovolný Unicode řetězec do QR kódu a zároveň udržet stav builderu předvídatelný.

### Co dál?

- Prozkoumejte další hodnoty ECI pro jazyky jako čínština (ECI 20) nebo ISO‑8859‑5.
- Upravte úrovně opravy chyb (`qr_generator.set_error_correction_level`) pro zlepšení spolehlivosti skenování.
- Kombinujte více ECI segmentů v jednom QR pro smíšené jazykové zprávy.

Šťastné kódování a užívejte si vytváření vícejazyčných QR kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat čárový kód s ECI pomocí Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Jak generovat QR kód jako obrázek v Pythonu s Aspose.Barcode – Kompletní průvodce](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Jak generovat čárový kód v Pythonu – kompletní krok‑za‑krokem průvodce](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}