---
category: general
date: 2026-09-07
description: Générez un code‑barres PDF417 en C# et apprenez à définir les dimensions
  du code‑barres pour un contrôle précis. Suivez ce guide étape par étape pour créer
  une image PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: fr
lastmod: 2026-09-07
og_description: Générez un code‑barres PDF417 en C# et apprenez à définir les dimensions
  du code‑barres. Ce tutoriel présente un exemple complet et exécutable.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Générer un code‑barres PDF417 en C# – guide complet avec dimensions
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Comment générer un code‑barres PDF417 en C# avec des dimensions personnalisées
url: /fr/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres PDF417 en C# avec des dimensions personnalisées

Si vous devez **générer un code-barres PDF417** dans une application .NET, ce guide vous montre exactement comment le faire. Vous verrez un exemple complet et exécutable qui crée une image PNG tout en vous permettant de contrôler les dimensions du code-barres.

Générer un code-barres PDF417 est une exigence courante pour les systèmes d'inventaire, les cartes d'embarquement et les documents sécurisés. Dans ce tutoriel, vous apprendrez également **comment définir les dimensions du code-barres** afin que la sortie corresponde à vos besoins de mise en page.

## Prérequis

- SDK .NET 6.0 ou version ultérieure installé  
- Visual Studio 2022 (ou tout IDE compatible C#)  
- Le package NuGet **Aspose.BarCode for .NET** (ou toute bibliothèque compatible qui prend en charge PDF417)  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Créer un générateur de code-barres PDF417

La première étape consiste à instancier un `BarcodeGenerator` avec le type `EncodeTypes.Pdf417` et le texte que vous souhaitez encoder. L'objet générateur contient tous les paramètres du code-barres.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Pourquoi c’est important :** L’énumération `EncodeTypes.Pdf417` indique à la bibliothèque d’utiliser la symbologie PDF417, qui prend en charge de grandes quantités de données et la correction d’erreurs. La chaîne de texte peut contenir des caractères Unicode, vous permettant d’encoder des symboles internationaux sans effort supplémentaire.

## Étape 2 : Comment définir les dimensions du code-barres

Contrôler la taille de chaque module (le plus petit carré noir/blanc) détermine la résolution globale de l’image. La propriété `XDimension.Pixels` définit la largeur en pixels d’un module.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c’est important :** Un `XDimension` plus grand produit une image à plus haute résolution, ce qui est utile pour l’impression ou la numérisation à distance. À l’inverse, une valeur plus petite réduit la taille du fichier pour une utilisation web.

## Étape 3 : Définir la mise en page PDF417 (colonnes et lignes)

PDF417 vous permet d’influencer la forme de la matrice en spécifiant le nombre de colonnes et de lignes. Cela peut affecter la lisibilité et la taille physique du code-barres.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Pourquoi c’est important :** Ajuster le nombre de colonnes et de lignes vous permet d’adapter le code-barres à un espace spécifique ou de répondre aux exigences de rapport d’aspect du scanner. La bibliothèque ajoute automatiquement un remplissage si les données ne remplissent pas complètement la matrice.

## Étape 4 : Enregistrer le code-barres en tant qu’image PNG

Enfin, écrivez le code-barres généré dans un fichier. PNG conserve une qualité sans perte, ce qui le rend idéal pour un traitement ultérieur.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Lorsque vous exécutez le programme, `Pdf417Layout.png` apparaît dans le dossier de sortie du projet. L’image ressemble à ceci :

![Image du code-barres PDF417 généré avec des dimensions personnalisées](og_image_placeholder.png)

*Texte alternatif de l’image : Image du code-barres PDF417 généré avec des dimensions personnalisées*  

**Pourquoi c’est important :** En enregistrant au format PNG, vous vous assurez que les dimensions exactes des modules que vous avez définies sont conservées, ce qui est crucial pour les applications de numérisation en aval.

## Exemple complet en un seul bloc

Voici le programme complet que vous pouvez copier, coller et exécuter sans modifications (à l’exception du chemin de sortie si vous le souhaitez).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Résultat attendu

- **Fichier :** `Pdf417Layout.png` (PNG, sans perte)  
- **Dimensions :** Déterminées par `XDimension` (2 px) × matrice (colonnes × lignes)  
- **Contenu :** Un code-barres PDF417 scannable encodant la chaîne Unicode `Åspóse.Barcóde©`

## Questions fréquentes et cas particuliers

### Que faire si j’ai besoin d’une image plus grande pour l’impression ?

Augmentez `XDimension.Pixels` à 4 ou 5. Des valeurs plus élevées produisent un code-barres à plus haute résolution mais augmentent également la taille du fichier.

### Puis-je encoder plus de données que la chaîne d’exemple ?

Oui. PDF417 peut contenir jusqu’à 1 850 caractères. Remplacez simplement l’argument texte dans le constructeur `BarcodeGenerator`. Si les données dépassent la capacité de la matrice, la bibliothèque ajoute automatiquement des lignes supplémentaires.

### Comment fonctionne la correction d’erreurs ?

PDF417 inclut une correction d’erreurs intégrée. Vous pouvez ajuster son niveau via :

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Des niveaux plus élevés augmentent la robustesse au prix de codes-barres plus grands.

### Que faire si le code-barres apparaît flou à l’écran ?

Assurez‑vous que le DPI de l’image de sortie correspond à l’environnement d’affichage. Vous pouvez définir le DPI lors de l’enregistrement :

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Astuces professionnelles

- **Astuce :** Testez toujours le code-barres généré avec le scanner réel que vous prévoyez d’utiliser. Différents appareils ont des tolérances variables pour la taille des modules et les zones calmes.  
- **Attention :** Des valeurs très petites de `XDimension` (< 1 px) peuvent apparaître comme des lignes invisibles sur des écrans à haute résolution DPI.  
- **Conseil pour les applications web :** Servez le PNG avec `Cache-Control: public, max-age=86400` pour réduire la surcharge de génération répétée.

## Conclusion

Vous savez maintenant comment **générer un code-barres PDF417** en C# et définir précisément les **dimensions du code-barres** pour répondre à n’importe quelle exigence. L’exemple complet et exécutable montre la création d’une image PNG avec une disposition personnalisée de colonnes/lignes et une taille de module, prête pour l’impression ou la distribution numérique.

### Prochaines étapes

- Explorez **comment générer un code-barres PDF417** avec différents formats d’image (JPEG, BMP).  
- Apprenez **comment définir les dimensions du code-barres** dynamiquement en fonction des entrées utilisateur ou du DPI de l’appareil.  
- Intégrez la génération de code-barres dans une API ASP.NET Core pour servir les codes-barres à la demande.

N’hésitez pas à expérimenter d’autres paramètres PDF417 tels que la correction d’erreurs, les marges et la couleur. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment définir le niveau d’erreur dans le code-barres PDF417 – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Comment enregistrer un code-barres en C# – Générer des codes-barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Générer un code-barres PDF417 en C# – Guide complet](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}