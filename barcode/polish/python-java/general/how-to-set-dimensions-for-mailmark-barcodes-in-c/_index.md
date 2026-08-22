---
category: general
date: 2026-08-22
description: Dowiedz się, jak ustawiać wymiary kodów kreskowych Mailmark w C# i zapisywać
  je jako obrazy PNG. Zawiera pełny kod, wyjaśnienia i wskazówki.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: pl
lastmod: 2026-08-22
og_description: Jak ustawić wymiary kodów kreskowych Mailmark w C# i wyeksportować
  je jako pliki PNG. Śledź kompletny przykład i unikaj typowych pułapek.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Jak ustawić wymiary kodów kreskowych Mailmark w C# – przewodnik krok po
  kroku
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Jak ustawić wymiary kodów kreskowych Mailmark w C#
url: /pl/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić wymiary kodów kreskowych Mailmark w C#

Jeśli potrzebujesz **ustawić wymiary** kodu kreskowego Mailmark w C#, ten przewodnik pokazuje dokładne kroki. Zobaczysz, jak skonfigurować wymiar X‑i wysokość pasków, a następnie zapisać kod jako obraz PNG bez dodatkowych narzędzi.

Generowanie kodów pocztowych to rutynowe zadanie przy tworzeniu oprogramowania do etykiet, ale domyślny rozmiar często nie pasuje do drukarki lub wymagań układu. Po zakończeniu tego samouczka będziesz mógł precyzyjnie kontrolować rozmiar kodu i wygenerować dwa prawidłowe typy Mailmark (C‑type i L‑type) gotowe do druku.

**Czego się nauczysz**

* Jak ustawić wymiar X‑dimension (szerokość modułu) i wysokość pasków dla `BarcodeGenerator`.
* Jak zapisać wygenerowany kod jako plik PNG przy użyciu `BarCodeImageFormat`.
* Typowe pułapki, takie jak nieprawidłowe ścieżki folderów lub nieobsługiwane wartości wymiarów.
* Wskazówki dotyczące ponownego użycia tej samej konfiguracji w wielu kodach.

## Wymagania wstępne

* .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+).
* Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolna kompatybilna biblioteka udostępniająca `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`).
* Podstawowa znajomość składni C# oraz operacji I/O na plikach.

> **Pro tip:** Zainstaluj pakiet poleceniem CLI  
> `dotnet add package Aspose.BarCode`, aby utrzymać projekt w porządku.

## Krok 1: Zdefiniuj folder wyjściowy

Zanim utworzysz jakikolwiek kod, musisz zdecydować, gdzie będą zapisywane pliki PNG. Użycie ścieżki bezwzględnej zapobiega niespodziankom na różnych maszynach.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Dlaczego to ważne*: Jeśli folder nie istnieje, `Save` zgłasza `IOException`. Wywołanie `Directory.CreateDirectory` jest idempotentne – nie robi nic, jeśli folder już istnieje.

## Krok 2: Utwórz kod Mailmark C‑type i **ustaw wymiary**

Mailmark C‑type koduje 20‑znakowy ciąg alfanumeryczny. Po zainicjowaniu generatora możesz **ustawić wymiary** poprzez obiekt `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Dlaczego wybrać te wartości?

* **X‑dimension** kontroluje szerokość najmniejszego paska (tzw. „modułu”). Wartość `4` piksele daje kod, który jest łatwo odczytywalny przez większość drukarek laserowych, a jednocześnie utrzymuje umiarkowany rozmiar pliku.
* **BarHeight** określa pionowy rozmiar pasków. `50` pikseli to typowa wysokość dla standardowych etykiet pocztowych, ale możesz ją zwiększyć dla większych formatów.

> **Edge case:** Niektóre drukarki wymagają minimalnej wysokości paska wynoszącej 30 px. Ustawienie wysokości niższej niż możliwości drukarki może spowodować nieczytelne kody.

## Krok 3: Utwórz kod Mailmark L‑type i **ustaw wymiary**

L‑type używa dłuższego ciągu danych (do 30 znaków). Takie samo podejście do ustawiania wymiarów ma zastosowanie.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Ponowne użycie konfiguracji

Jeśli generujesz wiele kodów o identycznych wymiarach, rozważ wyodrębnienie konfiguracji do metody pomocniczej:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Wywołanie `ApplyStandardDimensions(mailmarkC)` i `ApplyStandardDimensions(mailmarkL)` zmniejsza duplikację i sprawia, że przyszłe zmiany (np. przejście na moduły 5‑pikselowe) wymagają jedynie jednego wiersza edycji.

## Krok 4: Zweryfikuj wygenerowane pliki PNG

Po uruchomieniu programu otwórz oba pliki PNG w dowolnym przeglądarce obrazów. Powinny się wyświetlić dwa odrębne kody Mailmark, każdy o szerokości 4 px na moduł i wysokości 50 px.

*Oczekiwany wynik*

| Nazwa pliku                     | Przybliżone wymiary (px) |
|---------------------------------|--------------------------|
| `PostalMailmarkCType.png`       | 4 px × moduł × N modułów |
| `PostalMailmarkLType.png`       | 4 px × moduł × N modułów |

Dokładna szerokość zależy od długości zakodowanych danych, ale wysokość będzie zawsze **50 px**, ponieważ ustawiliśmy `BarHeight.Pixels`.

## Typowe problemy i jak ich unikać

| Problem                              | Objaw                                            | Rozwiązanie |
|--------------------------------------|--------------------------------------------------|-------------|
| Nieprawidłowa ścieżka folderu        | `IOException: Could not find a part of the path`| Użyj `Path.Combine` z `Environment.SpecialFolder` lub zweryfikuj ciąg ścieżki. |
| X‑dimension ustawiony na 0 lub ujemny| Kod kreskowy wygląda jak jednolita bloka         | Upewnij się, że `XDimension.Pixels` jest dodatnią liczbą całkowitą (minimum 1). |
| Nieobsługiwany `EncodeTypes.Mailmark`| `ArgumentException` przy tworzeniu generatora    | Sprawdź, czy masz najnowszą wersję biblioteki Aspose.BarCode, która zawiera obsługę Mailmark. |
| Zapis w niewłaściwym formacie obrazu | Uszkodzony plik PNG                               | Użyj `BarCodeImageFormat.Png` (lub `Jpeg`, jeśli potrzebny jest inny format). |

## Rozszerzenie przykładu

* **Różne rozmiary** – Zmień `XDimension.Pixels` na 3, aby uzyskać bardziej kompaktowy kod, lub zwiększ `BarHeight.Pixels` do 70 dla większych etykiet.
* **Generowanie wsadowe** – Przejdź pętlą po kolekcji ciągów danych, stosując te same ustawienia wymiarów w każdej iteracji.
* **Inne formaty obrazu** – Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp`, jeśli Twój przepływ pracy tego wymaga.

## Podsumowanie

Teraz wiesz **jak ustawić wymiary** kodów kreskowych Mailmark w C# i eksportować je jako pliki PNG. Konfigurując `XDimension.Pixels` i `BarHeight.Pixels`, kontrolujesz wizualny rozmiar zarówno kodów C‑type, jak i L‑type, zapewniając zgodność z wymaganiami drukarek i ograniczeniami układu.  

Od tego momentu możesz eksperymentować z różnymi wartościami wymiarów, integrować kod z większym systemem etykietowym lub generować partie kodów dla masowej wysyłki.

---

*Kolejne kroki*: zapoznaj się z **wymiarami BarcodeGenerator** dla kodów QR lub przeczytaj dokumentację Aspose.BarCode dotyczącą **ustawiania DPI** dla wydruków wysokiej rozdzielczości. Jeśli potrzebujesz osadzić kod w PDF, połącz to podejście z biblioteką **Aspose.PDF**, aby uzyskać kompletną, końcowo‑do‑końca rozwiązanie.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia, pomagające opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak ustawić obramowanie dla kodu ITF-14 – dostosowanie](/barcode/english/net/itf-14-barcode-customization/)
- [Jak skonfigurować kody Patch Code przy użyciu Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode for .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}