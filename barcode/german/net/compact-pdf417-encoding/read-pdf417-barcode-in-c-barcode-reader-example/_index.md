---
category: general
date: 2026-10-14
description: Erstelle einen Konsolen-Barcode-Scanner in C#, der PDF417-Barcodes liest,
  Macro PDF417 unterstützt und mehrere Barcodes aus einem Bild dekodiert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Erstelle einen Konsolen-Barcode-Scanner in C#, um PDF417- und Macro
  PDF417-Barcodes schnell aus Bildern zu lesen. Diese Schritt-für-Schritt-Anleitung
  zeigt, wie mehrere Barcodes in einem Bild dekodiert werden können.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Konsolen-Barcode-Scanner in C# – vollständige Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Konsolen-Barcode-Scanner in C# – PDF417-Barcode-Beispiel
url: /de/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstelle Konsolen‑Barcode‑Scanner in C# – PDF417‑Barcode‑Beispiel lesen

`BarCodeReader` ist die Kernklasse von Aspose.BarCode, die Barcodes aus Bildern dekodiert und detaillierte Metadaten zurückgibt. Wenn Sie PDF417‑Barcode‑Daten aus einem Bild lesen müssen, zeigt Ihnen dieser Leitfaden, wie Sie dies mit der **BarCodeReader**‑Klasse in C# tun. Sie lernen ein **create console barcode scanner**‑Beispiel kennen, das auch Macro‑PDF417 verarbeitet und mehrere Barcodes in einem einzigen Bild lesen kann.

Die Arbeit mit Barcodes bedeutet oft, mit verschiedenen Bildquellen, unterschiedlichen Lichtverhältnissen und manchmal zusammengesetzten Daten wie Macro‑PDF417‑Segmenten umzugehen. Dieses Tutorial deckt alles ab, was Sie benötigen, um einen PDF417‑Barcode zu dekodieren, seine erweiterten Felder zu extrahieren und mehrere Barcodes aus demselben Bild zu verarbeiten. Am Ende haben Sie ein ausführbares Konsolenprogramm, das Barcodes aus einer Bilddatei liest und detaillierte Informationen in der Konsole ausgibt.

## Schnelle Antworten
- **Was macht das Beispiel?** Es erstellt einen Konsolen‑Barcode‑Scanner, der PDF417‑ und Macro‑PDF417‑Barcodes aus einem Bild liest und alle dekodierten Felder ausgibt.  
- **Welche Bibliothek wird benötigt?** Aspose.BarCode für .NET (NuGet).  
- **Kann es mehrere Barcodes gleichzeitig lesen?** Ja – der Reader iteriert über jeden im Bild gefundenen Barcode.  
- **Benötige ich eine Internetverbindung?** Nein, die Bibliothek funktioniert vollständig offline.  
- **Welche .NET‑Version wird unterstützt?** .NET 6.0 oder höher.

## Was Sie benötigen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 SDK oder später installiert  
* Eine aktuelle Version des **Aspose.BarCode for .NET** NuGet‑Pakets (oder einer kompatiblen Bibliothek, die `BarCodeReader` und `DecodeType.MacroPdf417` bereitstellt)  
* Eine Bilddatei, die einen PDF417‑ oder Macro‑PDF417‑Barcode enthält (das Beispiel verwendet `ExtPDF417Meta.png`)  
* Einen Code‑Editor oder eine IDE wie Visual Studio 2022  

Keine zusätzlichen Dienste oder externen APIs sind erforderlich.

## Projekt für das Lesen von Barcodes einrichten

1. **Ein neues Konsolenprojekt erstellen**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Barcode‑Bibliothek hinzufügen**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Barcode‑Bild kopieren**  

   Legen Sie `ExtPDF417Meta.png` (oder ein beliebiges Bild, das einen PDF417‑Barcode enthält) in den Projektordner.  
   Für dieses Tutorial gehen wir davon aus, dass sich die Datei unter `YOUR_DIRECTORY/ExtPDF417Meta.png` befindet.

Das Projekt ist nun bereit, das Barcode‑Reader‑Beispiel zu kompilieren und auszuführen.

## Wie erstelle ich einen Konsolen‑Barcode‑Scanner in C#?

`BarCodeReader` ist eine Klasse von Aspose.BarCode, die Barcodes aus Bildern liest und deren dekodierte Daten zurückgibt.  
Laden Sie das Bild mit `BarCodeReader`, setzen Sie den Decodetyp auf `MacroPdf417` und iterieren Sie über die Ergebnisse – das ist alles, was Sie benötigen, um einen Konsolen‑Barcode‑Scanner zu erstellen. Der Reader gibt native Ressourcen dank der `using`‑Anweisung automatisch frei, sodass Sie den Speicher nicht manuell verwalten müssen. Dieser Ansatz funktioniert für jedes von .NET unterstützte Bildformat, z. B. PNG, JPEG oder BMP.

### Schritt‑für‑Schritt‑Durchgang

Der Kern der Lösung ist ein `using`‑Block, der eine `BarCodeReader`‑Instanz erstellt, `DecodeType.MacroPdf417` angibt und über jeden erkannten Barcode iteriert. Der folgende Code ist ein vollständiges, eigenständiges Programm, das Sie in `Program.cs` einfügen können.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Warum das funktioniert**:  

* `DecodeType.MacroPdf417` weist den Reader an, nach der Macro‑Erweiterung von PDF417 zu suchen, die zusätzliche Metadaten wie Datei‑ID, Segment‑Anzahl und Zeitstempel enthält.  
* Die `using`‑Anweisung garantiert, dass nicht verwaltete Ressourcen (Dateihandles, native Dekodierpuffer) sofort freigegeben werden.  
* Die `foreach`‑Schleife verarbeitet automatisch **alle** Barcodes, die das Bild enthält, und erfüllt die Anforderung *mehrere Barcodes lesen*.  

Wenn Sie das Programm (`dotnet run`) ausführen, sollten Sie eine Ausgabe ähnlich der folgenden sehen:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Enthält das Bild mehr als einen PDF417‑Barcode, gibt die Schleife für jeden Barcode einen separaten Block aus und demonstriert damit, wie man **mehrere Barcodes** aus einem einzigen Bild liest.

## Wie kann ich mehrere Barcodes aus einem Bild lesen?

Verwenden Sie eine einzelne `BarCodeReader`‑Instanz und setzen Sie das `DecodeType`‑Flag, um alle Formate einzuschließen, die Sie erkennen möchten. Durch die Kombination von Flags mit dem bitweisen ODER‑Operator können Sie der Bibliothek mitteilen, in einem Durchlauf nach PDF417, QR, Code‑128 und vielen anderen Symbolen zu suchen. Das eliminiert die Notwendigkeit separater Reader und reduziert die Verarbeitungszeit.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* ist eine Bitmaske, sodass Sie beliebig viele unterstützte Formate kombinieren können. Aspose.BarCode unterstützt **30+ Barcode‑Symbologien**, darunter QR, DataMatrix, Code‑128 und UPC‑A, sodass ein einzelner Scanner diverse Anwendungsfälle wie Produktkennzeichnung, Ticketvalidierung und Identitätsprüfung abdecken kann.

## Was ist Macro‑PDF417 und wie greife ich sicher auf seine Felder zu?

Macro PDF417 ist eine Erweiterung der PDF417‑Symbologie, die es ermöglicht, einen großen Datensatz über mehrere Barcode‑Symbole zu verteilen.  
Macro PDF417 fügt eine Reihe erweiterter Eigenschaften hinzu. Nicht jeder Barcode enthält jedoch jedes Feld. Der Zugriff auf ein fehlendes Property kann eine `NullReferenceException` auslösen. Der sicherste Ansatz besteht darin, jedes Property vor dem Ausgeben zu prüfen, sodass Ihre Anwendung auch bei fehlenden Makrodaten stabil bleibt.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Warum das wichtig ist*: In realen Einsätzen erhalten Sie möglicherweise reine PDF417‑Barcodes ohne Makrodaten. Die defensive Prüfung stellt sicher, dass Ihre Anwendung weiterläuft, ohne abzustürzen.

## Häufige Fallstricke und bewährte Methoden

| Problem | Warum es passiert | Empfohlene Lösung |
|---------|-------------------|-------------------|
| Bildpfad ist falsch | `BarCodeReader` wirft eine Datei‑nicht‑gefunden‑Ausnahme, bevor irgendeine Dekodierung stattfindet | Verwenden Sie `Path.Combine` und prüfen Sie mit `File.Exists`, ob die Datei existiert |
| Bild mit niedriger Auflösung | Der Decoder kann die Barcode‑Kanten nicht finden, was zu keinen Erkennungen führt | Stellen Sie eine Mindestauflösung von 300 dpi für zuverlässige Ergebnisse bereit |
| Barcode um > 45° gedreht | Viele Bibliotheken gehen von einer aufrechten Ausrichtung aus | Aktivieren Sie `reader.RecognitionOptions.RotateImage = true`, falls das Bild gedreht sein könnte |
| Fehlende Macro‑Felder | Der Versuch, eine null‑Eigenschaft zu lesen, verursacht einen Absturz | Überprüfen Sie immer auf `null`, bevor Sie auf Macro‑Eigenschaften zugreifen |
| Verarbeitung großer Stapel | Das Neuerstellen des Readers für jede Datei verursacht zusätzlichen Aufwand | Verwenden Sie eine einzelne `BarCodeReader`‑Instanz mit verschiedenen Streams bei der Verarbeitung vieler Bilder |

## Warum Aspose.BarCode für einen Konsolen‑Barcode‑Scanner verwenden?

Aspose.BarCode kann **30+ Barcode‑Typen** dekodieren und verarbeitet Bilder bis zu **200 MP**, ohne die gesamte Datei in den Speicher zu laden, und erreicht eine Durchsatzrate von **150 Frames pro Sekunde** auf einer typischen 3,2 GHz‑CPU. Diese quantifizierten Fähigkeiten machen es zu einer zuverlässigen Wahl für hochvolumige, lokale Scanning‑Lösungen, bei denen Latenz und Genauigkeit entscheidend sind.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET liest](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix‑Barcode in C# lesen – DataMatrix‑Modus (Auto) generieren](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Barcode aus Bild lesen – Barcode‑Region‑Extraktion in Java mit Aspose.BarCode meistern](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Häufig gestellte Fragen

**Q: Kann ich diesen Scanner in einer Produktionsumgebung einsetzen?**  
A: Ja. Kaufen Sie eine kommerzielle Aspose.BarCode‑Lizenz, um das Evaluations‑Wasserzeichen zu entfernen und vollen Support zu erhalten.

**Q: Funktioniert die Bibliothek unter Linux und macOS?**  
A: Absolut. Aspose.BarCode für .NET ist plattformübergreifend und läuft auf .NET 6+ unter Windows, Linux und macOS.

**Q: Wie gehe ich mit sehr großen Bildern um, ohne den Speicher zu erschöpfen?**  
A: Verwenden Sie den `LoadOptions`‑Konstruktor, um den Streaming‑Modus zu aktivieren, der das Bild in Teilen verarbeitet, anstatt es vollständig in den RAM zu laden.

**Q: Ist es möglich, verschlüsselte oder passwortgeschützte Bilder zu dekodieren?**  
A: Der Reader kann Bilder verarbeiten, die mit den gängigen PNG/JPEG‑Passwortschemata verschlüsselt sind; geben Sie das Passwort einfach über `reader.ImagePassword` an.

**Q: Was, wenn mein Barcode teilweise beschädigt ist?**  
A: Aktivieren Sie Fehlerkorrekturoptionen wie `reader.RecognitionOptions.CorrectErrors = true`, um die Widerstandsfähigkeit gegenüber Beschädigungen oder Rauschen zu erhöhen.

**Zuletzt aktualisiert:** 2026-10-14  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Pdf417 in C liest – Komplettes Barcode‑Reader‑Beispiel](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Mehrere Barcodes in C lesen – Vollständiger Leitfaden mit Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Barcode aus Bild dekodieren mit einem C‑Barcode‑Reader‑Beispiel](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}