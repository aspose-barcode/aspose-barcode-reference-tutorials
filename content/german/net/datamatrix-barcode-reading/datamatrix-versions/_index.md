---
title: Generieren Sie DataMatrix-Barcodes mit Aspose.BarCode für .NET
linktitle: DataMatrix-Versionen
second_title: Aspose.BarCode .NET-API
description: Erfahren Sie, wie Sie mit Aspose.BarCode für .NET DataMatrix-Barcodes in .NET generieren. Benutzerdefinierte Abmessungen, ECC-Unterstützung und mehr.
type: docs
weight: 12
url: /de/net/datamatrix-barcode-reading/datamatrix-versions/
---
Wenn Sie nach einer zuverlässigen Lösung zum Generieren von DataMatrix-Barcodes in Ihren .NET-Anwendungen suchen, ist Aspose.BarCode für .NET die richtige Wahl. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Verwendung von Aspose.BarCode für .NET zum Erstellen von DataMatrix-Barcodes. Wir unterteilen jedes Beispiel in mehrere Schritte, um sicherzustellen, dass Sie problemlos mitmachen können.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Eine Entwicklungsumgebung mit .NET-Unterstützung.
-  Eine Kopie von Aspose.BarCode für .NET, die Sie hier herunterladen können[dieser Link](https://releases.aspose.com/barcode/net/).
- Grundkenntnisse in C# und dem .NET Framework.

Sehen wir uns nun die DataMatrix-Versionen an und wie man sie mit Aspose.BarCode für .NET generiert.

## Namespaces importieren

In jedem C#-Projekt ist es wichtig, die erforderlichen Namespaces zu importieren. Im Fall von Aspose.BarCode müssen Sie Folgendes einschließen:

```csharp
using Aspose.BarCode.Generation;
```

 Dieser Namespace bietet Zugriff auf`BarcodeGenerator` Klasse, die für die Generierung von Barcodes von entscheidender Bedeutung ist.

Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen.

## Schritt 1: Richten Sie Ihren Verzeichnispfad ein

Beginnen Sie mit der Definition des Verzeichnispfads, in dem Sie die generierten DataMatrix-Barcodes speichern möchten.

```csharp
string path = "Your Directory Path";
```

 Ersetzen`"Your Directory Path"` mit dem tatsächlichen Pfad, in dem Sie die Barcode-Bilder speichern möchten.

## Schritt 2: Initialisieren Sie den Barcode-Generator

 Erstellen Sie eine Instanz von`BarcodeGenerator` Klasse und geben Sie den Barcode-Typ als an`DataMatrix`. Sie können auch die Daten angeben, die Sie im Barcode verschlüsseln möchten.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Code zum Generieren von Barcodes finden Sie hier
}
```

## Schritt 3: Barcode-Eigenschaften konfigurieren

Sie können verschiedene Eigenschaften des DataMatrix-Barcodes anpassen, z. B. seine Abmessungen und den ECC-Typ (Error Correction Code). Hier ist ein Beispiel für die Einstellung der X-Dimension auf 4 Pixel und die Auswahl von ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Schritt 4: DataMatrix-Version festlegen und speichern

Sie können die DataMatrix-Version angeben, indem Sie die Anzahl der Zeilen und Spalten festlegen. Speichern Sie nach der Konfiguration der Version das Barcodebild.

So erstellen Sie beispielsweise mit ECC200 einen DataMatrix-Barcode mit 22 Zeilen und 22 Spalten:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Ebenso können Sie einen Barcode mit unterschiedlichen Parametern generieren, indem Sie die Version und den ECC-Typ nach Bedarf ändern.

## Schritt 5: Wiederholen Sie diesen Vorgang für andere Versionen

Sie können Schritt 4 für andere DataMatrix-Versionen wiederholen. So erstellen Sie beispielsweise mit ECC200 einen Barcode mit 12 Zeilen und 64 Spalten:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Schritt 6: ECC-Typen wechseln

Wenn Sie den ECC-Typ in Ecc140 ändern möchten, können Sie dies tun, indem Sie die ECC-Eigenschaft aktualisieren:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Schritt 7: Barcodes mit verschiedenen Versionen und ECC generieren

Wiederholen Sie Schritt 4 für andere DataMatrix-Versionen und ECC-Typen und speichern Sie jeden Barcode unter einem eindeutigen Dateinamen.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Nachdem Sie nun gelernt haben, wie Sie mit Aspose.BarCode für .NET DataMatrix-Barcodes generieren, können Sie diese Funktionalität problemlos in Ihre .NET-Anwendungen integrieren.

## Abschluss

Aspose.BarCode für .NET vereinfacht den Prozess der Generierung von DataMatrix-Barcodes in Ihren .NET-Anwendungen. Mit dieser Schritt-für-Schritt-Anleitung können Sie Barcodes mit unterschiedlichen Versionen und ECC-Typen erstellen und so Flexibilität und Anpassung an Ihre spezifischen Anforderungen bieten.

 Wenn Sie Fragen haben oder Hilfe benötigen, zögern Sie nicht, die zu besuchen[Aspose.BarCode für .NET-Dokumentation](https://reference.aspose.com/barcode/net/) oder schauen Sie sich die an[Aspose.BarCode-Forum](https://forum.aspose.com/c/barcode/13) zur Unterstützung.

## FAQs

### F1: Was ist ECC in DataMatrix-Barcodes?

A1: ECC (Error Correction Code) ist ein wichtiger Bestandteil von DataMatrix-Barcodes, der zur Gewährleistung der Datenintegrität beiträgt. Verschiedene ECC-Stufen bieten unterschiedliche Grade der Fehlerkorrektur.

### F2: Kann ich mit Aspose.BarCode für .NET DataMatrix-Barcodes mit benutzerdefinierten Abmessungen generieren?

A2: Ja, Sie können die Abmessungen von DataMatrix-Barcodes anpassen, indem Sie die Anzahl der Zeilen und Spalten festlegen, wie im Tutorial gezeigt.

### F3: Wo kann ich Aspose.BarCode für .NET herunterladen?

 A3: Sie können Aspose.BarCode für .NET herunterladen von[dieser Link](https://releases.aspose.com/barcode/net/).

### F4: Gibt es eine kostenlose Testversion für Aspose.BarCode für .NET?

 A4: Ja, Sie können auf eine kostenlose Testversion von Aspose.BarCode für .NET zugreifen[Hier](https://releases.aspose.com/).

### F5: Wie kann ich eine temporäre Lizenz für Aspose.BarCode für .NET erhalten?

 A5: Um eine temporäre Lizenz für Aspose.BarCode für .NET zu erhalten, besuchen Sie[dieser Link](https://purchase.aspose.com/temporary-license/).