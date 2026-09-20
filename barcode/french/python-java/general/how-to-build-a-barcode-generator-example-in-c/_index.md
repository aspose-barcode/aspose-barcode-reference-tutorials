---
category: general
date: 2026-09-19
description: exemple de générateur de codes‑barres montrant comment changer la hauteur,
  créer un DataBar omnidirectionnel et ajuster les dimensions du code‑barres pour
  la sortie d’image en C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: fr
lastmod: 2026-09-19
og_description: exemple de générateur de code‑barres qui montre comment modifier la
  hauteur, créer un DataBar omnidirectionnel et ajuster les dimensions du code‑barres
  pour une image PNG en C#.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Exemple de générateur de code‑barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer un exemple de générateur de code‑barres en C#
url: /fr/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de générateur de code‑barres en C# – guide complet de programmation

Si vous avez besoin d’un **exemple de générateur de code‑barres** pour un projet .NET, ce guide vous montre exactement comment créer, configurer et enregistrer un code‑barres DataBar Omni‑Directional en C#. Vous apprendrez comment modifier la hauteur, ajuster les dimensions du code‑barres et générer une image PNG de haute qualité — le tout dans une seule application console exécutable.

Les étapes ci‑dessous couvrent tout, de l’installation du SDK requis à l’ajustement de la X‑dimension et de la hauteur des barres. À la fin du tutoriel, vous disposerez d’un générateur de code‑barres prêt à l’emploi que vous pourrez intégrer à la facturation, à la gestion des stocks ou à tout flux de travail de numérisation.

## Prérequis

Avant de commencer, assurez-vous d’avoir :

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Une licence active pour **Aspose.BarCode for .NET** (l’essai gratuit fonctionne pour les tests)

Si vous préférez une autre bibliothèque, les concepts d’ajustement des dimensions et d’enregistrement de l’image restent les mêmes ; il suffit de remplacer les appels d’API en conséquence.

## Étape 1 : Configurer le projet et ajouter le package Aspose.BarCode

Créez un nouveau projet console et référencez la bibliothèque de code‑barres.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

La commande `dotnet add package` récupère la dernière version stable d’Aspose.BarCode, qui inclut la prise en charge complète des symboles DataBar Omni‑Directional.

## Étape 2 : Écrire l’exemple complet de générateur de code‑barres

Ouvrez **Program.cs** et remplacez son contenu par le code suivant. Ce bloc contient le **exemple complet de générateur de code‑barres** — aucune partie manquante.

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **Create a barcode generator** – Le constructeur `BarcodeGenerator` associe le type d’encodage (`EncodeTypes.DatabarOmniDirectional`) aux données que vous souhaitez intégrer. C’est le cœur de l’étape **how to create databar**.  
* **Adjust barcode dimensions** – La propriété `XDimension.Pixels` définit la largeur de la barre la plus étroite. Modifier cette valeur influence la taille globale et la fiabilité de la lecture.  
* **How to change height** – La propriété `BarHeight.Pixels` contrôle la taille verticale. Augmenter la hauteur améliore la lisibilité pour les scanners portatifs, tandis que la diminuer économise de l’espace sur les petites étiquettes.  
* **Optional tweaks** – Définir les couleurs de premier plan/arrière-plan ou les niveaux de correction d’erreurs est optionnel mais montre comment étendre le concept **adjust barcode dimensions**.  
* **Create barcode image C#** – La méthode `Save` écrit le code‑barres sur le disque. Utiliser `BarCodeImageFormat.Png` garantit une compression sans perte, idéale pour la plupart des applications.

## Étape 3 : Compiler et exécuter l’exemple

Compilez et exécutez le programme :

```bash
dotnet run
```

Vous devriez voir la sortie console :

```
Barcode saved to DatabarOmniDirectional.png
```

Un fichier nommé **DatabarOmniDirectional.png** apparaît dans le dossier du projet. L’ouverture de l’image révèle un code‑barres DataBar Omni‑Directional net, prêt à être scanné.

## Comment modifier la hauteur après coup

Si vous devez générer des codes‑barres avec des hauteurs variables, encapsulez l’affectation de la hauteur dans une méthode :

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Appelez `SetBarHeight(generator, 45);` avant `Save`. Cette approche vous permet de **how to change height** dynamiquement en fonction des entrées utilisateur ou des fichiers de configuration.

## Comment créer des codes‑barres DataBar Omni‑Directional avec des données différentes

La symbologie DataBar Omni‑Directional prend en charge les identifiants GTIN‑14, GTIN‑13 et d’autres identifiants numériques. Pour encoder une valeur différente, remplacez simplement la chaîne dans le constructeur :

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Veillez à ce que les données soient numériques et correctement formatées ; sinon le générateur lève une `BarcodeException`.

## Ajuster les dimensions du code‑barres pour différents scénarios d’impression

Différents imprimantes et tailles d’étiquettes exigent des X‑dimensions et hauteurs différentes. Utilisez le tableau suivant comme référence rapide :

| Scénario                     | X‑Dimension (pixels) | Hauteur de la barre (pixels) |
|------------------------------|----------------------|------------------------------|
| Petite étiquette (25 mm × 15 mm)  | 1                    | 20                           |
| Étiquette moyenne (50 mm × 30 mm) | 2                    | 30                           |
| Grande étiquette (100 mm × 50 mm) | 3                    | 45                           |

Appliquez ces valeurs en définissant `generator.Parameters.Barcode.XDimension.Pixels` et `BarHeight.Pixels` en conséquence.

## Astuce pro : valider le code‑barres généré

Avant d’expédier une étiquette, vous pouvez vérifier sa lisibilité par programme :

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Cet extrait montre une vérification rapide de cohérence **adjust barcode dimensions**, garantissant que le code‑barres répond aux exigences de numérisation.

## Pièges courants et comment les éviter

| Piège                              | Pourquoi cela se produit                              | Solution                                                                 |
|------------------------------------|--------------------------------------------------------|--------------------------------------------------------------------------|
| Utilisation de données non numériques pour DataBar | DataBar attend des formats GTIN numériques            | Assurez‑vous que la chaîne correspond au modèle `(01)XXXXXXXXXXXXX`.    |
| Définir la X‑dimension à 0 ou négative | La bibliothèque lève `ArgumentOutOfRangeException`   | Utilisez un minimum de 1 pixel ; testez d’abord sur l’imprimante cible. |
| Enregistrement dans un dossier en lecture‑seule | `UnauthorizedAccessException` lors de `Save`         | Choisissez un répertoire accessible en écriture ou exécutez l’application avec les droits appropriés. |
| Oublier de libérer `BarCodeReader` | Fuite de mémoire dans les services de longue durée    | Enveloppez le lecteur dans un bloc `using` ou appelez `Dispose()` manuellement. |

## Récapitulatif du code source complet

Ci‑dessous se trouve le programme complet, prêt à copier, qui implémente le **exemple de générateur de code‑barres** du début à la fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

L’exécution de ce programme produit un fichier PNG qui ressemble à ceci (illustratif) :

![Code‑barres DataBar Omni‑Directional généré en C#](https://example.com/og-image.png "Code‑barres DataBar Omni‑Directional généré en C#")

*Texte alternatif de l’image* : **Code‑barres DataBar Omni‑Directional généré en C#** (correspond à `og_image_alt`).

## Conclusion

Vous disposez maintenant d’un **exemple de générateur de code‑barres** qui montre comment modifier la hauteur, comment créer des symboles DataBar Omni‑Directional, et comment **ajuster les dimensions du code‑barres** pour une numérisation optimale. Le code C# complet enregistre une image PNG, la valide, et peut être étendu pour une génération en masse ou une intégration dans des services web.

Ensuite, explorez des sujets connexes tels que **créer des QR codes avec Aspose.BarCode**, **traiter en lot plusieurs valeurs de code‑barres**, ou **intégrer des codes‑barres dans des documents PDF**. Chacun de ces sujets s’appuie sur les mêmes fondamentaux présentés dans ce guide.

Bon codage, et que vos codes‑barres soient toujours lisibles !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Exemple de générateur de code‑barres – créer une image DataBar en C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Comment générer et ajuster la hauteur du code‑barres pour Databar unidimensionnel avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Exemple de générateur de code‑barres en C# – définir la largeur et la hauteur](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}