---
category: general
date: 2026-10-08
description: Apprenez à créer une image de code‑barres en C# et découvrez comment
  ajuster le rapport d’aspect des codes‑barres DataBar empilés omnidirectionnels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: fr
lastmod: 2026-10-08
og_description: Créer une image de code‑barres en C# et apprendre à ajuster le rapport
  d’aspect des codes‑barres DataBar empilés omnidirectionnels avec un exemple de code
  complet.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Créer une image de code-barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer une image de code-barres et ajuster son rapport d’aspect en C#
url: /fr/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres et ajuster son ratio d'aspect en C#

Si vous devez **créer une image de code-barres** de manière programmatique, ce guide vous présente une solution complète, prête à l'emploi. Vous verrez exactement **comment ajuster le ratio d'aspect** pour un code-barres DataBar empilé omni‑directionnel, une exigence qui apparaît souvent dans les applications de vente au détail et de logistique.

Dans ce tutoriel, vous apprendrez à :
* Initialiser un `BarcodeGenerator` Aspose.BarCode pour la symbologie DataBar empilée omni‑directionnelle.  
* Définir la X‑dimension (largeur du module) en pixels pour contrôler l'épaisseur des barres.  
* Appliquer deux ratios d'aspect différents et enregistrer chaque résultat sous forme de fichier PNG.  
* Vérifier la sortie et comprendre pourquoi le ratio d'aspect est important.

Aucun outil externe n'est requis — il suffit de la bibliothèque Aspose.BarCode pour .NET et d'un environnement de développement .NET 6 (ou ultérieur).

## Comment créer une image de code-barres avec Aspose.BarCode

La première étape consiste à instancier le générateur avec la symbologie et la chaîne de données souhaitées. L'énumération `EncodeTypes.DatabarStackedOmniDirectional` indique à Aspose.BarCode de produire un code-barres DataBar empilé omni‑directionnel, largement utilisé pour les applications GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Pourquoi c'est important :** L'objet `BarcodeGenerator` est le point d'entrée pour toutes les tâches de création de code-barres. En spécifiant la symbologie et les données brutes dès le départ, vous garantissez que l'image générée est conforme à la norme GS1.

## Définir la X‑dimension (largeur du module)

La X‑dimension définit la largeur de la barre la plus étroite (le module). Une X‑dimension plus grande produit un code-barres plus épais, ce qui peut être utile pour les imprimantes à basse résolution.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c'est important :** Ajuster la X‑dimension fait partie du processus d'optimisation visuelle. Cela n'affecte pas les données encodées, mais cela influence la fiabilité du scan sur différents appareils.

## Comment ajuster le ratio d'aspect – première version (15)

Le ratio d'aspect contrôle la relation hauteur‑largeur du code-barres DataBar. La propriété `DataBar.AspectRatio` accepte des valeurs entières ; des nombres plus grands produisent des barres plus hautes.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Pourquoi c'est important :** Un ratio d'aspect de 15 est une valeur par défaut courante pour les scanners de détail. Le PNG résultant (`DatabarAspectRatio15.png`) aura une apparence plus haute, ce qui peut améliorer le succès du scan sur les appareils portables.

## Comment ajuster le ratio d'aspect – deuxième version (30)

Il se peut que vous ayez besoin d'un code-barres plus haut pour des formats d'étiquettes spécifiques. Modifier le ratio d'aspect est aussi simple que d'assigner une nouvelle valeur entière avant d'appeler à nouveau `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi c'est important :** En démontrant **comment ajuster le ratio d'aspect**, vous pouvez générer plusieurs images de code-barres à partir de la même source de données sans recréer le générateur. Cela réduit l'utilisation de la mémoire et accélère le traitement par lots.

### Résultat attendu

Après l'exécution du programme, vous trouverez deux fichiers PNG dans le répertoire d'exécution :

| File name                     | Aspect ratio | Visual description |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | Hauteur standard, adaptée à la plupart des scanners de point de vente. |
| `DatabarAspectRatio30.png`    | 30           | Barres plus hautes, utiles pour les grandes étiquettes ou les imprimantes à basse résolution. |

Les deux images contiennent le même GTIN encodé `(01)12345678901231`, mais les proportions visuelles diffèrent selon le ratio d'aspect que vous avez défini.

## Questions fréquentes et gestion des cas limites

### Et si j'ai besoin d'une X‑dimension différente ?

Vous pouvez modifier `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` à n'importe quel entier supérieur à zéro. Pour une sortie très haute résolution (par ex., 300 dpi), une valeur de 3‑4 pixels donne souvent des résultats plus nets.

### Comment choisir le bon ratio d'aspect ?

Le ratio optimal dépend de l'environnement de numérisation :
* **Étiquettes à profil bas** – utilisez un ratio plus petit (par ex., 10‑15) pour garder le code-barres compact.  
* **Grandes caisses d'expédition** – un ratio plus élevé (par ex., 25‑35) améliore la lisibilité à distance.  
* **Exigences réglementaires** – certaines normes imposent une hauteur minimale ; consultez la spécification GS1 pour les valeurs exactes.

### Puis-je générer d'autres formats de code-barres avec le même code ?

Oui. Remplacez `EncodeTypes.DatabarStackedOmniDirectional` par toute autre valeur `EncodeTypes` (par ex., `EncodeTypes.Code128`). Le reste du code — X‑dimension, ratio d'aspect (le cas échéant) et enregistrement — reste identique.

### Et si je dois créer l'image dans un autre format ?

`BarCodeImageFormat` prend en charge PNG, JPEG, BMP, GIF et TIFF. Il suffit de changer le deuxième argument de `Save`, par exemple :

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Astuce pro : réutiliser le générateur pour le traitement par lots

Lorsque vous devez créer des dizaines de codes-barres avec les mêmes paramètres visuels, instanciez le générateur une fois, mettez à jour uniquement la propriété `CodeText`, et appelez `Save` de manière répétée. Cela évite le surcoût lié à l'allocation répétée de tampons internes.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Conclusion

Vous savez maintenant comment **créer une image de code-barres** en C# avec Aspose.BarCode et précisément **comment ajuster le ratio d'aspect** pour les symboles DataBar empilés omni‑directionnels. En contrôlant la X‑dimension et le ratio d'aspect, vous pouvez produire des codes-barres qui répondent à n'importe quelle exigence de numérisation ou de mise en page tout en conservant une implémentation simple et maintenable.

### Prochaines étapes

* Explorez d'autres symbologies telles que **Code128** ou **QR Code** en échangeant la valeur `EncodeTypes`.  
* Combinez la génération de code-barres avec la création de PDF (par ex., en utilisant Aspose.PDF) pour intégrer les codes-barres directement dans les factures.  
* Expérimentez la sélection dynamique du ratio d'aspect en fonction de la taille de l'étiquette — cela étend le modèle **comment ajuster le ratio d'aspect** à un moteur complet de conception d'étiquettes.

N'hésitez pas à adapter l'exemple, partager vos résultats ou poser des questions complémentaires dans les commentaires. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres databar empilé en C# avec Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Comment créer une image de code-barres avec Aspose.Barcode en C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Comment ajuster la taille du code-barres – Ratio d'aspect Codablock F avec Aspose.BarCode pour .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}