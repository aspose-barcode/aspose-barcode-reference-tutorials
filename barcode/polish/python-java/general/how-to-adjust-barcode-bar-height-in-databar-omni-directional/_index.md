---
category: general
date: 2026-11-27
description: Dowiedz się, jak dostosować wysokość pasków kodu kreskowego w generatorze
  kodów DataBar Omni‑Directional. Krok po kroku kod pokazuje ustawianie wysokości
  na 30 px i 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: pl
lastmod: 2026-11-27
og_description: Dostosuj wysokość pasków kodu kreskowego w generatorze kodów DataBar
  Omni‑Directional przy użyciu Pythona. Przejdź przez kompletny przewodnik, aby ustawić
  wysokości, wymiar X i zapisać obrazy PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Dostosuj wysokość pasków kodu kreskowego w generatorze DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Jak dostosować wysokość paska kodu kreskowego w generatorze DataBar Omni‑Directional
url: /pl/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dostosować wysokość pasków kodu kreskowego w generatorze DataBar Omni‑Directional

Jeśli potrzebujesz **dostosować wysokość pasków kodu kreskowego** dla kodu DataBar Omni‑Directional, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, działający przykład w Pythonie, który zmienia wysokość pasków z 30 px na 60 px, zachowując jednocześnie X‑dimension i format obrazu.

Zmiana wymiarów wizualnych kodu kreskowego jest częstym wymogiem, gdy kod musi pasować do określonego rozmiaru etykiety lub wytycznych projektowych. Oprócz wysokości pasków możesz także chcieć dostosować **X‑dimension** (rozmiar modułu) lub wybrać inny **format obrazu kodu kreskowego**, taki jak PNG lub JPEG.

W tym samouczku:

* Zainstalujesz wymaganą bibliotekę (GroupDocs.Barcode for Python)
* Utworzysz generator kodu DataBar Omni‑Directional
* Ustawisz rozmiar modułu za pomocą `XDimension`
* Dwukrotnie zmienisz właściwość wysokości pasków
* Zapiszesz powstałe obrazy w wybranym **BarCodeImageFormat**

Nie potrzebujesz wcześniejszego doświadczenia z API GroupDocs — wystarczy podstawowa znajomość Pythona.

## Prerequisites

Zanim zaczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy zainstalowany
* pakiet `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Uprawnienia zapisu do folderu, w którym zostaną zapisane pliki PNG

Jeśli nie znasz **DataBar Omni‑Directional barcode**, koduje on 14‑cyfrowy GTIN i jest szeroko stosowany w handlu detalicznym do skanowania z dowolnej orientacji.

## Krok 1: Konfiguracja generatora kodu DataBar Omni‑Directional

Najpierw zaimportuj niezbędne klasy i utwórz generator z danymi GTIN, które chcesz zakodować.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Dlaczego to ważne:* Stała `EncodeTypes.DatabarOmniDirectional` informuje bibliotekę, że ma wygenerować symbologię Omni‑Directional. Ciąg danych zawiera AI `(01)`, które oznacza wartość GTIN‑14.

## Krok 2: Zdefiniuj X‑dimension (rozmiar modułu)

X‑dimension kontroluje szerokość najcieńszego paska. Typowa wartość dla renderowania na ekranie to **2 px na moduł**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Użycie spójnego **set XDimension** zapewnia prawidłowe skalowanie kodu kreskowego na różnych drukarkach i skanerach.

## Krok 3: Dostosuj wysokość paska do 30 px i zapisz obraz

Teraz zmieniamy właściwość wysokości paska. Pierwsza wysokość, którą użyjemy, to **30 px**, co jest odpowiednie dla małych etykiet.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Stała `BarCodeImageFormat.Png` wybiera **format obrazu kodu kreskowego** PNG, który zachowuje jakość bezstratną.

### Oczekiwany rezultat

Plik `DatabarBarHeight30Pixels.png` zawiera kod DataBar Omni‑Directional, którego paski mają wysokość 30 px. Poniżej przykładowy podgląd:

![Kod kreskowy DataBar z wysokością pasków 30 px](images/databar_30px.png "Kod kreskowy DataBar z wysokością pasków 30 px")

> **Wskazówka:** Jeśli otworzysz plik PNG w edytorze graficznym, zobaczysz dokładną wysokość pasków. Najcieńsze paski mają szerokość 2 px, zgodnie z wcześniejszym ustawieniem.

## Krok 4: Zwiększ wysokość paska do 60 px dla wyższego kodu

Dla zastosowań wymagających większej powierzchni wizualnej — np. etykieta frachtowa — możesz zwiększyć wysokość paska do **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Zmienia się tylko właściwość `BarHeight`; X‑dimension i kodowanie pozostają bez zmian, więc kod nadal jest odczytywalny.

## Krok 5: Zapisz zaktualizowany obraz kodu

Na koniec zapisz wyższy kod do drugiego pliku PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Oczekiwany rezultat

Plik `DatabarBarHeight60Pixels.png` przedstawia te same dane, ale każdy pasek ma teraz wysokość 60 px. Różnicę wizualną ilustruje poniższy obraz:

![Kod kreskowy DataBar z wysokością pasków 60 px](images/databar_60px.png "Kod kreskowy DataBar z wysokością pasków 60 px")

## Pełny, działający przykład

Łącząc wszystkie elementy, otrzymujesz kompletny skrypt, który możesz skopiować‑wkleić do pliku o nazwie `adjust_barcode_height.py` i uruchomić od razu.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Uruchom skrypt:

```bash
python adjust_barcode_height.py
```

Powinieneś zobaczyć dwa pliki PNG w folderze `output`, każdy odzwierciedlający ustawioną wysokość paska.

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|-----------|
| **Czy mogę użyć JPEG zamiast PNG?** | Tak. Zastąp `BarCodeImageFormat.Png` przez `BarCodeImageFormat.Jpeg`. JPEG jest stratny, więc lepiej używać PNG dla precyzyjnego skanowania. |
| **Co jeśli potrzebuję wysokości paska, która nie jest wielokrotnością 10?** | Właściwość `BarHeight.Pixels` przyjmuje dowolną wartość całkowitą. Wystarczy przypisać żądaną liczbę pikseli (np. `45`). |
| **Czy zmiana wysokości paska wpływa na zakodowane dane?** | Nie. Zmienia się tylko reprezentacja wizualna; oryginalny ciąg danych pozostaje niezmieniony. |
| **Jak zmienić X‑dimension po zapisaniu pierwszego obrazu?** | Możesz zmodyfikować `gen.parameters.barcode.x_dimension.pixels` w dowolnym momencie przed wywołaniem `save()`. Zmiana zostanie zastosowana do kolejnych obrazów. |
| **Czy generator jest bezpieczny wątkowo?** | Instancja `BarcodeGenerator` nie jest gwarantowanie bezpieczna wątkowo. Utwórz osobną instancję dla każdego wątku, jeśli generujesz kody równocześnie. |

## Zakończenie

Teraz wiesz, jak **dostosować wysokość pasków kodu kreskowego** w generatorze DataBar Omni‑Directional przy użyciu Pythona. Samouczek obejmował tworzenie generatora, ustawianie **X‑dimension**, modyfikację właściwości **wysokości paska** oraz zapisywanie obrazów w wybranym **formacie obrazu kodu kreskowego**.

Od tego momentu możesz eksperymentować z innymi wysokościami, różnymi rozmiarami modułów lub przełączać się na alternatywne formaty obrazu, takie jak JPEG czy BMP. Warto także przyjrzeć się dodatkowym funkcjom **barcode generator python**, np. dodawaniu tekstu czytelnego dla człowieka lub zmianie schematów kolorów.

Miłego kodowania i niech Twoje kody będą zawsze ostre i idealnie dopasowane!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki dotyczą ściśle powiązanych tematów, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak ustawić szerokość i dostosować wysokość dla kodu GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Tworzenie omni directional databar i obrazu kodu kreskowego w Pythonie](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – zmiana wysokości kodu](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}