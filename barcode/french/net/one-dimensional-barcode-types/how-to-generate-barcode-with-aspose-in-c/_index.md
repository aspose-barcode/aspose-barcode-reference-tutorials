---
category: general
date: 2026-09-19
description: Comment générer un code‑barres avec Aspose en C# – un guide étape par
  étape pour créer des codes‑barres avec Aspose rapidement et de manière fiable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: fr
lastmod: 2026-09-19
og_description: Comment générer un code-barres avec Aspose en C#. Suivez ce guide
  pour créer un code-barres avec Aspose, configurer MacroPdf417 et l’enregistrer au
  format PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Comment générer un code-barres avec Aspose – guide complet C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Comment générer un code‑barres avec Aspose en C#
url: /fr/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres avec Aspose en C#

Générer un code‑barres en C# est simple lorsque vous utilisez la bibliothèque Aspose.BarCode. Ce tutoriel vous montre comment **créer un code‑barres avec Aspose** étape par étape, en couvrant le format MacroPdf417, les paramètres d’apparence courants et la façon d’enregistrer le résultat sous forme d’image PNG.

Vous apprendrez à :

* Installer et référencer Aspose.BarCode pour .NET  
* Configurer les propriétés spécifiques à MacroPdf417 telles que l’ID du fichier, l’ID du segment et la somme de contrôle  
* Ajuster les options visuelles comme la dimension X et le nombre de colonnes  
* Exporter le code‑barres vers un fichier image  

Aucune expérience préalable avec Aspose n’est requise — juste une compréhension de base du C# et de Visual Studio.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

| Exigence | Détail |
|----------|--------|
| Runtime .NET | .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider, ou tout éditeur supportant le C# |
| Aspose.BarCode | Package NuGet `Aspose.BarCode` (version d’essai gratuite ou version sous licence) |
| Connaissances de base en C# | Familiarité avec les instructions `using` et l’initialisation d’objets |

Vous pouvez ajouter Aspose.BarCode à votre projet via le Gestionnaire de packages NuGet :

```bash
dotnet add package Aspose.BarCode
```

## Comment générer un code‑barres en C# – flux de travail global

Le processus se compose de quatre étapes logiques :

1. **Créer une instance de `BarcodeGenerator`** avec le type d’encodage souhaité (MacroPdf417) et le texte que vous voulez encoder.  
2. **Définir les options d’apparence communes** telles que la dimension X et le nombre de colonnes.  
3. **Configurer les propriétés spécifiques à MacroPdf417** comme l’ID du fichier, l’ID du segment et le horodatage.  
4. **Enregistrer le code‑barres** dans le format de fichier de votre choix (PNG dans cet exemple).

Chaque étape est détaillée ci‑dessous.

## Étape 1 : Créer un générateur de code‑barres pour MacroPdf417

La classe `BarcodeGenerator` est le point d’entrée pour toutes les tâches de création de code‑barres. Lors de son instanciation, vous transmettez deux arguments :

* `EncodeTypes.MacroPdf417` – indique à Aspose d’utiliser la symbologie MacroPdf417.  
* La chaîne de données – le texte qui sera encodé dans le code‑barres.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Pourquoi c’est important :** MacroPdf417 est un code‑barres bidimensionnel capable de contenir de grandes quantités de données et prend en charge des fonctionnalités macro telles que la segmentation de fichiers, ce qui est utile pour transmettre de gros fichiers par morceaux.

## Étape 2 : Définir les options d’apparence communes du code‑barres

Même si MacroPdf417 possède de nombreux paramètres spécialisés, vous devez tout de même contrôler la densité visuelle et la mise en page. Les paramètres les plus courants sont :

* **Dimension X** – largeur du plus petit module (pixel). Des valeurs plus petites produisent une image plus dense.  
* **Colonnes** – nombre de colonnes de données par ligne ; des nombres plus élevés réduisent la hauteur du code‑barres.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Astuce :** Gardez `XDimension` entre 2 et 4 pixels pour la plupart des scénarios d’affichage à l’écran. Des valeurs plus grandes améliorent la lisibilité sur les imprimantes basse résolution mais augmentent la taille globale de l’image.

## Étape 3 : Configurer les propriétés spécifiques à MacroPdf417

MacroPdf417 ajoute un ensemble de champs de métadonnées qui vous permettent de diviser un gros fichier en plusieurs segments de code‑barres. Les propriétés suivantes sont généralement requises :

| Propriété | Objectif |
|-----------|----------|
| `MacroPdf417FileID` | Identifiant unique pour l’ensemble du fichier (max 8 chiffres). |
| `MacroPdf417SegmentID` | Index du segment actuel (commence à 0). |
| `MacroPdf417SegmentsCount` | Nombre total de segments dans le fichier. |
| `MacroPdf417FileName` | Nom lisible du fichier original. |
| `MacroPdf417Checksum` | Somme de contrôle CCITT‑16 optionnelle pour la détection d’erreurs. |
| `MacroPdf417FileSize` | Taille du fichier original en octets. |
| `MacroPdf417TimeStamp` | Horodatage de la génération du fichier. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Chaînes optionnelles pour identifier le destinataire/l’expéditeur. |
| `MacroPdf417Terminator` | Détermine si le code‑barres est le dernier segment (`Set`) ou un segment intermédiaire (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Pourquoi ces champs sont utiles :**  
> *Lorsque vous devez transmettre un gros document sur un canal à faible bande passante, vous pouvez le scinder en plusieurs codes‑barres MacroPdf417. Le récepteur reconstruit le fichier original en lisant les métadonnées de chaque segment.*

## Étape 4 : Enregistrer le code‑barres généré sous forme d’image

Aspose prend en charge de nombreux formats de sortie : PNG, JPEG, BMP, TIFF, SVG et PDF. PNG est un format sans perte idéal pour le web ou les interfaces utilisateur.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Lorsque vous exécutez le programme, vous trouverez un fichier PNG similaire à l’illustration ci‑dessous.

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="comment générer un code‑barres avec Aspose en C#"}

> **Résultat attendu :** Un PNG de 300 × 150 pixels affichant un code‑barres MacroPdf417 qui encode le texte « Sample » ainsi que les métadonnées macro que vous avez fournies.

## Exemple complet, exécutable

En rassemblant tous les éléments, voici le programme complet que vous pouvez copier, coller et exécuter :

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Exécutez le programme avec `dotnet run` (ou appuyez sur **F5** dans Visual Studio). Après l’exécution, vérifiez que le fichier PNG existe et s’ouvre sans erreur.

## Questions fréquentes et gestion des cas limites

### Et si j’ai besoin d’un format d’image différent ?
Aspose prend en charge `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` et `Pdf`. Remplacez simplement `BarCodeImageFormat.Png` par la valeur d’énumération souhaitée.

### Comment générer plusieurs segments automatiquement ?
Vous pouvez placer le code ci‑dessus dans une boucle, en incrémentant `MacroPdf417SegmentID` à chaque itération et en mettant à jour la chaîne de données. Veillez à garder `MacroPdf417SegmentsCount` constant pour tous les segments.

### Que faire si les données dépassent la capacité d’un seul symbole MacroPdf417 ?
MacroPdf417 est conçu pour de gros chargements, mais chaque code‑barres a une capacité théorique maximale (≈ 1,1 KB par segment). Divisez le fichier source en blocs qui respectent cette limite, puis encodez chaque bloc comme un segment séparé.

### La somme de contrôle doit‑elle être calculée manuellement ?
Aspose peut générer automatiquement la somme de contrôle CCITT‑16 si vous définissez `MacroPdf417Checksum` à `0`. Dans l’exemple nous avons fourni une valeur codée en dur à des fins d’illustration ; en production, vous laisseriez généralement la bibliothèque la calculer.

### Comment changer les couleurs de premier plan/arrière‑plan du code‑barres ?
Utilisez les propriétés `BarColor` et `BackColor` :

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Conclusion

Vous savez maintenant **comment générer un code‑barres** en C# avec Aspose.BarCode et, plus précisément, **comment créer un code‑barres avec Aspose** pour la symbologie MacroPdf417. Le tutoriel a couvert l’installation, la configuration de l’apparence et des champs spécifiques aux macros.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants abordent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}