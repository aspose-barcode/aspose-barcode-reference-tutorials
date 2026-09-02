---
category: general
date: 2026-07-18
description: Použijte extcodetextbuilder aspose k vytvoření QR kódů, které kombinují
  prostý ASCII a UTF‑8 ruský text. Naučte se generování QR kódů pomocí Aspose.Barcode
  v Pythonu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: cs
lastmod: 2026-07-18
og_description: Použití ExtCodeTextBuilder v Aspose vám umožní kombinovat prosté a
  UTF‑8 kódované fragmenty v QR kódu. Postupujte podle tohoto krok‑za‑krokem průvodce
  pro Aspose.Barcode v Pythonu.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: Použijte extcodetextbuilder aspose – Vytvářejte QR kódy s kombinovaným ECI
  textem
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Použijte ExtCodeTextBuilder Aspose: generujte QR kódy s kombinovaným ECI textem'
url: /cs/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# použijte extcodetextbuilder aspose – Vytvořte QR kódy s kombinovaným ECI textem

Už jste se někdy zamýšleli, jak **použít extcodetextbuilder aspose** k vložení jak obyčejné angličtiny, tak cyrilických znaků do jediného QR kódu? Nejste v tom sami. Mnoho vývojářů narazí na problém, když potřebují kombinovat ASCII a ne‑ASCII data, zejména když cílový skener očekává správné ECI (Extended Channel Interpretation) značky.  

V tomto tutoriálu projdeme přesně kroky, jak vytvořit QR kód, který nese „HELLO123“ **a** ruské slovo „Привет“, vše pomocí Python API knihovny Aspose.Barcode. Na konci budete mít připravený skript, pochopíte, proč je každé volání důležité, a budete vědět, jak proces upravit pro jiné jazyky nebo datové formáty.

## Co se naučíte

- Jak **inicializovat ExtCodetextBuilder** a přidat obyčejné i ECI‑kódované fragmenty.  
- Proč hodnota **ECI encoding** `3` odpovídá UTF‑8 a jak to ovlivňuje skenování.  
- Přesné pořadí pro nastavení **generátoru QR kódu** s Aspose.Barcode.  
- Jak uložit výsledný obrázek a ověřit smíšený obsah.  

**Požadavky** – potřebujete Python 3.8+, nainstalovaný balíček `aspose-barcode` (`pip install aspose-barcode`) a složku, do které můžete zapisovat obrázky. Nic víc.

---

## použijte extcodetextbuilder aspose k vytvoření smíšeného codetextu

Prvním, co potřebujeme, je instance `ExtCodetextBuilder`. Představte si ji jako návrhový vzor builder, který spojuje různé kusy textu a automaticky vkládá správné ECI značky za scénou.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Proč je to důležité:**  
- `add_plain_codetext` zachová data tak, jak jsou, což je ideální pro čísla nebo anglická písmena.  
- `add_eci_codetext` vloží ECI segment (`[ECI:3]`) před zadaný řetězec a informuje jakýkoli kompatibilní čtečkový zařízení, že následující bajty jsou UTF‑8. Bez toho by skener interpretoval cyrilické bajty jako odpad.

> **Tip:** Pokud potřebujete jinou znakovou sadu, změňte hodnotu `eci_encoding` podle tabulky ECI (např. `26` pro ISO‑8859‑1).  

---

## Inicializace generování QR kódu s Aspose.Barcode

Nyní, když máme správně formátovaný `extended_codetext`, můžeme jej předat generátoru QR kódu. Aspose.Barcode abstrahuje nízkoúrovňové vytváření QR matice, takže se můžete soustředit na data.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Co se zde děje?**  
- `BarcodeGenerator()` vytvoří nový objekt generátoru s výchozím nastavením (velikost, rozlišení atd.).  
- `set_symbology` říká enginu, že chceme QR kód místo například Code128.  

Pokud potřebujete vyšší úroveň opravy chyb, můžete před přiřazením codetextu zavolat `qr_generator.parameters.barcode.qr_error_level = ...`.

---

## Přiřazení rozšířeného codetextu generátoru QR

S připraveným generátorem je dalším krokem jednoduše předat smíšený řetězec, který jsme vytvořili dříve.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Proč nepoužít `set_codetext`?**  
`set_codetext` zachází s vstupem jako s obyčejným textem a odstraňuje všechny ECI značky. `set_extended_codetext` zachová surové bajty, včetně ECI segmentu, a zajistí, že skener uvidí správný přepínač jazyka.

---

## Uložení obrázku QR kódu a ověření výsledku

Nakonec zapíšeme QR kód na disk. Aspose.Barcode podporuje PNG, JPEG, BMP a další; PNG je bezpečná výchozí volba, protože zachovává bezztrátová data.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Měli byste nyní mít PNG soubor na určeném místě. Otevřete jej v libovolné aplikaci pro skenování QR kódů, která podporuje ECI (většina moderních chytrých telefonů to umí). Naskenujte jednou – uvidíte „HELLO123“. Naskenujte znovu (nebo použijte skener, který zobrazuje surová data) – získáte také „Привет“. Obě části se objeví jako jeden payload, přesně tak, jak jsme jej vytvořili.

![příklad QR kódu s extcodetextbuilder aspose ukazující smíšený ECI text](YOUR_DIRECTORY/qr_extended.png)

*Alt text obrázku: příklad QR kódu s extcodetextbuilder aspose ukazující smíšený ECI text*

---

## Kompletní, připravený ke spuštění skript

Sestavením všeho dohromady získáte kompletní program, který můžete zkopírovat do souboru pojmenovaného `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Spusťte jej pomocí:

```bash
python qr_mixed_eci.py
```

Uvidíte zprávu v konzoli potvrzující umístění uložení a PNG se objeví přesně tam, kam jste zadali.

---

## Časté otázky a okrajové případy

### Co když můj skener nerozpozná cyrilickou část?

Ujistěte se, že skenovací aplikace deklaruje podporu ECI. Starší hardware může ECI segment ignorovat a interpretovat bajty jako ISO‑8859‑1, což vede k poškozeným znakům.

### Můžu přidat více než dva fragmenty?

Určitě. Zavolejte `add_plain_codetext` nebo `add_eci_codetext` tolikrát, kolik potřebujete. Builder je spojí v pořadí, ve kterém metody voláte.

### Jak změním velikost QR kódu nebo barvu popředí?

Použijte objekt `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Existuje způsob, jak vložit binární data (např. malý soubor) spolu s textem?

Ano. Použijte `add_binary_codetext` s polem bajtů a spárujte jej s vhodným ECI, pokud binární data představují konkrétní znakovou sadu. Builder se postará o potřebné přepínání režimů.

---

## Závěr

Nyní víte **jak použít extcodetextbuilder aspose** k tvorbě QR kódů, které plynule kombinují obyčejné ASCII a UTF‑8 kódovaný ruský text. Využitím `ExtCodetextBuilder`, nastavením správného **ECI encoding** a předáním výsledku do **generátoru QR kódu Aspose.Barcode** získáte jediný, standardy‑kompatibilní obrázek, který funguje na moderních skenerech.  

Odtud můžete zkusit vyměnit `eci_encoding=3` za jiné jazykové identifikátory nebo experimentovat s dalšími obyčejnými fragmenty pro vytvoření vícejazykových payloadů. Můžete také prozkoumat možnosti `BarCodeImageFormat` pro výstup ve formátu SVG nebo PDF, pokud potřebujete vektorovou grafiku.  

Šťastné kódování a neváhejte zanechat komentář, pokud narazíte na potíže – vaše zpětná vazba pomáhá tyto návody ještě vylepšovat!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Generovat čárový kód v Javě – Nastavit text kódu pomocí Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Vytvořit čárový kód aspose .net – Konfigurace textu DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Kódování textu Aztec Code s Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}