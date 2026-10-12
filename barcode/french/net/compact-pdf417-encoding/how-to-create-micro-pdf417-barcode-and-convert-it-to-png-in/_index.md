---
category: general
date: 2026-10-12
description: Apprenez à créer un code‑barres micro PDF417 et à le convertir en PNG
  avec C#. Guide étape par étape avec le code complet et des astuces.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: fr
lastmod: 2026-10-12
og_description: Créez un code‑barres micro PDF417 et convertissez‑le en PNG avec C#.
  Suivez ce guide complet pour générer les versions standard et GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Créer un code‑barres micro PDF417 et le convertir en PNG – Tutoriel C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Comment créer un code‑barres micro PDF417 et le convertir en PNG en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres micro PDF417 et le convertir en PNG en C#

Si vous devez **create micro PDF417 barcode** dans une application .NET, ce tutoriel vous montre exactement comment faire. Vous verrez un exemple complet et exécutable qui génère à la fois un code‑barres Micro PDF417 standard et une version conforme GS1, puis **convert barcode to PNG** pour une utilisation en aval telle que l’impression ou l’affichage web.

Générer un code‑barres, c’est plus que simplement appeler une méthode unique — choisir la bonne taille de module, le nombre de colonnes et le format d’encodage détermine la fiabilité de la lecture. À la fin de ce guide, vous comprendrez pourquoi chaque paramètre est important et comment les ajuster pour vos propres projets.

## Prérequis

| Exigence | Raison |
|----------|--------|
| .NET 6.0 SDK or later | Fournit le runtime pour l'application console C# |
| Visual Studio 2022 (or any C# IDE) | Facilite l'édition et le débogage |
| **Aspose.BarCode for .NET** NuGet package | Fournit les classes `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat` |
| Write permission to the output folder | Nécessaire pour les appels `Save` qui créent des fichiers PNG |

Vous pouvez ajouter le package Aspose.BarCode via la CLI :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer un projet console minimal

Créez un nouveau projet console et référencez la bibliothèque de codes‑barres. Le `Program.cs` suivant contient tout le code nécessaire ; aucun fichier externe n’est requis.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Le premier crée un code‑barres Micro PDF417 simple, tandis que le second suit les normes GS1, en incorporant les Identifiants d’Application (AIs). Choisissez en fonction de si votre système en aval attend des données GS1.
* **`XDimension.Pixels = 2`** – Contrôle la largeur du module. Des valeurs plus petites créent une image plus dense mais peuvent devenir illisibles sur des scanners à basse résolution. Deux pixels est une valeur sûre pour la plupart des imprimantes d’étiquettes.
* **`Pdf417.Columns = 4`** – Micro PDF417 vous permet de limiter le nombre de colonnes, réduisant ainsi la largeur globale. Quatre colonnes maintiennent le code‑barres compact sans sacrifier la capacité de données pour de courtes charges utiles.
* **`BarCodeImageFormat.Png`** – PNG conserve une qualité sans perte, essentielle pour la clarté du code‑barres. C’est pourquoi nous **convert barcode to PNG** plutôt que JPEG.

## Étape 2 : Exécuter le programme et vérifier la sortie

1. Construisez le projet : `dotnet build`.
2. Exécutez : `dotnet run`.

Vous devriez voir des messages console similaires à :

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Ouvrez les fichiers PNG générés avec n’importe quel visualiseur d’image. Les deux images affichent un code‑barres net et à fort contraste, prêt à être scanné.

### Résultat visuel attendu

| Type de code‑barres | Apparence |
|---------------------|-----------|
| **Micro PDF417** | Petit motif rectangulaire avec 4 colonnes, lisible par la plupart des scanners de codes‑barres 2‑D. |
| **GS1 Micro PDF417** | Même taille mais encode les AIs GS1 ; un scanner qui comprend GS1 renverra le GTIN et le numéro de série. |

Si un scanner ne parvient pas à lire l’image, essayez d’augmenter `XDimension.Pixels` à **3** ou **4**, ou réduisez le nombre de colonnes pour le Micro PDF417 standard.

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| Code‑barres flou après impression | Paramètres d’imprimante à basse résolution DPI | Exporter le PNG à 300 dpi ou plus, ou laisser le pilote d’imprimante gérer le redimensionnement. |
| Le scanner renvoie « données invalides » | Format AI GS1 manquant ou mal formé | Assurez‑vous que chaque AI est entouré de parenthèses et respecte la spécification GS1 (par ex., `(01)` pour GTIN‑14). |
| Fichier image non créé | Le dossier de sortie n’a pas les permissions d’écriture | Exécutez le programme avec des droits élevés ou choisissez un dossier comme `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Code‑barres trop grand pour l’étiquette | Nombre de colonnes par défaut trop élevé | Réduisez `Pdf417.Columns` (par ex., à **3**) ou augmentez `XDimension` pour diminuer la taille globale. |

## Étendre l’exemple

* **Different image formats** – Remplacez `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` si votre flux de travail le nécessite. PNG reste le meilleur choix pour une qualité sans perte.
* **Dynamic data** – Transmettez les entrées utilisateur ou les valeurs de base de données au constructeur `BarcodeGenerator` pour créer des codes‑barres à la volée.
* **Batch generation** – Encapsulez la logique de création dans une boucle qui lit les lignes d’un fichier CSV et enregistre chaque code‑barres avec un nom de fichier unique.

## Conclusion

Vous savez maintenant comment **create micro PDF417 barcode** en C# et **convert barcode to PNG** pour les scénarios standard et conformes GS1. Le code complet et exécutable montre les paramètres essentiels — dimension X, nombre de colonnes et type d’encodage — afin que vous puissiez adapter la solution à tout projet .NET nécessitant des codes‑barres 2‑D compacts et de haute qualité.

*Prochaines étapes* : explorez d’autres symbologies prises en charge par Aspose.BarCode (par ex., QR, DataMatrix), expérimentez différentes valeurs `XDimension` pour l’impression haute résolution, ou intégrez les PNG générés dans une API web qui fournit des codes‑barres à la demande.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres micro pdf417 en C# et l’enregistrer en PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Créer un code‑barres PNG en C# – guide complet du GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Générer un code‑barres Micro PDF417 en C# – Guide complet](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}