---
category: general
date: 2026-08-22
description: Naucz się generować kod DataMatrix w Pythonie i kodować rosyjski tekst
  przy użyciu Aspose.BarCode – przewodnik krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: pl
lastmod: 2026-08-22
og_description: Generuj kod DataMatrix w Pythonie i koduj rosyjski tekst przy użyciu
  Aspose.BarCode. Postępuj zgodnie z pełnym przykładem i uruchom go od razu.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Generowanie kodu DataMatrix w Pythonie – kompletny samouczek Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Jak wygenerować kod DataMatrix w Pythonie przy użyciu Aspose.BarCode
url: /pl/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod DataMatrix w Pythonie przy użyciu Aspose.BarCode

Jeśli potrzebujesz **generować kod DataMatrix** w Pythonie przy **kodowaniu rosyjskiego tekstu**, ten przewodnik pokaże Ci dokładne kroki. Zobaczysz kompletny, gotowy do uruchomienia przykład, który tworzy rozszerzony kod tekstowy, konfiguruje kod kreskowy i zapisuje obraz w jednym skrypcie.

Tworzenie kodów kreskowych zawierających znaki nie‑ASCII często rodzi pytania o zestawy znaków i kodowanie danych. Korzystając z `ExtCodetextBuilder` Aspose.BarCode, możesz bezpiecznie osadzić tekst UTF‑8, taki jak znaki cyrylicy, wewnątrz symbolu DataMatrix. Wynik działa z każdym skanerem obsługującym standard DataMatrix.

W tym tutorialu:

* Zainstalujesz wymagany pakiet Aspose.BarCode.
* Zbudujesz rozszerzony kod tekstowy, który miesza zwykłe dane i rosyjski tekst.
* **Wygenerujesz kod DataMatrix** przy użyciu rozszerzonego ciągu.
* Dostosujesz parametry kodu, takie jak rozmiar modułu.
* Zapiszesz kod jako plik PNG.

Żadne zewnętrzne usługi nie są wymagane; wszystko działa lokalnie na Twoim komputerze.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy zainstalowany.
* Aktywną licencję Aspose.BarCode for Python (bezpłatna wersja próbna wystarczy do rozwoju).
* Podstawową znajomość skryptów w Pythonie.

Możesz zainstalować bibliotekę Aspose.BarCode za pomocą pip:

```bash
pip install aspose-barcode
```

## Krok 1: Zbuduj rozszerzony ciąg kodu tekstowego

Pierwszym zadaniem jest stworzenie jednego ciągu, który zawiera zarówno zwykły identyfikator produktu, jak i rosyjską frazę. `ExtCodetextBuilder` pozwala łączyć różne części kodu tekstowego, zachowując informacje o ich kodowaniu.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Dlaczego ten krok jest ważny** – symbole DataMatrix przechowują surowe bajty. Gdy musisz mieszać różne alfabety, musisz poinformować enkoder, jaki zestaw znaków obowiązuje w każdym segmencie. Metoda `add_eci_codetext` wstawia wskaźnik ECI przed rosyjskim tekstem, zapewniając, że skanery interpretują bajty jako UTF‑8. Bez ECI znaki cyrylicy pojawiłyby się jako zniekształcone dane.

## Krok 2: Utwórz generator kodu DataMatrix

Po przygotowaniu rozszerzonego kodu tekstowego, utwórz instancję `BarcodeGenerator`, określając typ `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Dlaczego DataMatrix?** – DataMatrix to dwuwymiarowy kod kreskowy, który może przechowywać do 2 335 znaków alfanumerycznych lub 1 556 bajtów. Jest idealny dla małych przedmiotów, części przemysłowych i sytuacji, w których trzeba osadzić tekst wielojęzyczny.

## Krok 3: (Opcjonalnie) Skonfiguruj parametry kodu kreskowego

Aspose.BarCode udostępnia wiele parametrów. Dla większości zastosowań domyślne ustawienia generują czytelny symbol. Jednak możesz chcieć kontrolować rozmiar każdego modułu (najmniejszego kwadratu w macierzy), aby dopasować go do wymagań druku.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Inne przydatne parametry to poziom korekcji błędów, margines i kolor tła. Dostosowuj je tylko wtedy, gdy środowisko skanowania wymaga konkretnych tolerancji.

## Krok 4: Zapisz obraz kodu kreskowego

Na koniec zapisz kod do pliku. Metoda `save` obsługuje PNG, JPEG, BMP oraz kilka formatów wektorowych.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Gdy otworzysz `extended_codetext.png`, zobaczysz wyraźny symbol DataMatrix. Skanowanie go standardowym czytnikiem DataMatrix zwróci dwie części:

1. **ABC123** – zwykły identyfikator.
2. **Привет** – rosyjskie powitanie, poprawnie odkodowane jako UTF‑8.

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się kompletny skrypt, który możesz skopiować i wkleić do pliku o nazwie `generate_datamatrix.py`. Zamień `YOUR_DIRECTORY` na istniejący folder w swoim systemie.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Uruchom skrypt z wiersza poleceń:

```bash
python generate_datamatrix.py
```

Powinieneś zobaczyć wyjście konsoli podobne do:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Weryfikacja wyniku

Aby potwierdzić, że kod prawidłowo koduje rosyjską frazę:

1. Otwórz plik PNG w przeglądarce obrazów.
2. Użyj dowolnej aplikacji do skanowania DataMatrix (wiele aplikacji mobilnych to obsługuje) lub skanera sprzętowego.
3. Zdekodowany ciąg powinien wyświetlać `ABC123Привет` (lub dwie części oddzielone, w zależności od interfejsu skanera).

Jeśli rosyjskie znaki pojawią się jako bełkot, sprawdź ponownie, czy skaner obsługuje ECI UTF‑8. Większość nowoczesnych czytników tak robi, ale starsze urządzenia mogą wymagać dodatkowej konfiguracji.

## Typowe pułapki i jak ich unikać

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Zniekształcony wynik cyrylicy | Brak wskaźnika ECI | Użyj `add_eci_codetext` z `eci_encoding=3`. |
| Kod kreskowy za mały dla drukarki | Domyślny rozmiar modułu jest zbyt mały przy niskim DPI | Zwiększ `x_dimension` (np. `3.0` lub `4.0`). |
| Plik nie został zapisany | Nieprawidłowa ścieżka katalogu | Upewnij się, że `YOUR_DIRECTORY` istnieje i jest zapisywalny. |
| Skaner nie może odczytać | Zbyt duża gęstość danych | Zredukuj ilość kodowanych danych lub zwiększ poziom korekcji błędów (`generator.parameters.barcode.error_correction_level`). |

## Rozszerzanie przykładu

Możesz dostosować ten wzorzec do innych języków lub typów danych:

* **Koduj tekst japoński lub arabski** – zmień `eci_encoding` na odpowiednią wartość (np. 5 dla ISO‑8859‑5, 6 dla ISO‑8859‑7).  
* **Dodaj wiele segmentów ECI** – wywołaj `add_eci_codetext` wielokrotnie, każdy z własnym kodowaniem.  
* **Utwórz zamiast tego kod QR** – zamień `EncodeTypes.DATA_MATRIX` na `EncodeTypes.QR`.  

Wszystkie pozostałe kroki pozostają identyczne, ponieważ `ExtCodetextBuilder` abstrahuje niskopoziomowe operacje na bajtach.

## Zakończenie

Teraz wiesz, jak **generować kod DataMatrix** w Pythonie i **kodować rosyjski tekst** przy użyciu funkcji rozszerzonego kodu tekstowego Aspose.BarCode. Kompletny skrypt obsługuje negocjację zestawu znaków, tworzenie kodu i zapis obrazu w kilku linijkach kodu.

Następnie eksploruj inne symbologie kodów kreskowych (PDF417, Aztec) lub zintegrować generator z usługą internetową, która na żądanie zwraca obrazy PNG. Te same zasady – budowanie rozszerzonego kodu tekstowego i wybór odpowiedniego `EncodeTypes` – mają zastosowanie w całym zestawie Aspose.BarCode.

Miłego kodowania i ciesz się mocą wielojęzycznego generowania kodów kreskowych!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – Przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generowanie kodu DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}