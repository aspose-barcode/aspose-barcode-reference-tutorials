---
category: general
date: 2026-09-18
description: Apprenez à créer rapidement une image de code-barres PDF417 en C# et
  à définir les colonnes pour un code-barres compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Apprenez à créer rapidement une image de code-barres PDF417 en C#
  et à définir les colonnes pour un code-barres compact. Aspose.BarCode facilite le
  processus.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Créer une image de code-barres PDF417 – guide pas à pas en C#
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Comment créer une image de code-barres PDF417 en C# – guide complet
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres PDF417 en C# – guide complet

Si vous devez **créer une image de code-barres PDF417** dans une application .NET, vous êtes au bon endroit. Que vous imprimiez des étiquettes de carte d'embarquement, encodiez des données d'inventaire ou construisiez un système de billetterie mobile, le PDF417 offre des codes-barres bidimensionnels à haute capacité. Ce guide vous montre comment générer l'image avec Aspose.BarCode et comment définir les colonnes afin que le code-barres reste aussi compact que possible.

## Réponses rapides
- **Quelle bibliothèque crée des codes-barres PDF417 ?** Aspose.BarCode for .NET.
- **Combien de lignes de code sont nécessaires ?** Environ 10 lignes dans une application console.
- **Puis-je contrôler la largeur du code-barres ?** Oui, en définissant la propriété `Columns`.
- **Quel format d'image est recommandé ?** PNG pour une qualité sans perte.
- **.NET 6 est‑il pris en charge ?** Oui – la bibliothèque fonctionne avec .NET 6, .NET 7 et versions ultérieures.

## Qu'est-ce qu'une image de code-barres PDF417 ?
L'image de code-barres PDF417 est une matrice bidimensionnelle qui stocke jusqu'à 1 700 caractères par ligne, en utilisant des lignes et des colonnes pour empaqueter les données de façon dense. Aspose.BarCode rend cette matrice dans des formats d'image standard tels que PNG, JPEG ou BMP. Elle peut être enregistrée dans divers formats et convient à l'impression sur des étiquettes, des billets ou des écrans mobiles.

## Pourquoi définir les colonnes pour une image de code-barres PDF417 compacte ?
Définir les colonnes vous permet de réduire la largeur du code-barres, ce qui est essentiel pour les étiquettes étroites ou les éléments d'interface à espace limité. Aspose.BarCode prend en charge de 1 à 30 colonnes, et choisir un nombre inférieur réduit la largeur globale de l'image jusqu'à 40 % tout en préservant l'intégrité des données. Cet ajustement aide à placer les codes-barres sur de petites étiquettes sans sacrifier la lisibilité.

## Comment créer une image de code-barres PDF417 en C# ?
Chargez la bibliothèque `Aspose.BarCode`, configurez un `BarcodeGenerator` avec `EncodeTypes.Pdf417`, définissez `Columns` et `Truncate`, puis enregistrez le résultat au format PNG. Le processus complet ne nécessite que deux appels de méthode et produit un fichier image prêt à l'emploi. Vous pouvez également personnaliser les dimensions, les couleurs et ajouter du texte lisible par l'homme pour répondre aux besoins de votre application.

### Prérequis
- .NET 6+ SDK (ou plus récent)
- Visual Studio 2022 ou tout éditeur C#
- Package NuGet `Aspose.BarCode`

### Implémentation étape par étape

## Étape 1 : Installer le package NuGet Aspose.BarCode
`Aspose.BarCode` est une bibliothèque .NET pour générer et lire diverses symbologies de codes-barres.

```bash
dotnet add package Aspose.BarCode
```

Cette ligne unique importe tous les types dont vous aurez besoin, y compris `BarcodeGenerator`, `EncodeTypes` et l'énumération `BarCodeImageFormat`.

> **Astuce :** Si vous ciblez .NET Framework au lieu de .NET 6, utilisez la commande PowerShell classique `Install-Package Aspose.BarCode` dans la console du gestionnaire de packages.

## Étape 2 : Créer une application console minimale
`BarcodeGenerator` crée des images de code-barres en fonction des paramètres spécifiés. `EncodeTypes` énumère les symbologies de codes-barres prises en charge. `BarCodeImageFormat` énumère les formats d'image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Pourquoi c'est important :**  
- `EncodeTypes.Pdf417` indique à la bibliothèque que nous voulons un code-barres PDF417, pas un QR ou un Code128.  
- `XDimension.Pixels` contrôle la résolution de chaque petit module noir ou blanc.  
- Le bloc **comment définir les colonnes** influence directement la forme de l'**image de code-barres PDF417**.  
- `Truncate = true` supprime les lignes vides inutiles, vous offrant cet aspect « compact » apprécié par de nombreux scanners.

## Étape 3 : Approfondir – compréhension des colonnes et de la troncature

### Comment définir les colonnes
PDF417 organise les données dans une matrice de *lignes* × *colonnes*. La bibliothèque utilise par défaut 5 colonnes, ce qui convient à la plupart des cas. Cependant, vous pourriez avoir besoin d'un code-barres plus étroit pour s'adapter à une étiquette ou d'un plus large pour améliorer la fiabilité du scan. La propriété :

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

accepte des valeurs de **1** à **30** (la limite exacte dépend de la longueur des données). Voici une petite feuille de référence :

| Colonnes | Largeur approximative (mm) | Quand l'utiliser |
|----------|----------------------------|------------------|
| 1‑3      | Très étroite               | Petite étiquette, espace limité |
| 4‑6      | Standard                   | La plupart des reçus, tickets |
| 7‑10     | Plus large                 | Données à haute densité, meilleure lisibilité |

### Truncate (mode compact)
Définir `Truncate = true` indique à l'encodeur de couper toutes les lignes vides inutiles en bas. Le résultat est une **image de code-barres PDF417 compacte** qui occupe la plus petite surface possible tout en contenant toutes les données. Si vous obtenez des erreurs « code-barres trop grand pour l'étiquette », activez ce drapeau.

## Étape 4 : Exécuter l'application et vérifier la sortie
Compile and execute:

```bash
dotnet run
```

Vous devriez voir le message console confirmant l'emplacement d'enregistrement. Accédez au dossier et ouvrez `CompactPdf417.png`. L'image ressemblera à quelque chose comme ceci :

![Image générée du code-barres PDF417](./CompactPdf417.png "Image générée du code-barres PDF417 – PNG compact créé par Aspose.BarCode")

[Image générée du code-barres PDF417](./CompactPdf417.png "Image générée du code-barres PDF417 – PNG compact créé par Aspose.BarCode")

*Texte alternatif de l'image :* **Image générée du code-barres PDF417** – un fichier PNG compact produit par le code du tutoriel.

Si votre scanner peut le lire, félicitations—vous avez réussi à **générer un code-barres PDF417** et maîtrisé **comment définir les colonnes** pour une **image de code-barres PDF417** soignée.

## Étape 5 : Pièges courants et comment les résoudre

| Symptôme | Cause probable | Solution rapide |
|----------|----------------|-----------------|
| Le code-barres apparaît flou | `XDimension.Pixels` trop bas (par ex., 1) | Augmentez à 2‑3 pixels pour une image plus nette. |
| Le scanner ne peut pas lire | Trop de colonnes pour les données fournies | Réduisez `Columns` ou activez `Truncate`. |
| Mauvais format de fichier | Enregistré avec `BarCodeImageFormat.Jpeg` par erreur | Utilisez `BarCodeImageFormat.Png` pour des résultats sans perte. |
| Exception `ArgumentOutOfRangeException` | Le nombre de colonnes dépasse la plage autorisée | Maintenez les colonnes entre 1‑30 et assurez-vous que les données tiennent. |

## Étape 6 : Aller plus loin – personnaliser les couleurs et ajouter du texte

Si vous souhaitez que le code-barres corresponde à une palette de marque, vous pouvez ajuster les couleurs de premier plan et d'arrière-plan :

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Ou superposer du texte lisible par l'homme sous le code-barres :

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Ces ajouts sont optionnels, mais ils illustrent la flexibilité du flux de travail **générer un code-barres PDF417**.

## Conclusion
Nous avons parcouru un exemple complet, de bout en bout, qui **génère un code-barres PDF417** avec Aspose.BarCode, expliqué **comment définir les colonnes** pour contrôler les dimensions du code-barres, et enregistré le résultat sous forme d'une image **code-barres PDF417** nette au format PNG. Le code est autonome, fonctionne avec .NET 6+, et peut être intégré à n'importe quel projet existant avec un minimum d'effort.

Et ensuite ? Essayez d'encoder des charges utiles plus importantes (par ex., des chaînes JSON), expérimentez différents formats d'image, ou intégrez le générateur dans une API web qui fournit des codes-barres à la demande. Le ciel est la limite, et vous disposez maintenant d'une base solide pour construire.

Bon codage, et que vos codes-barres soient toujours lus du premier coup !

## Que devriez‑vous apprendre ensuite ?
Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer une image de code-barres en Java avec Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Générer un code-barres Java – définir la résolution d'image avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Questions fréquemment posées

**Q : Puis‑je utiliser le PNG généré dans une page web sans conversion supplémentaire ?**  
R : Oui, le PNG est nativement pris en charge par tous les navigateurs modernes, vous pouvez donc intégrer le fichier directement avec une balise `<img>`.

**Q : Combien de caractères un code-barres PDF417 peut‑il contenir ?**  
R : Jusqu'à 1 700 caractères par ligne et jusqu'à 30 lignes, ce qui donne un maximum théorique d'environ 51 000 caractères, bien que les limites pratiques dépendent des capacités du scanner.

**Q : Aspose.BarCode nécessite‑t‑il une licence pour le développement ?**  
R : Une licence d'évaluation gratuite est disponible pour les tests ; une licence commerciale est requise pour les déploiements en production.

**Q : Est‑il possible de générer des codes‑barres PDF417 dans un service en arrière‑plan ?**  
R : Absolument. La bibliothèque est thread‑safe pour les opérations en lecture seule, vous pouvez donc générer des codes‑barres dans ASP.NET Core ou les services Windows sans interaction UI.

**Q : Quels formats d'image, en plus du PNG, sont pris en charge ?**  
R : BMP, JPEG, GIF, TIFF et SVG sont tous pris en charge via l'énumération `BarCodeImageFormat`.

---

**Dernière mise à jour :** 2026-09-18  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Tutoriels associés

- [Créer un code-barres Pdf417 avec Aspose – Guide complet](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Comment générer une image de code-barres Pdf417 en C avec Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Créer un code-barres Pdf417 en C – Guide étape par étape](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}