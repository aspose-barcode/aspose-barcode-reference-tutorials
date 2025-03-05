---
title: Generuj kody kreskowe DataMatrix za pomocą Aspose.BarCode dla .NET
linktitle: Wersje DataMatrixa
second_title: Aspose.BarCode .NET API
description: Dowiedz się, jak generować kody kreskowe DataMatrix w .NET przy użyciu Aspose.BarCode dla .NET. Niestandardowe wymiary, obsługa ECC i wiele więcej.
type: docs
weight: 12
url: /pl/net/datamatrix-barcode-reading/datamatrix-versions/
---
Jeśli szukasz niezawodnego rozwiązania do generowania kodów kreskowych DataMatrix w aplikacjach .NET, Aspose.BarCode dla .NET jest właściwym wyborem. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces używania Aspose.BarCode dla .NET do tworzenia kodów kreskowych DataMatrix. Podzielimy każdy przykład na wiele kroków, dzięki czemu będziesz mógł z łatwością je wykonać.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:
- Środowisko programistyczne z obsługą .NET.
-  Kopia Aspose.BarCode dla .NET, z której możesz pobrać[ten link](https://releases.aspose.com/barcode/net/).
- Podstawowa znajomość C# i frameworka .NET.

Teraz przyjrzyjmy się wersji DataMatrix i sposobom ich generowania przy użyciu Aspose.BarCode dla .NET.

## Importuj przestrzenie nazw

W każdym projekcie C# istotne jest zaimportowanie niezbędnych przestrzeni nazw. W przypadku Aspose.BarCode musisz uwzględnić następujące informacje:

```csharp
using Aspose.BarCode.Generation;
```

 Ta przestrzeń nazw zapewnia dostęp do`BarcodeGenerator` class, która jest kluczowa przy generowaniu kodów kreskowych.

Podzielmy teraz przykład na wiele kroków.

## Krok 1: Skonfiguruj ścieżkę katalogu

Rozpocznij od zdefiniowania ścieżki katalogu, w którym chcesz zapisać wygenerowane kody kreskowe DataMatrix.

```csharp
string path = "Your Directory Path";
```

 Zastępować`"Your Directory Path"` z rzeczywistą ścieżką, w której chcesz zapisać obrazy kodów kreskowych.

## Krok 2: Zainicjuj generator kodów kreskowych

 Utwórz instancję`BarcodeGenerator` class i określ typ kodu kreskowego jako`DataMatrix`. Możesz także podać dane, które chcesz zakodować w kodzie kreskowym.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Tutaj znajduje się kod do generowania kodów kreskowych
}
```

## Krok 3: Skonfiguruj właściwości kodu kreskowego

Można dostosować różne właściwości kodu kreskowego DataMatrix, takie jak jego wymiary i typ ECC (kod korekcji błędów). Oto przykład ustawienia wymiaru X na 4 piksele i wybrania ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Krok 4: Ustaw wersję DataMatrix i zapisz

Wersję DataMatrix można określić, ustawiając liczbę wierszy i kolumn. Po skonfigurowaniu wersji zapisz obraz kodu kreskowego.

Na przykład, aby utworzyć kod kreskowy DataMatrix składający się z 22 wierszy i 22 kolumn przy użyciu ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Podobnie możesz wygenerować kod kreskowy o różnych parametrach, zmieniając w razie potrzeby wersję i typ ECC.

## Krok 5: Powtórz dla innych wersji

Możesz powtórzyć krok 4 dla innych wersji DataMatrix. Na przykład, aby utworzyć kod kreskowy składający się z 12 wierszy i 64 kolumn za pomocą ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Krok 6: Zmień typy ECC

Jeśli chcesz zmienić typ ECC na Ecc140, możesz to zrobić, aktualizując właściwość ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Krok 7: Wygeneruj kody kreskowe w różnych wersjach i ECC

Powtórz krok 4 dla innych wersji DataMatrix i typów ECC, zapisując każdy kod kreskowy z unikalną nazwą pliku.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Teraz, gdy już nauczyłeś się generować kody kreskowe DataMatrix przy użyciu Aspose.BarCode dla .NET, możesz łatwo zintegrować tę funkcjonalność z aplikacjami .NET.

## Wniosek

Aspose.BarCode dla .NET upraszcza proces generowania kodów kreskowych DataMatrix w aplikacjach .NET. Dzięki temu przewodnikowi krok po kroku możesz tworzyć kody kreskowe w różnych wersjach i typach ECC, oferując elastyczność i dostosowanie do konkretnych potrzeb.

 Jeśli masz jakieś pytania lub potrzebujesz pomocy, nie wahaj się odwiedzić[Aspose.BarCode dla dokumentacji .NET](https://reference.aspose.com/barcode/net/) lub sprawdź[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) dla wsparcia.

## Często zadawane pytania

### P1: Co to jest ECC w kodach kreskowych DataMatrix?

Odpowiedź 1: ECC (kod korekcji błędów) jest istotnym składnikiem kodów kreskowych DataMatrix, który pomaga zapewnić integralność danych. Różne poziomy ECC zapewniają różny stopień korekcji błędów.

### P2: Czy mogę generować kody kreskowe DataMatrix o niestandardowych wymiarach przy użyciu Aspose.BarCode dla .NET?

Odpowiedź 2: Tak, możesz dostosować wymiary kodów kreskowych DataMatrix, ustawiając liczbę wierszy i kolumn, jak pokazano w samouczku.

### P3: Gdzie mogę pobrać Aspose.BarCode dla .NET?

 A3: Możesz pobrać Aspose.BarCode dla .NET z[ten link](https://releases.aspose.com/barcode/net/).

### P4: Czy dostępna jest bezpłatna wersja próbna Aspose.BarCode dla .NET?

 O4: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.BarCode dla .NET[Tutaj](https://releases.aspose.com/).

### P5: Jak mogę uzyskać tymczasową licencję na Aspose.BarCode dla .NET?

 A5: Aby uzyskać tymczasową licencję na Aspose.BarCode dla .NET, odwiedź stronę[ten link](https://purchase.aspose.com/temporary-license/).