---
category: general
date: 2026-07-15
description: Générez rapidement un code‑barres PDF417 et apprenez comment définir
  les colonnes pour une image de code‑barres PDF417 compacte en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set columns
- pdf417 barcode image
- Aspose.BarCode PDF417
- C# barcode generation
- compact PDF417
language: fr
lastmod: 2026-07-15
og_description: Générez un code‑barres PDF417 avec Aspose.BarCode et apprenez comment
  définir les colonnes pour créer une image de code‑barres PDF417 compacte.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Générer un code‑barres PDF417 en C# – Guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly and learn how to set columns for a
    compact PDF417 barcode image in C#.
  headline: Generate PDF417 Barcode in C# – Complete Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Générer un code‑barres PDF417 en C# – Guide complet
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres PDF417 en C# – Guide complet

Vous avez déjà eu besoin de **générer un code-barres PDF417** dans un projet .NET mais vous ne saviez pas par où commencer ? Vous n'êtes pas seul. Dans de nombreuses applications d'entreprise — pensez aux imprimantes de cartes d'embarquement, aux étiquettes d'inventaire ou à la billetterie mobile — le PDF417 est le cheval de bataille qui emporte beaucoup de données dans un petit espace visuel.

Voici le point clé : la bibliothèque Aspose.BarCode rend le processus presque indolore, et vous pouvez même contrôler **comment définir les colonnes** afin que le code-barres soit aussi compact que possible. À la fin de ce tutoriel, vous disposerez d’une image PNG prête à l’emploi d’un **code-barres PDF417** que vous pourrez insérer dans n’importe quelle interface, e‑mail ou tâche d’impression.

## Ce que vous retirerez de ce tutoriel

- Une application console C# entièrement fonctionnelle qui crée un code-barres PDF417.
- Une compréhension claire de la *X‑Dimension* (taille du module) et de son importance.
- Des instructions étape par étape sur **comment définir les colonnes** pour un code-barres plus compact.
- Un fichier `PNG` enregistré que vous pouvez ouvrir immédiatement pour vérifier le résultat.
- Des astuces pour résoudre les problèmes courants (par ex., codes-barres illisibles, mauvais format d’image).

> **Prérequis** – SDK .NET 6+, Visual Studio 2022 (ou tout éditeur de votre choix), et une référence NuGet à `Aspose.BarCode`. Rien d’autre.

---

## Étape 1 : Installer le package NuGet Aspose.BarCode

Avant de pouvoir *générer un code-barres PDF417*, la bibliothèque doit être présente dans le projet.

```bash
dotnet add package Aspose.BarCode
```

Cette seule ligne importe tous les types dont vous aurez besoin, y compris `BarcodeGenerator`, `EncodeTypes` et l’énumération `BarCodeImageFormat`.

> **Astuce :** Si vous ciblez le .NET Framework au lieu de .NET 6, utilisez la commande PowerShell classique `Install-Package Aspose.BarCode` dans la console du gestionnaire de packages.

---

## Étape 2 : Créer une application console minimale

Créons une petite application qui ne fait rien d’autre que produire un code-barres. Ouvrez un nouveau dossier, exécutez `dotnet new console`, puis remplacez le fichier `Program.cs` généré automatiquement par le code ci‑dessous.

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

**Pourquoi c’est important :**  
- `EncodeTypes.Pdf417` indique à la bibliothèque que nous voulons un code-barres PDF417, pas un QR ou un Code128.  
- `XDimension.Pixels` contrôle la résolution de chaque petit module noir ou blanc.  
- Le bloc **comment définir les colonnes** influence directement la forme de l’**image du code-barres PDF417**.  
- `Truncate = true` supprime toutes les lignes vides inutiles, vous offrant cet aspect « compact » apprécié par de nombreux scanners.

---

## Étape 3 : Approfondir – Comprendre les colonnes et la troncature

### Comment définir les colonnes

PDF417 organise les données dans une matrice de *lignes* × *colonnes*. La bibliothèque utilise par défaut 5 colonnes, ce qui convient à la plupart des cas. Cependant, il peut être nécessaire d’avoir un code-barres plus étroit pour s’adapter à une étiquette ou plus large pour améliorer la fiabilité de la lecture. La propriété :

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

accepte des valeurs de **1** à **30** (la limite exacte dépend de la longueur des données). Voici une petite feuille de triche :

| Colonnes | Largeur approximative (mm) | Quand l’utiliser |
|----------|----------------------------|-------------------|
| 1‑3      | Très étroite               | Petite étiquette, espace limité |
| 4‑6      | Standard                   | La plupart des reçus, tickets |
| 7‑10     | Plus large                 | Données à haute densité, meilleure lisibilité |

### Troncature (Mode compact)

Définir `Truncate = true` indique à l’encodeur de couper toutes les lignes vides inutiles en bas. Le résultat est une **image de code-barres PDF417 compacte** qui occupe la plus petite surface possible tout en contenant toutes les données. Si vous obtenez un jour des erreurs « code-barres trop grand pour l’étiquette », basculez ce drapeau.

---

## Étape 4 : Exécuter l’application et vérifier la sortie

Compile and execute:

```bash
dotnet run
```

Vous devriez voir le message de la console confirmant l’emplacement d’enregistrement. Accédez au dossier et ouvrez `CompactPdf417.png`. L’image ressemblera à ceci :

![Image du code-barres PDF417 généré](./CompactPdf417.png "Image du code-barres PDF417 généré – PNG compact créé par Aspose.BarCode")

*Texte alternatif de l’image :* **Image du code-barres PDF417 généré** – un fichier PNG compact produit par le code du tutoriel.

Si votre scanner peut le lire, félicitations — vous avez réussi à **générer un code-barres PDF417** et maîtrisé **comment définir les colonnes** pour une **image de code-barres PDF417** soignée.

---

## Étape 5 : Problèmes courants et comment les résoudre

| Symptôme | Cause probable | Solution rapide |
|----------|----------------|-----------------|
| Le code-barres apparaît flou | `XDimension.Pixels` trop faible (ex., 1) | Augmentez à 2‑3 pixels pour une image plus nette. |
| Le scanner ne peut pas lire | Trop de colonnes pour les données fournies | Réduisez `Columns` ou activez `Truncate`. |
| Mauvais format de fichier | Enregistré avec `BarCodeImageFormat.Jpeg` par erreur | Utilisez `BarCodeImageFormat.Png` pour des résultats sans perte. |
| Exception `ArgumentOutOfRangeException` | Le nombre de colonnes dépasse la plage autorisée | Gardez les colonnes entre 1‑30 et assurez-vous que les données tiennent. |

---

## Étape 6 : Aller plus loin – Personnaliser les couleurs et ajouter du texte

Si vous souhaitez que le code-barres corresponde à la palette d’une marque, vous pouvez ajuster les couleurs de premier plan et d’arrière‑plan :

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Ou superposer du texte lisible par l’homme sous le code-barres :

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Ces ajouts sont optionnels, mais ils illustrent la flexibilité du flux de travail **générer un code-barres PDF417**.

---

## Conclusion

Nous avons parcouru un exemple complet, de bout en bout, qui **génère un code-barres PDF417** à l’aide d’Aspose.BarCode, expliqué **comment définir les colonnes** pour contrôler les dimensions du code-barres, et enregistré le résultat sous forme d’une image **PDF417 nette** au format PNG. Le code est autonome, fonctionne avec .NET 6+, et peut être intégré à n’importe quel projet existant avec un minimum d’effort.

Et ensuite ? Essayez d’encoder des charges utiles plus importantes (par ex., des charges JSON), expérimentez différents formats d’image, ou intégrez le générateur dans une API web qui fournit des codes-barres à la demande. Le ciel est la limite, et vous disposez maintenant d’une base solide pour construire.

Bon codage, et que vos codes-barres soient toujours lus du premier coup !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer une image de code-barres en Java avec Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Générer un code-barres Java – Définir la résolution d’image avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}