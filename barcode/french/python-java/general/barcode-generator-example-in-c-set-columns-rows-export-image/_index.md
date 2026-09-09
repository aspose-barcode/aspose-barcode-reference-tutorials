---
category: general
date: 2026-07-15
description: Exemple de générateur de code‑barres en C# montrant comment définir les
  colonnes, comment définir les lignes et exporter rapidement l’image du code‑barres.
  Suivez ce guide étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: fr
lastmod: 2026-07-15
og_description: Exemple de générateur de codes-barres en C# montre comment définir
  les colonnes, les lignes et exporter l'image du code-barres. Apprenez le flux de
  travail complet en quelques minutes.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Exemple de générateur de code-barres en C# – Colonnes, lignes et exportation
  d’image
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Exemple de générateur de codes-barres en C# – Définir les colonnes, les lignes
  et exporter l'image
url: /fr/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de générateur de code-barres en C# – Guide complet

Vous vous êtes déjà demandé comment créer un **exemple de générateur de code-barres** en C# qui vous permette d’ajuster les colonnes, les lignes, puis d’exporter le résultat sous forme d’image ? Vous n’êtes pas seul. De nombreux développeurs se heurtent à un mur lorsqu’ils ont besoin d’une méthode rapide pour générer des codes-barres DataBar Expanded Stacked avec des options de mise en page personnalisées. Dans ce tutoriel, nous résoudrons ce problème étape par étape, en vous montrant **comment définir les colonnes**, **comment définir les lignes**, et enfin **exporter des fichiers d’image de code-barres**—le tout avec du code propre, prêt pour la production.

À la fin de ce guide, vous disposerez d’un programme complet et exécutable qui crée une image de code-barres, ajuste sa mise en page et enregistre deux fichiers PNG sur le disque. Pas de bibliothèques mystérieuses, pas de configuration cachée—juste du C# pur et un SDK de code-barres fiable.

---

## Prérequis

- **.NET 6.0** (ou toute version .NET ultérieure). Le code se compile également avec .NET Framework, mais .NET 6+ vous offre les dernières améliorations d’exécution.
- Une **bibliothèque de génération de code-barres** qui prend en charge DataBar Expanded Stacked. Dans les exemples, nous utiliserons **Aspose.BarCode for .NET**, qui est gratuite en version d’essai et offre une API simple.
- Un environnement de développement—Visual Studio 2022, Rider ou VS Code conviendront.
- Permission d’écriture sur un dossier où les fichiers PNG seront enregistrés.

Si vous n’avez pas encore la bibliothèque, récupérez‑la depuis NuGet :

```bash
dotnet add package Aspose.BarCode
```

Cette seule ligne récupère tout ce dont vous avez besoin, y compris la classe `BarcodeGenerator` et l’énumération `BarCodeImageFormat` utilisée plus tard.

---

## Étape 1 : Configurer le squelette du projet

Créez une nouvelle application console et ajoutez les directives `using` nécessaires :

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Voici le squelette **complet** du fichier `Program.cs` :

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Astuce :** Gardez la méthode `Main` propre ; nous déléguerons le travail lourd à des méthodes auxiliaires plus tard. Cela rend le code plus facile à tester et à réutiliser.

---

## Étape 2 : Créer l’exemple de générateur de code-barres

Nous allons maintenant construire le **exemple de générateur de code-barres** principal qui crée un code-barres DataBar Expanded Stacked. C’est le cœur du tutoriel.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Pourquoi séparons‑nous cela dans une méthode distincte ? Cela isole la logique de **l’exemple de générateur de code-barres**, la rendant réutilisable si vous devez plus tard générer plusieurs codes-barres avec des données différentes.

---

## Étape 3 : Comment définir les colonnes

Le format DataBar Expanded Stacked peut être rendu avec une mise en page orientée colonnes. Par défaut, le SDK choisit une valeur raisonnable, mais il faut souvent l’adapter à une taille d’étiquette spécifique. Voici **comment définir les colonnes** à quatre :

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Pourquoi les colonnes sont importantes :** Chaque colonne ajoute de l’espace vertical, ce qui peut être crucial lors de l’impression sur des étiquettes étroites. La régler à `4` vous donne un code‑barres équilibré et lisible sans sacrifier la fiabilité du scan.

Dans le flux principal, nous appellerons cette méthode :

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Étape 4 : Comment définir les lignes

Parfois, vous avez besoin d’une mise en page plus compacte, surtout si vous imprimez sur une étiquette courte et large. C’est là que **comment définir les lignes** intervient. Passer d’une disposition centrée sur les colonnes à une disposition centrée sur les lignes peut réduire l’empreinte du code‑barres.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

L’appel ressemble à ceci :

```csharp
SetRows(generator, 3);
```

> **Note de cas limite :** Vous ne pouvez pas définir à la fois les colonnes *et* les lignes simultanément—le SDK privilégiera les lignes si vous attribuez une valeur non nulle à `Rows`. Assurez‑vous donc de réinitialiser l’autre propriété si vous changez de mise en page :

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Étape 5 : Exporter l’image du code‑barres

Une fois la mise en page configurée, l’étape finale consiste à **exporter des fichiers d’image de code‑barres**. Le SDK prend en charge PNG, JPEG, BMP, et plus encore. PNG est sans perte et fonctionne bien avec la plupart des imprimantes d’étiquettes.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Assembler le tout dans `Main` :

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Résultat attendu

Lorsque vous exécutez le programme, vous devriez voir deux fichiers PNG dans `YOUR_DIRECTORY` :

- **DatabarCols4.png** – un code‑barres rendu avec quatre colonnes verticales.
- **DatabarRows3.png** – les mêmes données, mais disposées en trois rangées horizontales.

Les deux images feront 300 × 150 px (comme défini dans `CreateGenerator`) et seront prêtes à être imprimées ou intégrées dans un PDF.

---

## Pièges courants & astuces

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Erreurs de chemin de fichier** | Utiliser un chemin relatif sans le répertoire approprié peut déclencher `DirectoryNotFoundException`. | Utilisez `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` ou assurez‑vous que le dossier existe avec `Directory.CreateDirectory`. |
| **Conflit lignes vs colonnes** | Le fait de définir les deux propriétés conduit le SDK à ignorer les colonnes. | Définissez explicitement la propriété opposée à `0` lorsque vous changez de mise en page. |
| **Type de code‑barres non pris en charge** | Toutes les bibliothèques de code‑barres ne prennent pas en charge DataBar Expanded Stacked. | Vérifiez que votre version de bibliothèque inclut `EncodeTypes.DatabarExpandedStacked`. |
| **Qualité d’image trop basse** | Le DPI par défaut peut être insuffisant pour les imprimantes haute résolution. | Ajustez `generator.Parameters.Image.ResolutionX/Y` à `300` ou plus. |

---

## Étendre l’exemple de générateur de code‑barres

Maintenant que vous disposez d’un **exemple de générateur de code‑barres** solide, vous vous demandez peut‑être ce que vous pouvez faire d’autre.

1. **Ajouter des couleurs** – Définissez `generator.Parameters.Barcode.ForegroundColor` à `Color.Blue`.
2. **Encoder des données différentes** – Passez une chaîne variable au lieu de la chaîne codée en dur `"Databar Expanded Stacked long"`.
3. **Traitement par lots** – Parcourez un fichier CSV de codes produit, en générant un PNG pour chacun.
4. **Intégrer avec une API web** – Exposez un point de terminaison qui renvoie le code‑barres sous forme de chaîne encodée en base64.

Chacune de ces extensions suit le même schéma : configurez l’instance `BarcodeGenerator`, puis appelez `Save` ou `Export` selon les besoins.

---

## Conclusion

Nous avons parcouru un **exemple complet de générateur de code‑barres** en C# qui montre **comment définir les colonnes**, **comment définir les lignes**, et comment **exporter des fichiers d’image de code‑barres**. Le code est autonome, fonctionne immédiatement avec Aspose.BarCode, et démontre les meilleures pratiques en matière de lisibilité et de maintenabilité.

N’hésitez pas à expérimenter—remplacez la chaîne de données, ajustez les dimensions de l’image, ou passez à une symbologie de code‑barres différente. Les concepts que vous avez appris ici—initialisation du générateur, configuration des paramètres de mise en page et exportation—s’appliquent à pratiquement tout type de code‑barres pris en charge par le SDK.

Des questions sur la création de programmes d’image de code‑barres en C#, ou besoin d’aide avec une imprimante d’étiquettes spécifique ? Laissez un commentaire ci‑dessous, et bon codage !

---

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d’API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer une image de code‑barres c# – Configurer les lignes & colonnes de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Créer une image de code‑barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}