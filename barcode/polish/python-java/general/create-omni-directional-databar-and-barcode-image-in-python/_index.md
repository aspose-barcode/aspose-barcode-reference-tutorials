---
category: general
date: 2026-08-12
description: Utwórz wielokierunkowy DataBar w Pythonie i dowiedz się, jak tworzyć
  obrazy kodów kreskowych w Pythonie przy użyciu Aspose.BarCode. Postępuj zgodnie
  z przewodnikiem krok po kroku, aby uzyskać pełne rozwiązanie.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: pl
lastmod: 2026-08-12
og_description: Utwórz omnidirectional databar w Pythonie i w kilka minut wygeneruj
  obraz kodu kreskowego w Pythonie. Ten samouczek przedstawia kompletny, działający
  przykład.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Stwórz wszechkierunkowy pasek danych – pełny przewodnik Pythona
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
title: Utwórz wszechkierunkowy obraz databar i kodu kreskowego w Pythonie
url: /pl/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz omni directional databar i obraz kodu kreskowego w Pythonie

Jeśli potrzebujesz **create omni directional databar** w projekcie Python, ten przewodnik pokaże Ci, jak to zrobić oraz jak **create barcode image python** przy użyciu biblioteki Aspose.BarCode. Otrzymasz gotowy‑do‑uruchomienia skrypt, który generuje dwa pliki PNG o różnych proporcjach.

Generowanie DataBar zgodnego ze specyfikacją Omni‑directional jest powszechnym wymogiem w aplikacjach detalicznych i logistycznych. Poradnik obejmuje instalację, konfigurację wymiaru X, dostosowanie proporcji oraz zapisywanie końcowych obrazów. Nie są wymagane żadne zewnętrzne usługi; wszystko działa lokalnie.

## Czego będziesz potrzebować

* Python 3.8 lub nowszy zainstalowany na Twoim komputerze.
* Dostęp do terminala lub wiersza poleceń.
* Uprawnienia do zapisu w folderze, w którym będą zapisywane obrazy kodów kreskowych.

Jedyną zależnością zewnętrzną jest **Aspose.BarCode for Python via .NET**, który obsługuje typ Omni‑directional DataBar od razu po zainstalowaniu.

## Krok 1: Zainstaluj Aspose.BarCode dla Pythona

Aspose.BarCode udostępnia klasę `BarcodeGenerator` używaną w przykładowym kodzie. Zainstaluj pakiet przy pomocy `pip`:

```bash
pip install aspose-barcode
```

Pakiet zawiera niezbędne powiązania środowiska .NET, więc nie musisz instalować .NET SDK osobno.

## Krok 2: Zaimportuj bibliotekę i utwórz generator

Pierwsza linia skryptu tworzy generator dla stosowanego Omni‑directional DataBar. Wartość GTIN‑14 `(01)12345678901231` jest używana jako przykładowe dane.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Dlaczego ten krok ma znaczenie*: Stała `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` informuje bibliotekę, aby zakodowała wartość jako Omni‑directional DataBar, co jest formatem wymaganym przez wiele skanerów punktu sprzedaży.

## Krok 3: Ustaw wymiar X (szerokość modułu)

Wymiar X określa szerokość najmniejszego modułu kreski. Wartość `2` piksele generuje wyraźny, czytelny kod kreskowy bez nadmiernego rozmiaru pliku.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Dlaczego ten krok ma znaczenie*: Dostosowanie wymiaru X pozwala zrównoważyć czytelność i wymiary obrazu. Zbyt mały wymiar X może źle wyglądać na drukarkach o niskiej rozdzielczości.

## Krok 4: Skonfiguruj proporcje i zapisz pierwszy obraz

Proporcje wpływają na ogólną wysokość DataBar w stosunku do jego szerokości. Proporcja `15` tworzy kompaktowy styl wizualny.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Wskazówka**: Użyj `pathlib.Path` do budowania ścieżki wyjściowej, co automatycznie tworzy brakujące katalogi.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Krok 5: Zmień proporcje dla drugiego stylu wizualnego i zapisz kolejny obraz

Zmiana proporcji na `30` powoduje wyższy kod kreskowy, który może być wymagany przez określony sprzęt skanujący.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Dlaczego ten krok ma znaczenie*: Różni detaliści i urządzenia skanujące mają odrębne ograniczenia rozmiarowe. Udostępnienie obu proporcji w jednym skrypcie pozwala wygenerować dokładny styl, którego potrzebujesz, bez duplikowania kodu.

## Pełny skrypt – create omni directional databar i barcode image python

Poniżej znajduje się kompletny, uruchamialny przykład, który zawiera wszystkie poprzednie kroki. Zapisz go jako `generate_databar.py` i uruchom przy pomocy `python generate_databar.py`.

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

### Oczekiwany wynik

Uruchomienie skryptu tworzy następujące pliki:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Oba obrazy przedstawiają prawidłowy Omni‑directional DataBar, który może być zeskanowany przez standardowy sprzęt detaliczny.

![example of create omni directional databar barcode image in Python](example_databar.png "create omni directional databar barcode image python")

*Powyższy obraz jest symbolem, który ilustruje dwa zapisane pliki PNG.*

## Rozwiązywanie typowych problemów

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode nie jest zainstalowany lub został zainstalowany w innym środowisku. | Aktywuj właściwe środowisko wirtualne i uruchom `pip install aspose-barcode`. |
| `PermissionError` przy zapisywaniu | Skrypt nie ma uprawnień do zapisu w docelowym folderze. | Wybierz katalog, do którego masz dostęp, lub uruchom skrypt z odpowiednimi uprawnieniami. |
| Kod kreskowy nie jest odczytywany | Zbyt mały wymiar X lub niekompatybilne proporcje z skanerem. | Zwiększ `x_dimension.pixels` do 3 lub 4 i przetestuj różne wartości `aspect_ratio` (np. 20, 25). |
| Brak środowiska .NET | Aspose.BarCode zależy od środowiska .NET na Windows/Linux. | Zainstaluj najnowsze środowisko .NET ze strony Microsoft; dokumentacja pakietu zawiera wskazówki specyficzne dla platformy. |

## Rozszerzanie przykładu

Możesz dostosować skrypt do generowania innych wariantów DataBar (np. `DATABAR_STACKED`, `DATABAR_EXPANDED`). Zastąp odpowiednio stałą `EncodeTypes`:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Jeśli potrzebujesz osadzić kod kreskowy w PDF, Aspose.PDF for Python może bezpośrednio zaimportować plik PNG lub możesz użyć metody `save` z `BarCodeImageFormat.Pdf`.

## Zakończenie

Ten poradnik pokazał, jak **create omni directional databar** oraz jak **create barcode image python** przy użyciu Aspose.BarCode. Masz teraz kompletny, powtarzalny skrypt, który generuje dwa pliki PNG o różnych proporcjach, radzi sobie z typowymi problemami i może być rozszerzony o inne formaty kodów kreskowych.

Następnie, eksploruj generowanie kodów QR, dodawanie kodu kreskowego do faktur PDF lub automatyzację przetwarzania wsadowego dużych katalogów produktów. Każdy z tych tematów opiera się na tym samym wzorcu `BarcodeGenerator` przedstawionym tutaj. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe poradniki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj obraz kodu kreskowego – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Utwórz obraz kodu DotCode – wiersze i kolumny (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Jak utworzyć obraz kodu kreskowego i renderować go w Javie](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}