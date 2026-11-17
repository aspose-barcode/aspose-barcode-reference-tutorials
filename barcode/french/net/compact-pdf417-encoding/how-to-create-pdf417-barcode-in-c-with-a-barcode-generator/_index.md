---
category: general
date: 2026-11-17
description: Apprenez à créer un code‑barres PDF417 en C# – un guide complet sur la
  façon de générer un code‑barres à partir d’une chaîne en utilisant un générateur
  de code‑barres C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: fr
lastmod: 2026-11-17
og_description: Créez un code‑barres PDF417 en C# rapidement. Ce tutoriel montre comment
  générer un code‑barres à partir d’une chaîne avec un générateur de code‑barres C#
  et inclut le code source complet.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Créer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Comment créer un code‑barres PDF417 en C# avec un générateur de code‑barres
url: /fr/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres PDF417 en C# avec un générateur de code-barres

Si vous devez **créer un code-barres PDF417** dans une application .NET, ce guide montre exactement comment le faire. Vous apprendrez **comment générer un code-barres** à partir d’une chaîne simple, configurer la taille du symbole et enregistrer le résultat sous forme de fichier PNG — le tout en utilisant un générateur de code-barres C# fiable.

Générer des codes-barres de façon programmatique élimine les étapes manuelles et garantit une qualité constante. Dans ce tutoriel, nous couvrirons tout, de la configuration du projet à l’image finale, afin que vous puissiez intégrer la création de code-barres dans n’importe quelle solution C# dès aujourd’hui.

## Prérequis

* .NET 6.0 SDK ou version ultérieure (le code fonctionne avec .NET Core et .NET Framework)
* Visual Studio 2022 (ou tout IDE supportant C#)
* Une licence ou un essai gratuit de **Aspose.BarCode for .NET** – la bibliothèque utilisée dans les exemples
* Familiarité de base avec la syntaxe C#

Aucun package supplémentaire n’est requis ; le package NuGet `Aspose.BarCode` contient toutes les classes dont vous avez besoin.

## Étape 1 – Configurer le générateur de code-barres C#

La première chose à faire lorsque vous **créez un code-barres PDF417** est d’instancier un objet `BarcodeGenerator`. Cet objet représente le **générateur de code-barres c#** qui gérera l’encodage, le rendu et l’enregistrement.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Pourquoi c’est important* : l’énumération `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417, qui est la même norme utilisée pour les cartes d’identité et les étiquettes de transport. La chaîne `"(01)12345678901234"` est un exemple de **générer un code-barres à partir d’une chaîne** qui montre également comment **créer un code-barres GS1**.

## Étape 2 – Configurer la dimension X (largeur du module)

La dimension X contrôle la largeur de la plus petite barre (module). Une valeur courante pour le rendu à l’écran est de 2 pixels.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Définir explicitement la dimension X empêche le générateur d’utiliser sa valeur par défaut, qui pourrait produire un code-barres trop petit pour certains lecteurs.

## Étape 3 – Définir le nombre de colonnes

PDF417 vous permet d’ajuster le nombre de colonnes, ce qui influence à la fois la forme du code-barres et sa capacité de données. Pour une étiquette compacte, quatre colonnes fonctionnent bien.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Si vous avez besoin d’un code-barres plus haut, augmentez le nombre de colonnes ; la bibliothèque calculera automatiquement le nombre de lignes requis.

## Étape 4 – Enregistrer le code-barres en tant qu’image

Enfin, exportez le code-barres vers un fichier PNG. Le PNG conserve des bords nets et prend en charge la transparence.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

L’exécution du programme crée `output/Gs1Pdf417.png`. Ouvrez le fichier dans n’importe quel visualiseur d’images — vous verrez un **code-barres PDF417** propre qui encode les données GS1 que vous avez fournies.

### Résultat attendu

![Code-barres PDF417 généré affichant le GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Code-barres PDF417 généré avec un générateur de code-barres C#"}

*L’image ci‑dessus démontre le résultat de l’exemple complet de code. Le code-barres peut être scanné par n’importe quel lecteur compatible PDF417.*

## Options supplémentaires et variantes courantes

### Modifier le format de l’image

Si vous préférez JPEG ou BMP, remplacez simplement `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. Le reste du code reste identique.

### Ajuster le niveau de correction d’erreurs

PDF417 prend en charge les niveaux de correction d’erreurs 0‑8. Des niveaux plus élevés augmentent la redondance mais agrandissent également le code-barres.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Générer d’autres codes-barres GS1

Le même `BarcodeGenerator` peut produire **créer un code-barres GS1** pour d’autres symbologies, telles que `EncodeTypes.Gs1DataMatrix` ou `EncodeTypes.Gs1Qr`. Il suffit d’échanger la valeur d’énumération :

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Gérer les données vides ou nulles

Lorsque vous **générez un code-barres à partir d’une chaîne**, validez toujours l’entrée :

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Cela évite les exceptions d’exécution et garantit que le code-barres respecte les règles de formatage GS1.

## Exemple complet et exécutable

Ci-dessous se trouve le programme complet que vous pouvez copier‑coller dans un nouveau projet console. Il inclut toutes les directives `using` nécessaires, la création de dossiers et la gestion des erreurs.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Exécutez le programme** (`dotnet run`) et vous trouverez `Gs1Pdf417.png` dans le dossier *output*. Scannez-le avec n’importe quel lecteur PDF417 pour vérifier que le GTIN `(01)12345678901234` est correctement encodé.

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code sur .NET Framework 4.6 ?**  
R : Oui. La bibliothèque Aspose.BarCode cible .NET Standard 2.0, qui est compatible avec .NET Framework 4.6 et versions ultérieures.

**Q : Et si j’ai besoin d’une image à plus haute résolution ?**  
R : Définissez la propriété `Resolution` avant d’enregistrer :

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q : Le code-barres est‑il toujours valide sans l’identifiant d’application GS1 ?**  
R : Ce sera un code-barres PDF417 standard, mais il ne sera pas reconnu comme un symbole conforme GS1. Incluez le préfixe `(01)` lorsque vous avez besoin de conformité **créer un code-barres GS1**.

## Conclusion

Vous savez maintenant comment **créer un code-barres PDF417** en C# en utilisant un **générateur de code-barres c#** robuste. Le tutoriel a couvert :

* Instanciation de `BarcodeGenerator` avec des données GS1  
* Configuration de la dimension X et du nombre de colonnes  
* Enregistrement du résultat sous forme d’image PNG  
* Extension de la solution avec correction d’erreurs, formats différents et validation des entrées  

Avec cette base, vous pouvez générer n’importe quel code-barres PDF417 ou GS1 directement à partir d’une chaîne, l’intégrer dans des rapports ou l’envoyer à des imprimantes. Explorez l’API Aspose.BarCode pour ajouter des couleurs, des marges, ou combiner plusieurs codes-barres en une seule image.

**Étapes suivantes** : essayez de générer un **créer un code-barres GS1** pour DataMatrix, expérimentez les calculs de colonnes dynamiques, ou intégrez le générateur dans un service web ASP.NET Core qui renvoie des images de code-barres à la demande.

Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres PDF417 en C# – guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Comment créer un code-barres micro PDF417 et générer un PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Comment créer un code-barres macro PDF417 en C# en utilisant Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}