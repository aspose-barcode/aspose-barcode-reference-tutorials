---
category: general
date: 2026-09-23
description: Dowiedz się, jak generować kod kreskowy Code 128 i zapisywać jego obraz
  przy użyciu Aspose.BarCode w Pythonie – przewodnik krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: pl
lastmod: 2026-09-23
og_description: Wygeneruj kod kreskowy Code 128 i zapisz jego obraz przy użyciu Aspose.BarCode
  w Pythonie. Skorzystaj z tego pełnego przykładu, aby utworzyć, dostosować i wyeksportować
  kod kreskowy jako plik PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Wygeneruj kod kreskowy Code 128 i zapisz jego obraz – przewodnik Pythona
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Jak wygenerować kod kreskowy Code 128 i zapisać obraz kodu kreskowego przy
  użyciu Aspose.BarCode
url: /pl/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy Code 128 i zapisać obraz kodu kreskowego przy użyciu Aspose.BarCode

Jeśli potrzebujesz **wygenerować kod kreskowy Code 128** i **zapisać obraz kodu kreskowego** w projekcie Python, ten samouczek pokazuje dokładne kroki. Korzystając z `ExtCodetextBuilder` Aspose.BarCode możesz osadzić zwykły tekst i segmenty Unicode w jednym ładunku, a następnie wyrenderować wynik jako plik PNG.

Zobaczysz kompletny, gotowy do uruchomienia skrypt, wyjaśnienie każdej linii oraz wskazówki dotyczące typowych problemów, takich jak obsługa kodowania ECI czy wybór właściwego folderu wyjściowego. Nie potrzebujesz dodatkowej dokumentacji — po prostu skopiuj, wklej i uruchom.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8+ zainstalowany.
* Pakiet `aspose.barcode` (zainstaluj poleceniem `pip install aspose-barcode`).
* Uprawnienia do zapisu w katalogu, w którym zostanie zapisany plik PNG.

Kod działa z dowolną symbologią obsługiwaną przez Aspose.BarCode, ale przykład koncentruje się na **Code 128**, ponieważ efektywnie koduje dane alfanumeryczne i obsługuje rozszerzone zestawy znaków.

## Krok 1: Import wymaganych klas

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Dlaczego ten krok?* Importowanie klas daje dostęp do buildera dla rozszerzonego kodu, writera tworzącego obraz oraz pomocnika wersji, który może być przydatny przy debugowaniu aktualizacji biblioteki.

## Krok 2: Zbuduj rozszerzony kod tekstowy

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` pozwala mieszać zwykły ASCII i dane Unicode w jednym ładunku kodu kreskowego. Bajt ECI (Extended Channel Interpretation) `0x03` informuje skaner, że kolejne bajty są kodowane w UTF‑8, co jest niezbędne dla języków takich jak rosyjski, chiński czy arabski.

## Krok 3: Skonfiguruj writer kodu kreskowego dla Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Ustawienie `encode_type` na `CODE_128` instruuje writer, aby wygenerował **kod kreskowy Code 128**. Właściwość `code_text` otrzymuje rozszerzony ciąg zbudowany w poprzednim kroku.

## Krok 4: Zapisz obraz kodu kreskowego jako PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Metoda `save` zapisuje kod kreskowy do pliku. Użycie `BarCodeImageFormat.PNG` zapewnia bezstratną kompresję i szeroką kompatybilność z aplikacjami webowymi i mobilnymi.

## Krok 5 (opcjonalnie): Zweryfikuj wersję biblioteki Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Znajomość dokładnej wersji biblioteki pomaga przy zgłaszaniu błędów lub porównywaniu zachowań między wydaniami.

## Oczekiwany wynik

Uruchomienie skryptu generuje wyjście w konsoli podobne do:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Wygenerowany PNG (`extended_codetext.png`) wygląda następująco:

![Kod kreskowy Code 128 wygenerowany w Pythonie i zapisany jako obraz PNG](images/code128_extended.png)

*Obraz przedstawia kod kreskowy Code 128, który koduje zarówno ciąg ASCII `ABC123`, jak i rosyjskie słowo „Пример”.*

## Często zadawane pytania i obsługa przypadków brzegowych

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę użyć innej symbologii?** | Tak. Zamień `BarCodeEncodeMode.CODE_128` na dowolny inny obsługiwany tryb, np. `QR`, `EAN_13` lub `PDF_417`. |
| **Co zrobić, jeśli mój tekst Unicode zawiera emotikony?** | Emotikony są również znakami UTF‑8, więc to samo wywołanie `add_eci_codetext` działa. Upewnij się, że docelowy skaner obsługuje używany ECI. |
| **Jak zmienić rozmiar obrazu?** | Ustaw `writer.x_dimension` i `writer.bar_height` przed wywołaniem `save`. |
| **Jakiego folderu użyć dla `output_path`?** | Dowolnego, do którego proces Pythona ma prawo zapisu. Użyj `os.makedirs` z `exist_ok=True`, aby utworzyć go automatycznie. |

## Porady profesjonalistów

* **Unikaj twardego kodowania ścieżek.** Używaj `os.path.join` oraz `Path` z modułu `pathlib` dla kompatybilności międzyplatformowej.
* **Waliduj kod kreskowy.** Po zapisaniu możesz odczytać obraz ponownie przy pomocy `barcode.BarCodeReader`, aby potwierdzić, że zakodowany tekst zgadza się z `extended_codetext`.
* **Wskazówka dotycząca wydajności.** Jeśli generujesz wiele kodów kreskowych w pętli, ponownie używaj jednej instancji `BarCodeWriter` i aktualizuj jedynie `code_text` w każdej iteracji.

## Zakończenie

Teraz wiesz, jak **wygenerować kod kreskowy Code 128** z mieszanymi danymi ASCII i Unicode oraz **zapisać obraz kodu kreskowego** jako PNG przy użyciu Aspose.BarCode w Pythonie. Pełny skrypt obejmuje budowanie rozszerzonego kodu tekstowego, konfigurację writera, eksport obrazu oraz sprawdzanie wersji biblioteki.

Od tego momentu możesz eksplorować:

* Dodawanie kolorów pierwszego/planu (`writer.back_color`, `writer.fore_color`).
* Osadzanie kodu kreskowego w PDF-ach przy użyciu `Aspose.PDF`.
* Korzystanie z klasy `BarCodeReader` do dekodowania zapisanego obrazu i automatycznej weryfikacji zawartości.

Miłego kodowania i zachęcamy do eksperymentowania z innymi symbologiami oraz formatami obrazu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}