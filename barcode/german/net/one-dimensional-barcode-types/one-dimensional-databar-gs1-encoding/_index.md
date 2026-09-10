---
date: 2026-03-07
description: Erfahren Sie, wie Sie ein‑dimensionalen Databar‑GS1‑kodierten Strichcode
  in .NET mit Aspose.BarCode erstellen. Dieser Leitfaden zeigt, wie Sie GS1 einstellen,
  den Barcode‑Generator konfigurieren und Barcodes schnell erzeugen.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Erstellen einer eindimensionalen Databar‑GS1‑Codierung mit Aspose.BarCode
url: /de/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen einer eindimensionalen Databar GS1‑Codierung mit Aspose.BarCode

In diesem Tutorial **erstellen Sie eindimensionale Databar**‑Barcodes, die dem GS1‑Standard entsprechen, mit der Aspose.BarCode‑Bibliothek für .NET. Egal, ob Sie eine strenge GS1‑Validierung oder einen flexibleren Barcode benötigen, wir führen Sie durch jeden Schritt – von der Installation der Bibliothek bis zum Umgang mit Codierungs‑Ausnahmen – damit Sie zuverlässige Barcodes in Ihren eigenen Anwendungen erzeugen können.

## Schnelle Antworten
- **Was bedeutet „create one-dimensional databar“?** Es bedeutet das Erzeugen eines linearen (1‑D) Barcodes der Databar‑Familie, der häufig im Einzelhandel und in der Logistik verwendet wird.  
- **Wie stelle ich die GS1‑Validierung ein?** Setzen Sie `IsAllowOnlyGS1Encoding` auf `true` in den `DataBar`‑Parametern.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wo kann ich die Bibliothek herunterladen?** Auf der offiziellen Aspose‑Release‑Seite (siehe Voraussetzungen).

## Was ist „create one-dimensional databar“?
Ein eindimensionaler Databar (auch als RSS bekannt) ist ein kompakter linearer Barcode, der numerische Daten, Datumsangaben oder AI‑(Application Identifier) Zeichenketten codieren kann. In Kombination mit GS1‑Codierung folgt der Barcode einer weltweit anerkannten Datenstruktur, was ihn ideal für Einzelhandel, Gesundheitswesen und Lieferketten‑Szenarien macht.

## Warum Aspose.BarCode für .NET verwenden?
Aspose.BarCode bietet eine fluente API, vollständige GS1‑Unterstützung und die Möglichkeit, jedes visuelle Detail des Barcodes fein abzustimmen. Es eliminiert das Rätselraten bei der Low‑Level‑Codierung und ermöglicht Ihnen, sich auf die Geschäftslogik zu konzentrieren.

## Voraussetzungen

1. **Aspose.BarCode für .NET** – herunterladen und installieren Sie es von [here](https://releases.aspose.com/barcode/net/).  
2. **Ihr Verzeichnispfad** – ersetzen Sie `"Your Directory Path"` in den Beispielen durch einen Ordner, in dem Sie Schreibrechte haben.

## Importieren von Namespaces

Fügen Sie die erforderlichen `using`‑Anweisungen am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.BarCode;
using System;
```

## Schritt 1: Initialisieren des Barcode‑Generators

Erstellen Sie eine `BarcodeGenerator`‑Instanz und geben Sie die Databar‑Expanded‑Symbologie an:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Schritt 2: GS1 einstellen – Barcode mit strenger GS1‑Validierung erzeugen

Aktivieren Sie die reine GS1‑Codierung, weisen Sie einen GS1‑konformen Codetext zu und speichern Sie das Bild:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Schritt 3: Barcode‑Erzeugung mit Aspose – Variable Codierung (keine GS1‑Prüfung)

Wenn Sie einen Barcode benötigen, der **nicht** die GS1‑Regeln erzwingt, deaktivieren Sie die Prüfung:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Schritt 4: GS1‑Prüfung im Barcode‑Generator – Umgang mit einer Ausnahme

Wenn `IsAllowOnlyGS1Encoding` auf `true` gesetzt ist, der Codetext jedoch nicht GS1‑konform ist, wirft Aspose eine Ausnahme. Das folgende Muster zeigt, wie man sie abfängt und protokolliert:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Häufige Fallstricke & Tipps
- **Fallstrick:** Das Bereitstellen einer Nicht‑GS1‑Zeichenkette, während die GS1‑Prüfung aktiviert ist, bricht die Barcode‑Erzeugung ab.  
- **Pro‑Tipp:** Validieren Sie Ihre AI‑Zeichenketten, bevor Sie sie `CodeText` zuweisen, um Laufzeitfehler zu vermeiden.  
- **Tipp:** Verwenden Sie absolute Pfade oder `Path.Combine`, um Dateinamen plattformübergreifend sicher zu erstellen.

## Fazit

Sie wissen jetzt, wie man **eindimensionale Databar**‑Barcodes mit GS1‑Codierung erstellt, wie man die GS1‑Prüfung umschaltet und wie man damit verbundene Ausnahmen behandelt – alles mit Aspose.BarCode für .NET. Erkunden Sie gerne weitere Stiloptionen wie Barcode‑Größe, Farbe und Ränder über das Objekt `Parameters.Barcode`.

Wenn Sie auf Probleme stoßen, sind die offizielle Dokumentation und das Community‑Forum ausgezeichnete Ressourcen:

- [Aspose.BarCode Dokumentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode Support‑Forum](https://forum.aspose.com/c/barcode/13)

## Häufig gestellte Fragen

### 1. Was ist GS1‑Codierung in Barcodes?
GS1‑Codierung ist eine standardisierte Methode, Daten (z. B. Produktkennungen) innerhalb eines Barcodes zu strukturieren, wodurch Interoperabilität zwischen Einzelhändlern, Herstellern und Logistik‑Anbietern gewährleistet wird.

### 2. Kann ich das Aussehen der erzeugten Barcodes anpassen?
Ja. Aspose.BarCode ermöglicht es Ihnen, Größe, Farben, Ränder und sogar menschenlesbaren Text über die Einstellungen `Parameters.Barcode` anzupassen.

### 3. Wo finde ich zusätzliche Ressourcen und Dokumentation für Aspose.BarCode?
Sie finden umfassende Dokumentation und Beispiele unter [Aspose.BarCode Dokumentation](https://reference.aspose.com/barcode/net/). Sie ist eine wertvolle Ressource zum Lernen und zur Fehlersuche.

### 4. Gibt es eine Testversion von Aspose.BarCode?
Ja, Sie können eine kostenlose Testversion von Aspose.BarCode für .NET von [hier](https://releases.aspose.com/) erhalten.

### 5. Wie kann ich eine Lizenz für Aspose.BarCode für .NET erwerben?
Um eine Lizenz für Aspose.BarCode für .NET zu erwerben, besuchen Sie die [Kaufseite](https://purchase.aspose.com/buy) auf der Aspose‑Website.

---

**Zuletzt aktualisiert:** 2026-03-07  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}