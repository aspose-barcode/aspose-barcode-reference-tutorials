---
category: general
date: 2026-09-28
description: Szybko odczytaj kod kreskowy PDF417 c# za pomocą Aspose.BarCode. Dekoduj
  wiele kodów kreskowych z jednego obrazu, wyodrębnij pola Macro‑PDF417 i obsługuj
  rotację lub przetwarzanie wsadowe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Szybko odczytaj kod kreskowy PDF417 c# za pomocą Aspose.BarCode. Ten
  przewodnik pokazuje, jak dekodować wiele kodów kreskowych z jednego obrazu, wyodrębnić
  wszystkie właściwości Macro‑PDF417 oraz obsługiwać obrócone lub wsadowe obrazy.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Odczytaj kod kreskowy PDF417 c# – pełny przykład kodu i przewodnik
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Jak odczytać kod kreskowy PDF417 c# – kompletny przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy PDF417 w C# – kompletny przewodnik krok po kroku

Zastanawiałeś się kiedyś **jak odczytać PDF417** z obrazu przy użyciu C#? Nie jesteś jedyny. Większość programistów napotyka problem, gdy muszą wyciągnąć rozszerzone pola Macro‑PDF417 ze zeskanowanego dokumentu. Dobre wieści? Dzięki kilku liniom kodu możesz **odczytać kod kreskowy PDF417 w C#**, dekodować wiele kodów kreskowych na tym samym obrazie i pobrać wszystkie ukryte właściwości, które oferuje specyfikacja.

## Szybkie odpowiedzi
- **Czy Aspose.BarCode może dekodować Macro‑PDF417?** Tak – wystarczy włączyć `DecodeType.MacroPdf417`, a biblioteka zwróci wszystkie rozszerzone pola.  
- **Ile kodów kreskowych można odczytać z jednego obrazu?** Nieograniczenie; API zwraca kolekcję obiektów `BarCodeResult`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku produkcyjnego; darmowa wersja próbna działa w celach oceny.  
- **Czy obrócone kody kreskowe zostaną wykryte?** Wbudowana kompensacja obrotu działa dla kodów zajmujących co najmniej 30 % szerokości obrazu.  
- **Czy obsługiwana jest przetwarzanie wsadowe?** Zdecydowanie – otocz czytnik w pętli `foreach` i zwalniaj każdą instancję przy pomocy `using`.

## Co to jest odczyt kodu PDF417 w C#?
`read pdf417 barcode c#` odnosi się do procesu używania biblioteki .NET do dekodowania symboli PDF417 (w tym Macro‑PDF417) z plików obrazów bezpośrednio w kodzie C#. SDK Aspose.BarCode udostępnia jednocallowe API, które obsługuje wczytywanie obrazu, wykrywanie kodów kreskowych i wyodrębnianie wszystkich pól zdefiniowanych przez ISO.

## Dlaczego warto używać Aspose.BarCode do dekodowania PDF417?
Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i może przetwarzać obrazy do **5000 × 5000 px** w czasie krótszym niż **0,1 s** na typowym sprzęcie serwerowym. Oferuje także wbudowaną obsługę rotacji, zniekształceń i odwróconych kodów, eliminując potrzebę niestandardowego przetwarzania obrazu. Dodatkowo biblioteka zawiera wbudowaną obsługę odczytu rozszerzonych pól Macro‑PDF417, co czyni ją kompleksowym rozwiązaniem dla skomplikowanych scenariuszy skanowania.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Core i .NET Framework).  
* Visual Studio 2022 (lub dowolny edytor, który preferujesz).  
* Pakiet NuGet **Aspose.BarCode for .NET** – to jest biblioteka, która faktycznie parsuje PDF417.  
* Przykładowy obraz zawierający kod Macro‑PDF417 (np. `ExtPDF417Meta.png`).  

Nie wymagana jest żadna dodatkowa konfiguracja; biblioteka dostarcza wszystkie potrzebne dekodery.

## Jak odczytać kod PDF417 w C#?

Wczytaj obraz przy użyciu `BarCodeReader`, określ `DecodeType.MacroPdf417` i iteruj po zwróconej kolekcji `BarCodeResult` – to kompletny sposób w mniej niż dziesięciu linijkach kodu. Czytnik automatycznie wyodrębnia zarówno zwykłe symbole PDF417, jak i rozszerzone dane Macro‑PDF417, dzięki czemu otrzymujesz identyfikatory plików, numery segmentów, znaczniki czasu i sumy kontrolne bez dodatkowego parsowania.

### Krok 1: zainstaluj Aspose.BarCode

Otwórz folder projektu w terminalu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

To polecenie pobiera najnowszą stabilną wersję (stan na lipiec 2026 to 23.12). Jeśli wolisz konsolę Package Manager w Visual Studio, użyj:

```powershell
Install-Package Aspose.BarCode
```

> **Wskazówka:** zablokuj wersję (`23.12.0`) w pliku `.csproj`, aby uniknąć przypadkowych zmian łamiących w przyszłości.

### Krok 2: utwórz szkielet aplikacji konsolowej

Utwórz nowy projekt konsolowy, jeśli jeszcze go nie masz:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Zastąp automatycznie wygenerowany `Program.cs` poniższym kodem. Wyjaśnimy każdy blok w kolejnych sekcjach.

### Krok 3: napisz pełny kod „jak odczytać PDF417”

`BarCodeReader` jest podstawową klasą, która strumieniuje obraz, wykrywa kody kreskowe i zwraca kolekcję obiektów `BarCodeResult`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — główna klasa odpowiedzialna za odczyt i dekodowanie kodów kreskowych z obrazów.  
* `DecodeType.MacroPdf417` — flaga, która instruuje SDK specjalne traktowanie Macro‑PDF417, jednocześnie zwracając zwykłe symbole PDF417.  
* `Extended.Pdf417.MacroPdf417` — obiekt przechowujący wszystkie opcjonalne pola zdefiniowane w ISO/IEC 15438, takie jak `FileID`, `SegmentID` i `Checksum`.  

Blok `using` zapewnia zwolnienie zasobów natywnych, zapobiegając wyciekom pamięci w długotrwałych usługach.

### Krok 4: uruchom aplikację i zweryfikuj wynik

Z terminala:

```bash
dotnet run
```

Powinieneś zobaczyć coś podobnego do:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Jeśli obraz zawiera więcej niż jeden kod kreskowy, pętla wypisuje linię separatora (`----------------------------------------`) i kontynuuje z następnym wynikiem — dokładnie tak wygląda **odczyt wielu kodów kreskowych** w praktyce.

## Częste pytania i przypadki brzegowe

### Co zrobić, gdy obraz zawiera zarówno symbole Macro‑PDF417, jak i zwykłe PDF417?

To samo wywołanie `BarCodeReader` zwróci oba. Możesz je odróżnić, sprawdzając `result.CodeType` (`MacroPdf417` vs `Pdf417`). Rozszerzone właściwości będą `null` dla zwykłego PDF417, więc warunek `if (macro != null)` zapobiega `NullReferenceException`.

### Mój kod jest obrócony lub skośny — czy czytnik nadal zadziała?

Aspose.BarCode zawiera wbudowaną kompensację rotacji i zniekształceń. Pod warunkiem, że kod zajmuje co najmniej 30 % szerokości obrazu, dekoder zazwyczaj się powiedzie. W skrajnych przypadkach możesz włączyć `reader.Options.AllowInvertedBarcodes = true;` przed wywołaniem `ReadBarCodes()`.

### Jak obsłużyć duże partie obrazów?

Umieść logikę odczytu w pętli `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Wzorzec `using` zapewnia zwolnienie natywnych zasobów każdego obrazu przed kolejną iteracją, utrzymując niskie zużycie pamięci.

## Pełny listing źródłowy (gotowy do kopiowania)

Poniżej znajduje się cały program w jednym bloku, gotowy do szybkiego kopiowania. Brak ukrytych zależności — jedynie pakiet NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Podsumowanie – co omówiliśmy

* **Jak odczytać kod PDF417 w C#** przy użyciu Aspose.BarCode.  
* Dokładne kroki, aby **odczytać wiele kodów kreskowych** z jednego obrazu.  
* Jak **odczytać obraz kodu kreskowego w C#** i wyodrębnić każde pole Macro‑PDF417.  
* Wskazówki dotyczące rotacji, przetwarzania wsadowego i obsługi brakujących danych rozszerzonych.

## Kolejne kroki i powiązane tematy

* **Encode PDF417** – generuj własne kody Macro‑PDF417 przy użyciu `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – przy użyciu tej samej klasy `BarCodeReader`.  
* **Integrate with ASP.NET Core** – udostępnij endpoint webowy, który przyjmuje przesłany obraz i zwraca JSON z odszyfrowanymi polami.  

### Dodatkowe przydatne linki
- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Odczyt kodu DataMatrix w C# – Generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Śmiało eksperymentuj: zmień ścieżkę obrazu, wrzuć zwykły PDF417 do tego samego folderu lub dostosuj flagi `DecodeType`, aby zobaczyć, jak biblioteka zachowuje się. Im więcej będziesz się bawić, tym pewniej poczujesz się w scenariuszach **odczytu obrazu kodu kreskowego w C#**.

Masz trudny obraz, który odmawia dekodowania? Dodaj komentarz poniżej lub otwórz zgłoszenie w repozytorium GitHub przykładowego projektu. Szczęśliwego kodowania!

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego w aplikacji komercyjnej?**  
A: Tak, możesz używać Aspose.BarCode w projektach komercyjnych, o ile posiadasz ważną licencję; dostępna jest darmowa wersja próbna do oceny.

**Q: Czy czytnik obsługuje obrazy chronione hasłem?**  
A: SDK działa z każdym standardowym formatem obrazu; ochrona hasłem nie ma zastosowania do obrazów rastrowych, a jedynie do plików PDF, które są obsługiwane przez oddzielny komponent Aspose.PDF.

**Q: Jakie wersje .NET są obsługiwane?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ oraz .NET 6+ są w pełni obsługiwane przez bieżącą wersję Aspose.BarCode.

**Q: Jak mogę poprawić wydajność przy bardzo dużych partiach obrazów?**  
A: Włącz `reader.Options.Quality = QualityMode.HighPerformance` i przetwarzaj obrazy równolegle przy użyciu `Parallel.ForEach`, nadal otaczając każdy `BarCodeReader` blokiem `using`.

**Q: Czy istnieje sposób, aby uzyskać tylko pola Macro‑PDF417 bez iteracji wszystkich wyników?**  
A: Tak – po wywołaniu `ReadBarCodes()` przefiltruj kolekcję przy użyciu `result => result.CodeType == DecodeType.MacroPdf417`, a następnie uzyskaj dostęp do właściwości `Extended.Pdf417.MacroPdf417`.

**Ostatnia aktualizacja:** 2026-09-28  
**Testowano z:** Aspose.BarCode 23.12 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak wygenerować obraz kodu PDF417 w C# z Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Utwórz kod PDF417 przy użyciu Aspose Barcode – przewodnik krok po kroku](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Odczyt wielu kodów kreskowych w C – kompletny przewodnik z PDF417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}