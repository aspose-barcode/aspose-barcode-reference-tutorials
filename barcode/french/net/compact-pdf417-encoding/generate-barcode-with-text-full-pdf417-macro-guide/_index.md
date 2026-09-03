---
category: general
date: 2026-07-18
description: Générez un code‑barres avec du texte en utilisant Aspose.BarCode pour
  .NET. Apprenez comment créer des codes‑barres PDF417, définir les options macro
  et exporter des images PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: fr
lastmod: 2026-07-18
og_description: Générez un code‑barres avec du texte en C# rapidement. Ce tutoriel
  étape par étape montre comment créer des codes‑barres PDF417, configurer les paramètres
  macro et enregistrer en PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Générer un code-barres avec texte – Création de macro Master PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Générer un code-barres avec du texte – Guide complet du macro PDF417
url: /fr/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres avec texte – Guide complet Macro PDF417

Vous vous êtes déjà demandé **comment générer des codes-barres PDF417** qui intègrent également du texte personnalisé ? Dans ce tutoriel, vous verrez exactement comment **générer un code-barres avec texte** en utilisant Aspose.BarCode for .NET, et nous passerons en revue chaque paramètre nécessaire pour un symbole Macro PDF417. Pas de superflu, juste un exemple complet et exécutable que vous pouvez intégrer à votre projet dès aujourd’hui.

Nous couvrirons :

* Le package NuGet requis et les directives using.  
* Comment créer un générateur de code-barres qui inclut des caractères Unicode.  
* Définir la taille du module, le nombre de colonnes et les ID spécifiques aux macros.  
* Enregistrer le résultat sous forme de fichier PNG et vérifier la sortie.  

À la fin, vous disposerez d’une image PNG prête à l’emploi d’un code-barres Macro PDF417 que vous pourrez intégrer dans des factures, des tickets ou tout document nécessitant un segment lisible par machine.

---

## Prérequis

| Exigence | Raison |
|----------|--------|
| **.NET 6.0** ou ultérieur | Aspose.BarCode prend en charge .NET Standard 2.0+, donc .NET 6 vous fournit le runtime le plus récent. |
| **Visual Studio 2022** (ou tout IDE C#) | Pour une édition et un débogage faciles. |
| **Aspose.BarCode for .NET** package NuGet | La bibliothèque qui crée réellement le code-barres. Installez‑la avec `dotnet add package Aspose.BarCode`. |
| **Permission d'écriture** sur le dossier de sortie | La méthode `Save` doit écrire le fichier PNG. |

Si l’un d’eux vous est inconnu, faites une pause et résolvez‑le — sinon le code lèvera des exceptions évidentes.

---

## Étape 1 – Installer et importer la bibliothèque

Tout d’abord, ajoutez le package NuGet à votre projet :

```bash
dotnet add package Aspose.BarCode
```

Ensuite, importez les espaces de noms nécessaires :

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Astuce :** Si vous utilisez Visual Studio, faites un clic droit sur le projet → *Manage NuGet Packages* → recherchez *Aspose.BarCode* et installez la dernière version stable.

---

## Étape 2 – Créer le générateur de code-barres avec votre texte personnalisé

La tâche *principale* est de **générer un code-barres avec texte** contenant des caractères spéciaux comme « Å » et « © ». Le constructeur prend le type d’encodage et la chaîne de données brutes :

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Pourquoi c’est important : `EncodeTypes.MacroPdf417` indique à Aspose que nous voulons la version macro, ce qui nous permet de diviser un long message en plusieurs symboles. La chaîne de texte peut être n’importe quelle séquence UTF‑8 ; Aspose gère la conversion en interne.

---

## Étape 3 – Ajuster l’apparence de base (taille du module)

Le “module” d’un code‑barres est le plus petit carré noir ou blanc. Définir sa taille en pixels contrôle les dimensions globales de l’image sans modifier la densité des données :

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si vous avez besoin d’une image plus grande pour l’impression, augmentez cette valeur à 4 ou 6. Gardez simplement à l’esprit que des modules plus grands augmentent la taille finale du PNG.

---

## Étape 4 – Configurer les options spécifiques à Macro PDF417

Macro PDF417 ajoute deux identifiants qui permettent à un scanner d’assembler plusieurs symboles. Vous définirez généralement :

| Propriété | Ce que cela fait |
|-----------|-------------------|
| `Columns` | Nombre de colonnes de données par symbole (affecte la largeur). |
| `MacroPdf417FileID` | Identifiant unique pour l’ensemble du fichier macro (doit être ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Index du segment actuel (0‑254). |

Voici le code :

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Note de cas limite :** `MacroPdf417FileID` doit être identique pour chaque segment du même fichier logique. Si vous générez plusieurs segments, réutilisez le même ID sinon vous vous retrouverez avec des symboles non liés qui ne peuvent pas être combinés.

---

## Étape 5 – Enregistrer le code‑barres en tant qu’image PNG

Maintenant que tout est configuré, écrivez l’image sur le disque :

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

La méthode `Save` crée automatiquement le PNG, gérant le DPI et la profondeur de couleur pour vous. Après exécution, ouvrez le fichier pour voir quelque chose comme ceci :

![Generate barcode with text example](/images/barcode-example.png){.center alt="Exemple de génération de code-barres avec texte"}

Si vous ne voyez pas de code‑barres, vérifiez que le dossier existe et que votre application a les droits d’écriture.

---

## Exemple complet, prêt à l’exécution

Copiez le fragment complet ci‑dessous dans une nouvelle application console (`dotnet new console`) et exécutez‑le. Il produira le PNG dans le dossier `C:\Barcodes` (créez d’abord le dossier).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Sortie attendue** (console) :

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

Et le PNG affichera un symbole Macro PDF417 compact contenant le texte « Åspóse.Barcóde© ».

---

## Questions fréquentes & pièges

| Question | Réponse |
|----------|--------|
| *Puis-je utiliser un autre format d’image ?* | Absolument—remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif`. Le PNG est sans perte, c’est pourquoi nous l’utilisons par défaut. |
| *Et si j’ai besoin de plus d’un segment ?* | Créez un nouveau `BarcodeGenerator` pour chaque segment, conservez le même `MacroPdf417FileID`, et incrémentez `MacroPdf417SegmentID` (0‑254). |
| *Mon texte contient des emojis—fonctionneront‑ils ?* | Aspose.BarCode prend en charge UTF‑8, donc la plupart des emojis fonctionnent. Assurez‑vous simplement que le scanner cible peut les décoder ; de nombreux scanners industriels ne gèrent que les données alphanumériques. |
| *Le code‑barres est trop large pour mon étiquette.* | Réduisez `Columns` ou augmentez la taille du module. Moins de colonnes produisent un symbole plus étroit, mais cela peut nécessiter une imprimante à DPI plus élevé. |
| *Ai‑je besoin d’une licence ?* | Une licence d’évaluation gratuite fonctionne pour les tests, mais elle ajoute un petit filigrane. Pour la production, achetez une licence pour supprimer le filigrane et débloquer toutes les fonctionnalités. |

---

## Prochaines étapes

Maintenant que vous savez **comment générer des codes‑barres PDF417** avec du texte personnalisé, vous pourriez vouloir :

* **Décoder** le code‑barres dans une application mobile en utilisant `BarCodeReader` d’Aspose.BarCode.  
* **Combiner** plusieurs segments macro en un seul document PDF pour l’impression en lot.  
* **Explorer d’autres symbologies** (QR, DataMatrix) avec des modèles de paramètres similaires.  
* **Ajuster le niveau de correction d’erreurs** via `Pdf417.ErrorCorrectionLevel` pour des environnements plus exigeants.  

Chacun de ces sujets s’appuie sur les mêmes concepts de base que vous venez d’apprendre, vous trouverez donc la transition fluide.

---

## Conclusion

Nous avons parcouru une solution complète, de bout en bout, qui vous permet de **générer un code‑barres avec texte** et, spécifiquement, **comment générer des symboles macro PDF417** en utilisant Aspose.BarCode for .NET. En définissant la dimension X, le nombre de colonnes et les ID macro, vous obtenez un contrôle total sur la taille, la mise en page et la gestion multi‑segments. Le PNG résultant peut être imprimé, intégré dans des PDF ou envoyé à un scanner sans aucune conversion supplémentaire.

Essayez‑le, ajustez les paramètres, et laissez le code‑barres servir votre cas d’utilisation. Si vous rencontrez un problème, la documentation Aspose et les forums communautaires sont d’excellentes ressources complémentaires. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer des codes‑barres PDF417 – Encodage PDF417 compact](/barcode/english/net/compact-pdf417-encoding/)
- [Comment générer un code‑barres DataMatrix avec Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Comment générer un code‑barres - Types de codes‑barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}