---
category: general
date: 2026-08-06
description: Szybko utwórz kod kreskowy DataBar Stacked w C#. Dowiedz się, jak ustawić
  wymiar X, dostosować proporcje i eksportować pliki PNG przy użyciu generatora DataBar
  Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: pl
lastmod: 2026-08-06
og_description: Utwórz kod kreskowy Databar stacked w C# z Aspose.BarCode. Ten samouczek
  pokazuje, jak skonfigurować wymiar X, zmienić współczynnik proporcji i zapisać obrazy
  PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Tworzenie kodu kreskowego Databar stacked w C# – kompletny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Tworzenie kodu kreskowego Databar stacked w C# – przewodnik krok po kroku
url: /pl/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy databar stacked w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć kod kreskowy databar stacked** w C#, ten przewodnik pokaże Ci dokładnie, jak to zrobić przy użyciu biblioteki Aspose.BarCode. Nauczysz się ustawiać wymiar X, zmieniać współczynnik proporcji kodu kreskowego oraz zapisywać wynik jako pliki PNG — wszystko w kilku zwięzłych krokach.

Generowanie kodu kreskowego DataBar Stacked jest powszechne, gdy trzeba zakodować dane GS1‑128 do skanowania w handlu detalicznym lub śledzenia logistycznego. W kolejnych sekcjach omówimy wszystko, od konfiguracji projektu po weryfikację wyniku, abyś mógł zintegrować rozwiązanie z dowolną aplikacją .NET bez pomijania żadnych szczegółów.

## Wymagania wstępne

* **.NET 6.0** (lub nowszy) zainstalowany – kod jest skierowany do nowoczesnego SDK.
* **Licencjonowana** kopia **Aspose.BarCode for .NET**. Darmowa wersja ewaluacyjna działa do testów, ale dodaje znak wodny.
* IDE, takie jak **Visual Studio 2022** lub **VS Code** z rozszerzeniem C#.
* Podstawowa znajomość składni **C#** oraz koncepcji identyfikatorów aplikacji GS1.

> **Porada:** Jeśli używasz menedżera pakietów NuGet, polecenie `dotnet add package Aspose.BarCode` automatycznie rozwiązuje wszystkie zależności.

## Krok 1: Utwórz nowy projekt konsolowy

Otwórz terminal lub konsolę Menedżera Pakietów i uruchom:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Polecenie `dotnet new console` tworzy minimalny plik **Program.cs**. Dodanie pakietu **Aspose.BarCode** udostępnia klasę `BarcodeGenerator`.

## Krok 2: Zainicjalizuj generator DataBar Stacked Omnidirectional

Otwórz **Program.cs** i zamień domyślną zawartość na poniższy kod. Pierwsza linia tworzy **BarcodeGenerator** skonfigurowany dla symboliki **DataBar Stacked Omnidirectional** i podaje ładunek GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Dlaczego to ważne:** Wartość wyliczenia `EncodeTypes.DatabarStackedOmniDirectional` informuje bibliotekę, aby wygenerowała **databar stacked barcode**, czyli wariant stosowany rodziny DataBar omnidirectional. Ta symbolika może pomieścić do 14 znaków numerycznych, co czyni ją idealną dla kodów GTIN‑14.

## Krok 3: Ustaw wymiar X (szerokość modułu)

Wymiar X kontroluje szerokość najmniejszego słupka (modułu). Zbyt mała wartość może źle wyglądać na drukarkach o niskiej rozdzielczości, natomiast zbyt duża może przekroczyć dostępne miejsce na etykiecie.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Wskazówka:** Właściwość `Pixels` jest wygodna do testów na ekranie. W scenariuszach skupionych na druku użyj `generator.Parameters.Barcode.XDimension.Millimeters`.

## Krok 4: Dostosuj współczynnik proporcji i zapisz pierwszy obraz

**Współczynnik proporcji** wpływa na stosunek wysokości do szerokości kodu kreskowego typu stacked. Typ DataBar Stacked Omnidirectional obsługuje proporcje od 10 do 30. Wygenerujemy dwa obrazy, aby zobrazować wpływ wizualny.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Wywołanie `generator.Save` zapisuje plik **PNG** w bieżącym katalogu roboczym. Wyliczenie `BarCodeImageFormat.Png` zapewnia bezstratną kompresję, co jest idealne do dalszego przetwarzania lub osadzania w plikach PDF.

## Krok 5: Zmień współczynnik proporcji na 30 i zapisz drugi obraz

Teraz zwiększamy wysokość słupków stacked, zmieniając współczynnik proporcji na **30**. To sprawia, że kod kreskowy jest wyższy bez zmiany wymiaru X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Uruchomienie programu teraz generuje dwa pliki PNG:

* **DatabarAspectRatio15.png** – kompaktowy kod kreskowy odpowiedni dla małych etykiet.
* **DatabarAspectRatio30.png** – wyższy kod kreskowy, który zwiększa niezawodność skanowania na powierzchniach o niskim kontraście.

Możesz otworzyć obrazy w dowolnym przeglądarce, aby zweryfikować, że słupki są prawidłowo ułożone i że zakodowane dane odpowiadają oryginalnemu ciągowi GS1.

## Krok 6: Zweryfikuj zakodowaną wartość (opcjonalnie)

Jeśli musisz potwierdzić, że kod kreskowy rzeczywiście odzwierciedla wprowadzony ciąg, możesz go odkodować przy użyciu tej samej biblioteki:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Dekoder powinien zwrócić `(01)12345678901231`, co dowodzi, że proces **create databar stacked barcode** zachował dane.

## Typowe pułapki i jak ich unikać

| Problem | Dlaczego się dzieje | Rozwiązanie |
|-------|----------------|-----|
| Kod kreskowy jest rozmyty | Wymiar X ustawiony zbyt nisko dla rozdzielczości wyjściowej | Zwiększ `XDimension.Pixels` lub użyj `Millimeters` dla druku |
| Skaner zgłasza „symbol nie znaleziony” | Współczynnik proporcji poza obsługiwanym zakresem 10‑30 | Utrzymuj proporcję w przedziale 10‑30; 15 i 30 są bezpiecznymi wartościami domyślnymi |
| Plik PNG zawiera znak wodny | Używanie darmowej licencji ewaluacyjnej Aspose.BarCode | Kup pełną licencję lub użyj wersji próbnej wyłącznie do testów |
| Dekodowanie nie powodzi się na drugim obrazie | Dekoder został skonfigurowany dla niewłaściwej symboliki | Użyj `DecodeType.DatabarStackedOmniDirectional` przy odczycie kodów stacked |

## Kolejne kroki

Teraz, gdy możesz **create databar stacked barcode** obrazy, możesz chcieć:

* **Osadź pliki PNG w fakturach PDF** przy użyciu biblioteki PDF, takiej jak **Aspose.PDF**.
* **Generuj kody kreskowe w locie w API webowym** – zwracaj bajty PNG bezpośrednio z kontrolera ASP.NET Core.
* **Eksperymentuj z innymi wariantami DataBar** (np. `DatabarExpanded`, `DatabarLimited`) zmieniając wyliczenie `EncodeTypes`.
* **Dostosuj kolory** ustawiając `generator.Parameters.Barcode.ForeColor` i `BackColor` dla projektów specyficznych dla marki.

Każdy z tych tematów opiera się na tych samych podstawowych koncepcjach omówionych tutaj: inicjalizacji `BarcodeGenerator`, konfigurowaniu parametrów wizualnych oraz zapisywaniu wyniku przy użyciu `BarCodeImageFormat`.

---

### Podsumowanie

Ten samouczek pokazał, jak **create databar stacked barcode** obrazy w C# przy użyciu Aspose.BarCode. Nauczyłeś się ustawiać **wymiar X**, modyfikować **współczynnik proporcji kodu kreskowego** oraz eksportować wynik jako pliki **PNG** przy użyciu `BarcodeGenerator`. Dzięki opcjonalnemu krokowi dekodowania możesz również zweryfikować, że zakodowane dane GS1 są poprawne. Zastosuj te wzorce w własnych aplikacjach do zarządzania zapasami, wysyłką lub sprzedażą detaliczną i odkryj liczne możliwości dostosowywania, które oferuje biblioteka. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Regulacja wysokości jednowymiarowego kodu Databar](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generowanie obrazu kodu kreskowego – Kupon GS1 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}