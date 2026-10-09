---
category: general
date: 2026-10-08
description: Generuj kod kreskowy PDF417 w C# i dowiedz się, jak efektywnie generować
  obrazy PDF417 przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: pl
lastmod: 2026-10-08
og_description: Generuj kod kreskowy PDF417 w C# z przewodnikiem krok po kroku. Dowiedz
  się, jak generować PDF417 i zapisać obraz kodu kreskowego jako PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Wygeneruj kod kreskowy PDF417 i utwórz obraz kodu kreskowego w C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Generuj kod kreskowy PDF417 i utwórz obraz kodu kreskowego C#
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego PDF417 i tworzenie obrazu kodu kreskowego C#

Jeśli potrzebujesz **generować kod kreskowy PDF417** w aplikacji .NET, ten samouczek pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, gotowy do uruchomienia przykład, który tworzy kod kreskowy, dostosowuje jego układ i zapisuje wynik jako obraz PNG.

Generowanie kodu kreskowego PDF417 jest powszechnym wymogiem dla etykiet wysyłkowych, kart pokładowych i systemów inwentaryzacji. Po przeczytaniu tego przewodnika będziesz wiedział, **jak generować PDF417** z precyzyjną kontrolą rozmiaru i układu, a także nauczysz się **tworzyć obraz kodu kreskowego C#**, który może być wyświetlany w interfejsie użytkownika lub wysyłany do drukarki.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7.2+)
- Visual Studio 2022 lub dowolne IDE obsługujące C#
- Aspose.BarCode for .NET (wersja próbna lub licencjonowana)  
  Zainstaluj ją przez NuGet:

```bash
dotnet add package Aspose.BarCode
```

Nie wymaga dodatkowej konfiguracji; biblioteka obsługuje kodowanie PNG wewnętrznie.

## Krok 1: Utworzenie projektu i importowanie przestrzeni nazw

Utwórz nowy projekt konsolowy i dodaj niezbędne dyrektywy `using`. Ten blok zawiera wszystko, co potrzebne do skompilowania przykładu.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Dlaczego ten krok jest ważny*: Importowanie przestrzeni nazw `Aspose.BarCode.Generation` daje dostęp do `BarcodeGenerator`, `EncodeTypes` oraz obiektów parametrów używanych do dostosowywania kodu kreskowego.

## Krok 2: Generowanie kodu kreskowego PDF417 z żądanym tekstem

Wewnątrz `Main` utwórz instancję `BarcodeGenerator` z `EncodeTypes.Pdf417`. Konstruktor przyjmuje typ kodu kreskowego oraz tekst, który ma zostać zakodowany.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Wyjaśnienie*: `EncodeTypes.Pdf417` informuje bibliotekę, że ma wygenerować symbologię PDF417. Ciąg `"Layout demo"` staje się ładunkiem danych zakodowanym w kodzie kreskowym.

## Krok 3: Precyzyjne dostosowanie rozmiaru kodu kreskowego za pomocą wymiaru X

Wymiar X kontroluje szerokość pojedynczego modułu (najmniejszego czarno‑białego kwadratu). Ustawienie go w pikselach daje dokładną kontrolę nad ostatecznym rozmiarem obrazu.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Dlaczego to ma znaczenie*: Mniejszy wymiar X skutkuje bardziej zwartym kodem kreskowym, co jest przydatne, gdy masz ograniczoną przestrzeń na etykiecie lub elemencie UI.

## Krok 4: Dostosowanie układu PDF417 (kolumny i wiersze)

PDF417 pozwala określić liczbę kolumn i wierszy. Zmiana tych wartości wpływa na proporcje kodu kreskowego.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Wyjaśnienie*: Przy 4 kolumnach i 9 wierszach kod kreskowy staje się wyższy niż szerszy, co pasuje do wielu formatów drukowania biletów.

## Krok 5: Zapis wygenerowanego kodu kreskowego jako obrazu PNG

Na koniec zapisz kod kreskowy do pliku. Enum `BarCodeImageFormat.Png` zapewnia bezstratną kompresję.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Co się tutaj dzieje*: `Save` tworzy plik obrazu na dysku. Możesz zamienić `BarCodeImageFormat.Png` na `Jpeg` lub `Bmp`, jeśli potrzebny jest inny format.

### Pełny przykład w jednym bloku

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Zamień `YOUR_DIRECTORY` na rzeczywistą ścieżkę folderu na swoim komputerze.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Uruchom program (`dotnet run`) i otwórz powstały plik `LayoutPdf417.png`. Powinieneś zobaczyć czysty kod kreskowy PDF417, który koduje tekst *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Wygenerowany kod kreskowy PDF417 zapisany jako PNG"}

*Oczekiwany wynik*: Plik PNG o przybliżonych wymiarach 150 × 300 pikseli (rozmiar zależy od wymiaru X) zawierający skanowalny kod kreskowy PDF417.

## Typowe wariacje i przypadki brzegowe

| Scenariusz | Jak dostosować kod |
|------------|--------------------|
| **Inny ładunek danych** | Zmień drugi argument `BarcodeGenerator` (`"Layout demo"` → dowolny ciąg, do 1 800 znaków). |
| **Wyższa rozdzielczość** | Zwiększ `XDimension.Pixels` (np. `4`) lub ustaw `Resolution` poprzez `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Przezroczyste tło** | Użyj `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Osadzenie w kontrolce Windows Forms PictureBox** | Zamiast `Save`, wywołaj `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Obsługa błędów** | Owiń kod generujący w blok `try…catch`, aby przechwycić `BarCodeException` w przypadku nieobsługiwanych znaków. |

## Porady profesjonalistów

- **Walidacja kodu kreskowego**: Po zapisaniu możesz wczytać PNG przy użyciu SDK skanera kodów kreskowych, aby upewnić się, że dane zgadzają się z oryginalnym ciągiem.
- **Wydajność**: Ponowne użycie jednej instancji `BarcodeGenerator` dla wielu kodów kreskowych zmniejsza narzut alokacji.
- **Bezpieczeństwo**: Jeśli kodowane dane zawierają poufne informacje, rozważ ich zaszyfrowanie przed przekazaniem do generatora.

## Podsumowanie

Teraz wiesz, jak **generować kod kreskowy PDF417** w C# i **tworzyć pliki obrazu kodu kreskowego C#**, które spełniają niestandardowe wymagania układu. Pełny przykład pokazuje inicjalizację generatora, dostosowanie rozmiaru i układu oraz zapis wyniku jako PNG. Od tego momentu możesz eksplorować dodatkowe funkcje, takie jak dostosowanie kolorów, osadzanie logo czy generowanie partii kodów kreskowych do masowego drukowania.

---

*Kolejne kroki*:  
- Eksperymentuj z innymi symbologiami (Code128, QR) przy użyciu tej samej klasy `BarcodeGenerator`.  
- Dowiedz się, jak odczytywać kody PDF417 przy pomocy `BarCodeReader` z Aspose.BarCode.  
- Zintegruj wygenerowany PNG w widokach ASP.NET Core MVC, aby renderować kody kreskowe w locie.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz krok‑po‑kroku wyjaśnienia, pomagające opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}