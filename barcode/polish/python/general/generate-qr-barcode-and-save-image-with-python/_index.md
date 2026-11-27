---
category: general
date: 2026-11-27
description: Generuj kod QR w Pythonie przy użyciu Aspose.Barcode i dowiedz się, jak
  szybko zapisać obraz kodu kreskowego na dysku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: pl
lastmod: 2026-11-27
og_description: Generuj kod QR w Pythonie przy użyciu Aspose.Barcode i natychmiast
  zapisz obraz kodu kreskowego. Zapoznaj się z kompletnym przykładem, aby tworzyć,
  dostosowywać i przechowywać kody QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Wygeneruj kod QR i zapisz obraz w Pythonie – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Wygeneruj kod QR i zapisz obraz w Pythonie
url: /pl/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu QR i zapisywanie obrazu w Pythonie

Jeśli potrzebujesz **wygenerować kod QR** w aplikacji Python, ten przewodnik pokaże Ci, jak to zrobić przy użyciu biblioteki Aspose.Barcode. Dowiesz się także, jak prawidłowo **zapisać obraz kodu** w lokalnym folderze, jak uzyskać informacje o wersji biblioteki oraz jak obsługiwać rozszerzone segmenty tekstu.

Tworzenie kodów QR jest powszechnym wymogiem w systemach biletowych, płatnościach mobilnych i śledzeniu produktów. Po zakończeniu tego tutorialu będziesz mieć gotowy skrypt, który generuje plik obrazu kodu QR i wypisuje informacje o wersji w celach debugowania lub zgodności.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy.
* Pakiet `aspose-barcode`. Zainstaluj go poleceniem `pip install aspose-barcode`.
* Uprawnienia do zapisu w katalogu, w którym zostanie zapisany obraz kodu.

Nie są wymagane żadne dodatkowe usługi zewnętrzne; cały proces odbywa się lokalnie.

## Krok 1: Zbuduj rozszerzony tekst kodu przy pomocy `ExtCodetextBuilder`

Rozszerzony tekst kodu pozwala mieszać zwykły tekst i segmenty ECI (Extended Channel Interpretation) w jednym kodzie QR. Jest to przydatne, gdy trzeba osadzić znaki z różnych zestawów znaków, np. znak euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Dlaczego ten krok jest ważny:**  
`ExtCodetextBuilder` tworzy ostateczny ciąg znaków, który zostanie przetworzony przez enkoder QR. Bez zbudowania rozszerzonego tekstu kod zawierałby jedynie zwykłe znaki ASCII i nie mógłby przedstawić symboli specyficznych dla lokalizacji.

## Krok 2: Pobierz połączony rozszerzony ciąg tekstowy

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Wynik wygląda następująco:

```
Extended codetext: ABC123[ECI3]€123
```

Znacznik w nawiasach `[ECI3]` informuje enkoder QR, aby przełączył się na określony zestaw znaków dla kolejnych znaków.

## Krok 3: Wygeneruj kod QR przy użyciu rozszerzonego tekstu

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Wyjaśnienie:**  
`BarcodeGenerator` przyjmuje dwa argumenty: typ kodu (`QR`) oraz dane do zakodowania (`extended_codetext`). Generator przygotowuje wszystkie wewnętrzne struktury potrzebne do renderowania.

## Krok 4: Zapisz wygenerowany obraz kodu

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Dlaczego warto używać tego podejścia:**  
Wywołanie `save` bezpośrednio zapisuje obraz na dysku, wykorzystując format wywnioskowany z rozszerzenia pliku. Metoda obsługuje PNG, JPEG, BMP i TIFF, dając elastyczność w zależności od potrzeb downstream.

### Weryfikacja zapisanego obrazu

Otwórz plik `output/qr_extended.png` dowolną przeglądarką obrazów. Powinieneś zobaczyć kod QR, który po zeskanowaniu zwraca ciąg `ABC123€123`. Większość nowoczesnych skanerów QR obsługuje segment ECI automatycznie.

## Krok 5: Zapytaj o informacje o wersji Aspose.BarCode (opcjonalne, ale przydatne)

Znajomość dokładnej wersji biblioteki Aspose.BarCode pomaga przy zgłaszaniu błędów lub weryfikacji kompatybilności.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typowy wynik:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Pełny skrypt – skopiuj, wklej i uruchom

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Uruchomienie skryptu generuje obraz kodu QR oraz wypisuje zarówno rozszerzony tekst, jak i informacje o wersji w konsoli.

## Typowe wariacje i przypadki brzegowe

| Sytuacja | Zalecana modyfikacja |
|-----------|------------------------|
| **Inny zestaw znaków** | Zmien identyfikator ECI przekazywany do `add_eci_codetext`. Dla UTF‑8 użyj `5`. |
| **Wyższy poziom korekcji błędów** | Ustaw `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` przed wywołaniem `save`. |
| **Niestandardowy rozmiar obrazu** | Skorzystaj z `barcode.parameters.image_width` i `barcode.parameters.image_height`, aby kontrolować wymiary w pikselach. |
| **Wyjście nie‑PNG** | Zmień rozszerzenie pliku w `output_path` na `.jpg` lub `.bmp`. Biblioteka automatycznie wybierze odpowiedni enkoder. |

## Porady profesjonalistów

* **Utwórz folder wyjściowy** programowo, jeśli może nie istnieć:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Zweryfikuj kod QR** po wygenerowaniu, odczytując go przy pomocy `aspose.barcode.BarcodeReader`. Dzięki temu masz pewność, że zakodowane dane są zgodne z oczekiwaniami, szczególnie przy użyciu segmentów ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Wskazówka dotycząca wydajności** – używaj jednego egzemplarza `BarcodeGenerator` w pętli, jeśli musisz wygenerować wiele kodów QR. Resetuj właściwość `code_text` zamiast tworzyć nowy obiekt przy każdej iteracji.

## Zakończenie

Teraz wiesz, jak **wygenerować kod QR** w Pythonie przy użyciu Aspose.Barcode, jak zbudować rozszerzony tekst łączący zwykłe i ECI segmenty oraz jak prawidłowo **zapisać obraz kodu** na dysku. Skrypt pokazuje także, jak pobrać informacje o wersji biblioteki w celu rozwiązywania problemów.

Kolejne kroki, które możesz rozważyć:

* Dodanie logo lub niestandardowych kolorów do kodu QR.
* Osadzenie kodu QR bezpośrednio w plikach PDF przy użyciu Aspose.PDF.
* Automatyzacja generowania wsadowego dla dużych zbiorów danych.

Śmiało eksperymentuj z różnymi ładunkami danych, poziomami korekcji błędów i formatami obrazów. Powodzenia w kodowaniu!


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}