---
category: general
date: 2026-08-19
description: Générez rapidement un code‑barres PDF417 en C#. Apprenez comment générer
  un code‑barres PDF417 en C# en utilisant Aspose.BarCode avec le mode compact et
  des paramètres personnalisés.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: fr
lastmod: 2026-08-19
og_description: Générez un code‑barres PDF417 en C# avec Aspose.BarCode. Ce tutoriel
  montre comment générer un code‑barres PDF417 en C# en mode compact, définir la dimension
  X et enregistrer au format PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Générer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Générer un code‑barres PDF417 en C# – guide complet avec mise en page compacte
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en C# – guide complet

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce tutoriel vous montre exactement comment le faire. Vous verrez un exemple concis, prêt pour la production, qui crée un code‑barres PDF417 compact, personnalise la dimension X et enregistre le résultat sous forme d’image PNG.

Générer un code‑barres PDF417 est fréquent lorsque vous devez encoder de grandes quantités de données — comme des informations de billet, des manifestes d’expédition ou des documents d’identité — dans un format lisible par machine. L’utilisation d’Aspose.BarCode rend le processus simple, et le code fonctionne avec .NET 6+ ou .NET Framework 4.7.2 et versions ultérieures.

Dans ce guide, vous allez :

* Installer le package NuGet Aspose.BarCode.
* Écrire un programme C# autonome qui **génère un code‑barres PDF417** avec un petit nombre de colonnes et le mode compact (truncation).
* Ajuster la largeur des barres (dimension X) pour un rendu plus net.
* Enregistrer le code‑barres sous forme de fichier PNG.
* Explorer des variantes, des cas limites et des conseils de bonnes pratiques.

## Prérequis

Avant de commencer, assurez-vous d’avoir :

* Visual Studio 2022 (ou tout IDE C#) avec le SDK .NET 6 installé.
* Un accès Internet pour télécharger le package NuGet **Aspose.BarCode**.
* Les droits d’écriture sur un dossier où le fichier PNG sera enregistré.

Aucune bibliothèque supplémentaire n’est requise ; Aspose.BarCode gère l’encodage d’image en interne.

## Étape 1 : Ajouter le package Aspose.BarCode

Ouvrez votre projet dans Visual Studio, faites un clic droit sur la solution et sélectionnez **Manage NuGet Packages**. Recherchez `Aspose.BarCode` et installez la dernière version stable.

```bash
dotnet add package Aspose.BarCode
```

> **Astuce pro :** Gardez le package à jour. Les nouvelles versions incluent souvent des améliorations de performances et la prise en charge des derniers runtimes .NET.

## Étape 2 : Créer une application console minimale

Créez un nouveau projet console C# si vous n’en avez pas déjà un :

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Remplacez le contenu de `Program.cs` par l’exemple complet ci‑dessous. Ce programme montre **comment générer un code‑barres PDF417 en C#** de bout en bout.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **`EncodeTypes.Pdf417`** – sélectionne la symbologie PDF417, qui supporte jusqu’à ~1,1 KB de données.
* **`XDimension.Pixels = 2`** – définit la largeur de base des barres. Des valeurs plus petites rendent le code‑barres plus fin ; des valeurs plus grandes améliorent la lisibilité sur les appareils à basse résolution.
* **`Pdf417.Columns = 3`** – limite le nombre de colonnes, forçant le générateur à utiliser plus de rangées, ce qui donne un code‑barres plus haut mais plus étroit.
* **`Pdf417.Truncate = true`** – active le mode compact, supprime le motif d’arrêt et réduit l’image sans perdre l’intégrité des données.
* **`Save(..., BarCodeImageFormat.Png)`** – écrit un fichier PNG. Vous pouvez également choisir `Jpeg`, `Bmp` ou `Svg` selon les besoins en aval.

Exécutez le programme :

```bash
dotnet run
```

Vous devriez voir la sortie console confirmant l’emplacement du fichier, et le dossier contiendra `CompactPdf417.png`. L’ouverture du PNG montre un code‑barres PDF417 compact et clair qui encode la chaîne Unicode.

## Étape 3 : Vérifier le code‑barres (optionnel mais recommandé)

Pour vous assurer que le code‑barres est lisible, vous pouvez utiliser n’importe quelle application de lecture PDF417 standard sur smartphone ou une bibliothèque de décodage sur ordinateur. Le texte encodé doit correspondre exactement à la chaîne `data` d’origine, caractères spéciaux inclus.

Si vous rencontrez des problèmes de décodage :

* Augmentez le `XDimension` à 3 ou 4 pixels.
* Réduisez le nombre de colonnes (par ex., `Columns = 2`).
* Désactivez `Truncate` (`Truncate = false`) pour ajouter le motif d’arrêt.

Ces ajustements échangent taille contre lisibilité, ce qui est utile pour les imprimantes ou scanners à basse résolution.

## Étape 4 : Explorer les variantes courantes

### 4️⃣ Générer un PDF417 haute densité pour l’impression

Si vous avez besoin d’un code‑barres qui tient sur une petite étiquette, augmentez le nombre de colonnes et réduisez la dimension X :

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Changer le format de sortie en SVG pour un redimensionnement vectoriel

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

La sortie SVG s’adapte sans perte de qualité, idéale pour les pages web responsives.

### 6️⃣ Encoder des données binaires (p. ex., un tableau d’octets)

Si vous devez intégrer des charges binaires, convertissez‑les d’abord en chaîne Base64 :

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Le code‑barres transporte maintenant l’information binaire, et le décodage doit inverser l’étape Base64.

## Questions fréquentes

| Question | Réponse |
|----------|--------|
| **Puis‑je générer un PDF417 sans Aspose ?** | Oui, d’autres bibliothèques comme ZXing.Net ou Dynamsoft existent, mais Aspose.BarCode offre un contrôle de mise en page plus riche (colonnes, troncature) et une meilleure gestion Unicode. |
| **Quelle est la longueur maximale des données ?** | PDF417 peut encoder jusqu’à 1 108 octets (≈ 1 KB) de données binaires. Si vous dépassez cette limite, envisagez de scinder les données sur plusieurs codes‑barres. |
| **Le mode compact est‑il conforme aux normes ?** | Le PDF417 tronqué fait partie de la spécification ISO/IEC 15438 et est largement supporté, mais vérifiez que votre scanner cible le supporte explicitement. |
| **Comment changer la couleur de fond ?** | Définissez `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` et `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` avant l’enregistrement. |

## Conclusion

Vous savez maintenant **comment générer un code‑barres PDF417 en C#** avec Aspose.BarCode, comment affiner la dimension X, activer le mode compact et exporter le résultat en image PNG. L’exemple complet et exécutable peut être copié dans n’importe quel projet .NET, et les variantes présentées vous permettent d’adapter le code‑barres à l’impression, au web ou aux scénarios de charge binaire.

Prochaines étapes possibles :

* Intégrer la génération de code‑barres dans une API ASP.NET Core qui renvoie l’image à la demande.
* Combiner PDF417 avec des QR‑codes sur la même étiquette pour une lecture double format.
* Utiliser la classe `Reader` d’Aspose.BarCode pour décoder l’image générée et vérifier les données programmatiquement.

Bon codage, et profitez de la flexibilité que les solutions **générer un code‑barres PDF417** apportent à vos applications !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}