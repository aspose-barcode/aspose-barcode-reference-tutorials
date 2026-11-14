---
category: general
date: 2026-11-14
description: Apprenez à créer rapidement un code‑barres PDF417 en C#. Ce guide montre
  également comment générer un PDF417 et comment personnaliser les paramètres du PDF417
  pour un contrôle précis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: fr
lastmod: 2026-11-14
og_description: Créez un code‑barres PDF417 en C# avec des instructions étape par
  étape. Apprenez à générer du PDF417 et à personnaliser les paramètres du PDF417
  pour des résultats précis.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Créer un code-barres PDF417 en C# – guide complet avec mise en page personnalisée
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Comment créer un code‑barres PDF417 avec une mise en page personnalisée en
  C#
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres PDF417 avec une mise en page personnalisée en C#

Si vous devez **créer un code-barres pdf417** pour un système de billetterie, une étiquette d’inventaire ou une lecture depuis une application mobile, ce tutoriel montre le processus complet. Vous verrez comment générer rapidement du PDF417 et comment personnaliser les paramètres du PDF417 tels que les colonnes et les lignes, afin que le code-barres s’adapte à vos contraintes de conception.

Générer un code-barres ne nécessite pas une bibliothèque graphique complexe — il suffit d’Aspose.BarCode pour .NET (ou toute API compatible). À la fin de ce guide, vous disposerez d’un fichier PNG prêt à l’emploi que vous pourrez intégrer dans des PDF, des pages web ou imprimer directement depuis votre application.

## Prérequis

- .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
- Aspose.BarCode pour .NET (package NuGet `Aspose.BarCode`)
- Connaissances de base en C# et Visual Studio (ou tout IDE)

> **Astuce pro :** Si vous utilisez un pipeline CI/CD, ajoutez la référence du package NuGet dans votre fichier de projet afin que les builds restent reproductibles.

## Étape 1 : Installer la bibliothèque de codes-barres

Ouvrez le dossier de votre projet dans un terminal et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package inclut la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel. Aucune dépendance native supplémentaire n’est requise.

## Étape 2 : Créer un code-barres PDF417 de base

Le premier objectif est de **créer un code-barres pdf417** avec les paramètres par défaut. Le programme suivant configure le générateur, encode une chaîne d’exemple et enregistre le résultat sous forme d’image PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Pourquoi cela fonctionne  :**  
`EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417. Le constructeur crée automatiquement un objet `Barcode` avec des valeurs de colonnes/lignes par défaut qui garantissent la lisibilité dans la plupart des cas d’utilisation.

Exécutez le programme (`dotnet run`). Vous trouverez `Pdf417Default.png` dans le dossier du projet. L’ouverture de l’image montre un code-barres PDF417 standard prêt à être scanné.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Exemple de création de code-barres PDF417 montrant la mise en page par défaut"}

## Étape 3 : Comment générer un PDF417 avec des dimensions personnalisées

Parfois, une étiquette de taille fixe ou un composant d’interface utilisateur nécessite une empreinte de code-barres spécifique. C’est là que **comment générer pdf417** avec des colonnes et des lignes personnalisées devient essentiel.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Pourquoi vous pourriez vouloir cela  :**  
- **Largeur limitée  :** Réduire le nombre de colonnes et augmenter le nombre de lignes crée un code-barres plus large mais plus court, idéal pour les étiquettes étroites.  
- **Hauteur limitée  :** Augmenter le nombre de colonnes et diminuer le nombre de lignes produit un code-barres plus haut et plus étroit, utile lorsque vous disposez d’un espace vertical.

Les propriétés `Columns` et `Rows` n’acceptent que des valeurs dans les plages documentées (2‑30 pour les colonnes, 1‑90 pour les lignes). Fournir une valeur hors de ces limites déclenche une `ArgumentOutOfRangeException`, il faut donc toujours valider les entrées utilisateur si vous exposez ces paramètres dans une interface.

## Étape 4 : Comment personnaliser davantage le PDF417

Au-delà des colonnes et des lignes, la symbologie PDF417 propose de nombreux paramètres optionnels :

| Propriété | Objectif | Valeurs typiques |
|-----------|----------|------------------|
| `ErrorLevel` | Contrôle la capacité de correction d’erreurs | 0‑8 (plus élevé = plus robuste) |
| `MacroPdf417` | Active le macro PDF417 pour les données multi‑segments | `true`/`false` |
| `CompactPdf417` | Produit un code-barres plus compact au prix d’une correction d’erreurs réduite | `true`/`false` |
| `SecurityLevel` | Ajoute un chiffre de contrôle de sécurité | 0‑2 |

Voici un exemple rapide qui fixe également le niveau d’erreur au maximum (8) pour un environnement bruyant :

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Pourquoi c’est important  :**  
Une correction d’erreurs plus élevée permet aux lecteurs de récupérer les données même si une partie du code-barres est endommagée. Cependant, cela augmente également la taille du code-barres, il faut donc équilibrer ce paramètre avec vos contraintes de mise en page.

## Étape 5 : Vérifier que le code-barres fonctionne

Après avoir généré le PNG, testez-le avec n’importe quelle application de lecture de codes-barres (la plupart des smartphones disposent de lecteurs PDF417 gratuits). Si le lecteur renvoie le texte original (`Custom layout text`), le code-barres est valide.

Si vous rencontrez des problèmes de lecture :

1. **Vérifier les dimensions  :** Assurez-vous que les colonnes/lignes restent dans la plage autorisée.  
2. **Ajuster le niveau d’erreur  :** Augmentez `ErrorLevel` pour les supports endommagés.  
3. **Examiner la qualité de l’image  :** Enregistrez avec un DPI plus élevé (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) si vous prévoyez d’imprimer.

## Code source complet pour un helper réutilisable

Voici une classe compacte et réutilisable que vous pouvez intégrer à n’importe quel projet .NET. Elle encapsule **comment générer pdf417** et **comment personnaliser pdf417** dans une seule méthode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Vous pouvez appeler ce helper ainsi :

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

La méthode abstrait le code répétitif, vous permettant de vous concentrer sur la logique métier.

## Pièges courants et comment les éviter

- **Valeurs hors plage  :** Validez toujours `columns` et `rows` avant de les assigner.  
- **Format d’image incorrect  :** Certains lecteurs anciens n’acceptent que le BMP ou le JPEG. Utilisez `BarCodeImageFormat.Bmp` si nécessaire.  
- **DPI faible pour l’impression  :** Le DPI par défaut est 96. Pour des impressions de haute qualité, définissez explicitement un DPI plus élevé (par ex., 300) lors de l’appel à `Save`.  
- **Absence de prise en charge de la police  :** PDF417 encode des données binaires, vous n’avez généralement pas besoin de spécifier une police. Cependant, si vous superposez du texte sur l’image, assurez‑vous que la police est installée sur la machine cible.

## Conclusion

Vous savez maintenant comment **créer un code-barres pdf417** de bout en bout, comment **générer pdf417** avec des paramètres de colonnes/lignes personnalisés, et comment **personnaliser pdf417** pour la correction d’erreurs et la compacité. En suivant le modèle de helper réutilisable, vous pouvez générer des codes-barres à la demande, les adapter à n’importe quelle contrainte de mise en page et garantir une lecture fiable en environnement de production.

**Prochaines étapes**

- Explorez d’autres symbologies telles que QR ou Code128 en utilisant la même classe `BarcodeGenerator`.  
- Combinez la sortie PNG avec une bibliothèque de génération de PDF (par ex., iText7) pour intégrer des codes-barres dans les factures.  
- Expérimentez `MacroPdf417` pour la transmission de données multi‑segments, une fonctionnalité utile dans les applications logistiques et de transport.

Bon codage, et que vos codes-barres soient toujours lus du premier coup !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres PDF417 en C# – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Comment générer un code-barres et personnaliser le code-barres PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Comment créer un code-barres PDF417 et exporter le PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}