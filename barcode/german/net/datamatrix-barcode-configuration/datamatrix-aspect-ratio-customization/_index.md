---
date: 2026-01-12
description: Erfahren Sie, wie Sie mit Aspose.BarCode für .NET ein Barcode‑PNG mit
  einem benutzerdefinierten DataMatrix‑Seitenverhältnis erstellen. Schritt‑für‑Schritt‑Anleitung
  zur Barcode‑Generierung und Größenanpassung.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Barcode-PNG erstellen – DataMatrix‑Seitenverhältnis – Aspose.BarCode
url: /de/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑PNG erstellen – DataMatrix‑Seitenverhältnis – Aspose.BarCode

zeugen einer **Barcode‑PNG**‑Datei mit einem benutzerdefinierten DataMatrix‑Seitenverhältnis ist ein häufiges Anliegen, wenn der Barcode in bestimmte Layout‑Beschränkungen passen muss. In diesem Tutorial führen wir Sie Schritt für Schritt durch das **Erstellen von Barcode‑PNG**‑Dateien mit Aspose.BarCode für .NET, erklären, warum Sie das Seitenverhältnis anpassen möchten, und zeigen, wie Sie das Ergebnis für Ihre Anwendung feinjustieren.

## Schnelle Antworten
- **Was steuert das „Seitenverhältnis“?** Es definiert das Breiten‑zu‑Höhe‑Verhältnis der DataMatrix‑Module.  
- **Kann ich PNG, JPEG oder SVG ausgeben?** Ja – die `Save`‑Methode unterstützt PNG, JPEG, BMP, GIF und mehr.  
- **Benötige ich eine Lizenz für dieses Feature?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine Voll­lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Wie viele Seitenverhältnis‑Werte sind gültig?** Jeder positive Float; typische Werte liegen zwischen 0,5 – 2,0.

## Was ist ein DataMatrix‑Barcode und warum das Seitenverhältnis anpassen?
DataMatrix ist ein zweidimensionaler Matrix‑Barcode, der große Datenmengen auf kleinem Raum speichert. Durch Anpassen des **Seitenverhältnisses** können Sie die Module horizontal strecken oder komprimieren, was nützlich ist, um den Barcode in schmale Spalten oder breite Etiketten zu passen, ohne die Lesbarkeit zu beeinträchtigen.

## Voraussetzungen

Bevor wir mit der Anpassung von DataMatrix‑Seitenverhältnissen beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. **Visual Studio** – jede aktuelle Version ist geeignet.  
2. **Aspose.BarCode für .NET** – laden Sie es [hier](https://releases.aspose.com/barcode/net/) herunter.  
3. **.NET Framework / .NET Core** – Ihr Projekt muss eine unterstützte Version anvisieren.

## Namespaces importieren

Zuerst müssen Sie den erforderlichen Namespace in Ihrem C#‑Projekt importieren:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro‑Tipp:** Lassen Sie diese `using`‑Anweisung am Anfang Ihrer Datei stehen, damit die `BarcodeGenerator`‑Klasse jederzeit verfügbar ist.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Erstellen Sie ein neues Konsolen‑ oder Windows‑Forms‑Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.BarCode‑DLL hinzu.

### Schritt 2: Barcode‑Generator initialisieren
Instanziieren Sie einen `BarcodeGenerator` mit dem DataMatrix‑Typ und den Daten, die Sie codieren möchten:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Diese Zeile erzeugt einen Generator, der bereit ist, einen DataMatrix‑Barcode mit dem Beispieltext zu erzeugen.

### Schritt 3: Seitenverhältnis anpassen und PNG‑Dateien speichern
Jetzt können Sie das **Seitenverhältnis** ändern und jede Version als PNG‑Bild speichern:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Der erste Aufruf erzeugt einen quadratisch proportionierten Barcode (`AspectRatio = 1`).  
- Der zweite Aufruf komprimiert den Barcode horizontal (`AspectRatio = 0.5`) und erzeugt ein breiteres Erscheinungsbild.

Sie haben nun zwei **Barcode‑PNG**‑Dateien mit unterschiedlichen Seitenverhältnissen, die Sie in Berichten, Etiketten oder UI‑Elementen verwenden können.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|-------|----------|
| **Generiertes Bild ist unscharf** | Erhöhen Sie den Parameter `Resolution` vor dem Speichern (`gen.Parameters.ImageResolution = 300`). |
| **Barcode lässt sich nicht scannen** | Stellen Sie sicher, dass das Seitenverhältnis zwischen 0,5 – 2,0 bleibt und ausreichend Rand (`gen.Parameters.Barcode.CodeTextParameters.Margin`) vorhanden ist. |
| **Dateipfad‑Fehler** | Verwenden Sie `Path.Combine`, um den Ausgabepfad zu bauen, und prüfen Sie, ob das Verzeichnis existiert. |

## Häufig gestellte Fragen

**F: Kann ich das Seitenverhältnis anderer Barcode‑Typen mit Aspose.BarCode für .NET anpassen?**  
A: Ja, viele 2‑D‑Barcodes (z. B. QR, PDF417) unterstützen Seitenverhältnis‑Anpassungen über ihre jeweiligen Parameter‑Objekte.

**F: Gibt es eine kostenlose Testversion von Aspose.BarCode für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.BarCode für .NET [hier](https://releases.aspose.com/) erhalten.

**F: Wo kann ich eine Lizenz für Aspose.BarCode für .NET erwerben?**  
A: Sie können eine Lizenz auf der Aspose‑Webseite [hier](https://purchase.aspose.com/buy) kaufen.

**F: Ist Aspose.BarCode für .NET mit verschiedenen .NET‑Framework‑Versionen kompatibel?**  
A: Ja, es funktioniert mit .NET Framework 4.x, .NET Core 3.1+ und den neuesten .NET‑Versionen.

**F: Kann ich Barcodes in verschiedenen Formaten mit Aspose.BarCode für .NET erzeugen?**  
A: Absolut – PNG, JPEG, BMP, GIF, TIFF, SVG und PDF werden alle sofort unterstützt.

## Fazit

Das Anpassen des **Seitenverhältnisses** eines DataMatrix‑Barcodes und das **Erstellen von Barcode‑PNG**‑Dateien ist mit Aspose.BarCode für .NET unkompliziert. Wenn Sie die obigen Schritte befolgen, können Sie perfekt dimensionierte Barcodes erzeugen, die exakt den Layout‑Anforderungen Ihres Projekts entsprechen. Erkunden Sie weitere Parameter wie `Resolution`, `Margin` und `Color`, um das Ergebnis weiter zu verfeinern.

Für weiterführende Informationen schauen Sie in die offizielle [Dokumentation](https://reference.aspose.com/barcode/net/) oder besuchen Sie die Community im [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13).

---

**Zuletzt aktualisiert:** 2026-01-12  
**Getestet mit:** Aspose.BarCode 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}