---
category: general
date: 2026-07-15
description: Szybko utwórz kod pocztowy w C#. Ten przykład generatora kodów kreskowych
  pokazuje, jak wyeksportować kod kreskowy w formacie PNG dla kodów Planet i RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: pl
lastmod: 2026-07-15
og_description: Utwórz kod pocztowy w C# za pomocą tego przewodnika krok po kroku.
  Poznaj przykład generatora kodów kreskowych, który umożliwia eksport obrazu kodu
  kreskowego w formacie PNG.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Stwórz kod pocztowy w C# – Kompletny przewodnik generatora
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Tworzenie kodu kreskowego pocztowego w C# – pełny przykład generatora
url: /pl/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utworzenie kodu pocztowego w C# – Pełny przykład generatora

Zastanawiałeś się kiedyś, jak **utworzyć kod pocztowy** w projekcie .NET, nie przeszukując niekończącej się dokumentacji? Nie jesteś sam. Niezależnie od tego, czy budujesz system etykiet pocztowych, czy automatyzujesz masową wysyłkę, generowanie czystego pliku PNG z kodem kreskowym to niezbędna umiejętność. W tym samouczku przeprowadzimy Cię przez kompletny **przykład generatora kodów kreskowych**, który dokładnie pokazuje, jak **wyeksportować obraz kodu kreskowego** w **formacie PNG**.

Omówimy wszystko, od konfiguracji katalogu wyjściowego po dostosowanie szerokości modułu i wysokości pasków dla standardów Planet i RM4SCC. Na koniec będziesz mieć gotową aplikację konsolową, która wygeneruje cztery pliki PNG — dwa z automatyczną wysokością i dwa o stałej wysokości 100 px. Bez zbędnych dodatków, tylko praktyczne rozwiązanie, które możesz skopiować i wkleić.

## Wymagania wstępne

- .NET 6 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
- IDE lub edytor, z którym czujesz się komfortowo (Visual Studio, VS Code, Rider…)
- Pakiet NuGet Aspose.BarCode for .NET (instaluj za pomocą `dotnet add package Aspose.BarCode`)

To wszystko — bez dodatkowych usług, bez interfejsów API webowych. Po prostu lokalny projekt C#.

## Utworzenie kodu pocztowego – krok po kroku

Poniżej dzielimy proces na pięć przejrzystych kroków. Każdy krok ma opisowy nagłówek **H2**, który zawiera główne lub drugorzędowe słowo kluczowe, dzięki czemu szybko znajdziesz to, czego potrzebujesz.

### Krok 1: Przygotowanie katalogu wyjściowego

Najpierw potrzebujemy folderu, w którym będą przechowywane wygenerowane pliki PNG. Hard‑kodowanie ścieżki działa w demonstracji, ale w produkcji prawdopodobnie odczytasz ją z konfiguracji.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Wskazówka:** Użycie `Path.Combine` sprawia, że kod jest niezależny od systemu operacyjnego, a `Directory.CreateDirectory` można wywołać bezpiecznie, nawet jeśli folder już istnieje.

### Krok 2: Generowanie kodu Planet z automatyczną wysokością

Teraz przechodzimy do sedna części **jak wygenerować kod Planet**. Tworzymy instancję `BarcodeGenerator`, ustawiamy szerokość modułu (X‑dimension) i pozwalamy bibliotece określić wysokość pasków.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Enum `EncodeTypes.Planet` informuje Aspose, że chcemy symbologię Planet, powszechną w usługach pocztowych wielu krajów. Ponieważ nie modyfikujemy `BarHeight`, generator wybiera rozsądny domyślny rozmiar, który zapewnia czytelność kodu.

### Krok 3: Generowanie kodu RM4SCC z automatyczną wysokością

RM4SCC to kanadyjski format kodu pocztowego. Kod jest lustrzanym odbiciem przykładu Planet, co ilustruje wzorzec **przykładu generatora kodów kreskowych**, który możesz ponownie wykorzystać dla dowolnej obsługiwanej symbologii.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Ponownie polegamy na automatycznej wysokości, co jest idealne dla szybkich prototypów lub gdy drukarka sama zajmuje się skalowaniem.

### Krok 4: Generowanie kodu Planet o stałej wysokości (100 px)

Czasami system pocztowy wymaga ścisłej wysokości pasków — być może drukarka oczekuje dokładnie 100 px. Oto jak **wyeksportować obraz kodu kreskowego** z wymuszoną wysokością.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Ustawienie `BarHeight.Pixels` nadpisuje automatyczne obliczenia. Pozostałe ustawienia pozostają niezmienione, zapewniając spójność wizualną między obrazami automatycznymi i o stałej wysokości.

### Krok 5: Generowanie kodu RM4SCC o stałej wysokości (100 px)

Powtarzamy podejście ze stałą wysokością dla RM4SCC. To pokazuje elastyczność **przykładu generatora kodów kreskowych**: możesz mieszać i dopasowywać ustawienia automatyczne i ręczne dla każdej symbologii.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Pełny listing źródłowy

Łącząc wszystko razem, oto kompletny, gotowy do uruchomienia program. Skopiuj poniższy blok do nowego projektu konsolowego i naciśnij **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

Uruchomienie tego programu tworzy następujące pliki (wszystkie w **formacie PNG**):

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Każdy obraz to wyraźna, czarno‑biała reprezentacja gotowa do druku lub dalszego przetwarzania.

## Dlaczego to podejście działa

- **Spójność:** Ustawiając `XDimension.Pixels` na 4 we wszystkich kodach, zapewniasz tę samą szerokość modułu, co jest kluczowe dla skanerów oczekujących określonego rozmiaru kropki.
- **Elastyczność:** Ta sama baza kodu pozwala przełączać się między automatyczną a stałą wysokością bez przepisywania logiki generatora — idealne dla rozwiązań wielokurierowych.
- **Wydajność:** Generowanie PNG to lekka operacja; biblioteka Aspose strumieniuje obraz bezpośrednio na dysk, unikając niepotrzebnego obciążenia pamięci.
- **Przenośność:** Wywołania `Path.Combine` i `Directory.CreateDirectory` utrzymują kod wieloplatformowy, więc ten sam kod działa na Windows, Linux i macOS.

## Typowe pułapki i jak ich unikać

| Problem | Dlaczego się pojawia | Rozwiązanie |
|------|----------------|-----|
| Kod kreskowy jest rozmyty | Użycie bardzo niskiego X‑dimension (np. 1 px) | Zwiększ `XDimension.Pixels` do co najmniej 3‑4 dla kodów pocztowych |
| Skaner odrzuca obraz | Wysokość paska jest za mała lub za duża dla drukarki | Użyj `BarHeight.Pixels`, aby dopasować do specyfikacji drukarki |
| Plik PNG jest uszkodzony | Zapomniano zamknąć strumień (rzadko w Aspose) | Pozwól metodzie `Save` obsłużyć zwolnienie zasobów; unikaj ręcznego zarządzania strumieniem, chyba że jest to konieczne |
| Folder wyjściowy nie został znaleziony | Ścieżka zakodowana na stałe wskazuje nieistniejący katalog | Zawsze wywołuj `Directory.CreateDirectory` przed zapisem |

## Rozszerzanie przykładu

Teraz, gdy opanowałeś podstawy **tworzenia kodu pocztowego**, możesz rozważyć:

- **Dodawanie tekstu czytelnego dla człowieka** pod kodem kreskowym (`DisplayText` property)
- **Zmiana kolorów** (`ForeColor`, `BackColor`) w celu brandingu
- **Przetwarzanie wsadowe** listy kodów pocztowych w formacie CSV (pętla po generatorze)
- **Eksport do innych formatów**, takich jak SVG lub PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Każde z tych rozszerzeń podąża tym samym wzorcem, który został pokazany w tym **przykładzie generatora kodów kreskowych**, więc możesz eksperymentować bez konieczności zaczynania od zera.

## Podsumowanie

Ty

## Co warto nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obraz kodu kreskowego C# – Przykład GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Jak utworzyć rozszerzony kod tekstowy dotcode przy użyciu Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Jak utworzyć kod Aztec z korekcją błędów w .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}