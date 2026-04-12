---
date: 2026-04-12
description: Erfahren Sie, wie Sie in Java mit Aspose.BarCode einen Code128‑Barcode
  mit leeren Balken erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie Barcode‑Java‑Bilder
  schnell generieren.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Barcode mit leeren Balken erzeugen
second_title: Aspose.BarCode Java API
title: Wie man in Java einen Code128-Barcode mit leeren Balken erstellt
url: /de/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie einen Code128-Barcode mit leeren Balken in Java

## Einführung

Die Integration der Barcode‑Erstellung in Java‑Anwendungen ist ein häufiges Anliegen, egal ob Sie Inventursysteme, Ticket‑Plattformen oder Point‑of‑Sale‑Lösungen entwickeln. Mit **Aspose.BarCode for Java** können Sie **Code128‑Barcodes** in nur wenigen Code‑Zeilen erzeugen. In diesem Tutorial führen wir Sie durch die Schritte, um **Barcode‑Java**‑Bilder zu **generieren**, die leere (nicht ausgefüllte) Balken enthalten, sodass Sie die visuelle Gestaltung des Barcodes vollständig steuern können.

## Schnelle Antworten
- **Welche Bibliothek?** Aspose.BarCode for Java  
- **Primärer Anwendungsfall?** Erstellung von Code128‑Barcodes mit leeren Balken für benutzerdefinierte UI‑Designs  
- **Voraussetzungen?** Java JDK 8+, Aspose.BarCode JAR, Schreibzugriff auf einen Ordner für das Ausgabebild  
- **Typische Implementierungszeit?** 5‑10 Minuten für ein Basisbeispiel  
- **Kann ich Farben anpassen?** Ja – die API bietet umfangreiche Styling‑Optionen  

## Was ist ein Code128‑Barcode?

Code128 ist eine hochdichte lineare Barcode‑Symbologie, die den gesamten ASCII‑Zeichensatz kodiert. Sie wird häufig in Logistik, Versand und Einzelhandel eingesetzt, weil sie alphanumerische Daten kompakt darstellen kann. Standardmäßig rendert Aspose.BarCode Code128‑Balken als solide Rechtecke; das Setzen der **FilledBars**‑Eigenschaft auf `false` verwandelt sie in leere (Umriss‑)Balken, was für stilistische Markenführung nützlich ist.

## Warum Aspose.BarCode for Java verwenden?

- **Umfangreicher Funktionsumfang** – unterstützt über 50 Barcode‑Typen, darunter QR, DataMatrix und PDF417.  
- **Keine externen Abhängigkeiten** – ein einzelnes JAR funktioniert auf jeder Java‑Runtime.  
- **Fein abgestimmte Kontrolle** – Sie können Balkenbreite, Farben, Schriftarten und die `FilledBars`‑Eigenschaft anpassen.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS ohne native Bibliotheken.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8 oder neuer installiert und `JAVA_HOME` konfiguriert.  
2. **Aspose.BarCode for Java** – laden Sie das neueste JAR von der [download page](https://releases.aspose.com/barcode/java/) herunter.  
3. **Dokumenten‑Verzeichnis** – ein Ordner auf Ihrem Computer, in dem das erzeugte Barcode‑Bild gespeichert wird.

## Pakete importieren

Importieren Sie in Ihrem Java‑Projekt die Klassen, die Sie für die Arbeit mit Aspose.BarCode benötigen:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Diese Importe geben Ihnen Zugriff auf den Barcode‑Generator, die Bildformat‑Aufzählung und die Ausnahmebehandlung.

## Schritt 1: Ressourcen‑Verzeichnis einrichten

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ersetzen Sie `"Your Document Directory"` durch den absoluten Pfad zu dem Ordner, den Sie in den Voraussetzungen erstellt haben. Dort wird die PNG‑Datei geschrieben.

## Schritt 2: Code128‑Barcode‑Generator‑Instanz erstellen

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Hier instanziieren wir `BarcodeGenerator` mit der Symbologie **CODE_128** und dem Beispieltext `"TEXT"`. Dies ist ein **barcode generator Java example**, das Sie an jede beliebige Zeichenkette anpassen können, die Sie kodieren möchten.

## Schritt 3: FilledBars‑Eigenschaft auf false setzen

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Durch Setzen von `FilledBars` auf `false` wird der erzeugte Barcode leere Balken anstelle von soliden Balken anzeigen, wodurch der gewünschte visuelle Effekt erzielt wird.

## Schritt 4: Barcode‑Bild speichern

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Die Methode `save` schreibt den Barcode im angegebenen Verzeichnis im PNG‑Format. Sie können `BarCodeImageFormat.PNG` zu `JPG`, `BMP` oder `TIFF` ändern, falls ein anderes **image type** benötigt wird.

## Häufige Anwendungsfälle

- **Benutzerdefinierte Markenführung** – leere Balken können mit Hintergrundmustern oder Farben überlagert werden.  
- **Druckfertige Assets** – erzeugen Sie hochauflösende PNGs zur Einbindung in Rechnungen oder Versandetiketten.  
- **Dynamische Erzeugung** – erstellen Sie Barcodes on‑the‑fly in Web‑Services oder Desktop‑Anwendungen.

## Fehlersuche‑Tipps

- **Ungültiger Pfad** – stellen Sie sicher, dass `dataDir` mit einem Dateiseparator (`/` oder `\\`) endet oder fügen Sie ihn mit `File.separator` hinzu.  
- **Lizenz erforderlich** – eine Testversion funktioniert für Evaluierungen, aber für den Produktionseinsatz ist eine vollständige **license** nötig.  
- **Nicht unterstützte Zeichen** – Code128 unterstützt den vollen ASCII‑Satz; vermeiden Sie Unicode‑Zeichen, es sei denn, Sie wechseln zu einer anderen Symbologie.

## Fazit

Sie haben nun gelernt, wie Sie **Code128‑Barcodes** mit leeren Balken mithilfe von Aspose.BarCode for Java **erstellen**. Dieser unkomplizierte Ansatz ermöglicht es Ihnen, anpassbare Barcode‑Grafiken schnell zu erzeugen, egal ob Sie ein Desktop‑Inventur‑Tool oder eine cloudbasierte API entwickeln.

## FAQ

### Ist Aspose.BarCode mit allen Java‑Entwicklungsumgebungen kompatibel?
Ja, Aspose.BarCode ist so konzipiert, dass es sich nahtlos in jede Java‑IDE oder jedes Build‑System integrieren lässt, einschließlich Maven, Gradle und reinen JAR‑Projekten.

### Kann ich das Aussehen des erzeugten Barcodes anpassen?
Absolut! Neben `FilledBars` können Sie Farben, Balkenbreite, Ränder und sogar den menschenlesbaren Text über die umfangreiche API ändern.

### Gibt es eine Testversion von Aspose.BarCode?
Ja, Sie können die Funktionen von Aspose.BarCode mit einer kostenlosen Testversion [hier](https://releases.aspose.com/) erkunden.

### Wie erhalte ich Support für Aspose.BarCode?
Für Fragen oder Unterstützung besuchen Sie das [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Wo finde ich die detaillierte Dokumentation zu Aspose.BarCode?
Die umfassende Dokumentation ist [hier](https://reference.aspose.com/barcode/java/) verfügbar.

**Zusätzliche Fragen**

**Q: Wie generiere ich ein Barcode‑Bild in einem anderen Format, z. B. JPEG?**  
A: Ändern Sie das zweite Argument von `save` zu `BarCodeImageFormat.JPEG`.

**Q: Kann ich mehrere Barcodes in einer Schleife erzeugen?**  
A: Ja – instanziieren Sie innerhalb Ihrer Schleife einen neuen `BarcodeGenerator` oder verwenden Sie dieselbe Instanz mit neuem `CodeText`.

---

**Zuletzt aktualisiert:** 2026-04-12  
**Getestet mit:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}