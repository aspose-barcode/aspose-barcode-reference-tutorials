---
category: general
date: 2026-08-03
description: Generuj kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Dowiedz
  się krok po kroku, jak dodać metadane Macro PDF417 i zapisać jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: pl
lastmod: 2026-08-03
og_description: Generuj kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Ten samouczek
  pokazuje, jak osadzić metadane Macro PDF417 i wyeksportować wynik jako obraz PNG.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Generowanie kodu kreskowego PDF417 w C# – krok po kroku tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik z Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik

Jeśli potrzebujesz **generować kod kreskowy PDF417 w C#** dla systemu logistycznego lub zarządzania dokumentami, ten samouczek pokaże Ci dokładnie, jak to zrobić przy użyciu Aspose.BarCode. Zobaczysz, jak skonfigurować kod kreskowy, osadzić metadane Macro PDF417 i zapisać wynik jako obraz PNG w zaledwie kilku linijkach kodu.

Generowanie kodu kreskowego PDF417 w C# często oznacza obsługę dodatkowych informacji, takich jak identyfikatory plików, numery segmentów czy znaczniki czasu. Ten przewodnik obejmuje te szczegóły, więc nie musisz przeszukiwać rozproszonej dokumentacji. Po przeczytaniu artykułu będziesz mieć gotowy do uruchomienia program, który tworzy zgodny obraz kodu Macro PDF417.

## Czego będziesz potrzebować

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Aspose.BarCode for .NET (v23.9 lub nowszy) – zainstaluj przez NuGet `Install-Package Aspose.BarCode`
- Środowisko programistyczne, takie jak Visual Studio 2022 lub Visual Studio Code
- Podstawowa znajomość składni C#

> **Pro tip:** Użyj najnowszej wersji Aspose.BarCode, aby skorzystać z poprawek błędów i wsparcia najnowszych specyfikacji PDF417.

## Jak generować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode

Proces składa się z czterech logicznych kroków. Każdy krok jest zamknięty w przejrzystym bloku kodu, abyś mógł go od razu skopiować, wkleić i uruchomić.

### Krok 1: Utwórz generator kodu kreskowego Macro PDF417

Najpierw utwórz instancję `BarcodeGenerator` z wyliczeniem `EncodeTypes.MacroPdf417`. Konstruktor przyjmuje także tekst, który chcesz zakodować – w tym przykładzie używamy łańcucha zawierającego znaki Unicode, aby pokazać obsługę pełnej szerokości.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Dlaczego to ważne*: Typ `MacroPdf417` informuje Aspose.BarCode, że symbol ma być traktowany jako kod makro, który może zawierać dodatkowe metadane na poziomie pliku. Bez tego flagi pola ustawione później zostaną zignorowane.

### Krok 2: Dostosuj podstawowy wygląd kodu kreskowego

Następnie określ wizualny rozmiar kodu kreskowego. `XDimension.Pixels` kontroluje szerokość pojedynczego modułu (najmniejszego czarno‑białego kwadratu), natomiast `Pdf417.Columns` wpływa na ogólny kształt, ustawiając liczbę kolumn.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Dlaczego to ważne*: Mniejszy `XDimension` daje obraz o wyższej rozdzielczości, co jest przydatne, gdy kod ma być skanowany z ekranu. Zmiana liczby kolumn może pomóc dopasować kod do ograniczonej przestrzeni bez utraty pojemności danych.

### Krok 3: Wypełnij metadane Macro PDF417

Macro PDF417 pozwala osadzić informacje na poziomie pliku, na których opiera się wiele systemów back‑office (np. ID pliku, ID segmentu, znacznik czasu). Poniższe właściwości ilustrują najczęściej używane pola.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Dlaczego to ważne*: Każde pole mapuje się bezpośrednio na segment specyfikacji kodu makro. Na przykład `MacroPdf417FileID` jednoznacznie identyfikuje logiczny plik, a `MacroPdf417SegmentsCount` informuje skaner, ile części ma się spodziewać. Dostarczenie dokładnych metadanych zapewnia, że systemy downstream mogą odtworzyć oryginalny dokument bez błędów.

### Krok 4: Zapisz obraz kodu kreskowego jako PNG

Na koniec wywołaj `Save`, aby zapisać kod na dysku. PNG jest bezstratny, co czyni go idealnym do skanowania wysokiej jakości.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Dlaczego to ważne*: Wyliczenie `BarCodeImageFormat.Png` gwarantuje, że plik wyjściowy zawiera dokładnie takie same dane pikselowe, jakie skonfigurowałeś. Jeśli potrzebny jest format wektorowy do skalowania, zamień `Png` na `Svg` – Aspose.BarCode obsługuje to od razu.

#### Oczekiwany wynik

Uruchomienie pełnego programu tworzy plik o nazwie **ExtPDF417Meta.png**. Obraz przedstawia gęsty, wielowierszowy symbol PDF417, który zawiera tekst „Åspóse.Barcóde©” oraz makro‑metadane, które podałeś. Skanowanie kodu przy użyciu czytnika kompatybilnego z PDF417 zwraca oryginalny tekst oraz blok danych w formacie podobnym do JSON, zawierający ID pliku, ID segmentu, znacznik czasu i inne pola.

![Zrzut ekranu wygenerowanego kodu kreskowego PDF417](/images/pdf417-example.png){: .center-image alt="przykładowy wynik generowania kodu kreskowego PDF417 w C#"}

## Pełny kod źródłowy (gotowy do kopiowania i wklejania)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Jak zweryfikować wynik

1. Otwórz `ExtPDF417Meta.png` w dowolnym przeglądarce obrazów.  
2. Użyj aplikacji skanującej PDF417 (np. *Zebra Scanner* lub *BarCode Reader* na Androidzie/iOS).  
3. Potwierdź, że odkodowana zawartość obejmuje oryginalny tekst oraz blok danych w stylu JSON z makro‑polami, które ustawiłeś.

## Częste pytania i obsługa przypadków brzegowych

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę wygenerować obraz wektorowy zamiast PNG?** | Tak. Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Svg`. Reszta kodu pozostaje niezmieniona. |
| **Co zrobić, gdy moje dane przekraczają domyślną pojemność?** | Zwiększ `Pdf417.Columns` lub ręcznie ustaw `Pdf417.Rows`. Większe wartości pozwalają na więcej kodowych słów w segmencie. |
| **Czy Unicode jest obsługiwany w zakodowanym tekście?** | Oczywiście. Przykład używa „Åspóse.Barcóde©”. Aspose.BarCode automatycznie przełącza się na kodowanie UTF‑8 w razie potrzeby. |
| **Czy muszę podpisać licencję dla Aspose.BarCode?** | W produkcji powinieneś zastosować licencję, aby uniknąć znaku wodnego wersji ewaluacyjnej. Wywołaj `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` przed utworzeniem generatora. |
| **Jak obsłużyć błędy przy zapisywaniu pliku?** | Otocz wywołanie `Save` w bloku try/catch i loguj `IOException` lub `BarCodeException` w celu diagnostyki. |

## Podsumowanie

Teraz wiesz, jak **generować kod kreskowy PDF417 w C#** przy użyciu Aspose.BarCode, osadzać pełne metadane Macro PDF417 i eksportować wynik jako wysokiej jakości obraz PNG. Kroki – tworzenie generatora, dostosowanie wyglądu, wypełnianie metadanych i zapisywanie obrazu – tworzą wzorzec, który możesz ponownie wykorzystać przy fakturach, etykietach wysyłkowych lub w każdej sytuacji wymagającej bogatych danych w kodzie kreskowym.

### Kolejne kroki

- Eksperymentuj z innymi formatami kodów kreskowych (np. QR, Code128), zmieniając `EncodeTypes`.  
- Zbadaj `Pdf417.ErrorCorrectionLevel`, aby poprawić niezawodność skanowania przy słabym oświetleniu.  
- Zintegruj wygenerowany obraz z raportem PDF przy użyciu Aspose.PDF, aby uzyskać pełną automatyzację dokumentów od początku do końca.  

Śmiało modyfikuj pola metadanych, aby dopasować je do reguł biznesowych, i niech generowanie kodów kreskowych stanie się płynną częścią Twoich aplikacji C#. Szczęśliwego kodowania!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak utworzyć kod kreskowy – Kompaktowy PDF417 z Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [biblioteka kodów kreskowych Java – Dodaj kod kreskowy do PDF przy użyciu Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}