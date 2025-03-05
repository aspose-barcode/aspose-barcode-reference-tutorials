---
title: Tworzenie dodatkowych danych kodów kreskowych za pomocą Aspose.BarCode dla .NET
linktitle: Dodatkowa konfiguracja danych kodu kreskowego
second_title: Aspose.BarCode .NET API
description: Wygeneruj dodatkowe dane kodu kreskowego za pomocą Aspose.BarCode dla .NET. Dostosuj kody kreskowe EAN-2 i EAN-5 bez wysiłku. Przewodnik krok po kroku dla programistów .NET.
type: docs
weight: 10
url: /pl/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

W świecie generowania i dostosowywania kodów kreskowych Aspose.BarCode dla .NET wyróżnia się jako potężne i wszechstronne narzędzie. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku przeprowadzi Cię przez proces konfigurowania dodatkowych danych kodu kreskowego przy użyciu Aspose.BarCode dla .NET. 

## Warunki wstępne

Zanim zagłębimy się w świat dodatkowych danych z kodów kreskowych, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne skonfigurowane za pomocą programu Visual Studio lub dowolnego innego narzędzia programistycznego .NET.
-  Kopia Aspose.BarCode dla .NET. Jeśli jeszcze tego nie zrobiłeś, możesz go pobrać[Tutaj](https://releases.aspose.com/barcode/net/).
- Podstawowa znajomość programowania w języku C#.
- Katalog, w którym można zapisać wygenerowane obrazy kodów kreskowych.

## Importowanie przestrzeni nazw

Najpierw upewnij się, że masz niezbędne przestrzenie nazw zawarte w kodzie C#, aby móc pracować z Aspose.BarCode dla .NET. Zaimportuj wymagane przestrzenie nazw na początku pliku C#:

```csharp
using Aspose.BarCode.Generation;
```

Podzielmy teraz proces konfigurowania dodatkowych danych kodu kreskowego na wiele kroków.

## Krok 1: Konfigurowanie ścieżki katalogu

 W kodzie C# zdefiniuj ścieżkę do katalogu, w którym chcesz zapisać wygenerowane obrazy kodów kreskowych. Zastępować`"Your Directory Path"` z rzeczywistą ścieżką katalogu.

```csharp
string path = "Your Directory Path";
```

## Krok 2: Tworzenie generatora kodów kreskowych

 Utwórz instancję`BarcodeGenerator` określając typ kodu kreskowego i dane, które chcesz zakodować. W tym przykładzie używamy kodu kreskowego EAN-13 z danymi „1234567890128”.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Krok 3: Dostosowywanie wymiarów kodu kreskowego

Ustaw wymiary kodu kreskowego, takie jak wymiar X (szerokość najmniejszego elementu w kodzie kreskowym) i odstęp dodatkowy. W tym przykładzie ustawiliśmy wymiar X na 2 piksele, a dodatkową przestrzeń na 20 pikseli.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Krok 4: Konfiguracja dodatku EAN-2

Aby skonfigurować dodatkowy kod kreskowy EAN-2, ustaw dane dodatkowe na żądaną wartość. W tym przypadku ustawiliśmy go na „12”. 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Krok 5: Zapisywanie obrazu kodu kreskowego

Zapisz wygenerowany obraz kodu kreskowego w określonym katalogu pod znaczącą nazwą. W tym przykładzie zapisujemy dodatkowy kod kreskowy EAN-2 jako „SupplementEAN2.png”.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Krok 6: Konfiguracja dodatku EAN-5

 Aby skonfigurować dodatkowy kod kreskowy EAN-5, wystarczy zmienić`SupplementData` do żądanej wartości. Tutaj ustawiliśmy go na „12345”.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Krok 7: Zapisywanie obrazu kodu kreskowego (EAN-5)

Na koniec zapisz obraz dodatkowego kodu kreskowego EAN-5 we wskazanym katalogu. W tym przypadku zapisujemy go jako „SuplementEAN5.png”.

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Teraz pomyślnie skonfigurowałeś i wygenerowałeś dodatkowe dane kodu kreskowego przy użyciu Aspose.BarCode dla .NET. Można zastosować tę metodę do tworzenia szerokiej gamy typów kodów kreskowych z różnymi danymi dodatkowymi.

## Wniosek

Aspose.BarCode dla .NET to potężne narzędzie do generowania i dostosowywania kodów kreskowych. W tym przewodniku przeszliśmy krok po kroku przez proces konfigurowania i generowania dodatkowych danych kodu kreskowego. Dzięki odpowiednim wymaganiom wstępnym i odrobinie kodowania możesz wydajnie pracować z danymi kodów kreskowych i spełniać swoje specyficzne potrzeby.

 Aby uzyskać więcej informacji i zaawansowane użytkowanie, zapoznaj się z sekcją[Aspose.BarCode dla dokumentacji .NET](https://reference.aspose.com/barcode/net/).

## Często Zadawane Pytania

### Czy mogę używać Aspose.BarCode dla .NET w moim projekcie .NET Core?
Tak, Aspose.BarCode dla .NET jest kompatybilny z .NET Core.

### Czy dostępna jest bezpłatna wersja próbna Aspose.BarCode dla .NET?
 Tak, możesz wypróbować bezpłatnie odwiedzając stronę[ten link](https://releases.aspose.com/).

### Gdzie mogę uzyskać tymczasową licencję na Aspose.BarCode dla .NET?
 Licencję tymczasową można uzyskać od[ten link](https://purchase.aspose.com/temporary-license/).

### Czy Aspose.BarCode obsługuje szeroką gamę typów kodów kreskowych?
Tak, obsługuje różne typy kodów kreskowych, w tym EAN-13, kod QR, kod 128 i inne.

### Czy mogę dostosować wygląd generowanych kodów kreskowych?
Oczywiście możesz dostosować wymiary, kolory i inne aspekty kodów kreskowych, aby spełnić Twoje wymagania.
