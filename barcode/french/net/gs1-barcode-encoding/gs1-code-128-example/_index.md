---
date: 2026-09-08
description: Apprenez à créer un code‑128 barcode et à générer des codes‑barres GS1
  en C# avec Aspose.BarCode pour .NET. Guide étape par étape, prérequis et personnalisation
  sans code.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Exemple GS1 Code 128
og_description: Apprenez à créer un code‑128 barcode et à générer des codes‑barres
  GS1 en C# avec Aspose.BarCode pour .NET. Suivez un guide étape par étape pour générer
  et enregistrer rapidement des images de barcode.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Comment créer un code‑128 barcode avec GS1 en utilisant Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Comment créer un code‑128 barcode avec GS1 en utilisant Aspose.BarCode
url: /fr/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres code 128 avec GS1 en utilisant Aspose.BarCode

Dans ce tutoriel, vous apprendrez à **créer un code‑barres code 128** conforme à la norme GS1 en utilisant la bibliothèque Aspose.BarCode pour .NET. Que vous ayez besoin d’un code‑barres pour l’inventaire, l’expédition ou le point de vente, ce guide vous accompagne à chaque étape—de la configuration de l’environnement de développement à l’enregistrement de l’image finale—pour que vous puissiez générer des codes‑barres fiables en quelques minutes.

## Réponses rapides
- **Quelle est la classe principale pour générer un code‑barres ?** `BarcodeGenerator` crée et configure l’image du code‑barres.  
- **Quelle symbologie utilise le Code 128 GS1 ?** Elle utilise le type `EncodeTypes.Code128` avec un formatage de données spécifique à GS1.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je changer le format de l’image ?** Oui—enregistrez en PNG, JPEG, BMP ou TIFF en modifiant l’extension du fichier.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+.

## Qu’est‑ce que créer un code‑barres code 128 ?
`create code 128 barcode` désigne la génération d’un code‑barres linéaire qui encode des données alphanumériques en utilisant la symbologie Code 128, largement adoptée dans la logistique car elle prend en charge l’ensemble complet ASCII et peut intégrer des Identifiants d’Application GS1. Le code‑barres peut stocker des identifiants de produit, des numéros de série et d’autres données personnalisées, ce qui le rend adapté à un large éventail de scénarios métier.

## Pourquoi utiliser Aspose.BarCode pour le Code 128 GS1 ?
Aspose.BarCode prend en charge **plus de 30 symbologies de codes‑barres** et peut rendre des images jusqu’à **10 000 × 10 000 px** sans perte de qualité, ce qui le rend idéal pour l’impression d’étiquettes haute résolution. La bibliothèque valide également automatiquement les structures de données GS1, réduisant le risque de codes‑barres mal formés sur les lignes de production. De plus, elle offre de nombreuses options de personnalisation (taille, couleur, mise en page) pour répondre aux exigences strictes des normes industrielles.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

1. **Environnement de développement .NET** – Visual Studio 2022, Rider ou tout IDE supportant .NET 6+.  
2. **Aspose.BarCode pour .NET** – téléchargez‑le depuis la **page de téléchargement Aspose.BarCode pour .NET** à l’adresse [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) et ajoutez le package NuGet `Aspose.BarCode` à votre projet.  
3. **Connaissances de base en C#** – vous devez être à l’aise avec la création d’applications console ou Windows.  
4. **Compréhension du Code 128 GS1** – optionnel mais utile ; GS1 utilise des Identifiants d’Application (AI) comme `(01)` pour le GTIN et `(21)` pour les numéros de série.

## Comment créer un code‑barres code 128 étape par étape

Chargez la bibliothèque, configurez le type de code‑barres, définissez les données GS1, personnalisez les dimensions, puis enregistrez l’image. La réponse directe à la question « comment créer un code‑barres code 128 ? » est : **instancier `BarcodeGenerator` avec `EncodeTypes.Code128` et des données formatées GS1, ajuster `XDimension` si nécessaire, puis appeler `Save` avec le nom de fichier et le format souhaités**. Les sections suivantes détaillent chaque étape.

### Étape 1 : définissez le chemin de votre répertoire
Définissez le dossier où l’image générée sera stockée. Garder le chemin configurable rend le code réutilisable dans différents environnements.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Remplacez `"Your Directory Path"` par un chemin absolu ou relatif que votre application peut écrire, tel que `@"C:\Barcodes"` ou `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Étape 2 : créez un code‑barres GS1 Code 128
Créez le générateur de code‑barres, spécifiez la symbologie et fournissez les données formatées GS1. La chaîne de données doit inclure les Identifiants d’Application entre parenthèses.

```csharp
string path = "Your Directory Path";
```

L’exemple utilise le GTIN `(01)12345678901231`, un numéro de série `(21)ASPOSE` et un AI personnalisé supplémentaire `(30)9876`. Aspose.BarCode insère automatiquement le caractère FNC1 requis pour la conformité GS1.

### Étape 3 : personnalisez les paramètres du code‑barres
Ajustez les paramètres visuels tels que `XDimension` (largeur de la barre fine) pour contrôler la densité du code‑barres. Vous pouvez également modifier la hauteur, les couleurs et les marges.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Définir `XDimension = 2` produit un code‑barres facilement lisible par la plupart des lecteurs portables tout en maintenant une taille d’image raisonnable.

### Étape 4 : enregistrez l’image du code‑barres
Persistez le code‑barres généré sur le disque. Vous pouvez choisir PNG pour une qualité sans perte, JPEG pour des fichiers plus légers ou TIFF pour les flux de travail d’impression. La méthode `Save` écrit le fichier image dans le format indiqué par l’extension du fichier.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Remplacez `GS1Code128Example.png` par tout nom de fichier valide et l’extension correspondant au format de sortie désiré.

### Étape 5 : vérifiez le code‑barres (optionnel)
Après l’enregistrement, vous pouvez recharger l’image dans votre application ou utiliser un lecteur de code‑barres pour confirmer que les données encodées correspondent à la chaîne d’origine. Cette étape est utile pendant le développement et les tests automatisés.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Problèmes courants et conseils de dépannage
- **FNC1 non détecté** – Assurez‑vous que la chaîne de données commence par une parenthèse ouvrante et inclut des AI GS1 valides ; la bibliothèque insère FNC1 automatiquement uniquement pour les modèles reconnus.  
- **Image non enregistrée** – Vérifiez que le répertoire cible existe et que l’application possède les droits d’écriture. Utilisez `Directory.CreateDirectory(path)` pour le créer à la volée.  
- **Code‑barres trop dense** – Diminuez `XDimension` ou augmentez la hauteur de l’image pour offrir plus d’espace aux lecteurs afin de lire les barres fines.  
- **Caractères non pris en charge** – Le Code 128 ne peut encoder que l’ensemble complet ASCII ; évitez les caractères Unicode en dehors de cette plage.

## Questions fréquemment posées

**Q : Puis‑je générer des codes‑barres dans une API Web sans installer le framework .NET complet ?**  
R : Oui, Aspose.BarCode fonctionne avec .NET Core et .NET 5/6, vous pouvez donc exposer un point d’accès REST léger qui renvoie des images de code‑barres à la demande.

**Q : La bibliothèque prend‑elle en charge la génération en lot de plusieurs codes‑barres ?**  
R : Absolument. Parcourez une collection de chaînes de données, créez un `BarcodeGenerator` pour chacune, puis appelez `Save` dans la boucle. La bibliothèque est thread‑safe pour le traitement parallèle.

**Q : Existe‑t‑il un moyen d’intégrer directement le code‑barres dans un PDF ?**  
R : Utilisez Aspose.PDF pour créer un document PDF, puis appelez `PdfPage.AddImage` avec le flux d’image du code‑barres. Cela évite d’écrire des fichiers intermédiaires sur le disque.

**Q : Comment garantir que le code‑barres respecte les normes de qualité ISO/GS1 ?**  
R : Définissez `BarcodeGenerator.Options.Barcode.XDimension` à au moins 0,33 mm et ajustez `BarHeight` selon la taille de l’étiquette. Aspose.BarCode valide le format AI et lève une exception en cas de données invalides.

**Q : Quelles options de licence sont disponibles pour une utilisation en production ?**  
R : Aspose propose des licences perpétuelles, d’abonnement et basées sur le cloud. Une licence d’essai fonctionne pour l’évaluation, mais une licence payante supprime le filigrane d’évaluation et débloque toutes les fonctionnalités.

## Ressources supplémentaires

- **Documentation** – Accédez à la référence complète de l’API sur [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Téléchargement** – Obtenez la dernière version de la bibliothèque depuis [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Essai gratuit** – Commencez un essai de 30 jours sur [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Achat** – Achetez une licence commerciale sur [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Support** – Rejoignez le forum communautaire sur [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) pour obtenir de l’aide.

---

**Dernière mise à jour :** 2026-09-08  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un code‑barres ITF‑14 .NET – Tutoriels complets Aspose.BarCode](/barcode/net/)  
- [Générer des codes‑barres Databar 2D unidimensionnels avec Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}