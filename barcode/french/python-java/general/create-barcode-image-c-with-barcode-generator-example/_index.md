---
category: general
date: 2026-09-10
description: Créer rapidement une image de code‑barres en C# à l’aide d’un exemple
  de générateur de code‑barres C# montrant comment définir les dimensions et enregistrer
  des fichiers PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: fr
lastmod: 2026-09-10
og_description: Créez une image de code‑barres en C# avec un exemple concis de générateur
  de code‑barres C#. Apprenez à configurer la taille, la hauteur et à exporter des
  fichiers PNG en quelques minutes.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Créer une image de code‑barres C# – exemple de générateur pas à pas
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Créer une image de code-barres en C# avec un exemple de générateur de code-barres
url: /fr/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres C# avec un exemple de générateur de code-barres

Si vous devez **créer une image de code-barres C#** pour l'étiquetage des produits, le suivi des stocks ou la numérisation mobile, ce guide présente une solution complète. Vous verrez un **exemple de générateur de code-barres C#** qui configure la largeur du module, la hauteur des barres et enregistre des fichiers PNG en quelques lignes de code.

Le tutoriel couvre tout, de l'installation de la bibliothèque requise à l'exécution d'un programme console prêt à être compilé. À la fin, vous disposerez de deux fichiers PNG de code-barres — l'un avec une hauteur de barre de 30 pixels et l'autre avec une hauteur de barre de 60 pixels — prêts à être utilisés dans n'importe quelle application .NET.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 SDK ou version ultérieure installé  
* Un environnement de développement tel que Visual Studio 2022 ou VS Code  
* Le package NuGet **Aspose.BarCode** (le code utilise `BarcodeGenerator` de cette bibliothèque)  

Vous pouvez ajouter le package avec la commande CLI suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le projet console

Créez un nouveau projet console et référencez la bibliothèque de code‑barres.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

La commande crée un fichier `Program.cs` où vous placerez le code du **exemple de générateur de code‑barres C#**.

## Étape 2 : Écrire le programme complet de génération de code‑barres

Remplacez le contenu de `Program.cs` par l'exemple complet et exécutable ci‑dessous. Le programme montre comment **créer une image de code‑barres C#** avec des dimensions personnalisées et comment enregistrer le résultat sous forme de fichiers PNG.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **EncodeTypes.DatabarOmniDirectional** – sélectionne la symbologie DataBar Omnidirectional, qui encode des données numériques et est largement utilisée dans le commerce de détail.  
* **XDimension.Pixels = 2** – définit la largeur du module ; une valeur plus petite produit un code‑barres plus compact.  
* **BarHeight.Pixels** – contrôle la hauteur visuelle des barres. Ajuster cette valeur vous permet de créer des code‑barres adaptés à différentes tailles d'étiquettes.  
* **Méthode Save** – écrit le code‑barres dans un fichier PNG, un format qui préserve les bords nets et fonctionne avec la plupart des bibliothèques d'imagerie.

## Étape 3 : Compiler et exécuter le programme

Exécutez la commande suivante depuis le dossier du projet :

```bash
dotnet run
```

Lorsque le programme se termine, vous verrez deux fichiers PNG dans le sous‑dossier `output` :

* `DatabarBarHeight30Pixels.png` – hauteur de barre de 30 pixels  
* `DatabarBarHeight60Pixels.png` – hauteur de barre de 60 pixels  

Les deux images contiennent les mêmes données encodées mais diffèrent par leur hauteur visuelle, illustrant comment le **exemple de générateur de code‑barres C#** peut être adapté à diverses exigences d'étiquetage.

## Étape 4 : Vérifier les code‑barres générés

Ouvrez les fichiers PNG avec n'importe quel visualiseur d'images. Vous devriez voir un code‑barres DataBar clair et à fort contraste. Pour confirmer que les code‑barres sont lisibles, vous pouvez utiliser une application de scanner mobile (p. ex., des applications basées sur ZXing) ou une bibliothèque de bureau telle que **Aspose.BarCode** en mode décodage :

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Si la sortie correspond à `(01)12345678901231`, la génération a réussi.

## Variations courantes et cas limites

| Situation | Ajustement | Extrait de code |
|-----------|------------|-----------------|
| **Symbologie différente** (p. ex., QR, Code128) | Modifier la valeur de `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Format d'image personnalisé** (JPEG, BMP) | Utiliser un autre enum `BarCodeImageFormat` | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Données dynamiques** (entrée utilisateur) | Remplacer la chaîne codée en dur par une variable | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Longueur de données invalide** | Capturer l'`ArgumentException` lancée par le générateur | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Astuce : validez toujours la longueur de l'entrée pour la symbologie sélectionnée ; Aspose.BarCode lève une exception si les données ne respectent pas la spécification.

## Liste de vérification de dépannage

* **Répertoire introuvable** – L'assistant `SaveBarcode` crée automatiquement le dossier `output`, mais assurez‑vous que l'application possède les permissions d'écriture.  
* **Taille d'image inattendue** – Vérifiez que `XDimension.Pixels` et `BarHeight.Pixels` sont définis avant d'appeler `Save`. Modifier ces valeurs après l'enregistrement n'affecte pas les fichiers déjà écrits.  
* **Code‑barres illisible** – Assurez‑vous que la chaîne encodée suit le format GS1 lors de l'utilisation des symbologies DataBar. Des parenthèses manquantes ou des identifiants d'application incorrects entraînent des échecs de décodage.

## Conclusion

Vous savez maintenant comment **créer une image de code‑barres C#** en utilisant un **exemple de générateur de code‑barres C#** pratique. Le programme complet définit la largeur du module, ajuste la hauteur des barres et enregistre des fichiers PNG avec un code minimal. À partir de là, vous pouvez explorer des fonctionnalités supplémentaires telles que la personnalisation des couleurs, l'exportation PDF multi‑pages ou la génération en temps réel dans les API web ASP.NET Core.

**Prochaines étapes**

* Expérimentez d'autres symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) pour élargir vos options de numérisation.  
* Intégrez le générateur dans un service web qui renvoie des images de code‑barres à la demande.  
* Combinez le code‑barres avec les métadonnées du produit dans une facture PDF en utilisant Aspose.PDF.

Bon codage, et profitez de la flexibilité que C# offre pour la création d'images de code‑barres !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Exemple de générateur de code‑barres en C# – Définir les colonnes, lignes et exporter l'image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Créer une image de code‑barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Exemple de générateur de code‑barres – Construire une image DataBar en C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}