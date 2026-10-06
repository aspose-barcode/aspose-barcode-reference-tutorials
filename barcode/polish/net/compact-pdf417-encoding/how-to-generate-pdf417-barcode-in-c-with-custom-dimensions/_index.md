---
category: general
date: 2026-09-07
description: Wygeneruj kod kreskowy PDF417 w C# i dowiedz się, jak ustawić wymiary
  kodu kreskowego, aby uzyskać precyzyjną kontrolę. Postępuj zgodnie z tym przewodnikiem
  krok po kroku, aby utworzyć obraz PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: pl
lastmod: 2026-09-07
og_description: Generuj kod kreskowy PDF417 w C# i dowiedz się, jak ustawić wymiary
  kodu. Ten tutorial przedstawia kompletny, działający przykład.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Generowanie kodu kreskowego PDF417 w C# – pełny przewodnik z wymiarami
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Jak wygenerować kod kreskowy PDF417 w C# z niestandardowymi wymiarami
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# z niestandardowymi wymiarami

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, gotowy do uruchomienia przykład, który tworzy obraz PNG, jednocześnie pozwalając kontrolować wymiary kodu kreskowego.

Generowanie kodu kreskowego PDF417 jest częstym wymogiem w systemach inwentaryzacji, kartach pokładowych i dokumentach zabezpieczonych. W tym tutorialu dowiesz się także **jak ustawić wymiary kodu kreskowego**, aby wynik pasował do Twoich potrzeb projektowych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- .NET 6.0 SDK lub nowszy zainstalowany  
- Visual Studio 2022 (lub dowolne IDE kompatybilne z C#)  
- Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolna kompatybilna biblioteka obsługująca PDF417)  

Pakiet możesz dodać za pomocą następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz generator kodu PDF417

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z typem `EncodeTypes.Pdf417` oraz tekstem, który chcesz zakodować. Obiekt generatora przechowuje wszystkie ustawienia kodu kreskowego.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Dlaczego to ważne:** Enum `EncodeTypes.Pdf417` informuje bibliotekę, że ma użyć symbologii PDF417, która obsługuje duże ładunki danych i korekcję błędów. Łańcuch tekstowy może zawierać znaki Unicode, więc możesz kodować międzynarodowe symbole bez dodatkowej pracy.

## Krok 2: Jak ustawić wymiary kodu kreskowego

Kontrolowanie rozmiaru każdego modułu (najmniejszego czarno‑białego kwadratu) określa ogólną rozdzielczość obrazu. Właściwość `XDimension.Pixels` ustawia szerokość jednego modułu w pikselach.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to ważne:** Większa wartość `XDimension` daje obraz o wyższej rozdzielczości, co jest przydatne przy drukowaniu lub skanowaniu z większej odległości. Odwrotnie, mniejsza wartość zmniejsza rozmiar pliku przy użyciu w sieci.

## Krok 3: Zdefiniuj układ PDF417 (kolumny i wiersze)

PDF417 pozwala wpływać na kształt macierzy, określając liczbę kolumn i wierszy. Może to wpływać na czytelność oraz fizyczny rozmiar kodu kreskowego.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Dlaczego to ważne:** Dostosowanie kolumn i wierszy pozwala dopasować kod kreskowy do określonej przestrzeni lub spełnić wymagania proporcji skanera. Biblioteka automatycznie dodaje wypełnienie, jeśli dane nie wypełniają macierzy w pełni.

## Krok 4: Zapisz kod kreskowy jako obraz PNG

Na koniec zapisz wygenerowany kod kreskowy do pliku. PNG zachowuje jakość bezstratną, co czyni go idealnym do dalszego przetwarzania.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Po uruchomieniu programu, w folderze wyjściowym projektu pojawi się plik `Pdf417Layout.png`. Obraz wygląda następująco:

![Wygenerowany obraz kodu PDF417 z niestandardowymi wymiarami](og_image_placeholder.png)

*Tekst alternatywny obrazu: Wygenerowany obraz kodu PDF417 z niestandardowymi wymiarami*  

**Dlaczego to ważne:** Zapis w formacie PNG zapewnia, że dokładne wymiary modułów, które ustawiłeś, zostaną zachowane, co jest kluczowe dla dalszych aplikacji skanujących.

## Pełny przykład w jednym bloku

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić bez modyfikacji (poza ewentualną zmianą ścieżki wyjściowej).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Oczekiwany wynik

- **Plik:** `Pdf417Layout.png` (PNG, bezstratny)  
- **Wymiary:** Determinowane przez `XDimension` (2 px) × macierz (kolumny × wiersze)  
- **Zawartość:** Skanowalny kod PDF417 kodujący ciąg Unicode `Åspóse.Barcóde©`

## Częste pytania i przypadki brzegowe

### Co zrobić, gdy potrzebny jest większy obraz do druku?

Zwiększ `XDimension.Pixels` do 4 lub 5. Większe wartości generują kod kreskowy o wyższej rozdzielczości, ale także zwiększają rozmiar pliku.

### Czy mogę zakodować więcej danych niż w przykładzie?

Tak. PDF417 może pomieścić do 1 850 znaków. Wystarczy zamienić argument tekstowy w konstruktorze `BarcodeGenerator`. Jeśli dane przekroczą pojemność macierzy, biblioteka automatycznie doda dodatkowe wiersze.

### Jak działa korekcja błędów?

PDF417 zawiera wbudowaną korekcję błędów. Jej poziom możesz dostosować za pomocą:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Wyższe poziomy zwiększają odporność, kosztem większych kodów kreskowych.

### Co zrobić, gdy kod kreskowy jest rozmyty na ekranie?

Upewnij się, że DPI wyjściowego obrazu odpowiada środowisku wyświetlania. DPI możesz ustawić przy zapisie:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Porady profesjonalne

- **Porada:** Zawsze testuj wygenerowany kod kreskowy na rzeczywistym skanerze, którego zamierzasz używać. Różne urządzenia mają różną tolerancję na rozmiar modułu i strefy ciszy.  
- **Uwaga:** Bardzo małe wartości `XDimension` (< 1 px) mogą renderować się jako niewidoczne linie na ekranach o wysokiej rozdzielczości DPI.  
- **Wskazówka dla aplikacji webowych:** Serwuj PNG z nagłówkiem `Cache-Control: public, max-age=86400`, aby zmniejszyć obciążenie związane z wielokrotnym generowaniem.

## Podsumowanie

Teraz wiesz, jak **wygenerować kod kreskowy PDF417** w C# oraz precyzyjnie **ustawić wymiary kodu kreskowego**, aby spełnić dowolne wymagania. Kompletny, gotowy do uruchomienia przykład demonstruje tworzenie obrazu PNG z niestandardowym układem kolumn/wierszy i rozmiarem modułu, gotowego do druku lub dystrybucji cyfrowej.

### Kolejne kroki

- Zbadaj **jak generować kod kreskowy PDF417** w różnych formatach obrazu (JPEG, BMP).  
- Naucz się **dynamicznie ustawiać wymiary kodu kreskowego** w oparciu o dane wejściowe użytkownika lub DPI urządzenia.  
- Zintegruj generowanie kodu kreskowego z API ASP.NET Core, aby udostępniać kody na żądanie.

Śmiało eksperymentuj z innymi ustawieniami PDF417, takimi jak korekcja błędów, marginesy i kolory. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak ustawić poziom błędu w kodzie PDF417 – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Jak zapisać kod kreskowy w C# – Generowanie kodów PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generowanie kodu PDF417 w C# – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}