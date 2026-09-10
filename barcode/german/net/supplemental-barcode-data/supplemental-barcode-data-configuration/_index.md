---
date: 2026-03-07
description: Erfahren Sie, wie Sie einen EAN‑13‑Barcode mit Zusatzdaten in C# mithilfe
  von Aspose.BarCode für .NET erstellen – generieren Sie schnell Barcode‑PNGs.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: EAN-13-Barcode mit Zusatzdaten erstellen – Aspose.BarCode
url: /de/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie einen EAN-13 Barcode mit Zusatzdaten – Aspose.BarCode für .NET

In diesem praxisnahen Tutorial **erstellen Sie einen EAN-13 Barcode**, der ergänzende EAN‑2- oder EAN‑5-Daten enthält, und Sie sehen, wie Sie **Barcode‑PNG**‑Dateien mit nur wenigen Zeilen C# generieren können. Egal, ob Sie ein Einzelhandels‑Kassensystem, eine Logistik‑Anwendung oder ein einfaches Inventar‑Tool entwickeln, die Möglichkeit, Zusatzinformationen hinzuzufügen, macht Ihre Barcodes deutlich nützlicher.

## Schnelle Antworten
- **Was bedeutet „Zusatzdaten“?** Zusätzliche Ziffern (EAN‑2/EAN‑5), die neben dem Hauptbarcode gedruckt werden und häufig für Preis‑ oder Ausgaben‑Nummern verwendet werden.  
- **Welcher Barcode‑Typ wird verwendet?** EAN‑13 als primäres Symbol, mit optionalen EAN‑2‑ oder EAN‑5‑Ergänzungen.  
- **Kann ich PNG‑Bilder ausgeben?** Ja – die `Save`‑Methode ermöglicht den direkten Export nach PNG.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Ist das kompatibel mit .NET Core / .NET 6?** Absolut – Aspose.BarCode unterstützt alle modernen .NET‑Runtimes.

## Voraussetzungen

- Visual Studio (oder jede .NET‑kompatible IDE).  
- Eine Kopie von Aspose.BarCode für .NET – laden Sie sie **[hier](https://releases.aspose.com/barcode/net/)** herunter.  
- Grundkenntnisse in C#.  
- Ein beschreibbarer Ordner, in dem die erzeugten PNG‑Dateien gespeichert werden.

## Importieren von Namespaces

Fügen Sie zunächst den Aspose.BarCode‑Namespace hinzu, damit Sie auf die Generator‑Klassen zugreifen können:

```csharp
using Aspose.BarCode.Generation;
```

> **Profi‑Tipp:** Wenn Sie .NET Core verwenden, fügen Sie Ihrem Projekt das NuGet‑Paket `Aspose.BarCode` hinzu, anstatt die DLL manuell zu referenzieren.

## Was ist ein Zusatz‑Barcode?

Ein Zusatz‑Barcode ist eine zusätzliche numerische Zeichenkette, die neben dem Haupt‑Barcode gedruckt wird.  
- **EAN‑2** – zweistellige Ergänzung, häufig für Ausgaben‑Nummern bei Zeitschriften verwendet.  
- **EAN‑5** – fünfstellige Ergänzung, üblicherweise für Preis‑Erweiterungen bei Einzelhandelsartikeln verwendet.

Das Hinzufügen dieser Ergänzungen ändert die primären EAN‑13‑Daten nicht; sie liefert lediglich zusätzlichen Kontext, den Scanner lesen können.

## Warum Aspose.BarCode für Zusatzdaten verwenden?

- **One‑line‑API** – konfigurieren Sie sowohl den Haupt‑Barcode als auch seine Ergänzung in einem einzigen Objekt.  
- **Vollständige Kontrolle über die Abmessungen** – passen Sie X‑Dimension, Abstand der Ergänzung und Bildformat an.  
- **Plattformübergreifend** – funktioniert auf .NET Framework, .NET Core und .NET 5/6+.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ausgabeverzeichnis einrichten

Definieren Sie, wo die PNG‑Dateien gespeichert werden sollen. Ersetzen Sie den Platzhalter durch einen echten Pfad auf Ihrem Rechner.

```csharp
string path = "Your Directory Path";
```

### Schritt 2: Barcode‑Generator initialisieren (Barcode Generator C#)

Erstellen Sie eine `BarcodeGenerator`‑Instanz, wobei Sie **EAN‑13** als Haupttyp angeben und die 13‑stellige Nutzlast bereitstellen.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Schritt 3: Barcode‑Abmessungen anpassen

Feinabstimmung der visuellen Größe des Barcodes und des für die Ergänzung reservierten Raums.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Schritt 4: EAN‑2‑Ergänzung hinzufügen

Setzen Sie die Zusatzdaten auf einen zweistelligen Wert (z. B. „12“). Dieser erscheint rechts vom Haupt‑Barcode.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Schritt 5: EAN‑2‑Barcode als PNG speichern

Exportieren Sie das Bild. Das Argument `BarCodeImageFormat.Png` sorgt für eine hochqualitative PNG‑Datei.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Schritt 6: Zu einer EAN‑5‑Ergänzung wechseln

Ändern Sie `SupplementData` zu einer fünfstelligen Zeichenkette für Preis‑Erweiterungen.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Schritt 7: EAN‑5‑Barcode als PNG speichern

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Warum das funktioniert:** Die gleiche `BarcodeGenerator`‑Instanz wird wiederverwendet, sodass Sie nur die `SupplementData`‑Eigenschaft vor jedem `Save`‑Aufruf ändern müssen. Das hält den Code kompakt und vermeidet unnötige Objekt‑Erstellung.

## Häufige Probleme & Tipps

- **Ungültiger Verzeichnispfad** – stellen Sie sicher, dass der Ordner existiert und die Anwendung Schreibrechte hat.  
- **Falsche Ergänzungs‑Länge** – EAN‑2 erwartet exakt 2 Ziffern, EAN‑5 erwartet 5; andernfalls wird eine Ausnahme ausgelöst.  
- **Bild nicht sichtbar** – prüfen Sie, dass `BarCodeImageFormat.Png` verwendet wird; andere Formate (z. B. JPEG) können Kompressionsartefakte einführen, die die Lesbarkeit durch Scanner beeinträchtigen.  

## Häufig gestellte Fragen

### Kann ich Aspose.BarCode für .NET in meinem .NET Core‑Projekt verwenden?
Ja, Aspose.BarCode für .NET ist vollständig kompatibel mit .NET Core, .NET 5 und .NET 6.

### Gibt es eine kostenlose Testversion von Aspose.BarCode für .NET?
Ja, Sie können es kostenlos testen, indem Sie **[diesen Link](https://releases.aspose.com/)** besuchen.

### Wo kann ich eine temporäre Lizenz für Aspose.BarCode für .NET erhalten?
Sie können eine temporäre Lizenz über **[diesen Link](https://purchase.aspose.com/temporary-license/)** erhalten.

### Unterstützt Aspose.BarCode eine breite Palette von Barcode‑Typen?
Absolut – es unterstützt EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 und viele weitere.

### Kann ich das Aussehen der erzeugten Barcodes anpassen?
Ja, Sie können Farben, Schriftarten, Ränder und sogar Hintergrundbilder mithilfe der umfangreichen `Parameters`‑API ändern.

## Fazit

Sie wissen jetzt, wie Sie **einen EAN‑13 Barcode** mit ergänzenden EAN‑2‑ oder EAN‑5‑Daten **erstellen** und **Barcode‑PNG**‑Dateien mit Aspose.BarCode für .NET **generieren**. Dieser Ansatz gibt Ihnen volle Kontrolle über Barcode‑Abmessungen, Abstand der Ergänzung und Ausgabeformat, was ihn ideal für den Einzelhandel, die Logistik und jede Situation macht, in der zusätzliche numerische Informationen erforderlich sind.

Für weiterführende Informationen sehen Sie sich das vollständige Referenzhandbuch an: **[Aspose.BarCode für .NET Dokumentation](https://reference.aspose.com/barcode/net/)**.

---

**Zuletzt aktualisiert:** 2026-03-07  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}