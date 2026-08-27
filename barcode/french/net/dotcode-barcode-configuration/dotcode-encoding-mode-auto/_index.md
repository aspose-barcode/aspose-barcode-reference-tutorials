---
date: 2026-06-14
description: Apprenez à créer un code‑barres dotcode .NET à l’aide d’Aspose.BarCode
  pour .NET. Guide étape par étape, prérequis, extraits de code et informations de
  licence.
keywords:
- create dotcode barcode .net
- Aspose.BarCode .NET
- DotCode encoding
linktitle: Mode d’encodage DotCode (Auto)
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create dotcode barcode .net using Aspose.BarCode for .NET.
    Step‑by‑step guide, prerequisites, code snippets, and licensing info.
  headline: Create DotCode Barcode .NET (Auto Mode) with Aspose.BarCode
  type: TechArticle
- description: Learn how to create dotcode barcode .net using Aspose.BarCode for .NET.
    Step‑by‑step guide, prerequisites, code snippets, and licensing info.
  name: Create DotCode Barcode .NET (Auto Mode) with Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Replace `"Your Directory Path"` with the actual folder where you want the
      PNG file saved.
  - name: Initialize Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core object that creates barcodes.
      It takes an `EncodeTypes` value and the data to encode. EncodeTypes is an enumeration
      that specifies the barcode symbology to generate. - We create an instance of
      `BarcodeGenerator` and specify `EncodeTypes.DotCode`. - The sec'
  - name: Customize DotCode Parameters
    text: The `DotCode` property group lets you fine‑tune the symbol. - Set the X‑dimension
      (module size) with `gen.Parameters.Barcode.XDimension.Pixels`. XDimension defines
      the size of a single module (dot) in pixels, controlling the overall barcode
      size. Here it’s 10 px, but you can adjust from 2 px to 30 p
  - name: Save the Barcode Image
    text: '- Call `gen.Save` with the full file path and `BarCodeImageFormat.Png`
      to write the image. BarCodeImageFormat enumerates supported image output formats
      such as PNG, JPEG, and SVG. - The library automatically handles DPI scaling,
      so the output is ready for printing or on‑screen display. That’s the co'
  type: HowTo
- questions:
  - answer: Up to 1,500 bytes, which covers most alphanumeric and Unicode strings.
    question: What is the maximum data capacity of DotCode in Auto mode?
  - answer: Yes—simply change the `BarCodeImageFormat` to `Svg` in the `Save` call.
    question: Can I generate SVG instead of PNG?
  - answer: No, it works with .NET Core and .NET 5/6/7 as well as the classic Framework.
    question: Does Aspose.BarCode require a full .NET Framework installation?
  - answer: Save the image to a memory stream and write it to the response with `Response.BinaryWrite`.
    question: How can I embed the generated barcode in an ASP.NET page?
  - answer: Visit the Aspose.BarCode forum [here](https://forum.aspose.com/c/barcode/13)
      for community and expert assistance.
    question: Where can I get help if I run into problems?
  type: FAQPage
second_title: Aspise.BarCode .NET API
title: Créer un code‑barres DotCode .NET (mode Auto) avec Aspose.BarCode
url: /fr/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres DotCode .NET (mode Auto) avec Aspose.BarCode

Lorsqu'il s'agit de génération de codes-barres en .NET, Aspose.BarCode pour .NET se démarque comme un outil polyvalent et puissant qui vous permet de **créer un code-barres DotCode .NET** rapidement et de manière fiable. Que vous soyez un développeur chevronné ou que vous débutiez, ce tutoriel vous guide pas à pas à travers le mode d'encodage Auto, afin que vous puissiez générer des symboles DotCode de haute qualité sans tracas.

## Réponses rapides
- **Que fait le mode Auto ?** Il sélectionne automatiquement l'encodage DotCode optimal en fonction de vos données d'entrée.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ai-je besoin d'une licence pour les tests ?** Oui – une licence temporaire fonctionne pour l'évaluation.  
- **Combien de types de codes-barres Aspose.BarCode prend‑il en charge ?** Plus de 50 symbologies, y compris QR, DataMatrix et DotCode.  
- **Puis‑je exporter en PNG, JPEG ou SVG ?** Les trois formats sont disponibles immédiatement.

## Qu'est‑ce que le mode d'encodage DotCode (Auto) ?
Le mode Auto choisit automatiquement l'encodage DotCode le plus efficace (numérique, alphanumérique ou octet) en fonction des données fournies. Cela élimine les conjectures et garantit une taille de symbole optimale ainsi qu'une lisibilité maximale. Il évalue la chaîne d'entrée, sélectionne la représentation interne appropriée et configure le symbole afin d'obtenir l'empreinte la plus petite possible tout en maintenant la fiabilité du scan.

## Pourquoi utiliser Aspose.BarCode pour .NET ?
Aspose.BarCode traite **des documents de plusieurs centaines de pages** sans charger le fichier complet en mémoire, prend en charge **plus de 50 symbologies de codes-barres**, et peut générer des images à **jusqu'à 300 dpi** — idéal à la fois pour les environnements de bureau et les serveurs à haut débit.

## Prérequis
Avant de plonger dans le mode Auto, assurez‑vous d'avoir :

1. **Aspose.BarCode pour .NET** – installez la bibliothèque. Vous pouvez trouver la documentation et le lien de téléchargement [ici](https://reference.aspose.com/barcode/net/) et [ici](https://releases.aspose.com/barcode/net/), respectivement.  
2. **Environnement de développement** – Visual Studio (toute version récente) ou VS Code avec le SDK .NET.  
3. **Connaissances de base en .NET** – familiarité avec la syntaxe C# et la structure d'un projet.  
4. **Curiosité** – la volonté d'expérimenter avec les paramètres du code-barres.

## Comment créer un code-barres DotCode .NET ?
Chargez vos données, créez une instance du générateur, ajustez quelques paramètres DotCode et enregistrez l'image — le tout tient en cinq lignes concises de C#. La classe `BarcodeGenerator` gère l'encodage, le rendu et la sortie du fichier, tandis que le mode Auto décide de la meilleure représentation interne pour vous. Cette approche fonctionne pour des chaînes de n'importe quelle longueur, y compris les caractères Unicode, et produit un PNG net qui peut être intégré dans des rapports, des étiquettes ou des pages web.

### Étape 1 : Définir le chemin du répertoire

```csharp
using Aspose.BarCode.Generation;
```

Remplacez `"Your Directory Path"` par le dossier réel où vous souhaitez enregistrer le fichier PNG.

### Étape 2 : Initialiser le générateur de code-barres

`BarcodeGenerator` est l'objet principal d'Aspose.BarCode qui crée les codes-barres. Il prend une valeur `EncodeTypes` et les données à encoder. EncodeTypes est une énumération qui spécifie la symbologie de code-barres à générer.

```csharp
string path = "Your Directory Path";
```

- Nous créons une instance de `BarcodeGenerator` et spécifions `EncodeTypes.DotCode`.  
- Le deuxième argument est la chaîne de données ; dans cet exemple nous utilisons `"犬Right狗"` pour démontrer la gestion Unicode.

### Étape 3 : Personnaliser les paramètres DotCode

Le groupe de propriétés `DotCode` vous permet d'ajuster finement le symbole.  

```csharp
System.Console.WriteLine("DotCodeEncodeModeAuto:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "犬Right狗"))
{
    // Additional settings go here
}
```

- Définissez la X‑dimension (taille du module) avec `gen.Parameters.Barcode.XDimension.Pixels`. XDimension définit la taille d'un seul module (point) en pixels, contrôlant la taille globale du code-barres. Ici, elle est de 10 px, mais vous pouvez l'ajuster de 2 px à 30 px.  
- Spécifiez l'encodage ECI en UTF‑8 via `gen.Parameters.Barcode.DotCode.ECIEncoding`, garantissant le rendu correct des caractères non ASCII. ECIEncoding définit l'Extended Channel Interpretation, indiquant l'encodage des caractères (par ex. UTF‑8) pour les données.

### Étape 4 : Enregistrer l'image du code-barres

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.ECIEncoding = ECIEncodings.UTF8;
```

- Appelez `gen.Save` avec le chemin complet du fichier et `BarCodeImageFormat.Png` pour écrire l'image. BarCodeImageFormat énumère les formats de sortie d'image pris en charge tels que PNG, JPEG et SVG.  
- La bibliothèque gère automatiquement le redimensionnement DPI, de sorte que la sortie est prête pour l'impression ou l'affichage à l'écran.

C’est le flux de travail complet — cinq étapes, aucune table d'encodage manuelle, et une intégration .NET complète.

## Problèmes courants et solutions
- **Des caractères indésirables apparaissent** – Assurez‑vous que `ECIEncoding` correspond au jeu de caractères de votre entrée (UTF‑8 est le plus sûr pour Unicode).  
- **L'image est floue** – Augmentez la X‑dimension ou définissez un DPI plus élevé en utilisant `gen.Parameters.ImageResolution`.  
- **Les longues chaînes de données provoquent des erreurs** – DotCode prend en charge jusqu'à **1 500 octets** en mode Auto ; divisez les données en plusieurs symboles si vous dépassez cette limite.

## Questions fréquentes
**Q : Quelle est la capacité maximale de données de DotCode en mode Auto ?**  
R : Jusqu'à 1 500 octets, ce qui couvre la plupart des chaînes alphanumériques et Unicode.

**Q : Puis‑je générer du SVG au lieu du PNG ?**  
R : Oui — il suffit de changer `BarCodeImageFormat` en `Svg` dans l'appel `Save`.

**Q : Aspose.BarCode nécessite‑t‑il une installation complète du .NET Framework ?**  
R : Non, il fonctionne avec .NET Core et .NET 5/6/7 ainsi qu'avec le Framework classique.

**Q : Comment intégrer le code‑barres généré dans une page ASP.NET ?**  
R : Enregistrez l'image dans un flux mémoire et écrivez‑la dans la réponse avec `Response.BinaryWrite`.

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
R : Consultez le forum Aspose.BarCode [ici](https://forum.aspose.com/c/barcode/13) pour obtenir l'aide de la communauté et des experts.

## Conclusion
Dans ce tutoriel, vous avez appris comment **créer un code‑barres DotCode .NET** en utilisant le mode d'encodage Auto d'Aspose.BarCode. Nous avons couvert les prérequis, les importations d'espaces de noms, la génération étape par étape et les conseils de dépannage. L'API riche de la bibliothèque vous permet de personnaliser la taille, l'encodage et le format de sortie, la rendant adaptée à tout, des étiquettes d'inventaire aux systèmes de fabrication à haut volume.

Pour une personnalisation plus poussée — comme ajouter du texte lisible, changer les couleurs ou intégrer la génération de PDF — explorez la documentation complète [ici](https://reference.aspose.com/barcode/net/). Vous pouvez également télécharger la dernière version de la bibliothèque depuis [ce lien](https://releases.aspose.com/barcode/net/) et obtenir une licence temporaire pour l'évaluation [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-06-14  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

```csharp
gen.Save($"{path}DotCodeEncodeModeAuto.png", BarCodeImageFormat.Png);
```
{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Personnaliser le ratio d'aspect DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Initialisation du lecteur DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-reader-initialization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}