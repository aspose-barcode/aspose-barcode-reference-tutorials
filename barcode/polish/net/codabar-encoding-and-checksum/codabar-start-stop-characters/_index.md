---
date: 2026-01-04
description: Dowiedz się, jak generować kod kreskowy Codabar z znakami start i stop
  przy użyciu Aspose.BarCode dla .NET. Szczegółowy, krok po kroku, poradnik generowania
  kodów kreskowych dla programistów.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Generowanie kodu kreskowego Codabar z znakami start/stop w Aspose.BarCode dla
  .NET
url: /pl/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego Codabar ze znakami start/stop w Aspose.BarCode dla .NET

## Introduction

Witamy w tym obszernym przewodniku, jak **generować obrazy kodu kreskowego Codabar** ze znakami start/stop przy użyciu Aspose.BarCode dla .NET. Niezależnie od tego, czy tworzysz system inwentaryzacji detalicznej, śledzenie próbek laboratoryjnych czy rozwiązanie do rekordów medycznych, Codabar jest niezawodną symbologią numeryczną, która wymaga wyraźnych znaków start i stop dla dokładnego skanowania. W ciągu kilku minut przeprowadzimy Cię przez wszystko, co potrzebne — od wymagań wstępnych po zapisanie ostatecznych plików PNG — abyś mógł od razu rozpocząć tworzenie kodów kreskowych Codabar.

## Quick Answers
- **What library do I need?** Aspose.BarCode for .NET  
- **Which format can I save the barcode in?** PNG (BarCodeImageFormat.Png)  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Can I change the start/stop symbols?** Yes – use CodabarSymbol.A, B, C, or D.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prerequisites

Zanim zaczniemy, upewnijmy się, że masz wszystko, co potrzebne, aby podążać za tym samouczkiem:

1. **Environment Setup** – Make sure you have a working .NET development environment on your machine. If you need guidance, refer to the [documentation](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode for .NET Library** – Download and install the library from the official [source](https://releases.aspose.com/barcode/net/).  
3. **Basic .NET Knowledge** – Familiarity with C# and Visual Studio (or any preferred IDE) will make the steps smoother.  
4. **IDE** – Visual Studio, Rider, or Visual Studio Code are all fine.

Now that we’ve covered the prerequisites, let’s dive into the actual code.

## Import Namespaces

Aby rozpocząć pracę z Aspose.BarCode dla .NET, upewnij się, że zaimportowałeś niezbędną przestrzeń nazw:

```csharp
using Aspose.BarCode.Generation;
```

## How to generate codabar barcode – Step‑by‑Step Guide

### Step 1: Initialize the Barcode Generator

Utwórz instancję `BarcodeGenerator`, określ **Codabar** jako typ kodowania i podaj ciąg danych, który już zawiera znaki start/stop (np. “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro tip:** Myślnik (`-`) jest jednym z prawidłowych symboli start/stop dla Codabar. Możesz również użyć A, B, C lub D w zależności od wymagań aplikacji.

### Step 2: Set the X‑Dimension (barcode element width)

X‑Dimension kontroluje szerokość najwęższego słupka. Dostosuj ją do swojego środowiska skanowania.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why it matters:** Większa X‑Dimension poprawia czytelność na drukarkach o niskiej rozdzielczości, podczas gdy mniejsza wartość oszczędza miejsce na etykietach o wysokiej gęstości.

### Step 3: Define Start and Stop Characters

Codabar obsługuje cztery symbole start/stop (A, B, C, D). Poniżej znajdują się przykłady dla każdej opcji. Wybierz tę, która odpowiada specyfikacji systemu, z którym się integrujesz.

#### Setting Start A and Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Setting Start B and Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Setting Start C and Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Setting Start D and Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Możesz powtórzyć konfigurację dla każdego potrzebnego symbolu; poniższy przykład zapisuje cztery oddzielne obrazy — po jednym dla każdej pary start/stop.

### Step 4: Save the Generated Barcode Images (PNG)

Na koniec zapisz kod kreskowy do plików PNG. Demonstracja użycia **save barcode png** oraz dostarcza gotowe zasoby do testów.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Każdy plik zawiera teraz **przykład kodu kreskowego Codabar** z odpowiednimi znakami start/stop.

## Common Issues & Troubleshooting

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| Kod kreskowy wygląda zniekształcony | X‑Dimension zbyt niska dla wybranej rozdzielczości drukarki | Zwiększ `XDimension.Pixels` (np. do 3 lub 4) |
| Skaner nie odczytuje start/stop | Nieprawidłowy symbol start/stop dla docelowego systemu | Sprawdź wymagany symbol (A‑D) i ustaw go odpowiednio |
| Plik PNG jest pusty lub uszkodzony | Nieprawidłowa ścieżka wyjściowa lub niewystarczające uprawnienia do zapisu | Upewnij się, że `path` wskazuje istniejący folder i aplikacja ma dostęp do zapisu |

## Frequently Asked Questions

### Q1: What is Codabar, and why are start and stop characters important?

Codabar to numeryczna symbologia kodów kreskowych szeroko stosowana w inwentaryzacji, bibliotekach i opiece zdrowotnej. Znaki start i stop definiują granice kodu kreskowego, zapewniając skanerom wiedzę, gdzie dane się zaczynają i kończą.

### Q2: Can I customize the appearance of Codabar barcodes with Aspose.BarCode for .NET?

Tak. Oprócz X‑Dimension możesz zmieniać kolory, dodawać marginesy, a nawet osadzać kod kreskowy w formatach PDF lub SVG przy użyciu tego samego API.

### Q3: Are there any limitations to Codabar barcodes in terms of data encoding?

Codabar głównie obsługuje dane numeryczne (0‑9) oraz kilka znaków specjalnych. Nie jest przeznaczony do pełnych łańcuchów alfanumerycznych.

### Q4: Is Aspose.BarCode for .NET suitable for commercial use, and how can I obtain a license?

Tak, jest gotowy do produkcji. Kup licencję na [stronie zakupu Aspose](https://purchase.aspose.com/buy).

### Q5: Where can I seek help or discuss issues related to Aspose.BarCode for .NET?

Dołącz do społeczności na [forum wsparcia Aspose.BarCode dla .NET](https://forum.aspose.com/c/barcode/13), aby uzyskać pomoc od inżynierów Aspose oraz innych programistów.

---

**Ostatnia aktualizacja:** 2026-01-04  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}