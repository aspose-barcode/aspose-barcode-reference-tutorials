---
date: 2026-01-04
description: Erfahren Sie, wie Sie bei der Generierung von Codabar‑Barcodes mit Aspose.BarCode
  für .NET eine Prüfsumme hinzufügen. Schritt‑für‑Schritt‑Anleitung, die die Mod10‑
  und Mod16‑Prüfsummenmodi abdeckt.
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: Wie man einer Codabar-Barcode-Prüfsumme mit Aspose.BarCode für .NET hinzufügt
url: /de/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Prüfsumme zu Codabar‑Barcodes mit Aspose.BarCode für .NET hinzufügt

Codabar ist eine weit verbreitete lineare Barcode‑Symbologie, insbesondere in Logistik, Bibliotheken und dem Gesundheitswesen. Das Hinzufügen einer Prüfsumme zu einem Codabar‑Barcode verbessert die Datenintegrität erheblich, indem Transkriptionsfehler bereits vor ihrer Entstehung erkannt werden. In diesem Tutorial lernen Sie **wie man eine Prüfsumme hinzufügt**, wenn Sie einen Codabar‑Barcode mit Aspose.BarCode für .NET erzeugen, und Sie sehen sowohl den Mod10‑ als auch den Mod16‑Prüfsummen‑Modus in Aktion.

## Schnellantworten
- **Was bedeutet „Prüfsumme hinzufügen“ bei Codabar?** Sie ermöglicht Fehlererkennungsziffern, die die codierten Daten validieren.
- **Welche Prüfsummen‑Modi werden unterstützt?** Mod10 (üblich) und Mod16 (für Szenarien mit höherer Genauigkeit).
- **Benötige ich eine Lizenz, um die Funktion zu nutzen?** Ja, für den Produktionseinsatz ist eine gültige Aspose.BarCode für .NET‑Lizenz erforderlich.
- **Welche .NET‑Versionen sind kompatibel?** Die Bibliothek funktioniert mit .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Wo finde ich die erzeugten Bilder?** Sie werden im Ordner gespeichert, den Sie in der Variable `path` angeben.

## Was bedeutet „Prüfsumme hinzufügen“ bei Codabar?
Eine Prüfsumme hinzuzufügen bedeutet, den Barcode‑Generator so zu konfigurieren, dass er basierend auf den bereitgestellten Daten ein zusätzliches Zeichen (oder mehrere Zeichen) berechnet und anhängt. Diese Zusatzinformation wird von Scannern überprüft und reduziert die Wahrscheinlichkeit von Fehlablesungen.

## Warum einen Codabar‑Barcode mit Prüfsumme erzeugen?
- **Verbesserte Zuverlässigkeit:** Erkennt Einzelzeichen‑Fehler und die meisten Vertauschungsfehler.
- **Compliance:** Bestimmte Branchen (z. B. Blutbanken) verlangen Barcodes mit aktivierter Prüfsumme.
- **Flexibilität:** Mit Aspose.BarCode können Sie zwischen Mod10 und Mod16 mit einer einzigen Property‑Änderung wechseln.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.BarCode für .NET** – laden Sie die neueste Version von [hier](https://releases.aspose.com/barcode/net/) herunter.  
2. **C#‑Entwicklungsumgebung** – Visual Studio, VS Code oder jede IDE, die .NET‑Entwicklung unterstützt.

Jetzt, wo alles eingerichtet ist, gehen wir die Implementierung Schritt für Schritt durch.

## Namespaces importieren

Fügen Sie den erforderlichen Namespace am Anfang Ihrer C#‑Datei hinzu, damit Sie auf die Barcode‑Generierungsklassen zugreifen können:

```csharp
using Aspose.BarCode.Generation;
```

## Schritt 1: Barcode‑Generator initialisieren

Erzeugen Sie eine `BarcodeGenerator`‑Instanz, geben Sie die Codabar‑Symbologie an und übergeben Sie die Daten, die Sie codieren möchten. Ersetzen Sie `"Your Directory Path"` durch den tatsächlichen Ordner, in dem die Bilder gespeichert werden sollen.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## Schritt 2: Codabar‑Barcode **ohne** Prüfsumme erzeugen

Falls Sie einen einfachen Barcode (ohne Prüfsumme) benötigen, setzen Sie die Prüfsummen‑Option auf `Default`. Das ist nützlich für Altsysteme, die keine Prüfsummen‑Ziffer erwarten.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## Schritt 3: Codabar‑Barcode mit **Mod10**‑Prüfsumme erzeugen

Aktivieren Sie die Prüfsumme und wählen Sie den Mod10‑Algorithmus. Dies ist der am häufigsten verwendete Prüfsummen‑Modus für Codabar.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## Schritt 4: Codabar‑Barcode mit **Mod16**‑Prüfsumme erzeugen

Für Anwendungen, die eine höhere Fehlererkennungs‑Fähigkeit benötigen, wechseln Sie zu Mod16. Die Code‑Änderung ist minimal – aktualisieren Sie einfach `CodabarChecksumMode`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

Mit diesen vier einfachen Schritten haben Sie **gelernt, wie man eine Prüfsumme** zu Codabar‑Barcodes hinzufügt und wie Sie zwischen den Mod10‑ und Mod16‑Modi mit Aspose.BarCode für .NET umschalten.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|--------|-----|
| Erzeugtes Bild ist leer | `path` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert, oder verwenden Sie `Directory.CreateDirectory(path)` vor dem Speichern |
| Prüfsumme nicht angewendet | `IsChecksumEnabled` blieb auf `Default` | Setzen Sie `IsChecksumEnabled = EnableChecksum.Yes` vor dem Speichern |
| Falscher Prüfsummen‑Modus | Falscher Enum‑Wert verwendet | Verwenden Sie `CodabarChecksumMode.Mod10` oder `CodabarChecksumMode.Mod16` nach Bedarf |

## Fazit

In diesem Leitfaden haben wir **gezeigt, wie man eine Prüfsumme** hinzufügt, wenn Sie einen Codabar‑Barcode mit Aspose.BarCode für .NET erzeugen, beide Prüfsummen‑Modi Mod10 und Mod16 demonstriert und erläutert, warum Barcodes mit Prüfsumme für die Datenintegrität unverzichtbar sind. Experimentieren Sie gern mit verschiedenen Datenstrings und entdecken Sie die umfangreichen Anpassungsoptionen, die Aspose bietet.

Wenn Sie auf Schwierigkeiten stoßen, steht Ihnen die Aspose.BarCode‑Community im [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13) zur Verfügung.

## Häufig gestellte Fragen

**Q: Kann ich die Mod16‑Prüfsumme für Bibliotheksbuch‑Barcodes verwenden?**  
A: Absolut. Mod16 bietet eine stärkere Fehlererkennung, was in hochfrequentierten Umgebungen wie Bibliotheken von Vorteil ist.

**Q: Beeinflusst das Aktivieren der Prüfsumme die Scan‑Geschwindigkeit?**  
A: Das zusätzliche Zeichen verursacht nur einen vernachlässigbaren Verarbeitungsaufwand; die meisten Scanner verarbeiten es ohne spürbare Verzögerung.

**Q: Wie prüfe ich die Prüfsumme programmgesteuert?**  
A: Nach der Barcode‑Erzeugung können Sie die Prüfsumme mit demselben `CodabarChecksumMode` neu berechnen und mit dem letzten Zeichen des codierten Strings vergleichen.

**Q: Ist es möglich, das Aussehen der Prüfsummen‑Ziffer anzupassen?**  
A: Ja. Verwenden Sie die Erscheinungs‑Einstellungen des `BarcodeGenerator` (z. B. `BarHeight`, `ForeColor`), um den gesamten Barcode einschließlich der Prüfsummen‑Ziffer zu stylen.

**Q: Was, wenn ich mehrere Barcodes in einer Schleife erzeugen muss?**  
A: Instanziieren Sie einen einzigen `BarcodeGenerator`, ändern Sie die `CodeText`‑Property für jede Iteration und rufen Sie `Save` mit einem eindeutigen Dateinamen auf.

---

**Zuletzt aktualisiert:** 2026-01-04  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}