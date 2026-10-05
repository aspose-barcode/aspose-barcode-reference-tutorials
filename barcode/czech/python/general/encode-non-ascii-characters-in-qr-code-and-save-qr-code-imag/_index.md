---
category: general
date: 2026-09-10
description: Zakódujte ne‑ASCII znaky do QR kódu a uložte obrázek QR kódu pomocí jednoduchého
  Python builderu. Postupujte podle krok‑za‑krokem průvodce s využitím ExtCodetextBuilder
  a BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: cs
lastmod: 2026-09-10
og_description: Zakódujte ne‑ASCII znaky do QR kódu a uložte obrázek QR kódu pomocí
  Pythonu. Tento tutoriál ukazuje, jak vytvořit rozšířený text kódu, vygenerovat QR
  kód a uložit obrázek.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Zakódujte ne‑ASCII znaky do QR kódu a uložte obrázek QR kódu – krok za krokem
  průvodce v Pythonu
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Zakódujte ne‑ASCII znaky do QR kódu a uložte obrázek QR kódu
url: /cs/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kódování ne‑ASCII znaků v QR kódu a uložení obrázku QR kódu

Pokud potřebujete **kódovat ne‑ASCII znaky** v QR kódu, tento návod vám přesně ukáže, jak to provést a následně **uložit obrázek QR kódu** na disk. Ať už pracujete s ruskými, čínskými nebo emoji daty, ExtCodetextBuilder vám umožní kombinovat prostý text a ECI‑kódované segmenty bez ručního manipulování s bajty.

Naučíte se, jak vytvořit rozšířený řetězec codetext, vygenerovat QR kód, který tento řetězec rozumí, a nakonec zapsat obrázek čárového kódu do souboru. Tutoriál předpokládá základní znalosti Pythonu a že máte nainstalovaný SDK `barcode`.

## Požadavky

* Python 3.8+ nainstalován.
* Python balíček `barcode` (nebo odpovídající SDK), který poskytuje `ExtCodetextBuilder`, `CodetextEncodingType` a `BarcodeGenerator`.
* Oprávnění k zápisu do adresáře, kam chcete **uložit obrázek QR kódu**.

Můžete nainstalovat SDK pomocí pip (nahraďte `barcode-sdk` skutečným názvem balíčku):

```bash
pip install barcode-sdk
```

## Krok 1: Vytvořte rozšířený codetext builder

Prvním krokem je vytvořit instanci `ExtCodetextBuilder`. Tento objekt sbírá více textových segmentů a vytváří jeden řetězec, který může interpretovat symbologie QR kódu.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Proč je to důležité*: QR kódy podporují **rozšířený codetext**, což znamená, že můžete vložit několik režimů kódování (plain, ECI, atd.) do jednoho čárového kódu. Builder abstrahuje nízkoúrovňové formátování požadované specifikací QR.

## Krok 2: Přidejte segment prostého textu

Prostý text je výchozí režim a funguje pro ASCII znaky. Přidání jej jako první poskytuje čitelný fallback pro skenery, které ignorují ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Pokud byste tento krok vynechali, QR kód by obsahoval pouze ECI segment, který některé starší čtečky nemusí správně dekódovat.

## Krok 3: Přidejte ECI‑kódovaný segment pro ne‑ASCII znaky

Pro zahrnutí znaků mimo rozsah ASCII — například cyrilice, čínštiny nebo emoji — musíte specifikovat ECI (Extended Channel Interpretation) kódování. Zde používáme UTF‑8 pro ruské slovo „Привет“.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Proč to funguje*: Specifikace QR definuje hodnoty ECI, které říkají scanneru, jakou znakovou sadu použít. Bez ECI markeru by surové bajty byly interpretovány jako ISO‑8859‑1, což vede k poškozenému výstupu.

## Krok 4: Získejte kombinovaný rozšířený codetext řetězec

Po přidání všech požadovaných segmentů zavolejte `get_extended_codetext()`, abyste získali finální řetězec, který očekává generátor čárových kódů.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Vytisknutá hodnota vypadá jako řada řídicích znaků následovaná skutečným textem, ale nikdy ji nemusíte ručně parsovat.

## Krok 5: Vygenerujte QR kód pomocí rozšířeného codetextu

Nyní vytvořte `BarcodeGenerator`, nastavte symbologii na QR (jediná běžná 2‑D symbologie, která podporuje rozšířený codetext) a předávejte kombinovaný řetězec.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tip*: Pokud zkusíte stejný postup s Code‑128 nebo DataMatrix, SDK vyvolá výjimku, protože tyto formáty nemohou interpretovat ECI markery.

## Krok 6: Uložte obrázek QR kódu

Nakonec zapište čárový kód do PNG souboru. Zde **uložíte obrázek QR kódu** pro pozdější použití.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Ujistěte se, že složka `output` existuje, nebo ji vytvořte pomocí `os.makedirs('output', exist_ok=True)` před voláním `save`.

### Kompletní spustitelný příklad

Spojením všech kroků získáte samostatný skript, který můžete spustit okamžitě:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Očekávaný výstup** (konzole):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Otevřením `qr_extended.png` libovolným QR scannerem se zobrazí `HelloWorldПривет`. Skenery, které rozumí ECI, zobrazí cyrilické znaky správně; ostatní zobrazí pouze ASCII část.

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| *Mohu použít jiné kódování jako Shift‑JIS?* | Ano. Nahraďte `CodetextEncodingType.UTF_8` za `CodetextEncodingType.SHIFT_JIS` a poskytněte odpovídající text. |
| *Co když kombinovaná data překročí kapacitu QR kódu?* | QR kódy mají limit verze (až 177 × 177 modulů). Pokud builder vyhodí výjimku velikosti, buď zvýšte úroveň opravy chyb, nebo rozdělte data do více QR kódů. |
| *Musím nastavit konkrétní verzi QR?* | SDK automaticky vybere nejmenší verzi, která data pojme. V případě potřeby můžete vynutit verzi pomocí `qr_generator.set_qr_version(10)`. |
| *Bude obrázek průhledný?* | Ve výchozím nastavení SDK zapisuje PNG s bílým pozadím. Pokud potřebujete průhlednost, použijte `qr_generator.set_background_color(Color.Transparent)` před `save`. |

## Závěr

V tomto tutoriálu jste se naučili, jak **kódovat ne‑ASCII znaky** v QR kódu pomocí `ExtCodetextBuilder` a následně **uložit obrázek QR kódu** pomocí `BarcodeGenerator`. Proces zahrnuje vytvoření rozšířeného codetext řetězce, přidání jak prostých, tak ECI‑kódovaných segmentů, generování QR symbologie a nakonec zápis souboru s obrázkem.

Odtud můžete dále zkoumat:

* Přidání dalších ECI segmentů (různé jazyky nebo emoji).
* Úprava úrovní opravy chyb QR pro vyšší spolehlivost.
* Vložení vygenerovaného PNG do PDF nebo webových stránek.

Šťastné programování a užívejte si tvorbu vícejazykových QR kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat obrázek QR kódu v Pythonu s Aspose.Barcode – Kompletní průvodce](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generovat Code128 čárový kód s Aspose.Barcode Python – Kompletní průvodce](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [zobrazit název produktu pomocí Python barcode knihovny – krok za krokem průvodce](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}