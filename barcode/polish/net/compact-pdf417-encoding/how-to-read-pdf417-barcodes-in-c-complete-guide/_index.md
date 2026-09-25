---
category: general
date: 2026-08-22
description: Jak odczytywać kody kreskowe PDF417 w C# w przewodniku krok po kroku,
  obejmującym odczyt wielu kodów z obrazu oraz wyodrębnianie szczegółów MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: pl
lastmod: 2026-08-22
og_description: Jak szybko odczytywać kody kreskowe PDF417 w C#. Ten samouczek pokazuje,
  jak odczytać wiele kodów z obrazu i uzyskać rozszerzone informacje MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Jak odczytać kody kreskowe PDF417 w C# – pełny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak odczytać kody kreskowe PDF417 w C# – kompletny przewodnik
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kody kreskowe PDF417 w C# – kompletny przewodnik

Jeśli potrzebujesz **jak odczytać PDF417** w aplikacji .NET, ten tutorial dostarcza gotowe rozwiązanie do uruchomienia. Nauczysz się, jak odczytać wiele kodów kreskowych z jednego obrazu, wyodrębnić pełny zestaw danych MacroPdf417 i wyświetlić go w konsoli. Podejście działa z biblioteką Aspose.BarCode for .NET i wymaga tylko kilku linii kodu.

Odczytywanie kodów kreskowych z obrazu to powszechne zadanie w systemach inwentaryzacji, weryfikacji biletów i zarządzaniu dokumentami. Po zakończeniu tego przewodnika będziesz w stanie zdekodować dowolny kod PDF417 lub MacroPdf417, obsłużyć kilka kodów na jednym obrazie oraz zrozumieć rozszerzone pola, które dostarcza MacroPdf417.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod kompiluje się również z .NET Framework 4.7+)
- Visual Studio 2022 lub dowolny edytor C#, którego używasz
- Pakiet NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Przykładowy obraz zawierający kod MacroPdf417 (np. `MacroPdf417.png`)

Nie wymagana jest dodatkowa konfiguracja; biblioteka wewnętrznie obsługuje wczytywanie obrazu i dekodowanie.

## Jak odczytać kody kreskowe PDF417 z obrazu w C#

Kluczowym elementem rozwiązania jest klasa `BarCodeReader`. Otwiera ona obraz, wykrywa wszystkie kody kreskowe określonego typu i zwraca kolekcję obiektów `BarCodeResult`. Poniższy kod przedstawia kompletny program konsolowy.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Dlaczego każdy wiersz ma znaczenie

| Krok | Cel |
|------|-----|
| **1️⃣ Initialize** | Tworzy `BarCodeReader` powiązany z plikiem obrazu i ogranicza wykrywanie do symbologii MacroPdf417, co przyspiesza przetwarzanie. |
| **2️⃣ Iterate** | `ReadBarCodes()` zwraca **wszystkie** kody kreskowe pasujące do żądanego typu, umożliwiając **odczyt wielu kodów** bez dodatkowych pętli. |
| **3️⃣ Basic output** | Wyświetla ogólną nazwę typu `CodeTypeName` oraz czytelny dla człowieka `CodeText`. Jest to przydatne do logowania lub szybkiej weryfikacji. |
| **4️⃣ Extended data** | MacroPdf417 zawiera dodatkowe metadane (identyfikator pliku, liczba segmentów, znaczniki czasu itp.). Obiekt `Extended.Pdf417` udostępnia każde pole bezpośrednio, dzięki czemu możesz przechowywać lub weryfikować cały pakiet danych. |

Uruchomienie programu na prawidłowym obrazie MacroPdf417 generuje w konsoli wyjście podobne do poniższego:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Wyjście potwierdza, że biblioteka pomyślnie odczytała kod kreskowy, wyodrębniła tekst i udostępniła wszystkie pola MacroPdf417.

## Odczytywanie wielu kodów kreskowych z jednego obrazu

W wielu rzeczywistych scenariuszach na jednej etykiecie umieszczonych jest kilka symboli PDF417 — pomyśl o liście przewozowej zawierającej kod przewoźnika, numer śledzenia i deklarację celną. Powyższy blok kodu już **odczytuje wiele kodów kreskowych**, ponieważ `ReadBarCodes()` zwraca enumerację wszystkich dopasowań. Nie wymagana jest dodatkowa konfiguracja; wystarczy przejść pętlą po wynikach, jak pokazano.

Jeśli chcesz ograniczyć czytnik do standardowego PDF417 (bez makra), a jednocześnie obsługiwać kilka kodów, zamień `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Reszta logiki pozostaje niezmieniona.

## Zrozumienie rozszerzonych danych MacroPdf417

MacroPdf417 to rozszerzenie standardowej specyfikacji PDF417. Dzieli duże ładunki na wiele segmentów i dodaje mały nagłówek opisujący cały plik. Najważniejsze pola to:

- **MacroPdf417FileID** – unikalny identyfikator współdzielony przez wszystkie segmenty tego samego pliku.
- **MacroPdf417SegmentID** – numer kolejny bieżącego segmentu.
- **MacroPdf417SegmentsCount** – łączna liczba oczekiwanych segmentów.
- **MacroPdf417FileName** – opcjonalna nazwa pliku przesyłana wraz z kodem kreskowym.
- **MacroPdf417Checksum** – wartość kontrolna służąca do sprawdzania błędów całego pliku.
- **MacroPdf417FileSize** – rozmiar oryginalnego binarnego ładunku.
- **MacroPdf417TimeStamp** – znacznik czasu w formacie ISO‑8601, kiedy kod został wygenerowany.
- **MacroPdf417Addressee / Sender** – opcjonalne pola tekstowe służące do routingu.
- **MacroPdf417Terminator** – wskazuje, czy dany segment jest ostatnim.

Gdy otrzymasz wszystkie segmenty, możesz odtworzyć oryginalny plik, sortując je według `MacroPdf417SegmentID` i łącząc wartości `CodeText`. Ta logika jest prosta do zaimplementowania, gdy pola są dostępne.

## Częste pułapki i profesjonalne wskazówki

- **Image quality matters** – niska rozdzielczość lub silnie skompresowane pliki PNG/JPEG mogą powodować pominięcie wykryć. Używaj DPI co najmniej 300 dpi dla drukowanych kodów.
- **Mixed symbologies** – jeśli obraz zawiera zarówno MacroPdf417, jak i zwykły PDF417, utwórz dwa czytniki (po jednym dla każdego `DecodeType`) lub użyj `DecodeType.AllSupported` i przefiltruj wyniki po `result.CodeTypeName`.
- **Memory usage** – instrukcja `using` natychmiast zwalnia `BarCodeReader`, zapobiegając pozostawaniu dużych buforów obrazu w pamięci.
- **Thread safety** – `BarCodeReader` nie jest bezpieczny wątkowo. Twórz osobną instancję na każdy wątek, jeśli dekodujesz obrazy równolegle.
- **Error handling** – otocz wywołanie `ReadBarCodes()` blokiem try/catch, aby przechwycić `BarCodeException` w przypadku uszkodzonych obrazów.

## Pełny działający przykład – podsumowanie

Poniżej znajduje się kompletny program, który możesz skopiować do nowego projektu konsolowego. Zawiera wszystkie dyrektywy `using`, stałą określającą ścieżkę do obrazu oraz wzorzec zwalniania zasobów.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Kompiluj poleceniem `dotnet build` i uruchom `dotnet run`. Konsola wypisze podstawowe dane każdego kodu oraz pełny ładunek MacroPdf417.

## Następne kroki

- **Reconstruct multipart files** – zbierz wszystkie segmenty, posortuj je według `MacroPdf417SegmentID` i połącz `CodeText` aby

## Co powinieneś się nauczyć dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z krok po kroku wyjaśnieniami, pomagając opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 – kompaktowe kodowanie PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak odczytać kody kreskowe PDF417 z tureckimi znakami w Javie](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Jak używać Aspose do kodu kreskowego PDF417 (chiński) w Javie](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}