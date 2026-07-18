---
category: general
date: 2026-07-18
description: Generuj kod kreskowy z tekstem przy użyciu Aspose.BarCode dla .NET. Dowiedz
  się, jak generować kody PDF417, ustawiać opcje makr i eksportować obrazy PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: pl
lastmod: 2026-07-18
og_description: Szybko generuj kod kreskowy z tekstem w C#. Ten krok po kroku poradnik
  pokazuje, jak generować kody kreskowe PDF417, konfigurować ustawienia makr i zapisywać
  jako PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Generuj kod kreskowy z tekstem – Master PDF417 Macro Creation
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Generuj kod kreskowy z tekstem – Pełny przewodnik po PDF417 Macro
url: /pl/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego z tekstem – Pełny przewodnik po Macro PDF417

Zastanawiałeś się kiedyś **jak generować PDF417** kody kreskowe, które dodatkowo zawierają własny tekst? W tym samouczku pokażemy dokładnie, jak **generować kod kreskowy z tekstem** przy użyciu Aspose.BarCode dla .NET i przeprowadzimy Cię przez wszystkie ustawienia potrzebne do symbolu Macro PDF417. Bez zbędnych wstępów, tylko kompletny, gotowy do uruchomienia przykład, który możesz od razu wkleić do swojego projektu.

Omówimy:

* Wymaganą paczkę NuGet oraz dyrektywy using.  
* Jak utworzyć generator kodu kreskowego obsługujący znaki Unicode.  
* Ustawienie rozmiaru modułu, liczby kolumn oraz identyfikatorów specyficznych dla macro.  
* Zapis wyniku jako plik PNG i weryfikację wyjścia.  

Pod koniec będziesz mieć gotowy do użycia obraz PNG z kodem Macro PDF417, który możesz osadzić w fakturach, biletach lub dowolnym dokumencie wymagającym segmentu odczytywanego maszynowo.

---

## Wymagania wstępne

| Wymaganie | Powód |
|-----------|-------|
| **.NET 6.0** lub nowszy | Aspose.BarCode obsługuje .NET Standard 2.0+, więc .NET 6 zapewnia najnowsze środowisko uruchomieniowe. |
| **Visual Studio 2022** (lub dowolne IDE C#) | Dla łatwej edycji i debugowania. |
| **Aspose.BarCode for .NET** pakiet NuGet | Biblioteka, która faktycznie tworzy kod kreskowy. Zainstaluj ją poleceniem `dotnet add package Aspose.BarCode`. |
| **Uprawnienia zapisu** do folderu wyjściowego | Metoda `Save` musi zapisać plik PNG. |

Jeśli któreś z tych zagadnień jest Ci nieznane, zatrzymaj się i je dopilnuj — w przeciwnym razie kod wyrzuci oczywiste wyjątki.

## Krok 1 – Zainstaluj i zaimportuj bibliotekę

Najpierw dodaj pakiet NuGet do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

Następnie wprowadź niezbędne przestrzenie nazw:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Wskazówka:** Jeśli używasz Visual Studio, kliknij prawym przyciskiem projektu → *Zarządzaj pakietami NuGet* → wyszukaj *Aspose.BarCode* i zainstaluj najnowszą stabilną wersję.

## Krok 2 – Utwórz generator kodu kreskowego z własnym tekstem

Głównym zadaniem jest **generowanie kodu kreskowego z tekstem**, który zawiera znaki specjalne, takie jak „Å” i „©”. Konstruktor przyjmuje typ kodowania i surowy ciąg danych:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Dlaczego to ważne: `EncodeTypes.MacroPdf417` informuje Aspose, że chcemy wersję macro, co pozwala podzielić dużą wiadomość na wiele symboli. Ciąg tekstowy może być dowolną sekwencją UTF‑8; Aspose obsługuje konwersję wewnętrznie.

## Krok 3 – Dostosuj podstawowy wygląd (rozmiar modułu)

„Moduł” kodu kreskowego to najmniejszy czarny lub biały kwadrat. Ustawienie jego rozmiaru w pikselach kontroluje wymiary obrazu bez zmiany gęstości danych:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jeśli potrzebujesz większego obrazu do druku, zwiększ tę wartość do 4 lub 6. Pamiętaj tylko, że większe moduły zwiększają ostateczny rozmiar pliku PNG.

## Krok 4 – Skonfiguruj opcje specyficzne dla Macro PDF417

Macro PDF417 dodaje dwa identyfikatory, które pozwalają skanerowi połączyć wiele symboli. Zazwyczaj ustawiasz:

| Właściwość | Co robi |
|------------|---------|
| `Columns` | Liczba kolumn danych na symbol (wpływa na szerokość). |
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku macro (musi być ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (0‑254). |

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Uwaga dotycząca przypadków brzegowych:** `MacroPdf417FileID` musi być taki sam dla każdego segmentu w tym samym logicznym pliku. Jeśli generujesz wiele segmentów, użyj tego samego ID, w przeciwnym razie otrzymasz niepowiązane symbole, których nie da się połączyć.

## Krok 5 – Zapisz kod kreskowy jako obraz PNG

Teraz, gdy wszystko jest skonfigurowane, zapisz obraz na dysku:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Metoda `Save` automatycznie tworzy PNG, obsługując DPI i głębię kolorów. Po wykonaniu otwórz plik, aby zobaczyć coś podobnego:

![Generate barcode with text example](/images/barcode-example.png){.center alt="Przykład generowania kodu kreskowego z tekstem"}

Jeśli nie widzisz kodu kreskowego, sprawdź dwukrotnie, czy folder istnieje i czy aplikacja ma uprawnienia do zapisu.

## Pełny, gotowy do uruchomienia przykład

Skopiuj cały fragment poniżej do nowej aplikacji konsolowej (`dotnet new console`) i uruchom go. Wygeneruje on PNG w folderze `C:\Barcodes` (najpierw utwórz folder).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Oczekiwany wynik** (konsola):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

A plik PNG wyświetli zwarty symbol Macro PDF417 zawierający tekst „Åspóse.Barcóde©”.

## Częste pytania i pułapki

| Pytanie | Odpowiedź |
|----------|-----------|
| *Czy mogę użyć innego formatu obrazu?* | Oczywiście — zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`. PNG jest bezstratny, dlatego domyślnie go używamy. |
| *Co zrobić, jeśli potrzebuję więcej niż jednego segmentu?* | Utwórz nowy `BarcodeGenerator` dla każdego segmentu, zachowaj identyczny `MacroPdf417FileID` i zwiększ `MacroPdf417SegmentID` (0‑254). |
| *Mój tekst zawiera emotikony — czy będą działać?* | Aspose.BarCode obsługuje UTF‑8, więc większość emotikonów jest obsługiwana. Upewnij się jednak, że docelowy skaner potrafi je odczytać; wiele przemysłowych skanerów obsługuje tylko dane alfanumeryczne. |
| *Kod kreskowy jest za szeroki dla mojej etykiety.* | Zmniejsz `Columns` lub zwiększ rozmiar modułu. Mniej kolumn daje węższy symbol, ale może wymagać drukarki o wyższym DPI. |
| *Czy potrzebna jest licencja?* | Darmowa licencja ewaluacyjna działa do testów, ale dodaje mały znak wodny. W produkcji zakup licencję, aby usunąć znak wodny i odblokować pełne funkcje. |

## Kolejne kroki

Teraz, gdy wiesz **jak generować PDF417** kody kreskowe z własnym tekstem, możesz chcieć:

* **Odczytać** kod kreskowy w aplikacji mobilnej przy użyciu `BarCodeReader` Aspose.BarCode.  
* **Połączyć** wiele segmentów macro w jeden dokument PDF do drukowania wsadowego.  
* **Zbadać inne symbologie** (QR, DataMatrix) z podobnymi wzorcami parametrów.  
* **Dostosować poziom korekcji błędów** za pomocą `Pdf417.ErrorCorrectionLevel` w trudniejszych warunkach.

Każdy z tych tematów opiera się na tych samych podstawowych koncepcjach, które właśnie poznałeś, więc przejście będzie płynne.

## Podsumowanie

Przeprowadziliśmy kompletną, end‑to‑end procedurę, która pozwala **generować kod kreskowy z tekstem**, a konkretnie **jak generować macro PDF417** przy użyciu Aspose.BarCode dla .NET. Ustawiając wymiar X, liczbę kolumn i identyfikatory macro, zyskujesz pełną kontrolę nad rozmiarem, układem i obsługą wielu segmentów. Powstały PNG można drukować, osadzać w PDF‑ach lub wysyłać do skanera bez dodatkowej konwersji.

Spróbuj, zmodyfikuj parametry i niech kod kreskowy działa na korzyść Twojego biznesu. Jeśli napotkasz problem, dokumentacja Aspose oraz fora społeczności są doskonałymi źródłami dalszych informacji. Szczęśliwego kodowania!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne, działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}