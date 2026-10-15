---
category: general
date: 2026-10-08
description: Dowiedz się, jak tworzyć obraz kodu kreskowego w C# i odkryj, jak dostosować
  współczynnik proporcji dla składanych, wielokierunkowych kodów DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: pl
lastmod: 2026-10-08
og_description: Utwórz obraz kodu kreskowego w C# i dowiedz się, jak dostosować proporcje
  dla kodów DataBar stacked wszechkierunkowych, korzystając z pełnego przykładu kodu.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Tworzenie obrazu kodu kreskowego w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak utworzyć obraz kodu kreskowego i dostosować jego proporcje w C#
url: /pl/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego i dostosować jego proporcje w C#

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** programowo, ten przewodnik pokazuje kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz dokładnie **jak dostosować proporcje** dla kodu DataBar stacked omni‑directional, co jest częstym wymogiem w aplikacjach detalicznych i logistycznych.

W tym tutorialu dowiesz się, jak:
* Zainicjalizować `BarcodeGenerator` z biblioteki Aspose.BarCode dla symbologii DataBar stacked omni‑directional.  
* Ustawić wymiar X (szerokość modułu) w pikselach, aby kontrolować grubość pasków.  
* Zastosować dwa różne współczynniki proporcji i zapisać każdy wynik jako plik PNG.  
* Zweryfikować wynik i zrozumieć, dlaczego proporcje mają znaczenie.

Nie są wymagane żadne zewnętrzne narzędzia — wystarczy biblioteka Aspose.BarCode for .NET oraz środowisko programistyczne .NET 6 (lub nowsze).

## Jak utworzyć obraz kodu kreskowego przy użyciu Aspose.BarCode

Pierwszym krokiem jest utworzenie generatora z żądaną symbologią i ciągiem danych. Enum `EncodeTypes.DatabarStackedOmniDirectional` informuje Aspose.BarCode, aby wygenerował kod DataBar stacked omni‑directional, szeroko stosowany w aplikacjach GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Dlaczego to ważne:** Obiekt `BarcodeGenerator` jest punktem wejścia dla wszystkich zadań związanych z tworzeniem kodów kreskowych. Określając symbologię i surowe dane od razu, zapewniasz, że wygenerowany obraz spełnia standard GS1.

## Ustawianie wymiaru X (szerokość modułu)

Wymiar X definiuje szerokość najcieńszego paska (modułu). Większy wymiar X daje grubszą etykietę, co może być przydatne przy drukarkach o niskiej rozdzielczości.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to ważne:** Regulacja wymiaru X jest częścią procesu strojenia wizualnego. Nie wpływa ona na zakodowane dane, ale ma wpływ na niezawodność skanowania na różnych urządzeniach.

## Jak dostosować proporcje – pierwsza wersja (15)

Proporcje kontrolują stosunek wysokości do szerokości kodu DataBar. Właściwość `DataBar.AspectRatio` przyjmuje wartości całkowite; większe liczby powodują wyższe paski.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Dlaczego to ważne:** Proporcja 15 jest powszechnym domyślnym ustawieniem dla skanerów detalicznych. Powstały plik PNG (`DatabarAspectRatio15.png`) będzie miał wyższy wygląd, co może zwiększyć skuteczność skanowania na urządzeniach ręcznych.

## Jak dostosować proporcje – druga wersja (30)

Możesz potrzebować wyższego kodu dla konkretnych formatów etykiet. Zmiana proporcji jest tak prosta, jak przypisanie nowej wartości całkowitej przed ponownym wywołaniem `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to ważne:** Demonstracja **jak dostosować proporcje** pozwala generować wiele obrazów kodów kreskowych z tego samego źródła danych bez ponownego tworzenia generatora. To zmniejsza zużycie pamięci i przyspiesza przetwarzanie wsadowe.

### Oczekiwany wynik

Po uruchomieniu programu znajdziesz dwa pliki PNG w katalogu wykonawczym:

| Nazwa pliku                     | Proporcja | Opis wizualny |
|---------------------------------|-----------|----------------|
| `DatabarAspectRatio15.png`      | 15        | Standardowa wysokość, odpowiednia dla większości skanerów przy kasie. |
| `DatabarAspectRatio30.png`      | 30        | Wyższe paski, przydatne przy dużych etykietach lub drukarkach o niskiej rozdzielczości. |

Oba obrazy zawierają ten sam zakodowany GTIN `(01)12345678901231`, ale ich proporcje wizualne różnią się w zależności od ustawionej proporcji.

## Częste pytania i obsługa przypadków brzegowych

### Co zrobić, jeśli potrzebuję innego wymiaru X?

Możesz zmienić `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` na dowolną liczbę całkowitą większą od zera. Dla bardzo wysokiej rozdzielczości (np. 300 dpi) wartość 3‑4 piksele często daje wyraźniejsze rezultaty.

### Jak wybrać właściwą proporcję?

Optymalna proporcja zależy od środowiska skanowania:
* **Etykiety niskoprofilowe** – użyj mniejszej proporcji (np. 10‑15), aby kod był kompaktowy.  
* **Duże kontenery transportowe** – wyższa proporcja (np. 25‑35) poprawia czytelność z większej odległości.  
* **Wymagania regulacyjne** – niektóre normy nakładają minimalną wysokość; sprawdź specyfikację GS1, aby poznać dokładne liczby.

### Czy mogę generować inne formaty kodów kreskowych przy użyciu tego samego kodu?

Tak. Zamień `EncodeTypes.DatabarStackedOmniDirectional` na dowolną inną wartość `EncodeTypes` (np. `EncodeTypes.Code128`). Reszta kodu – wymiar X, proporcja (jeśli ma zastosowanie) i zapisywanie – pozostaje bez zmian.

### Co zrobić, jeśli potrzebuję utworzyć obraz w innym formacie?

`BarCodeImageFormat` obsługuje PNG, JPEG, BMP, GIF oraz TIFF. Wystarczy zmienić drugi argument metody `Save`, na przykład:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Pro tip: ponowne użycie generatora przy przetwarzaniu wsadowym

Gdy musisz utworzyć dziesiątki kodów kreskowych o tych samych ustawieniach wizualnych, zainicjalizuj generator raz, aktualizuj jedynie właściwość `CodeText` i wywołuj `Save` wielokrotnie. Dzięki temu unikniesz kosztów związanych z wielokrotnym alokowaniem wewnętrznych buforów.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Podsumowanie

Teraz wiesz, jak **utworzyć obraz kodu kreskowego** w C# przy użyciu Aspose.BarCode oraz **jak precyzyjnie dostosować proporcje** dla symboli DataBar stacked omni‑directional. Kontrolując wymiar X i proporcje, możesz tworzyć kody spełniające dowolne wymagania skanowania lub układu, zachowując prostą i łatwą w utrzymaniu implementację.

### Kolejne kroki

* Eksploruj inne symbologie, takie jak **Code128** czy **QR Code**, zamieniając wartość `EncodeTypes`.  
* Połącz generowanie kodów kreskowych z tworzeniem PDF (np. przy użyciu Aspose.PDF), aby osadzać kody bezpośrednio w fakturach.  
* Eksperymentuj z dynamicznym doborem proporcji w zależności od rozmiaru etykiety — to rozszerza wzorzec **jak dostosować proporcje** do pełnoprawnego silnika projektowania etykiet.

Śmiało dostosowuj przykład, dziel się wynikami lub zadawaj pytania w komentarzach. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}