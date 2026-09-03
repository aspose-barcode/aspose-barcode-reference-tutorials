---
date: 2026-05-24
description: Dowiedz się, jak utworzyć kod kreskowy Codabar ze znakami początkowymi
  i końcowymi przy użyciu Aspose.BarCode dla .NET. Szczegółowy samouczek generowania
  kodów kreskowych krok po kroku dla programistów.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar – znaki początkowe/końcowe
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Utwórz kod kreskowy Codabar z znakami początkowymi/końcowymi w Aspose.BarCode
  dla .NET
url: /pl/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy Codabar ze znakami start/stop w Aspose.BarCode dla .NET

## Wprowadzenie

W tym samouczku **utworzysz obrazy kodu kreskowego Codabar**, które zawierają wyraźne znaki start/stop przy użyciu Aspose.BarCode dla .NET. Niezależnie od tego, czy budujesz system zarządzania zapasami w handlu detalicznym, śledzenie próbek laboratoryjnych, czy rozwiązanie do rekordów medycznych, numeryczna symbologia Codabar opiera się na tych znakach granicznych, aby zapewnić niezawodne skanowanie. W ciągu kilku kolejnych minut omówimy wszystko, od konfiguracji środowiska po zapisywanie plików PNG, abyś mógł od razu rozpocząć generowanie kodów kreskowych Codabar.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode dla .NET  
- **W jakim formacie mogę zapisać kod kreskowy?** PNG (`BarCodeImageFormat.Png`)  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić znaki start/stop?** Tak – użyj `CodabarSymbol.A`, `B`, `C` lub `D`.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Czym jest Codabar i dlaczego znaki start/stop są niezbędne?

Codabar to numeryczna symbologia kodów kreskowych szeroko stosowana w bibliotekach, opiece zdrowotnej i zarządzaniu zapasami. Znaki start i stop (A‑D lub myślnik) definiują granice kodu, umożliwiając skanerom wykrycie, gdzie dane się zaczynają i kończą, z dokładnością odczytu 99,9 %.

## Dlaczego używać Aspose.BarCode dla .NET?

Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i może generować obrazy do **10 000 × 10 000 px** bez ładowania całego dokumentu do pamięci. Działa na Windows, Linux i macOS oraz jest kompatybilny z .NET Framework, .NET Core i .NET 5+, co daje elastyczność na wszystkich nowoczesnych platformach.

## Wymagania wstępne

1. **Konfiguracja środowiska** – Upewnij się, że masz działające środowisko programistyczne .NET. Jeśli potrzebujesz wskazówek, odwołaj się do [dokumentacji](https://reference.aspose.com/barcode/net/).  
2. **Biblioteka Aspose.BarCode dla .NET** – Pobierz i zainstaluj bibliotekę z oficjalnego [źródła](https://releases.aspose.com/barcode/net/).  
3. **Podstawowa znajomość .NET** – Znajomość C# oraz IDE, takiego jak Visual Studio, Rider lub VS Code.  
4. **IDE** – Visual Studio, Rider lub Visual Studio Code są w pełni wystarczające.

Teraz, gdy omówiliśmy wymagania wstępne, przejdźmy do właściwego kodu.

## Jak wygenerować kod kreskowy Codabar ze znakami start/stop?

Załaduj `BarcodeGenerator`, ustaw typ kodowania na **Codabar** i przekaż ciąg danych, który już zawiera wymagane znaki start/stop (np. „-12345-”). Następnie skonfiguruj X‑Dimension, opcjonalnie wybierz inny znak start/stop i na końcu zapisz obraz jako PNG. Ten kompletny przepływ tworzy gotowy do użycia kod kreskowy w kilku linijkach C#.

### Importowanie przestrzeni nazw

`BarcodeGenerator` i powiązane typy znajdują się w przestrzeni nazw `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Krok 1: Inicjalizacja generatora kodu kreskowego

`BarcodeGenerator` jest podstawową klasą tworzącą obrazy kodów kreskowych. Przyjmuje typ symbologii oraz ciąg danych jako argumenty konstruktora.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Porada:** Myślnik (`-`) jest jednym z prawidłowych znaków start/stop dla Codabar. Możesz także użyć `A`, `B`, `C` lub `D` w zależności od wymagań aplikacji.

### Krok 2: Ustaw X‑Dimension (szerokość elementu kodu kreskowego)

`XDimension` kontroluje szerokość najcieńszego paska. Większe wartości poprawiają czytelność na drukarkach o niskiej rozdzielczości, natomiast mniejsze wartości oszczędzają miejsce na etykietach o wysokiej gęstości.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dlaczego to ważne:** Dostosowanie `XDimension` pomaga spełnić specyfikacje skanerów, które często wymagają minimalnej szerokości paska wynoszącej 0,25 mm.

### Krok 3: Definiowanie znaków start i stop

Codabar obsługuje cztery znaki start/stop (A, B, C, D). Poniżej znajdują się przykłady dla każdej opcji. Wybierz ten, który odpowiada specyfikacji systemu, z którym się integrujesz.

#### Ustawianie Start A i Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Ustawianie Start B i Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Ustawianie Start C i Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Ustawianie Start D i Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Możesz powtórzyć konfigurację dla każdego potrzebnego symbolu; poniższy przykład zapisuje cztery osobne obrazy — po jednym dla każdej pary start/stop.

### Krok 4: Zapis wygenerowanych obrazów kodu kreskowego (PNG)

`Save` zapisuje kod kreskowy do pliku. Użycie `BarCodeImageFormat.Png` tworzy bezstratne obrazy PNG, idealne do zastosowań internetowych i drukowanych.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Każdy plik zawiera teraz **przykład kodu kreskowego Codabar** z odpowiednimi znakami start/stop.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| Kod kreskowy wygląda na zniekształcony | X‑Dimension zbyt niska dla wybranej rozdzielczości drukarki | Zwiększ `XDimension.Pixels` (np. do 3 lub 4) |
| Skaner nie odczytuje start/stop | Nieprawidłowy znak start/stop dla docelowego systemu | Zweryfikuj wymagany znak (A‑D) i ustaw go odpowiednio |
| Plik PNG jest pusty lub uszkodzony | Nieprawidłowa ścieżka wyjściowa lub niewystarczające uprawnienia do zapisu | Upewnij się, że `path` wskazuje istniejący folder i aplikacja ma prawo zapisu |

## Najczęściej zadawane pytania

**Q1: Co to jest Codabar i dlaczego znaki start i stop są ważne?**  
A: Codabar to numeryczna symbologia kodów kreskowych używana w zarządzaniu zapasami, bibliotekach i opiece zdrowotnej. Znaki start/stop definiują granice kodu, zapewniając, że skanery wiedzą, gdzie dane się zaczynają i kończą.

**Q2: Czy mogę dostosować wygląd kodów kreskowych Codabar przy użyciu Aspose.BarCode dla .NET?**  
A: Tak. Poza X‑Dimension możesz zmieniać kolory, dodawać marginesy oraz eksportować do PDF lub SVG przy użyciu tego samego API.

**Q3: Czy istnieją ograniczenia kodów kreskowych Codabar pod względem kodowania danych?**  
A: Codabar głównie obsługuje dane numeryczne (0‑9) oraz ograniczony zestaw znaków specjalnych. Nie nadaje się do pełnych ciągów alfanumerycznych.

**Q4: Czy Aspose.BarCode dla .NET nadaje się do użytku komercyjnego i jak mogę uzyskać licencję?**  
A: Tak, jest gotowy do produkcji. Zakup licencję na [stronie zakupu Aspose](https://purchase.aspose.com/buy).

**Q5: Gdzie mogę uzyskać pomoc lub dyskutować problemy związane z Aspose.BarCode dla .NET?**  
A: Dołącz do społeczności na [forum wsparcia Aspose.BarCode dla .NET](https://forum.aspose.com/c/barcode/13), gdzie pomogą zarówno inżynierowie Aspose, jak i inni programiści.

---

**Ostatnia aktualizacja:** 2026-05-24  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Znaki start/stop i suma kontrolna Codabar](/barcode/net/codabar-encoding-and-checksum/)
- [Jak dodać sumę kontrolną do kodów Codabar przy użyciu Aspose.BarCode dla .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Kompleksowe samouczki i przykłady Aspose.BarCode dla .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}