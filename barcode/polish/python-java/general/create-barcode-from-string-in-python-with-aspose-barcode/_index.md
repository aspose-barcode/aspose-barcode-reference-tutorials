---
category: general
date: 2026-10-15
description: Utwórz kod kreskowy z ciągu znaków w Pythonie przy użyciu Aspose.BarCode,
  dowiedz się, jak wygenerować kod kreskowy Code 128 i zapisać go jako PNG w kilku
  linijkach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: pl
lastmod: 2026-10-15
og_description: Utwórz kod kreskowy z ciągu znaków w Pythonie, aby zakodować dane
  w kodzie Code 128 i zapisać go jako plik PNG przy użyciu Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Utwórz kod kreskowy z ciągu znaków w Pythonie – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Utwórz kod kreskowy z ciągu znaków w Pythonie przy użyciu Aspose.BarCode
url: /pl/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy z ciągu znaków w Pythonie przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć kod kreskowy z ciągu znaków** w Pythonie, ten przewodnik pokaże Ci dokładne kroki z użyciem Aspose.BarCode. Dowiesz się, jak **wygenerować kod kreskowy Code 128**, dostosować jego wygląd oraz **zapisać kod kreskowy w formacie PNG** na dysku. Rozwiązanie działa na każdej platformie obsługującej Python 3.9+ i wymaga tylko kilku linii kodu.

Programowe generowanie kodów kreskowych eliminuje błędy ręcznego wprowadzania i usprawnia przepływy pracy, takie jak śledzenie zapasów, biletowanie czy drukowanie etykiet. Po zakończeniu tego samouczka będziesz w stanie **zakodować dane w kodzie kreskowym**, dostosować wymiary i przechowywać obraz w dowolnym miejscu.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- Zainstalowany Python 3.9 lub nowszy  
- Dostęp do Internetu w celu pobrania pakietu Aspose.BarCode  
- Uprawnienia do zapisu w katalogu, w którym zapiszesz plik PNG  

Jeśli używasz wirtualnego środowiska (gorąco zalecane), aktywuj je teraz.

## Zainstaluj pakiet Aspose.BarCode dla Pythona

Aspose udostępnia czystą bibliotekę Pythona, która obsługuje wszystkie popularne symbologie kodów kreskowych, w tym Code 128. Zainstaluj ją przy pomocy pip:

```bash
pip install aspose-barcode
```

*Wskazówka:* Zablokuj wersję (np. `aspose-barcode==23.9`), aby uniknąć nieoczekiwanych zmian w produkcji.

## Utwórz kod kreskowy z ciągu znaków w Pythonie

Pierwszym funkcjonalnym krokiem jest zaimportowanie wymaganych klas i utworzenie generatora dla wybranej symbologii. Ten przykład używa **Code 128**, który jest idealny dla danych alfanumerycznych.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Dlaczego to ważne:** `EncodeTypes.CODE_128` informuje bibliotekę, którego standardu kodu kreskowego użyć, a drugi argument (`"1234567890"`) to **ciąg znaków, który chcesz zakodować w kodzie kreskowym**. Możesz go zamienić na dowolny ciąg ASCII o długości do 80 znaków dla Code 128.

## Wygeneruj kod kreskowy Code 128

Gdy generator jest gotowy, możesz wyprodukować obraz kodu kreskowego w pamięci. Biblioteka automatycznie renderuje kod na podstawie podanych danych.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

W tym momencie `barcode_image` jest instancją `System.Drawing.Image` (na Windows) lub kompatybilnym obiektem obrazu na innych platformach. Możesz go wyświetlić bezpośrednio w interfejsie GUI, osadzić w PDF-ie lub kontynuować dalsze dostosowywanie.

## Dostosuj wygląd kodu kreskowego

Drobne dostrojenie właściwości wizualnych zapewnia niezawodne skanowanie kodu w Twoim konkretnym środowisku. Typowe korekty obejmują wymiar X (szerokość najcieńszego paska) oraz ogólną wysokość paska.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Dlaczego warto zmieniać te wartości?*  
- **Wymiar X** wpływa na gęstość kodu; mniejsza wartość daje bardziej zwarty kod, który mieści się na małych etykietach.  
- **Wysokość paska** wpływa na czytelność; wyższe paski są łatwiejsze do wykrycia przez skanery z większej odległości.

Możesz także zmienić kolory, dodać marginesy lub osadzić tekst czytelny dla człowieka za pomocą obiektu `parameters`. Zapoznaj się z dokumentacją Aspose.BarCode, aby poznać pełną listę opcji.

## Jak zapisać kod kreskowy jako PNG

Zapis wygenerowanego obrazu to ostatni krok w **tworzeniu kodu kreskowego z ciągu znaków**. Biblioteka obsługuje kilka formatów; PNG jest bezstratny i szeroko wspierany.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

Metoda `save` zapisuje obraz w systemie plików w podanym formacie. Jeśli docelowy katalog (`output/` w tym przykładzie) nie istnieje, Python zgłosi `FileNotFoundError`. Utwórz katalog wcześniej lub obsłuż wyjątek:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Oczekiwany rezultat:** Po uruchomieniu skryptu, `output/barcode.png` zawiera wyraźny kod kreskowy Code 128, który koduje `"1234567890"`. Otworzenie pliku w dowolnym przeglądarce obrazów pokaże czarno‑biały kod gotowy do skanowania.

## Pełny, gotowy do uruchomienia przykład

Łącząc wszystkie elementy, oto samodzielny skrypt, który możesz skopiować, wkleić i uruchomić:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Uruchom skrypt poleceniem `python create_barcode.py`. Jeśli wszystko zostało poprawnie zainstalowane, zobaczysz:

```
Barcode saved to output/barcode.png
```

Otwórz plik PNG i zweryfikuj, że kod kreskowy odpowiada oryginalnemu ciągowi, używając dowolnej aplikacji skanującej kody kreskowe.

## Częste pytania i przypadki brzegowe

- **Co zrobić, jeśli potrzebuję innej symbologii?**  
  Zamień `EncodeTypes.CODE_128` na inną wartość wyliczeniową, taką jak `EncodeTypes.QR`, `EncodeTypes.EAN_13` lub `EncodeTypes.PDF_417`. Reszta kodu pozostaje bez zmian.

- **Czy mogę wygenerować kod kreskowy z znaków nie‑ASCII?**  
  Code 128 obsługuje pełny zestaw 128 znaków ASCII. Dla danych Unicode rozważ użycie QR Code (`EncodeTypes.QR`), który natywnie obsługuje UTF‑8.

- **Jak zmienić format obrazu?**  
  Przekaż inną stałą z `BarCodeImageFormat` do `save`, np. `BarCodeImageFormat.JPEG` lub `BarCodeImageFormat.BMP`.

- **Co zrobić, gdy katalog wyjściowy jest tylko do odczytu?**  
  Owiń wywołanie `save` w blok try/except i obsłuż `PermissionError`, np. pytając użytkownika o alternatywną ścieżkę.

- **Wskazówka dotycząca wydajności:**  
  Generowanie tysięcy kodów w pętli może obciążać CPU. Ponownie używaj jednej instancji `BarcodeGenerator` i aktualizuj jedynie `generator.parameters.barcode.code_text` między iteracjami.

## Zakończenie

Teraz wiesz, jak **utworzyć kod kreskowy z ciągu znaków** w Pythonie przy użyciu Aspose.BarCode, **wygenerować kod kreskowy Code 128**, dostosować jego rozmiar oraz **zapisać kod kreskowy w formacie PNG** na dysku. To kompleksowe rozwiązanie pozwala **zakodować dane w kodzie kreskowym** szybko i niezawodnie, ułatwiając integrację kodów w systemach inwentaryzacji, platformach biletowych czy dowolnych aplikacjach wymagających identyfikatorów odczytywanych maszynowo.

**Kolejne kroki**

- Eksploruj inne symbologie (alternatywy dla `generate code 128 barcode`) takie jak QR lub DataMatrix.  
- Dodaj logikę obsługi błędów, aby skrypt był odporny w środowisku produkcyjnym (`how to save barcode` failures).  
- Osadź wygenerowany PNG w PDF‑ach lub raportach HTML (`generate barcode png` for web).  

Miłego kodowania i ciesz się prostotą programowego generowania kodów kreskowych!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}