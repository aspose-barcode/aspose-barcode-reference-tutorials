---
category: general
date: 2026-11-27
description: Apprenez comment ajuster la hauteur des barres du code‑à‑barres dans
  un générateur de code‑à‑barres DataBar Omni‑Directionnel. Le code étape par étape
  montre comment définir les hauteurs à 30 px et 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: fr
lastmod: 2026-11-27
og_description: Ajustez la hauteur des barres du code‑barres dans un générateur DataBar
  Omni‑Directionnel avec Python. Suivez le guide complet pour définir les hauteurs,
  la dimension X et enregistrer des images PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Ajuster la hauteur des barres du code‑barres dans le générateur DataBar
  omnidirectionnel
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Comment ajuster la hauteur des barres du code‑barres dans le générateur DataBar
  omnidirectionnel
url: /fr/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajuster la hauteur des barres du code‑barres dans le générateur DataBar Omni‑Directional

Si vous devez **ajuster la hauteur des barres du code‑barres** pour un code‑barres DataBar Omni‑Directional, ce guide vous montre exactement comment faire. Vous verrez un exemple complet et exécutable en Python qui change la hauteur des barres de 30 px à 60 px tout en conservant la X‑dimension et le format d’image.

Modifier les dimensions visuelles d’un code‑barres est une exigence courante lorsque le code‑barres doit s’adapter à une taille d’étiquette ou à une directive de conception spécifique. En plus de la hauteur des barres, vous pouvez également ajuster la **X‑dimension** (taille du module) ou choisir un **format d’image de code‑barres** différent comme PNG ou JPEG.

Dans ce tutoriel vous allez :

* Installer la bibliothèque requise (GroupDocs.Barcode for Python)
* Créer un générateur de code‑barres DataBar Omni‑Directional
* Définir la taille du module avec `XDimension`
* Ajuster la propriété de hauteur des barres deux fois
* Enregistrer les images résultantes dans le **BarCodeImageFormat** souhaité

Aucune expérience préalable avec l’API GroupDocs n’est requise — il suffit de connaissances de base en Python.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Python 3.8 ou une version plus récente installé
* paquet `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Permission d’écriture sur un dossier où les fichiers PNG seront enregistrés

Si vous ne connaissez pas le **code‑barres DataBar Omni‑Directional**, il encode un GTIN à 14 chiffres et est largement utilisé dans le commerce de détail pour la lecture sous n’importe quelle orientation.

## Étape 1 : Configurer le générateur de code‑barres DataBar Omni‑Directional

Tout d’abord, importez les classes nécessaires et créez une instance du générateur avec les données GTIN que vous souhaitez encoder.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Pourquoi c’est important :* La constante `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque de produire la symbologie Omni‑Directional. La chaîne de données inclut l’AI `(01)` qui marque une valeur GTIN‑14.

## Étape 2 : Définir la X‑dimension (taille du module)

La X‑dimension contrôle la largeur de la barre la plus étroite. Une valeur courante pour le rendu à l’écran est de **2 px par module**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Utiliser un **set XDimension** cohérent garantit que le code‑barres s’adapte correctement sur différents imprimantes et scanners.

## Étape 3 : Ajuster la hauteur des barres à 30 px et enregistrer l’image

Nous allons maintenant modifier la propriété de hauteur des barres. La première hauteur que nous utiliserons est de **30 px**, adaptée aux petites étiquettes.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

La constante `BarCodeImageFormat.Png` sélectionne le **format d’image du code‑barres** PNG, qui préserve une qualité sans perte.

### Résultat attendu

Le fichier `DatabarBarHeight30Pixels.png` contient un code‑barres DataBar Omni‑Directional dont les barres mesurent 30 px de hauteur. Vous trouverez ci‑dessous un aperçu de substitution :

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Astuce :** Si vous ouvrez le PNG dans un éditeur d’image, vous verrez la hauteur exacte des barres. Les barres étroites font 2 px de largeur, comme défini précédemment.

## Étape 4 : Modifier la hauteur des barres à 60 px pour un code‑barres plus haut

Pour les applications nécessitant une empreinte visuelle plus grande — comme une étiquette de fret — vous pouvez augmenter la hauteur des barres à **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Seule la propriété `BarHeight` change ; la X‑dimension et l’encodage restent identiques, de sorte que le code‑barres reste lisible.

## Étape 5 : Enregistrer l’image du code‑barres mis à jour

Enfin, écrivez le code‑barres plus haut dans un deuxième fichier PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Résultat attendu

Le fichier `DatabarBarHeight60Pixels.png` montre les mêmes données encodées, mais chaque barre mesure maintenant 60 px de hauteur. La différence visuelle est illustrée ci‑dessous :

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Exemple complet et exécutable

En rassemblant tous les éléments, voici le script complet que vous pouvez copier‑coller dans un fichier nommé `adjust_barcode_height.py` et exécuter directement.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Run the script:

```bash
python adjust_barcode_height.py
```

Vous devriez voir deux fichiers PNG dans le dossier `output`, chacun reflétant la hauteur de barre que vous avez définie.

## Questions fréquentes et cas particuliers

| Question | Answer |
|----------|--------|
| **Puis‑je utiliser JPEG au lieu de PNG ?** | Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. JPEG est avec perte, donc privilégiez PNG pour un scan précis. |
| **Que faire si j’ai besoin d’une hauteur de barre qui n’est pas un multiple de 10 ?** | La propriété `BarHeight.Pixels` accepte n’importe quelle valeur entière. Il suffit d’assigner le nombre de pixels souhaité (par ex. `45`). |
| **Le changement de la hauteur des barres affecte‑t‑il les données encodées ?** | Non. Seule la représentation visuelle change ; la chaîne de données sous‑jacente reste identique. |
| **Comment modifier la X‑dimension après avoir enregistré la première image ?** | Vous pouvez modifier `gen.parameters.barcode.x_dimension.pixels` à tout moment avant d’appeler `save()`. Le changement s’appliquera aux images suivantes. |
| **Le générateur est‑il thread‑safe ?** | L’instance `BarcodeGenerator` n’est pas garantie d’être thread‑safe. Créez une instance séparée par thread si vous générez des codes‑barres de façon concurrente. |

## Conclusion

Vous savez maintenant comment **ajuster la hauteur des barres du code‑barres** dans un générateur de code‑barres DataBar Omni‑Directional avec Python. Le tutoriel a couvert la création du générateur, la définition de la **X‑dimension**, la modification de la propriété **barcode bar height**, et l’enregistrement des images dans le **format d’image du code‑barres** souhaité.

À partir d’ici, vous pouvez expérimenter d’autres hauteurs, différentes tailles de modules, ou passer à des formats d’image alternatifs comme JPEG ou BMP. Vous pouvez également explorer d’autres fonctionnalités du **barcode generator python** telles que l’ajout de texte lisible par l’homme ou la modification des schémas de couleur.

Bon codage, et gardez vos codes‑barres nets et parfaitement dimensionnés !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment définir la largeur et ajuster la hauteur d’un code‑barres GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Créer un databar omni‑directionnel et une image de code‑barres en Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – changer la hauteur du code‑barres](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}