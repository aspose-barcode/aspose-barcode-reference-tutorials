---
category: general
date: 2026-09-29
description: Apprenez à créer un code‑barres Databar Expanded Stacked et à générer
  une image de code‑barres en C#. Ce guide étape par étape montre comment définir
  les lignes et les colonnes à l’aide de BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: fr
lastmod: 2026-09-29
og_description: Génération de codes-barres Databar Expanded Stacked en C# expliquée.
  Suivez le tutoriel pour créer des images de codes-barres, définir les lignes et
  enregistrer des fichiers PNG avec BarcodeGenerator.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: Génération de code‑barres Databar Expanded Stacked en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Génération de code‑barres Databar Expanded Stacked en C#
url: /fr/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Génération de code‑barres Databar Expanded Stacked en C#

Si vous devez générer un code‑barres **Databar Expanded Stacked** en C#, ce guide vous montre exactement **comment créer des images de code‑barres** avec des lignes et des colonnes personnalisées. Vous verrez **comment définir les lignes**, comment définir les colonnes, et comment **générer des fichiers d’image de code‑barres** à l’aide de la classe `BarcodeGenerator` d’Aspose.BarCode.

Dans ce tutoriel vous allez :

* Installer le package NuGet requis.
* Initialiser un `BarcodeGenerator` pour la symbologie Databar Expanded Stacked.
* Configurer le nombre de colonnes et de lignes.
* Enregistrer les fichiers PNG résultants.
* Comprendre les pièges courants tels que les licences manquantes ou les chemins d’image incorrects.

Les seules conditions préalables sont un SDK .NET récent (≥ .NET 6) et un IDE tel que Visual Studio 2022. Aucun service externe n’est requis.

## Installer et configurer la bibliothèque BarcodeGenerator C#

Avant d’écrire du code, ajoutez le package Aspose.BarCode à votre projet :

```bash
dotnet add package Aspose.BarCode
```

Si vous utilisez Visual Studio, vous pouvez également l’installer via le **Gestionnaire de packages NuGet** (recherchez *Aspose.BarCode*). Après la restauration du package, vous pouvez commencer à coder.

> **Astuce :** La version d’évaluation gratuite ajoute un petit filigrane aux codes‑barres générés. Pour une utilisation en production, obtenez un fichier de licence et appelez `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` avant de créer tout objet code‑barres.

## Générer une image de code‑barres Databar Expanded Stacked

Créez une nouvelle application console (ou intégrez le code dans n’importe quel projet C#) et ajoutez les instructions `using` suivantes :

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Écrivez maintenant le programme complet. Le code suit exactement les étapes de l’exemple original et ajoute des commentaires explicatifs.

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Pourquoi chaque étape est importante

* **Étape 1** crée un `BarcodeGenerator` lié à la symbologie *Databar Expanded Stacked*, nécessaire pour la lecture GS1 compatible commerce de détail.
* **Étape 2** montre **comment définir les lignes** indirectement en ajustant d’abord les colonnes — cela démontre que les réglages de colonnes et de lignes sont indépendants.
* **Étape 3** persiste l’image, vous permettant de vérifier l’impact visuel du nombre de colonnes.
* **Étape 4** ré‑initialise le générateur afin que la configuration des lignes n’hérite pas de la valeur de colonne précédemment définie, source fréquente de confusion.
* **Étape 5** montre explicitement **comment définir les lignes**, qui est le principal objectif du mot‑clé secondaire.
* **Étape 6** enregistre la seconde image, vous offrant une comparaison côte à côte de la densité basée sur les colonnes vs. les lignes.

L’exécution du programme produit deux fichiers PNG dans le répertoire de sortie :

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

Ouvrez l’un ou l’autre fichier avec un visualiseur d’images pour confirmer que le code‑barres s’affiche correctement.

## Variations courantes et cas limites

| Scénario | Ce qu’il faut modifier | Raison |
|----------|------------------------|--------|
| **Charge utile de données différente** | Remplacez le deuxième argument de `BarcodeGenerator` par votre propre chaîne (par ex., `"123456789012"`). | Le code‑barres encode le texte fourni ; assurez‑vous qu’il respecte les règles GS1 pour Databar. |
| **Autres formats d’image** | Utilisez `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. | Choisissez un format qui correspond à votre pipeline de traitement en aval. |
| **Résolution supérieure** | Appelez `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);` où le dernier argument représente les DPI. | Améliore la lisibilité lors de l’impression d’étiquettes de grande taille. |
| **Gestion de la licence** | Ajoutez le fragment de code `License` avant toute création de générateur. | Supprime le filigrane d’évaluation et débloque toutes les fonctionnalités. |

## Conseils pour une génération fiable de code‑barres

* **Validez la chaîne d’entrée** – Databar Expanded Stacked attend des données numériques jusqu’à 70 caractères. Fournir des caractères non numériques peut provoquer une exception.
* **Vérifiez les chemins de fichiers** – Utilisez `Path.Combine(Environment.CurrentDirectory, "output.png")` pour éviter les répertoires codés en dur qui pourraient ne pas exister sur la machine cible.
* **Libérez les objets** – `BarcodeGenerator` implémente `IDisposable`. Enveloppez‑le dans un bloc `using` si vous générez de nombreux codes‑barres dans une boucle afin de libérer rapidement les ressources natives.

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## Conclusion

Vous savez maintenant **comment créer un code‑barres Databar Expanded Stacked** et **comment définir les lignes** (et les colonnes) en utilisant l’API **barcode generator C#**, et vous pouvez **générer des fichiers d’image de code‑barres** au format PNG. En suivant l’exemple complet ci‑dessus, vous pouvez intégrer des codes‑barres Databar dans des systèmes d’inventaire, des applications point‑of‑sale ou toute solution .NET nécessitant des codes‑barres GS1 à haute densité.

**Prochaines étapes**

* Expérimentez d’autres symbologies telles que `EncodeTypes.DatabarExpanded` ou `EncodeTypes.QR`.  
* Explorez la classe `BarcodeReader` pour vérifier que vos images générées sont lisibles.  
* Combinez la génération de code‑barres avec la création de PDF (par ex., en utilisant `Aspose.PDF`) pour produire des étiquettes imprimables.

Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment définir les colonnes pour un code‑barres Databar Expanded Stacked – guide complet C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Comment modifier la taille du code‑barres en C# avec DataBar Stacked](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked : générer une image de code‑barres en C#](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}