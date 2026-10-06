---
category: general
date: 2026-10-05
description: Dowiedz się, jak tworzyć kod kreskowy PDF417 w C# i generować PNG kodu
  kreskowego, korzystając z kodu krok po kroku oraz wskazówek najlepszych praktyk.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: pl
lastmod: 2026-10-05
og_description: Utwórz kod kreskowy PDF417 w C# i natychmiast wygeneruj PNG. Skorzystaj
  z tego pełnego samouczka, aby uzyskać rozwiązanie gotowe do produkcji.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Tworzenie kodu kreskowego PDF417 w C# – pełny przewodnik generowania PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Jak stworzyć kod kreskowy PDF417 i zapisać go jako PNG w C#
url: /pl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy PDF417 i zapisać go jako PNG w C#

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Otrzymasz gotowy fragment C#, który generuje wysokiej jakości **barcode PNG** plik, oraz zrozumiesz każde ustawienie wpływające na wynik.

Generowanie kodów kreskowych jest powszechnym wymogiem w systemach biletowych, śledzeniu zapasów i zabezpieczonym kodowaniu dokumentów. Po zakończeniu tego samouczka będziesz mógł odpowiedzieć na pytanie „**how to generate PDF417**” przy użyciu kompletnego, działającego przykładu.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Środowisko programistyczne, takie jak Visual Studio 2022 lub VS Code  
* Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolna kompatybilna biblioteka obsługująca PDF417)  

Możesz dodać pakiet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

Poniższy kod używa API Aspose, ponieważ zapewnia szczegółową kontrolę nad parametrami PDF417 i obsługuje eksport do PNG od razu.

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy i zaimportuj wymagane przestrzenie nazw:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Przestrzeń nazw `Aspose.BarCode.Generation` zawiera klasę `BarcodeGenerator`, która jest punktem wejścia do **tworzenia kodu kreskowego PDF417** obrazów.

## Krok 2: Utwórz kod kreskowy PDF417 z żądanym tekstem

Zainicjalizuj generator przy użyciu wyliczenia `EncodeTypes.Pdf417` oraz danych, które chcesz zakodować. Przykład używa łańcucha znaków zawierającego znaki specjalne, aby zademonstrować obsługę Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Generator teraz posiada obiekt kodu kreskowego, który możesz skonfigurować przed renderowaniem.

## Krok 3: Skonfiguruj parametry wizualne

Dostrajanie kodu kreskowego poprawia czytelność i zmniejsza rozmiar obrazu. Najczęściej modyfikowane ustawienia to **X‑dimension**, **columns** i **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** kontroluje szerokość każdego modułu; wartość `2` piksele daje kompaktowy, ale czytelny kod kreskowy.  
* **Columns** określają, ile kolumn danych używa kod. Mniej kolumn sprawia, że kod jest węższy, ale wyższy.  
* **Truncate** aktywuje tryb „compact” zdefiniowany w specyfikacji PDF417, który usuwa niepotrzebne wiersze wypełniające.  

Możesz eksperymentować z `Rows` i `ErrorCorrectionLevel`, jeśli Twój przypadek użycia wymaga większej odporności na uszkodzenia.

## Krok 4: Zapisz kod kreskowy jako obraz PNG

Na koniec wyeksportuj kod kreskowy do pliku PNG. PNG zachowuje ostre krawędzie i obsługuje przezroczystość, co czyni go idealnym w scenariuszach internetowych i drukowanych.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Uruchomienie programu tworzy `CompactPdf417.png` w określonym katalogu. Obraz wygląda następująco:

![Kompaktowy kod kreskowy PDF417 utworzony w C#](compact-pdf417.png "Przykład kompaktowego kodu kreskowego PDF417 utworzonego w C#")

*Powyższy tekst alternatywny zawiera główne słowo kluczowe, spełniając zarówno wymagania SEO, jak i dostępności.*

## Pełny, działający przykład

Łącząc wszystkie elementy, oto samodzielny program, który możesz skopiować, wkleić i uruchomić:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Oczekiwany wynik

Po otwarciu `CompactPdf417.png` powinieneś zobaczyć pionowy, wysokiej gęstości kod kreskowy, który koduje ciąg *Åspóse.Barcóde©*. Zeskanowanie obrazu dowolnym czytnikiem PDF417 zwróci oryginalny tekst.

## Dlaczego te ustawienia mają znaczenie

* **X‑dimension** wpływa zarówno na rozmiar fizyczny, jak i prędkość skanowania. Mniejsze moduły zwiększają gęstość danych, ale mogą wymagać skanerów o wyższej rozdzielczości.  
* **Columns** wpływają na proporcje obrazu. Dla mobilnych paragonów niska liczba kolumn utrzymuje kod wąski, aby zmieścił się na wąskim papierze.  
* **Truncate** zmniejsza liczbę wierszy, oszczędzając tusz i miejsce bez utraty integralności danych, ponieważ PDF417 już zawiera słowa korekcyjne.  

Zrozumienie tych parametrów pozwala dostosować kod kreskowy do ograniczeń docelowego medium — czy to drukarka etykiet, strona internetowa, czy aplikacja mobilna.

## Typowe warianty i przypadki brzegowe

### Generowanie innych formatów obrazu

Jeśli wolisz JPEG lub BMP, zmień wyliczenie `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG kompresuje obraz, ale może wprowadzać artefakty wpływające na skanowanie przy małych rozmiarach.

### Dostosowywanie korekcji błędów

W trudnych warunkach (np. oznakowanie zewnętrzne) zwiększ poziom korekcji błędów:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Wyższe poziomy dodają więcej redundancji, co sprawia, że kod jest większy, ale bardziej odporny.

### Kodowanie danych binarnych

PDF417 może kodować ładunki binarne. Przekaż `byte[]` zamiast łańcucha znaków:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Biblioteka automatycznie przełącza się w tryb binarny.

### Obsługa bardzo długich ciągów

Gdy dane przekraczają domyślną pojemność, generator automatycznie tworzy dodatkowe wiersze. Możesz ograniczyć liczbę wierszy, aby uniknąć zbyt dużych obrazów:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Jeśli zawartość nadal nie mieści się, rozważ podzielenie jej na wiele kodów kreskowych.

## Porady profesjonalne

* **Cache the generator** jeśli potrzebujesz tworzyć wiele kodów kreskowych z tymi samymi ustawieniami. Ponowne użycie obiektu unika wielokrotnej alokacji zasobów wewnętrznych.  
* **Set `Resolution`** w `ImageOptions`, jeśli potrzebujesz określonej rozdzielczości DPI do druku:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output** programowo przy użyciu `BarCodeReader`, aby upewnić się, że wygenerowany PNG można odczytać przed udostępnieniem go użytkownikom.

## Podsumowanie

Teraz wiesz, jak **create PDF417 barcode** w C# i **generate barcode PNG** z pełną kontrolą nad rozmiarem, kolumnami i trybem kompaktowym. Pełny przykład demonstruje standardowe podejście, wyjaśnia, dlaczego każde ustawienie ma znaczenie, oraz omawia warianty takie jak korekcja błędów, formaty alternatywne i dane binarne. Skorzystaj z powyższych wskazówek, aby dostosować rozwiązanie do swojego konkretnego przepływu pracy, niezależnie od tego, czy tworzysz system biletowy, generator etykiet logistycznych, czy bezpieczny enkoder dokumentów.

---

**Kolejne kroki**

* Zbadaj inne symbologie 2D (DataMatrix, QR) używając tej samej klasy `BarcodeGenerator`.  
* Zintegruj tworzenie kodu kreskowego z API ASP.NET Core, aby na żądanie udostępniać pliki PNG.  
* Połącz obraz kodu kreskowego z bibliotekami generującymi PDF, aby osadzić go bezpośrednio w raportach.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy pdf417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak wygenerować mikro kod kreskowy pdf417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}