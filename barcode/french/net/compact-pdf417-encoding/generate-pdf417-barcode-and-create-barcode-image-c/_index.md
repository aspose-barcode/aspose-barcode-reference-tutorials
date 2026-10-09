---
category: general
date: 2026-10-08
description: Générez un code‑barres PDF417 en C# et apprenez comment créer des images
  PDF417 efficacement avec Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: fr
lastmod: 2026-10-08
og_description: Générez un code‑barres PDF417 en C# avec un guide étape par étape.
  Apprenez à générer un PDF417 et à enregistrer l’image du code‑barres au format PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Générer un code-barres PDF417 et créer une image de code-barres en C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Générer un code‑barres PDF417 et créer une image de code‑barres C#
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 et créer une image de code‑barres C#

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce tutoriel vous montre exactement comment le faire. Vous verrez un exemple complet et exécutable qui crée un code‑barres, personnalise sa mise en page et enregistre le résultat sous forme d’image PNG.

La génération d’un code‑barres PDF417 est une exigence courante pour les étiquettes d’expédition, les cartes d’embarquement et les systèmes d’inventaire. À la fin de ce guide, vous saurez **comment générer PDF417** avec un contrôle fin sur la taille et la mise en page, et vous apprendrez également à **créer une image de code‑barres C#** qui peut être affichée dans une interface utilisateur ou envoyée à une imprimante.

## Prérequis

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7.2+)
- Visual Studio 2022 ou tout IDE compatible C#
- Aspose.BarCode for .NET (version d’essai gratuite ou version sous licence)  
  Installez‑le via NuGet :

```bash
dotnet add package Aspose.BarCode
```

Aucune configuration supplémentaire n’est requise ; la bibliothèque gère l’encodage PNG en interne.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et ajoutez les directives `using` nécessaires. Ce bloc comprend tout ce dont vous avez besoin pour compiler l’exemple.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Pourquoi cette étape est importante* : l’importation de l’espace de noms `Aspose.BarCode.Generation` vous donne accès à `BarcodeGenerator`, `EncodeTypes` et aux objets de paramètres utilisés pour personnaliser le code‑barres.

## Étape 2 : Générer le code‑barres PDF417 avec le texte souhaité

Dans `Main`, instanciez `BarcodeGenerator` avec `EncodeTypes.Pdf417`. Le constructeur prend le type de code‑barres et le texte que vous voulez encoder.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Explication* : `EncodeTypes.Pdf417` indique à la bibliothèque de produire une symbologie PDF417. La chaîne `"Layout demo"` devient la charge utile de données encodée dans le code‑barres.

## Étape 3 : Ajuster finement la taille du code‑barres avec la X‑dimension

La X‑dimension contrôle la largeur d’un seul module (le plus petit carré noir/blanc). La définir en pixels permet un contrôle précis de la taille finale de l’image.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Pourquoi c’est important* : une X‑dimension plus petite produit un code‑barres plus compact, ce qui est utile lorsque l’espace sur une étiquette ou un élément d’interface est limité.

## Étape 4 : Personnaliser la mise en page du PDF417 (colonnes et lignes)

PDF417 vous permet de spécifier le nombre de colonnes et de lignes. Modifier ces valeurs change le rapport d’aspect du code‑barres.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Explication* : avec 4 colonnes et 9 lignes, le code‑barres devient plus haut que large, correspondant à de nombreux formats d’impression de billets.

## Étape 5 : Enregistrer le code‑barres généré sous forme d’image PNG

Enfin, écrivez le code‑barres dans un fichier. L’énumération `BarCodeImageFormat.Png` garantit une compression sans perte.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Ce qui se passe ici* : `Save` crée le fichier image sur le disque. Vous pouvez remplacer `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` si un autre format est requis.

### Exemple complet en un seul bloc

Voici le programme complet, prêt à être exécuté. Remplacez `YOUR_DIRECTORY` par le chemin réel d’un dossier sur votre machine.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Exécutez le programme (`dotnet run`) et ouvrez le fichier `LayoutPdf417.png` généré. Vous devriez voir un code‑barres PDF417 propre qui encode le texte *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Code-barres PDF417 généré enregistré en PNG"}

*Résultat attendu* : un fichier PNG d’environ 150 × 300 pixels (la taille varie selon la X‑dimension) contenant un code‑barres PDF417 lisible.

## Variations courantes et cas limites

| Scénario | Comment adapter le code |
|----------|--------------------------|
| **Charge utile de données différente** | Changez le deuxième argument de `BarcodeGenerator` (`"Layout demo"` → n’importe quelle chaîne, jusqu’à 1 800 caractères). |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` (par ex., `4`) ou définissez `Resolution` via `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Arrière‑plan transparent** | Utilisez `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Intégration dans un PictureBox Windows Forms** | Au lieu de `Save`, appelez `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Gestion des erreurs** | Enveloppez le code de génération dans un bloc `try…catch` pour capturer `BarCodeException` en cas de caractères non pris en charge. |

## Astuces professionnelles

- **Valider le code‑barres** : après l’enregistrement, vous pouvez charger le PNG avec un SDK de lecteur de code‑barres pour vérifier que les données correspondent à la chaîne d’origine.
- **Performance** : réutiliser une même instance de `BarcodeGenerator` pour plusieurs codes‑barres réduit la surcharge d’allocation.
- **Sécurité** : si les données encodées contiennent des informations sensibles, envisagez de les chiffrer avant de les transmettre au générateur.

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C# et **créer des fichiers d’image de code‑barres C#** répondant à des exigences de mise en page personnalisées. L’exemple complet montre comment initialiser le générateur, ajuster la taille et la mise en page, puis enregistrer le résultat sous forme de PNG. À partir d’ici, vous pouvez explorer des fonctionnalités supplémentaires telles que la personnalisation des couleurs, l’insertion de logos ou la génération en lot de plusieurs codes‑barres pour une impression massive.

---

*Prochaines étapes* :  
- Expérimentez d’autres symbologies (Code128, QR) en utilisant la même classe `BarcodeGenerator`.  
- Apprenez à lire les codes‑barres PDF417 avec le `BarCodeReader` d’Aspose.BarCode.  
- Intégrez le PNG généré dans les vues ASP.NET Core MVC pour un rendu de code‑barres à la volée.

## Que devez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}