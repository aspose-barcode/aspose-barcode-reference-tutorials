---
category: general
date: 2026-08-09
description: Créez rapidement un code‑barres databar à 4 colonnes en C# avec Aspose.BarCode.
  Apprenez à configurer les colonnes, les lignes et à enregistrer des images PNG dans
  ce guide concis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: fr
lastmod: 2026-08-09
og_description: Créez un code‑barres databar à 4 colonnes en C# avec Aspose.BarCode,
  puis personnalisez les lignes et exportez des images PNG pour votre application.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Créer un code‑barres databar à 4 colonnes en C# – tutoriel rapide
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Créer un code‑barres Databar à 4 colonnes en C# – guide étape par étape
url: /fr/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres databar à 4 colonnes en C# – guide étape par étape

Si vous devez **créer un code‑barres databar à 4 colonnes** en C#, ce tutoriel vous montre exactement comment procéder. Nous parcourrons la génération d’un code‑barres DataBar Expanded Stacked, la configuration de quatre colonnes et l’enregistrement du résultat sous forme d’image PNG.

Dans ce guide, vous apprendrez à :

* Initialiser le `BarcodeGenerator` pour un symbole **DataBar Expanded Stacked**.  
* Définir le nombre de colonnes à 4 (l’exigence principale).  
* Ajuster le nombre de lignes lorsque vous avez besoin d’une disposition empilée avec trois lignes.  
* Exporter le code‑barres au format PNG en utilisant le **format d’image de code‑barres** approprié.

Vous avez seulement besoin de la bibliothèque Aspose.BarCode for .NET (version 23.10 ou ultérieure) et d’un environnement de développement .NET 6+ tel que Visual Studio 2022. Aucune dépendance supplémentaire n’est requise.

---

## Comment créer un code‑barres databar à 4 colonnes

La première étape consiste à créer une instance de `BarcodeGenerator` qui cible la symbologie **DataBar Expanded Stacked**. Cette classe encapsule toutes les options de rendu, ce qui facilite le passage entre les dispositions basées sur les colonnes et celles basées sur les lignes.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi cela fonctionne :**  
`EncodeTypes.DatabarExpandedStacked` indique à Aspose.BarCode de produire la version empilée de la famille DataBar. La propriété `DataBar.Columns` contrôle le nombre de modules verticaux occupés par le code‑barres. La définir à 4 correspond à l’exigence de **créer un code‑barres databar à 4 colonnes**. Enfin, `Save` écrit la représentation visuelle sur le disque en utilisant le **format d’image de code‑barres** `Png`.

### Configurer les colonnes du DataBar Expanded Stacked

Si vous avez besoin d’un nombre de colonnes différent, modifiez simplement l’entier attribué à `Columns`. La propriété accepte des valeurs de 1 à 4 pour la variante expanded stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Astuce :* Testez toujours le code‑barres généré avec un lecteur qui prend en charge la famille DataBar, car l’apparence visuelle seule ne garantit pas la lisibilité.

### Enregistrer l’image du code‑barres

L’énumération `BarCodeImageFormat` propose plusieurs options (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG est sans perte et fonctionne bien pour la plupart des scénarios web et desktop.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Si vous avez besoin d’un format différent, remplacez `Png` par la valeur d’énumération souhaitée. Le fichier enregistré peut être intégré directement dans du HTML, des PDF, ou imprimé sur des étiquettes.

## Créer un code‑barres avec des lignes personnalisées

Parfois, une disposition empilée nécessite un nombre spécifique de lignes au lieu de colonnes. La même classe `BarcodeGenerator` expose une propriété `Rows` à cet effet.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi les lignes comptent :**  
Lorsque le code‑barres empilé est plus haut que large, la propriété `Rows` détermine en combien de tranches horizontales le symbole est divisé. Définir `Rows = 3` crée un code‑barres empilé à trois lignes, ce qui est utile pour des largeurs d’étiquette étroites.

### Définir les lignes du code‑barres dynamiquement

Vous pouvez calculer le nombre de lignes à l’exécution en fonction des données d’entrée :

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Cette flexibilité vous permet de **définir les lignes du code‑barres** sans recompilation de l’application.

## Exemple complet de bout en bout

Voici un programme unique qui génère à la fois un code‑barres à 4 colonnes et un code‑barres à 3 lignes, démontrant comment les deux configurations coexistent.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Résultat attendu :**  
Deux fichiers PNG apparaissent dans le répertoire de travail de l’application :

* `DatabarCols4.png` – un code‑barres DataBar Expanded Stacked avec quatre colonnes verticales.  
* `DatabarRows3.png` – la même symbologie disposée en trois lignes horizontales.

Les deux images peuvent être ouvertes avec n’importe quel visualiseur d’images ou intégrées dans un contrôle UI.

---

## Questions fréquentes et cas particuliers

| Question | Réponse |
|----------|--------|
| *Puis‑je utiliser une symbologie de code‑barres différente ?* | Oui. Remplacez `EncodeTypes.DatabarExpandedStacked` par une autre valeur `EncodeTypes` (par ex., `EncodeTypes.QR`), mais les propriétés `Columns` et `Rows` sont spécifiques aux familles DataBar. |
| *Que se passe-t-il si la chaîne de données dépasse la longueur maximale ?* | La symbologie DataBar Expanded Stacked prend en charge jusqu’à 61 caractères numériques. Dépasser cette limite génère une `ArgumentException`. Validez l’entrée avant de l’attribuer au générateur. |
| *Dois‑je disposer du `BarcodeGenerator` ?* | `BarcodeGenerator` implémente `IDisposable`. Dans un service de longue durée, encapsulez‑le dans un bloc `using` ou appelez `Dispose()` manuellement pour libérer les ressources natives. |
| *Puis‑je générer du SVG au lieu de PNG ?* | Absolument. Utilisez `BarCodeImageFormat.Svg` dans la méthode `Save`. |
| *La bibliothèque est‑elle compatible avec .NET Core ?* | Aspose.BarCode for .NET prend en charge .NET Core 3.1, .NET 5, .NET 6 et les versions ultérieures. Aucun changement de code n’est nécessaire. |

---

## Conclusion

Vous savez maintenant comment **créer un code‑barres databar à 4 colonnes** en C# avec Aspose.BarCode, comment ajuster la disposition avec des lignes, et comment exporter le résultat dans un **format d’image de code‑barres** pratique. L’exemple complet montre les configurations basées sur les colonnes et sur les lignes, vous offrant une base solide pour tout scénario d’impression d’étiquettes ou de numérisation mobile.

**Prochaines étapes**

* Expérimentez avec différents contenus de données et vérifiez la compatibilité du lecteur.  
* Explorez des options de style supplémentaires telles que les couleurs de premier plan/arrière‑plan (`generator.Parameters.Barcode.Color`).  
* Combinez le code‑barres avec d’autres graphiques en utilisant l’API `Graphics` pour des conceptions d’étiquettes personnalisées.  

N’hésitez pas à adapter le code pour des projets ASP.NET Core, Windows Forms ou Xamarin—Aspose.BarCode fonctionne sur toutes les plateformes .NET. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer une image de code‑barres c# – Configurer les lignes & colonnes de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Comment créer un texte de code étendu dotcode avec Aspose.BarCode pour .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}