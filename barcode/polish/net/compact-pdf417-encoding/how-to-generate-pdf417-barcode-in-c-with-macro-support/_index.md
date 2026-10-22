---
category: general
date: 2026-10-21
description: Dowiedz się, jak generować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Szczegółowe kroki obejmują ustawienia kodu PDF417, tworzenie makro‑kodu PDF417 oraz
  zapisywanie jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: pl
lastmod: 2026-10-21
og_description: Jak wygenerować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Postępuj zgodnie z tym samouczkiem krok po kroku, aby skonfigurować ustawienia kodu
  PDF417, utworzyć makro kod PDF417 i wyeksportować do formatu PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Jak wygenerować kod kreskowy PDF417 w C# – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy PDF417 w C# z obsługą makr
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# z obsługą makr

Jeśli potrzebujesz wygenerować kod kreskowy PDF417 w C#, ten przewodnik pokaże Ci kompletną, gotową do uruchomienia rozwiązanie. Niezależnie od tego, czy tworzysz system etykiet logistycznych, czy kodujesz duże bloki danych, zobaczysz, jak skonfigurować ustawienia kodu PDF417, stworzyć kod Macro PDF417 i zapisać wynik jako obraz PNG.

Generowanie kodu PDF417 nie wymaga manipulacji bitami na niskim poziomie. Korzystając z klasy **barcode generator C#** z Aspose.BarCode, możesz skupić się na logice biznesowej, a biblioteka zajmie się kodowaniem, korekcją błędów i renderowaniem obrazu.

## Czego będziesz potrzebować

Zanim rozpoczniesz, upewnij się, że masz:

- **.NET 6.0** lub nowszy (kod działa również z .NET Framework 4.6+)
- Pakiet NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Środowisko programistyczne, takie jak Visual Studio 2022 lub Visual Studio Code
- Uprawnienia do zapisu w folderze, w którym zostanie zapisany obraz PNG

Te wymagania wstępne zapewniają, że przykład skompiluje się i uruchomi bez dodatkowej konfiguracji.

## Jak wygenerować kod PDF417 – przegląd krok po kroku

Poniżej znajduje się zwięzła mapa procesu:

1. **Utwórz instancję `BarcodeGenerator`** używając `EncodeTypes.MacroPdf417`.
2. **Dostosuj podstawowy wygląd kodu** (rozmiar modułu, kolory itp.).
3. **Skonfiguruj ustawienia specyficzne dla PDF417**, w tym pola makr.
4. **Zapisz wygenerowany obraz kodu** przy użyciu `BarCodeImageFormat PNG`.

Każdy krok jest opisany szczegółowo, wraz z pełnymi fragmentami kodu, które możesz skopiować bezpośrednio do aplikacji konsolowej.

## Krok 1: Przygotowanie środowiska programistycznego

Utwórz nowy projekt konsolowy i dodaj odwołanie do Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Otwórz `Program.cs` i dodaj wymagane przestrzenie nazw:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te importy dają dostęp do `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`.

## Krok 2: Utwórz generator kodu Macro PDF417

Pierwsza linia implementacji tworzy obiekt **Macro PDF417 barcode**. Enum `EncodeTypes.MacroPdf417` informuje bibliotekę, że ma używać wariantu makro PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Dlaczego to ważne:** Użycie `EncodeTypes.MacroPdf417` włącza pola makro (`FileID`, `SegmentID` itp.), które pozwalają podzielić duży ładunek na wiele obrazów kodów, zachowując kolejność.

## Krok 3: Dostosuj podstawowy wygląd kodu

Zanim zmodyfikujesz parametry specyficzne dla PDF417, ustaw szerokość modułu (piksela). Wartość `2` zapewnia wyraźny, skanowalny obraz bez nadmiernego rozmiaru pliku.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Tutaj możesz także zmienić kolory pierwszego planu/tła, jeśli Twoje UI wymaga innej palety.

## Krok 4: Skonfiguruj ustawienia specyficzne dla PDF417

**Ustawienia kodu PDF417** są dostępne poprzez `generator.Parameters.Barcode.Pdf417`. Najważniejsze pola makro pokazano poniżej:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Zrozumienie poszczególnych właściwości

| Właściwość | Cel | Typowy zakres |
|------------|-----|---------------|
| `Columns` | Określa liczbę kolumn danych w każdym wierszu. Więcej kolumn zmniejsza liczbę wierszy, ale zwiększa szerokość. | 1 – 30 |
| `MacroPdf417FileID` | 32‑bitowy identyfikator grupujący wszystkie segmenty tego samego logicznego pliku. Musi być taki sam dla każdego segmentu. | Dowolna dodatnia liczba całkowita |
| `MacroPdf417SegmentID` | Indeks zerowy bieżącego segmentu. Zwiększaj przy każdym kolejnym kodzie. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów tworzących pełny plik. Wszystkie segmenty muszą zostać wygenerowane. | ≥ 1 |
| `MacroPdf417FileName` | Opcjonalna opisowa nazwa (maks. 255 znaków). Przydatna przy debugowaniu. | Ciąg alfanumeryczny |

> **Pro tip:** Utrzymuj `Columns` w przedziale od 3 do 7 dla większości drukarek etykiet. Wyższe wartości mogą przekroczyć szerokość drukowalną na urządzeniach o niskiej rozdzielczości.

## Krok 5: Zapisz kod jako obraz PNG

Na koniec zapisz kod na dysku przy użyciu `BarCodeImageFormat PNG`. PNG zachowuje jakość bezstratną, co jest kluczowe dla niezawodnego skanowania.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Po zakończeniu programu znajdziesz plik `MacroPdf417.png` w folderze projektu. Otwierając go, zobaczysz czysty kod Macro PDF417 gotowy do druku.

### Oczekiwany wynik

Wygenerowany obraz wygląda podobnie do przykładu poniżej (tylko ilustracja):

![Przykład kodu kreskowego Macro PDF417](macro-pdf417-barcode.png "Kod kreskowy Macro PDF417 wygenerowany kodem C#")

*Tekst alternatywny obrazu to „Kod kreskowy Macro PDF417 wygenerowany kodem C#”, spełniający wymagania dostępności i SEO.*

## Typowe problemy i rozwiązywanie ich

| Problem | Objaw | Rozwiązanie |
|---------|-------|-------------|
| **Nieprawidłowy `EncodeTypes`** | Kod wyświetla się jako QR lub zwykły tekst. | Upewnij się, że używasz `EncodeTypes.MacroPdf417` (nie `EncodeTypes.Pdf417`). |
| **Niezgodne identyfikatory segmentów** | Skaner zgłasza „brakujący segment”. | Inkrementuj `MacroPdf417SegmentID` kolejno i utrzymuj spójny `SegmentsCount` we wszystkich plikach. |
| **Zbyt duży rozmiar modułu** | Kod jest zbyt szeroki dla etykiety. | Zmniejsz `XDimension.Pixels` lub obniż `Columns`. |
| **Błędy ścieżki pliku** | `UnauthorizedAccessException` przy zapisie. | Zapisuj do folderu, do którego masz prawa, np. `Environment.CurrentDirectory`. |
| **Brak pakietu NuGet** | Błąd kompilacji: `BarcodeGenerator` nie znaleziony. | Uruchom `dotnet add package Aspose.BarCode` przed budowaniem. |

Rozwiązanie tych problemów na wczesnym etapie oszczędza czas przy integracji generowania kodów w większych przepływach pracy.

## Rozszerzanie przykładu

Teraz, gdy potrafisz wygenerować pojedynczy kod Macro PDF417, rozważ następujące kroki:

- **Generowanie wsadowe**: Pętla po kolekcji fragmentów danych, aktualizująca `MacroPdf417SegmentID` przy każdej iteracji.
- **Różne formaty obrazu**: Zamień `BarCodeImageFormat.Png` na `Jpeg` lub `Bmp`, jeśli Twój system downstream preferuje te formaty.
- **Osadzanie w PDF**: Użyj Aspose.PDF, aby umieścić PNG w raporcie PDF do dystrybucji.
- **Weryfikacja skanowania**: Przetestuj wygenerowane kody przy użyciu skanera sprzętowego lub aplikacji mobilnej obsługującej Macro PDF417.

Te warianty zachowują podstawowe **PDF417 barcode settings**, jednocześnie dostosowując wynik do potrzeb projektu.

## Podsumowanie

Teraz wiesz, **jak wygenerować kod PDF417 w C#** przy użyciu Aspose.BarCode – od stworzenia `BarcodeGenerator` z `EncodeTypes.MacroPdf417`, przez konfigurację pól makro, po zapis wyniku jako `BarCodeImageFormat PNG`. Pełny, działający kod demonstruje zalecaną metodę, wyjaśnia znaczenie poszczególnych ustawień i podkreśla typowe pułapki, które możesz napotkać.

Śmiało eksperymentuj z liczbą kolumn, kolorami czy formatami wyjściowymi i włącz generator do własnych aplikacji, aby uzyskać niezawodne kodowanie danych o wysokiej gęstości.


## Co powinieneś nauczyć się dalej?


Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, pomagające opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak generować kody PDF417 w C# z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Jak utworzyć kod Macro PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak zapisać kod kreskowy i wygenerować PDF417 z Aspose w C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}