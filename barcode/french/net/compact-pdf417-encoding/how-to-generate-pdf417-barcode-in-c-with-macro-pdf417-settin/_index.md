---
category: general
date: 2026-10-15
description: Apprenez à générer un code‑barres PDF417 en C# en utilisant les paramètres
  Macro‑PDF417, à définir les dimensions du code‑barres et à l’enregistrer au format
  PNG. Exemple de code complet inclus.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: fr
lastmod: 2026-10-15
og_description: Comment générer un code‑barres PDF417 en C# avec une configuration
  complète Macro‑PDF417, le contrôle des dimensions et la sortie PNG. Suivez l’exemple
  complet.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Comment générer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Comment générer un code‑barres PDF417 en C# avec les paramètres Macro‑PDF417
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres PDF417 en C# avec les paramètres Macro‑PDF417

Si vous avez besoin de **comment générer un code‑barres PDF417** pour un flux de travail documentaire, ce guide vous montre les étapes exactes. Vous verrez comment configurer les paramètres Macro‑PDF417, définir les dimensions du code‑barres et exporter le résultat sous forme d’image PNG — le tout dans un seul programme C# exécutable.

Générer un code‑barres PDF417 ne nécessite pas plusieurs bibliothèques ni de post‑traitement complexe. En utilisant Aspose.Barcode pour .NET, vous pouvez contrôler chaque aspect du code‑barres, de la largeur du module au checksum, et produire une image de haute qualité prête à être imprimée ou scannée.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* SDK .NET 6.0 (ou ultérieur) installé  
* Visual Studio 2022 ou tout IDE C# de votre choix  
* Package NuGet Aspose.Barcode pour .NET (`Install-Package Aspose.Barcode`)  

Ces prérequis garantissent que le code se compile sans configuration supplémentaire.

## Étape 1 : Créer un générateur de code‑barres pour un code‑barres Macro‑PDF417

La première opération crée une instance `BarcodeGenerator` qui cible le format `EncodeTypes.MacroPdf417`. Le constructeur reçoit les données que vous souhaitez encoder — dans ce cas, la chaîne `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Créer le générateur initialise l’objet interne `Parameters`, que vous utiliserez pour ajuster les propriétés du **code‑barres PDF417 C#**.

## Étape 2 : Définir l’apparence de base du code‑barres – définir les dimensions du code‑barres

Contrôler la taille visuelle d’un code‑barres améliore la fiabilité de la lecture. La propriété `XDimension.Pixels` définit la largeur du module (point), tandis que `Pdf417.Columns` détermine le nombre de colonnes que le code‑barres contiendra.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Définir ces dimensions garantit que le code‑barres s’insère dans les tailles d’étiquettes typiques et répond aux spécifications des scanners.

## Étape 3 : Fournir l’identification de fichier Macro‑PDF417

Macro‑PDF417 étend le code‑barres PDF417 standard avec des métadonnées au niveau du fichier. Vous devez attribuer un ID de fichier unique, un ID de segment, le nombre total de segments, et un nom de fichier lisible par l’homme.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Ces **paramètres Macro PDF417** permettent aux systèmes en aval de reconstruire le fichier original à partir de plusieurs segments de code‑barres.

## Étape 4 : Ajouter des métadonnées macro supplémentaires – inclure le checksum du code‑barres

Au‑delà de l’identification, Macro‑PDF417 peut stocker le checksum, la taille du fichier, l’horodatage, le destinataire, l’expéditeur et un drapeau de terminaison. Fournir un checksum améliore les contrôles d’intégrité des données lors du décodage.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Inclure un **checksum de code‑barres** et d’autres métadonnées rend le code‑barres auto‑descriptif, ce qui est précieux pour les pipelines automatisés de traitement de documents.

## Étape 5 : Enregistrer le code‑barres généré sous forme d’image PNG – choisir le format d’image du code‑barres

L’étape finale écrit le code‑barres dans un fichier. La méthode `Save` accepte un chemin de fichier et une énumération `BarCodeImageFormat`. PNG fournit une compression sans perte, préservant les bords nets pour une lecture fiable.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Après exécution, le fichier `MacroPdf417.png` contient un code‑barres PDF417 net, prêt à être intégré dans des PDF, imprimé sur des étiquettes ou affiché à l’écran.

## Résultat attendu

L’ouverture de `C:/Barcodes/MacroPdf417.png` montre un code‑barres rectangulaire avec le texte encodé « Sample text ». Le code‑barres inclut les métadonnées macro que vous avez définies, que vous pouvez vérifier avec n’importe quel scanner PDF417 supportant Macro‑PDF417. Les dimensions de l’image reflètent la largeur du module (2 px) et le nombre de colonnes (5), produisant un code‑barres compact mais lisible.

## Variantes courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Longueur de données différente** | Remplacez `"Sample text"` par n’importe quelle chaîne UTF‑8 ; le générateur ajuste automatiquement la taille du code‑barres. |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` à 3 ou 4 pour des modules plus grands, utile pour les imprimantes basse résolution. |
| **Plus de segments** | Modifiez `MacroPdf417SegmentsCount` pour correspondre au nombre total de parties de code‑barres que vous prévoyez de générer. |
| **Format d’image alternatif** | Utilisez `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` si votre système en aval préfère ces formats. |
| **Correction d’erreur personnalisée** | Modifiez `generator.Parameters.Barcode.Pdf417.ErrorLevel` (plage 0‑8) pour équilibrer densité de données et tolérance aux erreurs. |

**Astuce :** Validez toujours le code‑barres généré avec un scanner physique avant de le déployer en production. Les scanners peuvent avoir des limites spécifiques de firmware concernant la largeur du module ou le nombre de colonnes.

## Code source complet

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

L’exécution de ce programme crée `MacroPdf417.png` dans le dossier `C:/Barcodes`. La console confirme la génération réussie.

## Conclusion

Vous savez maintenant **comment générer un code‑barres PDF417** en C# avec un contrôle complet du Macro‑PDF417, **comment définir les dimensions du code‑barres**, **comment intégrer le checksum du code‑barres** et d’autres métadonnées macro, ainsi que **comment exporter le résultat en utilisant le format d’image choisi**. L’exemple complet peut être copié dans n’importe quel projet .NET, modifié pour différents chargements de données, et intégré à des pipelines d’automatisation documentaire plus larges.

### Prochaines étapes

* Explorez les **niveaux de correction d’erreur du code‑barres PDF417 C#** pour améliorer la fiabilité de la lecture.  
* Combinez plusieurs segments Macro‑PDF417 pour encoder de gros fichiers tels que des PDF ou des images.  
* Passez le **format d’image du code‑barres** à SVG pour des graphiques vectoriels évolutifs dans les applications web.  

N’hésitez pas à expérimenter avec les paramètres et à partager vos résultats dans les commentaires ou sur les forums communautaires. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}