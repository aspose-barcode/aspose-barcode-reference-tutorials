---
category: general
date: 2026-11-23
description: Jak generować obrazy kodów kreskowych w Pythonie przy użyciu Aspose.BarCode.
  Dowiedz się, jak stworzyć kod Planet, dostosować wymiar X i wyeksportować PNG z
  pustymi paskami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: pl
lastmod: 2026-11-23
og_description: Jak generować kod kreskowy w Pythonie przy użyciu Aspose.BarCode.
  Ten tutorial przeprowadzi Cię przez tworzenie kodu Planet z pustymi paskami i zapisanie
  go jako PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Jak generować kod kreskowy w Pythonie – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Jak generować obrazy kodów kreskowych w Pythonie przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować obrazy kodów kreskowych w Pythonie przy użyciu Aspose.BarCode

Generowanie obrazów kodów kreskowych w Pythonie jest proste dzięki bibliotece Aspose.BarCode. Ten przewodnik pokazuje krok po kroku, jak wygenerować kod kreskowy przy użyciu symboliki Planet, dostosować wymiar X oraz utworzyć plik PNG w stylu pustych pasków.

Zobaczysz kompletny, gotowy do uruchomienia skrypt, który możesz skopiować do swojego projektu. Samouczek obejmuje także typowe warianty — takie jak przełączenie na inną symbolikę lub format wyjściowy — abyś mógł dostosować rozwiązanie do własnych wymagań.

## Wymagania wstępne

* Python 3.8 lub nowszy zainstalowany.
* Dostęp do terminala lub wiersza poleceń.
* Aktywna licencja Aspose.BarCode dla Pythona (bezpłatna wersja ewaluacyjna działa do testów).
* Podstawowa znajomość zarządzania pakietami w Pythonie (`pip`).

## Krok 1: Zainstaluj pakiet Aspose.BarCode

Aspose udostępnia swoje API dla Pythona poprzez PyPI. Zainstaluj je przy użyciu standardowego menedżera pakietów:

```bash
pip install asposebarcode
```

> **Porada:** Użyj wirtualnego środowiska (`python -m venv venv`), aby utrzymać zależności odizolowane od innych projektów.

## Krok 2: Zaimportuj wymagane klasy Aspose.BarCode

Instrukcja importu wczytuje generator, wyliczenie symbolik oraz wyliczenie formatów obrazu.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` tworzy obiekt kodu kreskowego.
* `EncodeTypes` wylicza wszystkie obsługiwane symboliki — tutaj użyjemy `Planet`.
* `BarCodeImageFormat` określa typ pliku wyjściowego (PNG, JPEG, itp.).

## Krok 3: Utwórz generator kodu kreskowego dla symboliki Planet

Zainicjuj generator z wybraną symboliką i danymi, które chcesz zakodować.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Symbolika `Planet` generuje okrągły wzór, który jest idealny do celów dekoracyjnych lub brandingowych.

## Krok 4: Dostosuj wymiar X (szerokość modułu)

Wymiar X kontroluje szerokość najmniejszego paska (modułu). Ustawienie go na 4 piksele daje wyraźny, wysokiej rozdzielczości obraz.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Zmiana wymiaru X jest przydatna, gdy potrzebujesz kodu kreskowego, który dobrze skalowalny jest do druku lub wyświetlania na ekranie.

## Krok 5: Wyłącz wypełnione paski, aby uzyskać styl pustych pasków

Kod kreskowy w stylu pustych pasków pokazuje jedynie kontury pasków, co może być przydatne w aplikacjach o dużym nacisku na design.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Gdy `filled_bars` jest ustawione na `False`, generator rysuje puste kształty zamiast wypełnionych.

## Krok 6: Zapisz obraz kodu kreskowego jako plik PNG

Na koniec zapisz kod kreskowy na dysku. PNG jest bezstratny i szeroko wspierany.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

Metoda `save` automatycznie tworzy docelowy katalog, jeśli nie istnieje.

## Pełny przykład – kompletny, gotowy do uruchomienia skrypt

Połączenie wszystkich elementów daje Ci samodzielny program, który możesz uruchomić od razu:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Oczekiwany wynik:** Po uruchomieniu skryptu, `output/PlanetEmptyBars.png` zawiera obraz 200 × 200 pikseli kodu kreskowego Planet z pustymi paskami. Otwarcie pliku w dowolnej przeglądarce obrazów wyświetli okrągły wzór z zakodowaną wewnątrz wartością liczbową.

## Typowe warianty i przypadki brzegowe

### Przełączenie na inną symbolikę

Jeśli potrzebujesz kodu QR, Code 128 lub innego formatu, zamień `EncodeTypes.Planet` na odpowiednią wartość wyliczenia:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Zmiana formatu obrazu

Aspose.BarCode obsługuje PNG, JPEG, BMP i TIFF. Aby wygenerować JPEG zamiast tego:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Dostosowanie rozmiaru obrazu bez utraty jakości

Możesz kontrolować ogólne wymiary obrazu za pomocą właściwości `resolution` lub skalując jednocześnie wymiary X i Y. Dla wydruków wysokiej rozdzielczości ustaw wyższą wartość DPI:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Obsługa długich ciągów danych

Symbolika Planet ma ograniczoną pojemność danych (do 8 znaków). Jeśli spróbujesz zakodować dłuższy ciąg, generator zgłosi wyjątek. Zweryfikuj długość przed utworzeniem kodu kreskowego:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Wskazówki i pułapki

* **Aktywacja licencji:** W zastosowaniach produkcyjnych zastosuj plik licencji na początku skryptu przy użyciu `asposebarcode.License().set_license("Aspose.Total.lic")`. Pominięcie tego kroku spowoduje dodanie znaku wodnego do obrazu wyjściowego.
* **Bezpieczeństwo wątków:** Instancje `BarcodeGenerator` nie są bezpieczne wątkowo. Utwórz osobną instancję na każdy wątek, jeśli generujesz kody kreskowe równolegle.
* **Wydajność:** Ponowne użycie generatora dla wielu wartości (poprzez `barcode.value = "new data"`) jest szybsze niż tworzenie nowego obiektu przy każdej iteracji.
* **Ścieżki plików:** Używaj `os.path.join`, aby budować ścieżki niezależne od platformy, szczególnie przy wdrażaniu na Linuxie lub macOS.

## Zakończenie

Teraz wiesz, jak generować obrazy kodów kreskowych w Pythonie przy użyciu Aspose.BarCode, dostosowywać wymiar X, tworzyć styl pustych pasków i zapisywać wynik jako PNG. Pełny przykład można dostosować do innych symbolik, formatów wyjściowych i stylów wizualnych, co daje elastyczną bazę dla każdej funkcji związanej z kodami kreskowymi w Twoich aplikacjach.

**Kolejne kroki:** Zbadaj dodatkowe słowa kluczowe, takie jak *Python barcode generation*, próbując różnych kodowań, eksperymentuj z ustawieniami kompresji *barcode image PNG*, lub zintegrować wygenerowane obrazy z usługą webową przy użyciu Flask lub FastAPI. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i zbadać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak stworzyć kod kreskowy Planet PNG w Pythonie](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Jak stworzyć obraz kodu kreskowego w Pythonie przy użyciu Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [Jak wygenerować obraz kodu QR w Pythonie przy użyciu Aspose.Barcode – Pełny przewodnik](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}