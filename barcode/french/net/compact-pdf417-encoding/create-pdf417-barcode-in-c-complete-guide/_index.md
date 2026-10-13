---
category: general
date: 2026-09-22
description: Créer un code‑barres PDF417 en C# avec Aspose.BarCode. Apprenez à générer
  des images de code‑barres PDF417, à définir les colonnes/lignes et à les enregistrer
  au format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
language: fr
lastmod: 2026-09-22
og_description: Créez un code‑barcode PDF417 en C# avec Aspose.BarCode. Apprenez à
  générer des images de code‑barcode PDF417, à personnaliser la mise en page et à
  exporter en PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Créer un code‑barres PDF417 en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
    PDF417 barcode images, set columns/rows, and save as PNG.
  headline: Create PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
- image generation
title: Créer un code‑barres PDF417 en C# – guide complet
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres PDF417 en C# – guide complet

Si vous devez **créer un code‑barres PDF417** dans une application .NET, ce tutoriel vous montre exactement comment faire. Vous verrez un exemple complet, exécutable, qui génère un code‑barres PDF417, personnalise sa disposition en colonnes et lignes, puis enregistre le résultat sous forme d’image PNG.

La génération de codes‑barres est une exigence courante pour les systèmes d’inventaire, les plateformes de billetterie et l’automatisation de documents. À la fin de ce guide, vous serez capable de répondre à la question *comment générer un code‑barres PDF417* de façon programmatique, sans quitter votre IDE.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- .NET 6.0 ou version ultérieure installé (le code fonctionne également avec .NET Framework 4.8)
- Une version récente de **Aspose.BarCode for .NET** (l’essai gratuit suffit pour le développement)
- Un IDE tel que Visual Studio 2022 ou Visual Studio Code
- Une connaissance de base de la syntaxe C#

> **Astuce :** Si vous utilisez une chaîne CI/CD, ajoutez le package NuGet `Aspose.BarCode` à votre fichier projet afin que la restauration s’effectue automatiquement lors de la construction.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable de la bibliothèque à votre projet et met à jour le fichier `.csproj` en conséquence.

## Étape 2 : Créer un générateur de code‑barres PDF417

L’objet générateur est le point d’entrée pour toutes les opérations de code‑barres. Vous spécifiez la symbologie (`EncodeTypes.Pdf417`) et le texte que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;

// ...

// Step 2: Instantiate the generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

La classe `BarcodeGenerator` encapsule l’algorithme d’encodage, de sorte que vous n’avez pas à gérer la manipulation de bits de bas niveau.

## Étape 3 : Ajuster la mise en page PDF417 – colonnes et lignes

PDF417 vous permet de contrôler le nombre de colonnes (modules horizontaux) et de lignes (modules verticaux). Modifier ces valeurs change la densité et la taille physique du code‑barres.

```csharp
// Step 3: Configure layout
generator.Parameters.Barcode.Pdf417.Columns = 4; // supported range: 2‑10
generator.Parameters.Barcode.Pdf417.Rows = 9;    // optional; if omitted, rows are auto‑calculated
```

- **Colonnes** : Détermine le nombre de colonnes de données que le code‑barres contiendra. Moins de colonnes produisent un code‑barres plus haut.
- **Lignes** : Vous permet de forcer une hauteur spécifique. Le laisser à `0` laisse le moteur choisir le nombre optimal.

## Étape 4 : Enregistrer l’image du code‑barres au format PNG

Enfin, exportez le code‑barres vers un format d’image compatible avec la plupart des frameworks UI.

```csharp
using Aspose.BarCode;

// ...

// Step 4: Save as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

L’énumération `BarCodeImageFormat.Png` garantit une compression sans perte, idéale pour un traitement ultérieur ou l’impression.

## Exemple complet fonctionnel

Rassemblez le tout dans une application console nommée `Pdf417Demo`.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Install Aspose.BarCode via NuGet before running this code

            // 2️⃣ Create the generator
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 3️⃣ Set layout – 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;

            // 4️⃣ Define output path
            string outputPath = Path.Combine(
                Environment.CurrentDirectory, "Pdf417_4x9.png");

            // 5️⃣ Save the barcode
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created at: {outputPath}");
        }
    }
}
```

### Résultat attendu

L’exécution du programme affiche une ligne de confirmation et crée un fichier similaire à la capture d’écran ci‑dessous :

![Generated PDF417 barcode](/images/pdf417-example.png "Create PDF417 barcode – PNG output")

Le fichier `Pdf417_4x9.png` enregistré contient un symbole PDF417 clair et lisible qui encode le texte **« Sample »**.

## Comment générer un code‑barres PDF417 avec des données personnalisées

Si vous devez encoder plus qu’un seul mot, remplacez simplement le deuxième argument de `BarcodeGenerator` par n’importe quelle chaîne (y compris des sauts de ligne). La bibliothèque répartit automatiquement les données sur les lignes et colonnes selon la mise en page que vous avez définie.

```csharp
var generator = new BarcodeGenerator(
    EncodeTypes.Pdf417,
    "OrderID: 12345\nDate: 2026-09-22\nCustomer: John Doe");
```

Les mêmes paramètres de mise en page (colonnes = 4, lignes = 9) s’appliquent toujours, mais le code‑barres s’allongera verticalement si les données dépassent l’espace disponible.

## Cas limites et dépannage

| Situation | À vérifier | Correction recommandée |
|-----------|------------|------------------------|
| Le code‑barres apparaît trop petit à l’écran | DPI du PNG enregistré | Passer un objet `Resolution` : `generator.Save(path, BarCodeImageFormat.Png, new Resolution(300))` |
| Les lignes sont ignorées | `Rows` à `0` ou non défini | Attribuer explicitement un entier positif (ex. : `Rows = 9`) |
| Le texte est tronqué | Nombre de colonnes trop faible pour la longueur des données | Augmenter `Columns` (max 10) ou laisser le moteur auto‑dimensionner avec `Columns = 0` |
| Le scan échoue sur mobile | Contraste insuffisant | Utiliser `generator.Parameters.Barcode.ForegroundColor = Color.Black` et `BackgroundColor = Color.White` |

Ces astuces vous aident à affiner le code‑barres pour les appareils de lecture du monde réel.

## Pourquoi choisir Aspose.BarCode pour le PDF417

- **Contrôle total** sur la mise en page (colonnes, lignes, correction d’erreurs)
- **Génération d’image sans dépendance** – aucune bibliothèque graphique externe requise
- **Support multiplateforme** (Windows, Linux, macOS) grâce à .NET Standard
- **Documentation exhaustive** et exemples de code fournis directement par le vendeur

Utiliser cette bibliothèque garantit que la tâche **créer un code‑barres PDF417** reste maintenable et pérenne.

## Conclusion

Vous savez maintenant comment **créer un code‑barres PDF417** en C# avec Aspose.BarCode, ajuster ses colonnes et lignes, puis exporter le résultat sous forme de fichier PNG. Cette solution complète répond à la question *comment générer un code‑barres PDF417* pour tout projet .NET, et vous pouvez l’étendre en modifiant le texte encodé, le format d’image ou la résolution.

**Prochaines étapes**

- Expérimentez d’autres formats d’image tels que `Jpeg` ou `Bmp`.
- Combinez le code‑barres avec un document PDF à l’aide de `Aspose.PDF` pour une génération de rapports de bout en bout.
- Explorez les niveaux de correction d’erreurs (`generator.Parameters.Barcode.Pdf417.ErrorLevel`) afin d’améliorer la fiabilité du scan dans des environnements bruyants.

Bon codage, et profitez d’intégrer des symboles PDF417 robustes dans vos applications !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment enregistrer un code‑barres en C# – Générer des codes‑barres PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Exemple Aspose barcode : générer un Macro PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Générer un code‑barres PDF417 C# – guide complet avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}