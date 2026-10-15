---
category: general
date: 2026-10-15
description: Vytvořte čárový kód ze řetězce pomocí Aspose.Barcode pro Python. Naučte
  se, jak generovat čárový kód, nastavit rozměry a uložit jej jako PNG během několika
  minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: cs
lastmod: 2026-10-15
og_description: Vytvořte čárový kód ze řetězce pomocí Aspose.Barcode pro Python. Tento
  tutoriál vám krok za krokem ukáže, jak vygenerovat poštovní čárový kód a uložit
  jej jako PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Vytvořte čárový kód ze řetězce v Pythonu – průvodce Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Jak vytvořit čárový kód ze řetězce v Pythonu pomocí Aspose
url: /cs/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód ze řetězce v Pythonu pomocí Aspose

Pokud potřebujete rychle **vytvořit čárový kód ze řetězce**, Aspose.Barcode pro Python to usnadňuje. V tomto průvodci uvidíte přesně **jak generovat čárový kód** obrázky, upravit X‑dimenzi a uložit výsledek jako PNG soubor — vše pomocí několika řádků kódu.

Také získáte kompletní **příklad generátoru čárových kódů**, který můžete zkopírovat a vložit do svého projektu. Nejsou potřeba žádné externí skripty ani složitá konfigurace a tutoriál funguje s aktuálním vydáním Aspose.Barcode 23.10.

## Požadavky

- Python 3.8+ nainstalovaný na vašem počítači  
- Aktivní licence Aspose.Barcode pro Python (bezplatná zkušební verze funguje pro hodnocení)  
- `pip install aspose-barcode` spuštěný ve vašem virtuálním prostředí  

Tyto položky zajišťují, že kód poběží bez chyb při importu.

## Vytvoření čárového kódu ze řetězce pomocí Aspose.Barcode (Python)

Prvním krokem je vytvořit instanci `BarcodeGenerator` s požadovanou symbologií — v tomto případě **Planet** poštovním čárovým kódem — a řetězcem, který chcete zakódovat.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Proč je to důležité:**  
`EncodeTypes.Planet` říká Aspose, aby použil poštovní symbologii Planet, která je navržena pro třídění pošty v mnoha zemích. Druhý argument (`"123456"`) je surový řetězec, který bude zakódován do čárového kódu. Změnou této hodnoty můžete **vytvořit čárový kód ze řetězce** pro jakýkoli poštovní kód nebo sledovací číslo, které potřebujete.

## Jak generovat čárový kód s vlastními rozměry

Šířka modulu poštovního čárového kódu (X‑dimenze) často musí odpovídat tiskovým specifikacím. Aspose vám umožňuje nastavit šířku v pixelech a automaticky vypočítat výšku.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Proč byste to mohli upravit:**  
Větší X‑dimenze dělá pruhy silnější, což může zlepšit spolehlivost skenování na tiskárnách s nízkým rozlišením. Naopak menší hodnota snižuje velikost obrázku pro webové použití. Tento řádek ukazuje **jak generovat čárový kód** obrázky, které splňují přesné požadavky na velikost.

## Uložení obrázku čárového kódu

Po nastavení generátoru jednoduše zavoláte `save`. Metoda přijímá výstupní cestu a formát obrázku, který chcete.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Co získáte:**  
PNG soubor pojmenovaný `PostalPlanetAuto.png` obsahující Planet čárový kód, který kóduje `"123456"`. Soubor můžete otevřít v libovolném prohlížeči obrázků a ověřit výsledek.

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="Snímek obrazovky vygenerovaného poštovního čárového kódu uloženého jako PNG"}

## Kompletní příklad generátoru čárových kódů

Níže je kompletní, připravený ke spuštění skript, který zahrnuje všechny výše uvedené kroky. Zkopírujte jej do souboru nazvaného `generate_postal_barcode.py` a spusťte `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Očekávaný výstup

Spuštěním skriptu získáte:

```
Barcode saved to PostalPlanetAuto.png
```

…a vytvoří soubor `PostalPlanetAuto.png`, který vypadá takto:

![Generated Planet barcode](barcode_example.png){.align-center alt="Vygenerovaný Planet čárový kód uložený jako PNG"}

## Běžné varianty a okrajové případy

| Situace | Co změnit | Proč |
|-----------|----------------|-----|
| **Různá symbologie** (např. Code128) | Nahraďte `EncodeTypes.Planet` za `EncodeTypes.Code128` | Umožňuje **generovat čárový kód** pro inventární štítky, nejen pro poštovní kódy. |
| **Delší datové řetězce** | Zajistěte, aby vybraná symbologie podporovala délku; pro Planet musíte zachovat 6 číslic. | Zabraňuje runtime `ValueError`. |
| **Vyšší rozlišení** | Zvyšte `x_dimension.pixels` na 6 nebo 8. | Produkuje silnější pruhy pro tisk s vysokým DPI. |
| **Jiné formáty obrázků** | Použijte `BarCodeImageFormat.JPEG` nebo `BarCodeImageFormat.GIF`. | Užitečné, když PNG není vhodný pro váš pracovní postup. |
| **Běh ve webové službě** | Nahraďte volání `save` na souborovém systému `BytesIO` streamem a vraťte bajty. | Umožňuje generování čárových kódů za běhu ve Flask nebo Django. |

**Tip:** Vždy ověřte vstupní řetězec před voláním `BarcodeGenerator`. Neplatná data (špatná délka, nečíselné znaky pro Planet) vyvolají výjimku a přeruší vaši aplikaci.

## Jak generovat čárový kód v Flask endpointu (volitelný další krok)

Pokud chcete vystavit **příklad generátoru čárových kódů** jako REST API, můžete zabalit funkci `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Tento úryvek ukazuje, jak **generovat čárový kód** na vyžádání bez zápisu na disk, což je užitečné pro mikro‑služby.

## Závěr

Nyní víte, jak **vytvořit čárový kód ze řetězce** v Pythonu pomocí Aspose.Barcode, jak **generovat čárový kód** s vlastními rozměry a jak **uložit** výsledek jako PNG soubor. Kompletní **příklad generátoru čárových kódů** zahrnuje validaci vstupu, ošetření chyb a znovupoužitelnou funkci, kterou můžete integrovat do větších aplikací.

Dále prozkoumejte jiné symbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) nebo vložte generátor do webového frameworku jako Flask nebo Django. Oba kroky prohloubí vaše pochopení knihovny **aspose barcode python** a rozšíří způsoby, jak můžete **generovat poštovní čárové kódy** obrázky pro reálné projekty.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat čárový kód v Pythonu – kompletní krok‑za‑krokem průvodce](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Vytvořit čárový kód PNG v Pythonu – Kompletní průvodce Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Jak generovat čárový kód s ECI pomocí Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}