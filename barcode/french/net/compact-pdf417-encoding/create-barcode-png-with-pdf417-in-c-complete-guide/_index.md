---
category: general
date: 2026-10-15
description: Créez rapidement un PNG de code‑barres avec C#. Apprenez à générer un
  code‑barres, modifier les lignes, configurer les paramètres du code‑barres et générer
  un code‑barres PDF417 dans un seul tutoriel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: fr
lastmod: 2026-10-15
og_description: Créer rapidement un PNG de code‑barres en C#. Ce tutoriel montre comment
  générer un code‑barres, modifier les lignes, configurer le code‑barres et générer
  un code‑barres PDF417 avec un code clair.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Créer un PNG de code-barres avec PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Créer un PNG de code-barres avec PDF417 en C# – guide complet
url: /fr/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code-barres avec PDF417 en C# – guide complet

Si vous devez **create barcode PNG** depuis du code C#, ce guide vous montre exactement comment le faire. Nous parcourrons la génération d'un code-barres PDF417, la modification des lignes et la configuration de tous les paramètres clés avant d'enregistrer le résultat sous forme d'image PNG.

Vous apprendrez à créer des images **generate barcode** de manière programmatique, à ajuster la mise en page pour correspondre à votre conception, et à comprendre les options de configuration de l'apparence d'un code-barres. Aucun outil externe n'est requis — seulement la bibliothèque Aspose.BarCode (ou tout package .NET de code-barres compatible) et quelques lignes de code.

## Ce dont vous aurez besoin

- .NET 6.0 ou ultérieur (l'exemple utilise .NET 6, mais toute version .NET récente fonctionne)
- Une référence au package NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Une connaissance de base de C# et Visual Studio (ou de votre IDE préféré)

> **Astuce :** Si vous préférez une alternative gratuite, la même surface d'API est disponible dans la bibliothèque open‑source `ZXing.Net` ; cependant, les extraits de code ci‑dessous ciblent Aspose.BarCode car elle fournit des contrôles directs de la mise en page PDF417.

## Étape 1 : Configurer le projet et ajouter la bibliothèque de code-barres

Créez une nouvelle application console et ajoutez le package NuGet :

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Ensuite, ouvrez `Program.cs` et ajoutez les directives `using` requises :

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Ces espaces de noms exposent la classe `BarcodeGenerator` et l'énumération `EncodeTypes` que vous utiliserez pour créer des images **generate PDF417 barcode**.

## Étape 2 : Créer un PNG de code-barres – générateur de base

La première ligne d'action crée une instance `BarcodeGenerator` configurée pour l'encodage PDF417. C’est le cœur de **how to generate barcode** images.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Pourquoi c’est important :** Le drapeau `EncodeTypes.Pdf417` indique à la bibliothèque quelle symbologie utiliser. Le deuxième argument (`"Layout test"`) est le texte brut qui sera encodé dans le code-barres.

## Étape 3 : Comment configurer le code-barres – définir la taille du module

Un module (ou dimension X) définit le plus petit élément imprimable du code-barres. Le modifier change la taille globale de l'image sans affecter la densité des données.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Définir `Pixels = 2` donne un résultat **create barcode PNG** compact et haute résolution qui fonctionne bien pour les miniatures web et l'impression.

## Étape 4 : Comment changer les lignes – personnaliser la mise en page PDF417

PDF417 vous permet de contrôler explicitement le nombre de colonnes et de lignes. C’est l’étape qui répond à **how to change rows** dans un code-barres.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Cas limite :** Si vous demandez plus de lignes que les données ne le nécessitent, la bibliothèque ajoutera automatiquement des lignes de remplissage. Inversement, demander trop peu de lignes peut provoquer une exception car les données ne tiennent pas.

## Étape 5 : Enregistrer le code-barres généré en fichier PNG

Enfin, écrivez l'image sur le disque. Cela complète le flux de travail **create barcode PNG**.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

Lorsque vous exécutez le programme, vous verrez un fichier nommé `Pdf417_4x9.png` dans le dossier du projet. L'image contient un code-barres PDF417 avec exactement 4 colonnes et 9 lignes, rendu avec des modules de 2 pixels.

### Exemple complet exécutable

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Sortie attendue** (console) :

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Ouvrez le fichier PNG et vous verrez un code-barres PDF417 propre, prêt à être scanné.

## Comment générer un code-barres avec des données différentes

Si vous devez **generate barcode** pour une autre chaîne, remplacez simplement le deuxième argument du constructeur `BarcodeGenerator` :

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Les mêmes étapes de configuration (taille du module, lignes, colonnes) s'appliquent, vous permettant de réutiliser le code pour plusieurs charges utiles.

## Comment changer les lignes dynamiquement en fonction de la longueur du contenu

Parfois, le nombre de lignes doit s'adapter à la longueur du texte encodé. Vous pouvez calculer un nombre de lignes sûr avant de créer le générateur :

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Cet extrait garantit que vous ne demanderez jamais moins de trois lignes (le minimum de la bibliothèque) tout en augmentant pour des données plus longues.

## Comment configurer le code-barres pour différents formats d'image

Bien que le tutoriel se concentre sur le PNG, vous pouvez passer à JPEG, BMP ou TIFF en modifiant l'énumération `BarCodeImageFormat` :

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

Le PNG reste le meilleur choix pour une qualité sans perte, surtout lorsque le code-barres sera imprimé.

## Problèmes courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le code-barres apparaît flou | Dimension X trop grande ou mise à l'échelle de l'image après l'enregistrement | Conservez `XDimension.Pixels` ≤ 3 pour une utilisation à l'écran, ou augmentez la résolution avec un format vectoriel (PDF) |
| Le scanner ne peut pas lire le code-barres | Trop peu de lignes pour la longueur des données | Augmentez `Pdf417.Rows` ou laissez la bibliothèque ajuster automatiquement la taille en omettant le réglage explicite des lignes |
| `ArgumentOutOfRangeException` lors de l'enregistrement | Le répertoire de sortie n'existe pas | Assurez‑vous que `outputPath` pointe vers un dossier valide ou créez‑le avec `Directory.CreateDirectory` |

## Résumé

Ce tutoriel a démontré comment créer des fichiers **create barcode PNG** en C# en utilisant la symbologie PDF417. Vous avez appris :

- **How to generate barcode** avec la classe `BarcodeGenerator`
- **How to change rows** et colonnes pour contrôler la mise en page
- **How to configure barcode** paramètres tels que la taille du module et le format d'image
- Comment **generate PDF417 barcode** et l'enregistrer en image PNG

Vous disposez maintenant d'un bloc de code réutilisable que vous pouvez adapter à différentes charges de données, formats d'image ou exigences de mise en page.

## Prochaines étapes

- Expérimentez avec `Pdf417.ErrorCorrectionLevel` pour améliorer la fiabilité du scan sur des impressions de basse qualité.  
- Combinez plusieurs codes-barres en un seul PDF avec Aspose.PDF pour la génération d'étiquettes en lot.  
- Explorez d'autres symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) en changeant la valeur de l'énumération — cela correspond au mot‑clé secondaire **generate pdf417 barcode** tout en montrant des capacités plus larges.

Bon codage, et profitez de créer des PNG de code-barres nets pour chaque application !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres PDF417 et exporter un PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [Comment générer des codes-barres PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Comment créer un PNG de code-barres avec un ratio d'aspect personnalisé en C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}