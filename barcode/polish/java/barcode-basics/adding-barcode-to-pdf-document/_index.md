---
date: 2025-12-08
description: Dowiedz się, jak tworzyć dokumenty PDF w Javie i dodawać kody kreskowe
  za pomocą Aspose.BarCode. Przewodnik krok po kroku po generowaniu i osadzaniu kodów
  kreskowych w plikach PDF.
linktitle: Adding Barcode to PDF Document
second_title: Aspose.BarCode Java API
title: Jak utworzyć dokument PDF w Javie z kodem kreskowym przy użyciu Aspose.BarCode
url: /pl/java/barcode-basics/adding-barcode-to-pdf-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak stworzyć dokument PDF w Javie z kodem kreskowym przy użyciu Aspose.BarCode

## Introduction

Tworzenie dokumentów PDF w Javie zawierających kody kreskowe odczytywanych maszynowo jest powszechnym wymogiem w systemach inwentaryzacji, etykietach wysyłkowych i bezpiecznych przepływach dokumentów. W tym samouczku nauczysz się **jak tworzyć dokumenty PDF w Javie** i osadzać kod kreskowy bezpośrednio w pliku przy użyciu **Aspose.BarCode for Java**. Przejdziemy przez każdy krok — od generowania obrazu kodu kreskowego po wstawienie go do istniejącego PDF — abyś mógł dodać funkcję kodu kreskowego do swoich aplikacji Java w kilka minut.

## Quick Answers
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode for Java (plus Aspose.PDF do obsługi PDF).  
- **Czy mogę generować dowolny typ kodu kreskowego?** Tak — Aspose.BarCode obsługuje ponad 50 symbologii, w tym Code 39, QR, DataMatrix i inne.  
- **Czy potrzebuję licencji do rozwoju?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w produkcji.  
- **Czy kod jest kompatybilny z Java 8+?** Absolutnie — API jest przeznaczone dla Java 8 i nowszych.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego scenariusza „dodaj kod kreskowy do PDF”.

## Prerequisites

Zanim zaczniemy, upewnij się, że masz następujące elementy:

- **Java Development Kit (JDK)** — najnowsza stabilna wersja zainstalowana.  
- **Aspose.BarCode for Java** — pobierz ze [strony pobierania](https://releases.aspose.com/barcode/java/).  
- **Aspose.PDF for Java** — wymagane do manipulacji plikami PDF (dołączone do pakietu BarCode).

## Import Namespaces

Najpierw zaimportuj potrzebne klasy. Ten krok konfiguruje środowisko zarówno dla generowania kodów kreskowych, jak i manipulacji PDF.

```java
// Import Aspose.BarCode namespaces
import com.aspose.pdf.*;
import com.aspose.pdf.facades.*;

import com.aspose.barcode.generation.*;
import com.aspose.barcode.*;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.barcode.EncodeTypes;
```

## Step 1: Set Up Your Java Project

Utwórz nowy projekt Java w wybranym IDE (IntelliJ IDEA, Eclipse, NetBeans itp.). Dodaj pobrany **Aspose.BarCode.jar** (oraz jego zależności) do ścieżki kompilacji projektu. To zapewnia, że kompilator może znaleźć odwoływane klasy.

## Step 2: Generate Barcode Image – *how to add barcode*

Zainicjalizuj `BarcodeGenerator`, wybierz symbologię i ustaw tekst kodu. To miejsce, w którym **ustawiasz symbologię kodu kreskowego** i **generujesz obiekty barcode Java**.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD, "1234567");
generator.save(dataDir + "barcodeToPDF.bmp", BarCodeImageFormat.BMP);
```

> **Wskazówka:** Zastąp `EncodeTypes.CODE_39_STANDARD` dowolną inną wartością `EncodeTypes` (np. `QR`, `DATA_MATRIX`), aby wygenerować różne formaty kodów kreskowych.

## Step 3: Create a PDF Document – *add image pdf java*

Teraz **utworzymy dokument PDF**, który będzie zawierał obraz kodu kreskowego. Aspose.PDF upraszcza to zadanie.

```java
Document doc = new Document();
doc.getPages().add();
```

W tym momencie masz pusty PDF gotowy do przyjęcia treści.

## Step 4: Add Barcode Image to PDF Document – *add barcode existing pdf*

Jeśli musisz osadzić kod kreskowy w **istniejącym PDF**, możesz otworzyć plik za pomocą `PdfFileMend`. Poniższy kod wiąże PDF, wstawia obraz kodu kreskowego i zapisuje wynik.

```java
PdfFileMend mender = new PdfFileMend();
mender.bindPdf(doc);
mender.addImage(in, 1, 100, 600, 200, 700);
mender.save(dataDir + "AddImage_out.pdf");
mender.close();
```

- `in` jest `InputStream`, który wskazuje na obraz kodu kreskowego wygenerowany wcześniej.  
- Numeryczne parametry (`1, 100, 600, 200, 700`) określają numer strony oraz pozycję (współrzędne X, Y, szerokość, wysokość). Dostosuj je do swojego układu.

## Common Issues & Solutions

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Obraz się nie wyświetla** | Nieprawidłowe współrzędne lub indeks strony. | Sprawdź numer strony (`1` dla pierwszej strony) i upewnij się, że strumień obrazu nie jest zamknięty przed `addImage`. |
| **Nieobsługiwany typ kodu kreskowego** | Użycie symbologii nieobjętej licencją. | Sprawdź plik licencji; w razie potrzeby zaktualizuj. |
| **FileNotFoundException** | Ścieżka `dataDir` jest niepoprawna. | Użyj ścieżki bezwzględnej lub `System.getProperty("user.dir")` aby dynamicznie zbudować katalog. |

## Frequently Asked Questions

**P:** Czy mogę dostosować wygląd kodu kreskowego w dokumencie PDF?  
**O:** Tak. Aspose.BarCode pozwala zmieniać kolory, czcionki, marginesy i nawet dodawać tekst czytelny dla człowieka. Dostosuj właściwości `BarcodeGenerator` przed zapisem.

**P:** Czy Aspose.BarCode jest kompatybilny z różnymi symbologiami kodów kreskowych?  
**O:** Absolutnie. Obsługiwane jest ponad 50 symbologii, w tym Code 128, QR, DataMatrix, PDF417 i inne.

**P:** Jak mogę uzyskać tymczasową licencję dla Aspose.BarCode?  
**O:** Odwiedź [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/) na stronie Aspose, aby zamówić 30‑dniową licencję ewaluacyjną.

**P:** Gdzie mogę uzyskać pomoc i wsparcie w sprawach związanych z Aspose.BarCode?  
**O:** Forum [Aspose.BarCode](https://forum.aspose.com/c/barcode/13) to aktywna społeczność, w której możesz zadawać pytania i dzielić się rozwiązaniami.

**P:** Czy mogę wypróbować Aspose.BarCode dla Javy za darmo przed zakupem?  
**O:** Tak, możesz pobrać darmową wersję próbną ze [strony wydań](https://releases.aspose.com/) i przetestować wszystkie funkcje bez licencji.

## Conclusion

Teraz wiesz **jak tworzyć dokumenty PDF w Javie** i osadzać kody kreskowe przy użyciu Aspose.BarCode. Ta funkcjonalność usprawnia przepływy pracy, takie jak generowanie etykiet wysyłkowych, tworzenie bezpiecznych faktur czy budowanie systemów śledzenia inwentarza. Eksperymentuj z różnymi symbologiami, dostosowuj położenie obrazu i integruj kod w większych usługach Java, aby w pełni wykorzystać technologię kodów kreskowych.

---

**Ostatnia aktualizacja:** 2025-12-08  
**Testowano z:** Aspose.BarCode 24.11 for Java, Aspose.PDF 24.11 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}