---
category: general
date: 2026-10-12
description: Comment générer rapidement un code‑barres en C#. Apprenez à créer un
  code‑barres vide et à personnaliser la largeur des barres pour des codes‑barres
  postaux clairs.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: fr
lastmod: 2026-10-12
og_description: Comment générer un code-barres en C# avec Aspose.BarCode. Ce guide
  vous montre comment créer un code-barres vide et ajuster les dimensions des barres
  selon les normes postales.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: Comment générer des images de code‑barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Comment générer des images de code-barres en C# avec Aspose.BarCode
url: /fr/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des images de code-barres en C# avec Aspose.BarCode

Si vous avez besoin de **comment générer des codes-barres** à partir d'une chaîne dans une application .NET, ce guide fournit une solution complète, prête à l'emploi. Vous verrez comment générer les codes-barres standards Planet et RM4SCC, ajuster la largeur des barres pour la lisibilité, et **créer des variantes de code-barres vides** où les barres ne sont pas remplies. Le code fonctionne avec la dernière version d'Aspose.BarCode pour .NET (v.24.10) et s'exécute sur .NET 6 ou version ultérieure.

La génération de codes-barres est une exigence courante pour les étiquettes d'expédition, les systèmes d'inventaire et les plateformes de billetterie. À la fin de ce tutoriel, vous serez capable de produire à la fois des codes-barres remplis et vides de manière programmatique, sans avoir besoin d'outils externes.

## Prérequis

* .NET 6 SDK (ou toute version .NET plus récente)
* Visual Studio 2022 ou VS Code
* Une licence valide d'Aspose.BarCode pour .NET (l'évaluation gratuite fonctionne pour les tests)
* Une connaissance de base des applications console C#

Vous pouvez installer le package NuGet Aspose.BarCode avec :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer un projet console minimal

Créez un nouveau projet console et ajoutez les directives `using` requises. Le code suivant est un exemple autonome ; copiez‑le dans `Program.cs` et exécutez‑le.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Pourquoi cette étape est importante

* **Project scaffolding** garantit que le tutoriel est exécutable sans configuration supplémentaire.
* Les espaces de noms `using Aspose.BarCode.Generation;` et `using Aspose.BarCode;` exposent la classe `BarcodeGenerator` et les formats d'image.
* Créer le dossier de sortie de façon programmatique évite les erreurs « directory not found » lors du premier lancement.

## Étape 2 : Générer un code-barres Planet rempli

Le premier appel à `GeneratePlanetBarcode` passe `filled: true`. Cela produit un code-barres Planet standard où chaque barre est rendue comme un rectangle noir plein.

* **Fichier résultant** : `PostalPlanetFilledBars.png`
* **Indication visuelle** : Les barres apparaissent noires, conformément aux spécifications postales pour le courrier imprimé.

### Résultat attendu

L'exécution du programme créera une image similaire à celle ci‑dessous (l'image réelle n'est pas affichée ici, mais vous verrez un code-barres clair à 6 chiffres lorsque vous ouvrirez le fichier).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Étape 3 : Créer un code-barres vide (Planet avec barres non remplies)

Pour **créer un code-barres vide**, la même méthode est appelée avec `filled: false`. La propriété `FilledBars` indique à Aspose.BarCode de ne dessiner que les contours des barres, laissant l'intérieur transparent.

* **Fichier résultant** : `PostalPlanetEmptyBars.png`
* **Cas d'utilisation** : Les codes-barres vides sont utiles lorsque vous souhaitez que l'arrière‑plan affiche un logo ou une couleur tout en conservant la lisibilité du code-barres.

### Résultat attendu

Le PNG généré ne contient que les contours des barres :

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Étape 4 : Générer un code-barres RM4SCC rempli

RM4SCC est la norme néerlandaise de code-barres postal. L'exemple utilise la même X‑dimension (4 pixels) pour maintenir la cohérence visuelle avec les codes-barres Planet.

* **Fichier résultant** : `PostalRM4SCCFilledBars.png`
* **Pourquoi RM4SCC ?** Il encode des données numériques dans un format compact accepté par de nombreux services postaux européens.

### Résultat attendu

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Conseils pratiques et pièges courants

| Tip | Explanation |
|-----|-------------|
| **Dimension X cohérente** | Utiliser la même valeur `XDimension.Pixels` pour différentes symbologies garantit une apparence uniforme sur les étiquettes imprimées. |
| **Ne pas réutiliser la même instance de générateur** | Modifier `FilledBars` sur un générateur existant peut produire des résultats inattendus ; créez un nouveau `BarcodeGenerator` pour chaque code-barres distinct. |
| **Vérifier le format d'image** | Le PNG est sans perte et idéal pour les codes-barres ; la compression JPEG peut flouter les barres fines, entraînant des échecs de lecture. |
| **Gestion de la licence** | Si vous exécutez le code sans licence, les images générées contiendront un filigrane. Appliquez votre licence tôt dans `Main` avec `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Sécurité des threads** | `BarcodeGenerator` n'est **pas** thread‑safe. Créez des instances séparées par thread si vous générez des codes-barres en parallèle. |

## Cas limites que vous pourriez rencontrer

* **Limites de longueur des données** – Les codes-barres Planet acceptent jusqu'à 6 caractères numériques. Fournir plus de caractères déclenche une `ArgumentException`. Validez la longueur de l'entrée avant d'appeler le générateur.
* **Données non numériques** – RM4SCC attend également des données numériques. Pour des données alphanumériques, vous avez besoin d'une symbologie différente (par ex., Code128). Le même schéma de définition de `FilledBars` fonctionne pour tout type de code-barres qui le supporte.
* **Impression haute résolution** – Si vous avez besoin de codes-barres plus grands que la taille à l'écran, augmentez `XDimension.Pixels` (par ex., 8 ou 10) et éventuellement définissez `Resolution` dans `generator.Parameters.Image`. Cela maintient la netteté des barres lors d'une impression à 300 dpi.

## Récapitulatif du fichier source complet

Voici à nouveau le fichier source complet pour un copier‑coller rapide. Il inclut toutes les étapes, les commentaires et l'extrait de licence optionnel (commenté).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Conclusion

Vous savez maintenant **comment générer des images de code-barres** en C# avec Aspose.BarCode, et vous pouvez **créer des variantes de code-barres vides** en basculant la propriété `FilledBars`. Le tutoriel a couvert :

* Configurer un projet console et installer le package Aspose.BarCode
* Générer des codes-barres Planet et RM4SCC remplis
* Produire un code-barres Planet vide (contour uniquement)
* Ajuster la largeur des barres pour la lisibilité et gérer les pièges courants

Ensuite, explorez d'autres symbologies (Code128, QR, DataMatrix) et expérimentez avec la couleur, la taille et les formats d'image. Intégrer la génération de codes-barres dans une API web ou un service Windows suit le même schéma — il suffit de remplacer la méthode `Main` de la console par le point d'entrée de votre application.

Bonne programmation, et laissez vos applications commencer à scanner !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}