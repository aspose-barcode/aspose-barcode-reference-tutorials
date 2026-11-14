---
category: general
date: 2026-11-14
description: Créer un code‑barres micro PDF417 en C# avec Aspose.BarCode – guide étape
  par étape couvrant la configuration du générateur, la dimension X, les colonnes
  et l’exportation PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: fr
lastmod: 2026-11-14
og_description: Créer un code‑barres micro PDF417 en C# avec Aspose.BarCode. Apprenez
  à configurer le générateur, définir XDimension, choisir les colonnes et exporter
  en PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Créer un code-barres micro PDF417 en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Comment créer un code‑barres micro PDF417 en C#
url: /fr/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres micro PDF417 en C#  

Si vous devez **créer un code-barres micro PDF417** rapidement, ce guide vous montre une solution complète, prête à l’emploi. Vous verrez comment instancier le générateur de code-barres, configurer la X‑dimension, choisir le nombre de colonnes, et enfin enregistrer le résultat sous forme d’image PNG — le tout en utilisant la bibliothèque Aspose.BarCode pour .NET.

Générer un code-barres micro PDF417 ne nécessite pas de pipeline de construction complexe. À la fin de ce tutoriel, vous disposerez d’un seul fichier C# qui produit une image de code-barres de haute qualité que vous pouvez intégrer dans des rapports, des étiquettes ou des applications mobiles.

## Prérequis  

Avant de commencer, assurez-vous d’avoir :

* SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+).  
* Un environnement de développement tel que Visual Studio 2022, VS Code ou Rider.  
* Une licence Aspose.BarCode pour .NET (ou une clé d’évaluation gratuite). Vous pouvez l’obtenir sur le site [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Astuce :** Si vous utilisez la version d’évaluation, le PNG généré contiendra un petit filigrane « Evaluation ». Une version sous licence le supprime automatiquement.

## Étape 1 : Configurer le projet  

Créez un nouveau projet console et ajoutez le package NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

La commande `dotnet add package` récupère les dépendances de l’**exemple Aspose.BarCode C#**, de sorte que vous n’avez pas à gérer les DLLs manuellement.

## Étape 2 : Écrire le code complet  

Remplacez le fichier `Program.cs` auto‑généré par le code suivant. Il montre comment **créer un code-barres micro pdf417** du début à la fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante  

* **Constructeur BarcodeGenerator** – Instancie le **générateur de code-barres micro pdf417** avec le texte que vous souhaitez encoder.  
* **XDimension.Pixels** – Contrôle la largeur du module ; le définir à `2` pixels produit un code-barres dense et haute résolution, adapté à la plupart des lecteurs.  
* **Pdf417.Columns** – MicroPDF417 ne prend en charge que 1 à 4 colonnes. Choisir `4` réduit la hauteur du code-barres, ce qui est utile lorsque l’espace vertical est limité.  
* **Méthode Save** – Enregistre le code-barres dans un fichier PNG. Le PNG est sans perte, garantissant que le lecteur lit exactement le motif que vous avez généré.

## Étape 3 : Compiler et exécuter  

Compilez et exécutez le programme :

```bash
dotnet run
```

Vous devriez voir la sortie console :

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Un fichier nommé **MicroPdf417.png** apparaît dans le dossier du projet. Ouvrez-le avec n’importe quel visualiseur d’images ; vous verrez un code‑barres micro PDF417 net qui encode la chaîne `"Åspóse.Barcóde©"`.

![Exemple de code-barres micro PDF417 généré](MicroPdf417.png "Exemple de code-barres micro PDF417 généré"){.center-image width=400 alt="Exemple d'image de code-barres micro PDF417 généré"}

*L'image ci‑dessus est le résultat du code présenté à l'étape 2.*

## Étape 4 : Variantes courantes et cas limites  

| Situation | How to adapt the code |
|-----------|----------------------|
| **Longueur de données différente** | MicroPDF417 peut encoder jusqu’à 1 200 caractères. Il suffit de changer le deuxième argument de `BarcodeGenerator`. |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` à `3` ou `4`. Des modules plus grands améliorent la lisibilité sur les lecteurs basse résolution mais augmentent la taille de l’image. |
| **Couleurs personnalisées** | Après avoir créé le générateur, définissez `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` et `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Enregistrement dans d’autres formats** | Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins en aval. |
| **Intégration dans un PDF** | Utilisez `generator.Save(\"barcode.pdf\", BarCodeImageFormat.Pdf);` puis fusionnez le PDF avec d’autres documents en utilisant Aspose.PDF. |

> **Attention :** Définir `XDimension.Pixels` en dessous de `1` déclenche une `ArgumentOutOfRangeException`. Gardez toujours une valeur de `1` ou plus.

## Étape 5 : Vérifier le code‑barres  

Pour vous assurer que le code‑barres se lit correctement :

1. Ouvrez le PNG dans un visualiseur d’images.  
2. Utilisez n’importe quelle application de lecture de code‑barres sur smartphone qui prend en charge PDF417 (la plupart des applications « scanner de QR‑code » le supportent).  
3. Scannez l’image ; l’application doit afficher le texte original `"Åspóse.Barcóde©"`.

Si le scan échoue, revérifiez les paramètres **X‑dimension** et **column** – une largeur de module trop petite ou un nombre de colonnes non pris en charge peut rendre le motif illisible.

## Conclusion  

Vous savez maintenant comment **créer un code‑barres micro pdf417** en C# avec Aspose.BarCode. Le tutoriel a couvert :

* Instanciation d’un **générateur de code‑barres micro pdf417**.  
* **Définir XDimension pixels** pour contrôler la largeur du module.  
* **Définir les colonnes du code‑barres** pour ajuster la forme.  
* **Enregistrer le code‑barres en PNG** pour une sortie d’image sans perte.  

À partir de là, vous pouvez explorer des fonctionnalités supplémentaires telles que la personnalisation des couleurs, l’intégration du code‑barres dans des PDF, ou la génération de codes‑barres à la volée dans les API web ASP.NET Core. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer un code‑barres PNG en C# – guide complet sur GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Comment créer un code‑barres macro PDF417 en C# avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Créer un code‑barres PDF417 en C# avec Aspose.BarCode – guide étape par étape](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}