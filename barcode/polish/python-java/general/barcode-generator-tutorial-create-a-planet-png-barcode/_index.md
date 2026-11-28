---
category: general
date: 2026-11-27
description: Samouczek generatora kodów kreskowych, który pokazuje, jak generować
  PNG kodu kreskowego, zmieniać rozmiar kodu oraz tworzyć kod Planet w Pythonie, krok
  po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- how to generate barcode
- change barcode size
- create barcode png
- create planet barcode
language: pl
lastmod: 2026-11-27
og_description: Poradnik generatora kodów kreskowych prowadzi Cię krok po kroku, jak
  wygenerować kod kreskowy w formacie PNG, zmienić jego rozmiar oraz stworzyć kod
  Planet przy użyciu Pythona.
og_image_alt: Screenshot of a Planet barcode PNG generated in a barcode generator
  tutorial
og_title: Samouczek generatora kodów kreskowych – utwórz kod kreskowy Planet PNG
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Barcode generator tutorial that shows how to generate barcode PNG,
    change barcode size, and create a Planet barcode in Python with step‑by‑step code.
  headline: Barcode generator tutorial – create a Planet PNG barcode
  type: TechArticle
tags:
- barcode
- Python
- image-generation
title: Poradnik generatora kodów kreskowych – stwórz kod kreskowy Planet PNG
url: /pl/python-java/general/barcode-generator-tutorial-create-a-planet-png-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Samouczek generatora kodów kreskowych – tworzenie kodu Planet w formacie PNG

Jeśli szukasz **samouczka generatora kodów kreskowych**, ten przewodnik pokaże Ci dokładnie, jak wygenerować kod Planet (POSTNET), zmienić rozmiar kodu kreskowego i zapisać go jako obraz PNG przy użyciu Pythona. Niezależnie od tego, czy potrzebujesz kodów kreskowych do etykiet pocztowych, czy do śledzenia zapasów, otrzymasz kompletny, gotowy do uruchomienia przykład w kilku prostych krokach.

Ten samouczek obejmuje wszystko – od instalacji wymaganej biblioteki po dostosowanie wymiaru X i wysokości kreski. Po jego zakończeniu zrozumiesz **jak generować obrazy kodów kreskowych** programowo i będziesz gotów dostosować kod do innych symbologii lub formatów wyjściowych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy zainstalowany.
* Dostęp do Internetu w celu zainstalowania pakietu `aspose-barcode` (biblioteka używana w tym samouczku).
* Katalog, do którego można zapisywać pliki, w którym zostanie zapisany wygenerowany PNG.

> **Pro tip:** Użyj wirtualnego środowiska (`python -m venv venv`), aby izolować zależności.

## Krok 1: Zainstaluj bibliotekę Aspose.BarCode dla Pythona

Najłatwiejszy sposób pracy z kodami kreskowymi w Pythonie to oficjalny pakiet **Aspose.BarCode**, który natywnie obsługuje symbologię Planet.

```bash
pip install aspose-barcode
```

Pakiet zawiera klasy `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`, które będą potrzebne później.

## Krok 2: Zaimportuj wymagane klasy i skonfiguruj generator

Utwórz nowy plik Pythona (np. `planet_barcode.py`) i zaimportuj niezbędne symbole.

```python
# planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data to encode – Planet (POSTNET) expects a numeric string.
postal_code = "123456"
```

Stała `EncodeTypes.Planet` informuje generator, aby użył symbologii **Planet**, idealnej dla amerykańskich usług pocztowych.

## Krok 3: Utwórz generator kodu kreskowego (how to generate barcode)

Zainicjuj generator z żądanymi danymi. To jest serce procesu **how to generate barcode**.

```python
# Initialize the generator with Planet symbology and the data string.
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)
```

W tym momencie `barcode_generator` zawiera domyślny obraz kodu (zwykle szerokość modułu 2 px i wysokość kreski 50 px). Aby obraz był odpowiedni do druku lub użycia cyfrowego, będziesz chciał **zmienić rozmiar kodu kreskowego**.

## Krok 4: Zmiana rozmiaru kodu kreskowego – dostosowanie wymiaru X i wysokości kreski

### 4.1 Dostosowanie wymiaru X (szerokość modułu)

Wymiar X kontroluje szerokość każdej pojedynczej kreski (modułu). Ustawienie go na 4 piksele daje bardziej szczegółowy, wyższej rozdzielczości kod.

```python
# Set the X dimension (module width) to 4 pixels.
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

### 4.2 Ustawienie wysokości kreski

Wysokość kreski określa ogólny pionowy rozmiar kodu. Wysokość 100 pikseli sprawdza się w większości urządzeń skanujących.

```python
# Set the bar height to 100 pixels.
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

Obie właściwości są częścią hierarchii `parameters.barcode`, która grupuje wszystkie ustawienia wizualne kodu kreskowego.

## Krok 5: Zapisz kod kreskowy jako obraz PNG (create barcode png)

Po skonfigurowaniu rozmiaru, wyeksportuj obraz. Metoda `save` przyjmuje ścieżkę pliku oraz enum formatu obrazu.

```python
# Define the output path – adjust the directory as needed.
output_path = "output/PostalPlanetBarHeight100Pixels.png"

# Save the barcode as a PNG file.
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

Uruchomienie skryptu wygeneruje plik o nazwie `PostalPlanetBarHeight100Pixels.png` w folderze `output`. Obraz zawiera czysty kod Planet gotowy do druku lub osadzenia w plikach PDF.

## Krok 6: Zweryfikuj wygenerowany kod kreskowy (create planet barcode)

Otwórz PNG w dowolnym przeglądarce obrazów, aby potwierdzić, że kod wygląda prawidłowo. Możesz także zeskanować go aplikacją mobilną do skanowania kodów; powinna zwrócić pierwotne dane (`123456`).

Jeśli kod nie zostanie zeskanowany:

* Upewnij się, że wymiar X nie jest ustawiony zbyt nisko (poniżej 2 px może powodować problemy z czytelnością).
* Sprawdź, czy wysokość kreski wynosi co najmniej 50 px, aby zapewnić niezawodne skanowanie.
* Zweryfikuj, czy ciąg danych spełnia wymagania Planet (tylko cyfry, odpowiednia długość).

## Pełny skrypt – wszystko razem

Poniżej znajduje się kompletny, samodzielny skrypt, który możesz skopiować i od razu uruchomić.

```python
# planet_barcode.py
"""
Barcode generator tutorial: create a Planet PNG barcode.
This script demonstrates how to generate a barcode, change barcode size,
and save the result as a PNG image using Aspose.BarCode for Python.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def main():
    # 1️⃣ Define the data to encode.
    postal_code = "123456"

    # 2️⃣ Create the generator for Planet symbology.
    barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)

    # 3️⃣ Change barcode size.
    #    - X dimension (module width) = 4 pixels for higher resolution.
    #    - Bar height = 100 pixels for a larger visual footprint.
    barcode_generator.parameters.barcode.x_dimension.pixels = 4
    barcode_generator.parameters.barcode.bar_height.pixels = 100

    # 4️⃣ Prepare the output directory.
    output_dir = "output"
    os.makedirs(output_dir, exist_ok=True)
    output_path = os.path.join(output_dir, "PostalPlanetBarHeight100Pixels.png")

    # 5️⃣ Save the barcode as PNG.
    barcode_generator.save(output_path, BarCodeImageFormat.Png)

    print(f"✅ Barcode generated and saved to: {output_path}")

if __name__ == "__main__":
    main()
```

Uruchomienie `python planet_barcode.py` wygeneruje PNG pokazany poniżej.

![PNG kodu kreskowego Planet wygenerowany w samouczku generatora kodów kreskowych](https://example.com/planet_barcode.png "PNG kodu kreskowego Planet wygenerowany w samouczku generatora kodów kreskowych")

*Tekst alternatywny obrazu:* **PNG kodu kreskowego Planet wygenerowany w samouczku generatora kodów kreskowych** (zgodny z wymaganą długością tekstu alt).

## Typowe wariacje i przypadki brzegowe

| Sytuacja | Co dostosować | Dlaczego ma znaczenie |
|-----------|----------------|------------------------|
| **Różna długość danych** | Upewnij się, że ciąg danych spełnia wymaganą liczbę cyfr dla Planet (5, 9 lub 11 cyfr). | Nieprawidłowe długości powodują `ArgumentException`. |
| **Wyższa rozdzielczość DPI** | Ustaw `barcode_generator.parameters.image_resolution.dpi = 300`. | Poprawia jakość druku na drukarkach o wysokiej rozdzielczości. |
| **Inne formaty obrazu** | Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`. | Wybierz format pasujący do dalszego przetwarzania. |
| **Wiele kodów kreskowych w jednym obrazie** | Użyj `barcode_generator.save_multiple([...])` (dostępne w nowszych wersjach). | Przydatne przy generowaniu etykiet wsadowych. |

## Lista kontrolna rozwiązywania problemów

* **Kod nie pojawia się** – Sprawdź, czy katalog wyjściowy istnieje i masz uprawnienia do zapisu.
* **Skaner nie odczytuje kodu** – Zwiększ wymiar X lub wysokość kreski; nie ustawiaj ich poniżej minimalnych progów czytelności.
* **ImportError** – Upewnij się, że pakiet `aspose-barcode` został zainstalowany w tym samym środowisku Pythona, w którym uruchamiasz skrypt.

## Zakończenie

Ten **samouczek generatora kodów kreskowych** przeprowadził Cię przez cały proces tworzenia kodu Planet w formacie PNG, od instalacji biblioteki po **zmianę rozmiaru kodu kreskowego** i zapis obrazu. Masz teraz solidne podstawy do **generowania kodów kreskowych** programowo i możesz rozszerzyć kod o inne symbologie, formaty lub operacje wsadowe.

**Kolejne kroki**

* Poznaj inne symbologie, takie jak `EncodeTypes.Code128` lub `EncodeTypes.QR` (odnosi się do drugiego słowa kluczowego *create barcode png* dla różnych typów).
* Zintegruj wygenerowany PNG z PDF‑ami przy użyciu `reportlab` lub `PyPDF2`.
* Zautomatyzuj generowanie wsadowe dla listy kodów pocztowych (nawiązuje do *create planet barcode* w skali).

Miłego kodowania i niech Twoje kody kreskowe zawsze skanują się za pierwszym razem!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak utworzyć kod Planet PNG w Pythonie](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Kompletny samouczek generatora kodów kreskowych dla tworzenia kodu Planet w Pythonie](/barcode/english/python-java/general/complete-barcode-generator-tutorial-for-creating-a-planet-ba/)
- [Jak zapisać PNG z przykładu generatora kodów kreskowych w Pythonie](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}