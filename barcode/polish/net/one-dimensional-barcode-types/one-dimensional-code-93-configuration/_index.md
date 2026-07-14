---
date: 2026-02-25
description: Dowiedz się, jak generować obraz kodu kreskowego i zapisywać go jako
  PNG przy użyciu Aspose.BarCode dla .NET – kompletny przykład Aspose Barcode.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Generuj obraz kodu kreskowego – Code 93 z Aspose.BarCode
url: /pl/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

 answer with only translated content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generuj obraz kodu kreskowego – jednowymiarowy Code 93 z Aspose.BarCode

## Wprowadzenie

W dzisiejszej erze cyfrowej kody kreskowe stały się nieodłączną częścią naszego życia, upraszczając procesy takie jak zarządzanie zapasami, etykietowanie produktów i śledzenie przy kasie. **Generowanie obrazu kodu kreskowego** jest często pierwszym krokiem w integrowaniu tych identyfikatorów w aplikacjach. Aspose.BarCode for .NET udostępnia solidne, łatwe w użyciu API, które pozwala tworzyć wysokiej jakości kody Code 93 w zaledwie kilku linijkach kodu C#. Niezależnie od tego, czy tworzysz system magazynowy, aplikację detaliczną, czy własne narzędzie raportowe, ten tutorial przeprowadzi Cię przez kompletny **aspose barcode example**, pokazując jak generować, dostosowywać i **zapisywać pliki PNG kodu kreskowego**.

## Szybkie odpowiedzi
- **Co obejmuje tutorial?** Tworzenie i zapisywanie obrazu kodu kreskowego Code 93 z obsługą sumy kontrolnej.  
- **Jakiej biblioteki użyto?** Aspose.BarCode for .NET (najnowsze stabilne wydanie).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w trakcie rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić format wyjściowy?** Tak – możesz zapisać jako PNG, JPEG, BMP itd., zmieniając `BarCodeImageFormat`.  
- **Jakie są minimalne wymagania?** .NET Framework 4.6+ lub .NET Core 3.1+ oraz Visual Studio.

## Czym jest kod kreskowy Code 93?
Code 93 to symbologia o wysokiej gęstości, alfanumeryczna, obsługująca pełny zestaw znaków ASCII. Często wybierana ze względu na kompaktowy rozmiar i wbudowaną sumę kontrolną, co pomaga zapewnić integralność danych podczas skanowania.

## Dlaczego generować obrazy kodów kreskowych przy użyciu Aspose.BarCode?
- **Pełna kontrola** nad typem kodowania, sumą kontrolną, rozmiarem i formatem obrazu.  
- **Brak zewnętrznych zależności** – biblioteka działa na każdej platformie .NET.  
- **Doskonała jakość renderowania**, odpowiednia zarówno do wyświetlania na ekranie, jak i druku w wysokiej rozdzielczości.  
- **Kompleksowa dokumentacja** oraz duży zestaw przykładów przyspieszających rozwój.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz następujące elementy:

1. **Visual Studio** (dowolna aktualna edycja).  
2. **Aspose.BarCode for .NET** zainstalowany – możesz go pobrać ze strony oficjalnej.  
3. Podstawowa znajomość **C#** oraz struktury projektu .NET.

Teraz, gdy wszystko jest gotowe, przejdźmy do przewodnika krok po kroku.

## Importowanie przestrzeni nazw

Najpierw zaimportuj wymagane przestrzenie nazw, aby uzyskać dostęp do klas generowania kodów kreskowych.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Krok 1: Ustaw ścieżkę katalogu

Określ, gdzie zostanie zapisany wygenerowany obraz kodu kreskowego. Zastąp placeholder prawidłowym folderem na swoim komputerze.

```csharp
string path = "Your Directory Path";
```

## Krok 2: Utwórz jednowymiarowy kod kreskowy Code 93

Utwórz instancję `BarcodeGenerator` z typem `Code93Extended` oraz danymi, które chcesz zakodować.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Krok 3: Włącz sumę kontrolną (opcjonalnie)

Code 93 zawiera sumę kontrolną domyślnie. Możesz ją włączyć/wyłączyć przy użyciu właściwości `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Krok 4: Zapisz obraz kodu kreskowego (Zapisz Barcode PNG)

Wygeneruj obraz i zapisz go jako plik PNG w folderze określonym wcześniej.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Krok 5: Obsługa wyjątków – generowanie bez sumy kontrolnej

Jeśli musisz utworzyć kod kreskowy **bez** sumy kontrolnej, musisz obsłużyć potencjalne wyjątki, które mogą wystąpić.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Typowe problemy i rozwiązania
- **Nieprawidłowa ścieżka** – upewnij się, że katalog istnieje i aplikacja ma uprawnienia do zapisu.  
- **Nieobsługiwane znaki** – Code 93 obsługuje pełny zestaw ASCII, ale znaki kontrolne mogą powodować błędy.  
- **Licencja nie ustawiona** – bez ważnej licencji biblioteka działa w trybie ewaluacyjnym i może dodać znak wodny.

## Najczęściej zadawane pytania (FAQ)

### P: Gdzie mogę znaleźć dokumentację Aspose.BarCode for .NET?
O: Dokumentację znajdziesz pod adresem [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### P: Jak pobrać Aspose.BarCode for .NET?
O: Aspose.BarCode for .NET możesz pobrać ze strony [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### P: Czy dostępna jest darmowa wersja próbna Aspose.BarCode for .NET?
O: Tak, darmową wersję próbną Aspose.BarCode for .NET możesz uzyskać [tutaj](https://releases.aspose.com/).

### P: Jak mogę kupić licencję na Aspose.BarCode for .NET?
O: Licencję możesz zakupić na stronie zakupu [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### P: Gdzie mogę uzyskać wsparcie lub zadać pytania dotyczące Aspose.BarCode for .NET?
O: Forum społecznościowe do wsparcia i dyskusji znajdziesz pod adresem [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}