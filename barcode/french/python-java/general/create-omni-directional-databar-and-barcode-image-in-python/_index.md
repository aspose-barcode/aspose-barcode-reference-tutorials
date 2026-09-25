---
category: general
date: 2026-08-12
description: Créez un databar omnidirectionnel avec Python et apprenez comment créer
  une image de code‑barres en Python en utilisant Aspose.BarCode. Suivez le guide
  étape par étape pour une solution complète.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: fr
lastmod: 2026-08-12
og_description: Créez un databar omnidirectionnel avec Python et générez une image
  de code‑barres en quelques minutes. Ce tutoriel présente un exemple complet et exécutable.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Créer une databar omnidirectionnelle – guide complet Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Créer une image de databar et de code‑barres omnidirectionnelle en Python
url: /fr/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un databar omnidirectionnel et une image de code-barres en Python

Si vous devez **créer un databar omnidirectionnel** dans un projet Python, ce guide vous montre comment le faire ainsi que comment **créer une image de code-barres en Python** en utilisant la bibliothèque Aspose.BarCode. Vous obtiendrez un script prêt à l'exécution qui génère deux fichiers PNG avec des rapports d'aspect différents.

Générer un DataBar conforme à la spécification omnidirectionnelle est une exigence courante pour les applications de vente au détail et de logistique. Le tutoriel couvre l'installation, la configuration de la dimension X, l'ajustement du rapport d'aspect et l'enregistrement des images finales. Aucun service externe n'est requis ; tout s'exécute localement.

## Ce dont vous aurez besoin

* Python 3.8 ou une version plus récente installé sur votre machine.
* Accès à un terminal ou à l'invite de commande.
* Permission d'écriture sur un dossier où les images de code-barres seront enregistrées.

La seule dépendance tierce est **Aspose.BarCode for Python via .NET**, qui prend en charge le type Omni‑directional DataBar dès l'installation.

## Étape 1 : Installer Aspose.BarCode pour Python

Aspose.BarCode fournit la classe `BarcodeGenerator` utilisée dans le code d'exemple. Installez le paquet avec `pip` :

```bash
pip install aspose-barcode
```

Le paquet inclut les liaisons d'exécution .NET nécessaires, vous n'avez donc pas besoin d'installer le SDK .NET séparément.

## Étape 2 : Importer la bibliothèque et créer le générateur

La première ligne du script crée un générateur pour un DataBar Omni‑directionnel empilé. La valeur GTIN‑14 `(01)12345678901231` est utilisée comme donnée d'exemple.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Pourquoi cette étape est importante* : la constante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` indique à la bibliothèque d'encoder la valeur en tant que Omni‑directional DataBar, le format requis par de nombreux scanners de point de vente.

## Étape 3 : Définir la dimension X (largeur du module)

La dimension X définit la largeur du plus petit module de barre. Une valeur de `2` pixels produit un code-barres clair et lisible sans taille de fichier excessive.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Pourquoi cette étape est importante* : ajuster la dimension X vous permet d'équilibrer lisibilité et dimensions de l'image. Une dimension X trop petite peut rendre le code-barres difficile à lire sur des imprimantes à basse résolution.

## Étape 4 : Configurer le rapport d'aspect et enregistrer la première image

Le rapport d'aspect influence la hauteur globale du DataBar par rapport à sa largeur. Un rapport d'aspect de `15` crée un style visuel compact.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Astuce** : utilisez `pathlib.Path` pour construire le chemin de sortie, ce qui crée automatiquement les répertoires manquants.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Étape 5 : Modifier le rapport d'aspect pour un deuxième style visuel et enregistrer une autre image

Passer le rapport d'aspect à `30` produit un code-barres plus haut qui peut être requis par du matériel de scanner spécifique.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Pourquoi cette étape est importante* : différents détaillants et appareils de lecture ont des contraintes de taille distinctes. Fournir les deux rapports d'aspect dans un même script vous permet de générer le style exact dont vous avez besoin sans dupliquer le code.

## Script complet – créer un databar omnidirectionnel et une image de code-barres en Python

Voici l'exemple complet et exécutable qui intègre toutes les étapes précédentes. Enregistrez-le sous le nom `generate_databar.py` et exécutez-le avec `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Résultat attendu

L'exécution du script crée les fichiers suivants :

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Les deux images affichent un DataBar omnidirectionnel valide qui peut être scanné par l'équipement de vente au détail standard.

![exemple de création d'un databar omnidirectionnel image de code-barres en Python](example_databar.png "créer un databar omnidirectionnel image de code-barres python")

*L'image ci‑dessus est un espace réservé illustrant les deux fichiers PNG enregistrés.*

## Gestion des problèmes courants

| Issue | Reason | Fix |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode n'est pas installé ou installé dans un environnement différent. | Activez l'environnement virtuel correct et exécutez `pip install aspose-barcode`. |
| `PermissionError` when saving | Le script n'a pas la permission d'écriture pour le dossier cible. | Choisissez un répertoire que vous possédez ou exécutez le script avec les privilèges appropriés. |
| Barcode does not scan | La dimension X est trop faible ou le rapport d'aspect est incompatible avec le scanner. | Augmentez `x_dimension.pixels` à 3 ou 4, et testez différentes valeurs de `aspect_ratio` (par ex., 20, 25). |
| Missing .NET runtime | Aspose.BarCode dépend du runtime .NET sur Windows/Linux. | Installez le dernier runtime .NET depuis le site de Microsoft ; la documentation du paquet fournit des instructions spécifiques à chaque plateforme. |

## Extension de l'exemple

Vous pouvez adapter le script pour générer d'autres variantes de DataBar (par ex., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Remplacez la constante `EncodeTypes` en conséquence :

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Si vous devez intégrer le code-barres dans un PDF, Aspose.PDF for Python peut importer directement le fichier PNG ou vous pouvez utiliser la méthode `save` avec `BarCodeImageFormat.Pdf`.

## Conclusion

Ce tutoriel a montré comment **créer un databar omnidirectionnel** et comment **créer une image de code-barres en Python** en utilisant Aspose.BarCode. Vous disposez maintenant d'un script complet et reproductible qui génère deux fichiers PNG avec des rapports d'aspect différents, gère les problèmes courants et peut être étendu à d'autres formats de code-barres.

Ensuite, explorez la génération de QR codes, l'ajout du code-barres aux factures PDF, ou l'automatisation du traitement par lots pour de grands catalogues de produits. Chacun de ces sujets s'appuie sur le même modèle `BarcodeGenerator` présenté ici. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer une image de code-barres – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Comment créer une image de code-barres et l'afficher en Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}