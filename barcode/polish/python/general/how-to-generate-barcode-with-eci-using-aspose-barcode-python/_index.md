---
category: general
date: 2026-08-19
description: Jak generować kod kreskowy z ECI przy użyciu Aspose.Barcode dla Pythona.
  Dowiedz się, jak dodać dane ECI, połączyć zwykły tekst i zapisać obraz w jednym
  przejrzystym przewodniku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: pl
lastmod: 2026-08-19
og_description: Jak generować kod kreskowy z ECI przy użyciu Aspose.Barcode dla Pythona.
  Skorzystaj z tego samouczka, aby dowiedzieć się, jak dodać dane ECI, dostosować
  wygląd i zapisać wynik.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Jak wygenerować kod kreskowy z ECI przy użyciu Aspose.Barcode w Pythonie
  – krok po kroku
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
title: Jak wygenerować kod kreskowy z ECI przy użyciu Aspose.Barcode w Pythonie
url: /pl/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy z ECI przy użyciu Aspose.Barcode w Pythonie

Jeśli potrzebujesz wiedzieć **jak generować kod kreskowy**, który zawiera zarówno zwykłe znaki, jak i dane zakodowane przy użyciu ECI, ten przewodnik pokazuje cały proces. Zobaczysz dokładnie **jak dodać eci** sekcje, dostosujesz rozmiar i zapiszesz obraz na dysku przy użyciu jednego, uruchamialnego skryptu.

Tutorial obejmuje:

* Pobieranie wersji biblioteki Aspose.Barcode (opcjonalne, ale przydatne przy debugowaniu).  
* Budowanie rozszerzonego ciągu kodowego, który miesza zwykłe i zakodowane w ECI znaki.  
* Tworzenie generatora kodu kreskowego dla symbologii obsługującej rozszerzony ciąg kodowy.  
* Dostosowywanie wymiarów kodu kreskowego i zapisywanie finalnego pliku PNG.

Nie wymaga żadnej zewnętrznej dokumentacji; skopiuj kod, uruchom go i otrzymasz obraz kodu kreskowego, który zawiera chińskie znaki zakodowane przy użyciu ECI 26 (UTF‑8).

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy zainstalowany.  
* Pakiet `aspose-barcode` zainstalowany (`pip install aspose-barcode`).  
* Uprawnienia do zapisu w folderze, w którym zamierzasz zapisać plik PNG.

Jeśli używasz środowiska wirtualnego, najpierw je aktywuj, aby utrzymać zależności w izolacji.

## Krok 1: Zweryfikuj wersję Aspose.Barcode (opcjonalnie)

Znajomość dokładnej wersji biblioteki pomaga, gdy musisz zgłaszać błędy lub porównywać funkcje między wydaniami.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Dlaczego to jest ważne*: Wyświetlona wersja potwierdza, że środowisko uruchomieniowe odpowiada dokumentacji, której używasz. Różne wersje mogą obsługiwać różne wartości ECI, więc jest to szybka kontrola poprawności.

## Krok 2: Zbuduj rozszerzony ciąg kodowy z częściami zwykłymi i zakodowanymi w ECI

Aspose.Barcode udostępnia `ExtCodetextBuilder` do łączenia zwykłych danych i segmentów zakodowanych w ECI. W tym przykładzie mieszamy ciąg liczbowy z chińskimi znakami.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Wyjaśnienie*:  
* `add_plain_codetext` wstawia dane, które symbologia kodu kreskowego traktuje jako zwykłe znaki.  
* `add_eci_codetext` instruuje generator, aby przed dostarczonym tekstem dodał wskaźnik ECI (tutaj **26**, który mapuje na UTF‑8). To jest dokładnie **jak dodać eci** dane do kodu kreskowego.

Możesz wywołać `add_eci_codetext` wielokrotnie, aby osadzić kilka różnych bloków językowych. Builder automatycznie obsługuje wymagane sekwencje ucieczki.

## Krok 3: Wybierz symbologię obsługującą rozszerzony ciąg kodowy

Nie każdy typ kodu kreskowego może przechowywać segmenty ECI. Code 128, QR i Data Matrix są popularnymi wyborami. Przykład używa Code 128, ponieważ jest szeroko wspierany i dobrze radzi sobie z mieszanymi danymi alfanumerycznymi.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Dlaczego Code 128?*: Akceptuje pełny zakres ASCII oraz sekwencje ucieczki ECI generowane przez builder, co czyni go idealnym dla scenariusza „jak generować kod kreskowy”, w którym mieszane są zwykłe i zakodowane znaki.

## Krok 4: Dostosuj wygląd kodu kreskowego

Możesz kontrolować rozmiar, wysokość, marginesy i wiele innych aspektów wizualnych za pomocą obiektu `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Wskazówka*: Jeśli planujesz drukować kod kreskowy, zwiększ `x_dimension` i `bar_height` proporcjonalnie, aby zachować czytelność przy docelowej rozdzielczości DPI.

## Krok 5: Zapisz obraz kodu kreskowego

Na koniec zapisz wygenerowany obraz do pliku. Aspose.Barcode obsługuje PNG, JPEG, BMP i wiele innych formatów.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Upewnij się, że folder `output` istnieje lub utwórz go poleceniem `os.makedirs("output", exist_ok=True)` przed wywołaniem `save`.

### Oczekiwany rezultat

Po otwarciu pliku `extended_codetext.png` powinieneś zobaczyć kod kreskowy Code 128, który koduje ciąg liczbowy `1234567890` oraz chińskie znaki „特殊字符”. Zeskanowanie kodu nowoczesnym skanerem respektującym ECI zwróci oryginalny mieszany ciąg.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Kod kreskowy wygenerowany w przykładzie jak generować kod kreskowy"}

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli potrzebuję innego zestawu znaków?

Wybierz odpowiednią wartość ECI z tabeli ISO/IEC 18004. Na przykład ECI 27 reprezentuje ISO‑8859‑1 (Latin‑1). Zastąp numeryczny identyfikator w `add_eci_codetext` odpowiednio.

### Czy mogę osadzić więcej niż jeden blok ECI?

Tak. Wywołaj `add_eci_codetext` wielokrotnie. Builder wstawia niezbędne kody przełączania ECI między blokami, zachowując kolejność, w jakiej je dodajesz.

### Czy generator obsługuje kody QR z ECI?

Oczywiście. Zastąp `barcode.Symbology.CODE_128` przez `barcode.Symbology.QR` i dostosuj wszelkie parametry specyficzne dla QR (np. poziom korekcji błędów) za pomocą `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Jak radzić sobie z bardzo długimi ciągami danych?

Dla kodów liniowych, takich jak Code 128, maksymalna długość wynosi około 80 znaków przy użyciu rozszerzonego ciągu kodowego. Jeśli przekroczysz tę granicę, rozważ przejście na symbologię dwuwymiarową, taką jak QR lub Data Matrix, które mogą przechowywać tysiące znaków.

## Pełny, uruchamialny skrypt

Poniżej znajduje się kompletny program, który możesz skopiować‑wkleić do pliku o nazwie `generate_extended_barcode.py` i uruchomić bezpośrednio.

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


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować obraz kodu kreskowego z dostosowaniem dodatkowej przestrzeni przy użyciu Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Jak wygenerować obraz kodu kreskowego w Javie przy użyciu Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Jak wygenerować kod DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}