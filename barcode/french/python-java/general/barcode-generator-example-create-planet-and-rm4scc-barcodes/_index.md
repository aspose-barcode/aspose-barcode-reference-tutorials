---
category: general
date: 2026-10-24
description: Exemple de générateur de code‑barres montrant comment créer un code‑barres
  Planet et comment définir la hauteur du code‑barres avec Python. Suivez le guide
  étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: fr
lastmod: 2026-10-24
og_description: Exemple de générateur de code‑barres démontrant comment créer un code‑barres
  Planet et comment définir la hauteur du code‑barres en Python. Obtenez une solution
  complète et exécutable.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Exemple de générateur de codes-barres – créer des codes-barres Planet et
  RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Exemple de générateur de codes-barres – créer des codes-barres Planet et RM4SCC
  avec hauteur personnalisée
url: /fr/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de générateur de code‑barres – créer des codes Planet et RM4SCC avec une hauteur personnalisée

Si vous recherchez un **exemple de générateur de code‑barres**, ce guide vous fournit une solution complète, prête à l’emploi. Vous verrez **comment créer des images de code‑barres Planet**, apprendrez **comment définir la hauteur du code‑barres**, et comprendrez les petites différences entre le dimensionnement automatique et manuel.

Le tutoriel parcourt deux scénarios réalistes : un code‑barres Planet qui utilise la hauteur par défaut (auto), et un code‑barres RM4SCC dont la hauteur est forcée à 100 px. À la fin, vous pourrez générer des fichiers PNG pour tout type de code‑barres supporté avec une API unique et cohérente.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Python 3.8 ou une version plus récente installé.
* Le package `aspose-barcode` (ou toute bibliothèque fournissant `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`). Installez‑le avec  

  ```bash
  pip install aspose-barcode
  ```
* Des droits d’écriture sur un dossier où les fichiers PNG seront enregistrés.

Aucune dépendance système supplémentaire n’est requise.

## Vue d’ensemble de la solution

Le cœur de l’**exemple de générateur de code‑barres** se compose de trois étapes réutilisables :

1. **Instancier** un `BarcodeGenerator` avec la valeur `EncodeTypes` souhaitée et la chaîne de données.
2. **Configurer** la dimension X (largeur du module) et, si besoin, la hauteur du code‑barres.
3. **Enregistrer** l’image sur le disque au format PNG.

Les deux exemples partagent les étapes 1 et 3 ; seule l’étape 2 diffère car le code‑barres Planet s’appuie sur le calcul automatique de la hauteur fourni par la bibliothèque, tandis que le code‑barres RM4SCC montre **comment définir la hauteur du code‑barres** manuellement.

Voici un diagramme de haut niveau illustrant le flux :

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Texte alternatif : Exemple de générateur de code‑barres montrant les codes Planet et RM4SCC avec des hauteurs différentes.*

## Comment créer un code‑barres Planet – hauteur automatique

Le code‑barres Planet fait partie de la famille postale utilisée par de nombreux services postaux nationaux. Dans la plupart des cas, vous laissez le SDK déterminer la hauteur, ce qui maintient les proportions visuelles correctes pour des longueurs de données variables.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Pourquoi cela fonctionne**

* `EncodeTypes.Planet` indique à la bibliothèque d’utiliser la symbologie Planet.
* Définir `x_dimension.pixels` à 4 donne à chaque module une largeur de 4 px, valeur couramment utilisée pour les étiquettes imprimées.
* Aucune hauteur explicite n’est définie ; le SDK calcule la hauteur optimale en fonction des données et de la dimension X, ce qui fait de cet exemple le **exemple de générateur de code‑barres** le plus simple pour les codes postaux.

**Résultat attendu**

Un fichier PNG 2‑D nommé `PostalPlanetBarHeightAuto.png` contenant un code‑barres Planet net. La hauteur sera d’environ 30 px (selon la version de la bibliothèque) et la largeur sera de 4 px × nombre de modules.

## Comment définir la hauteur du code‑barres – exemple RM4SCC personnalisé

RM4SCC est un autre code‑barres postal qui nécessite souvent une hauteur fixe pour correspondre aux modèles d’étiquettes. Cette partie du tutoriel montre **comment définir la hauteur du code‑barres** à un nombre de pixels précis.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Pourquoi cela fonctionne**

* `EncodeTypes.RM4SCC` sélectionne la symbologie RM4SCC.
* La dimension X reste à 4 px pour garder la taille du module cohérente entre les deux codes‑barres.
* `bar_height.pixels = 100` force le code‑barres à mesurer exactement 100 px de haut, en écrasant le calcul automatique. C’est la méthode recommandée **pour définir la hauteur du code‑barres** lorsque votre mise en page exige une taille spécifique.

**Résultat attendu**

Un fichier PNG nommé `PostalRM4SCCBarHeight100Pixels.png` affichant un code‑barres RM4SCC haut. La largeur reste déterminée par la dimension X, tandis que la hauteur est fixée à 100 px, ce qui le rend adapté aux imprimantes d’étiquettes haute résolution.

## Script complet – combiner les deux exemples

Si vous préférez un script unique qui génère les deux images, copiez le code suivant dans `generate_barcodes.py` et exécutez‑le.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explication du script**

* Deux fonctions d’assistance maintiennent le code DRY (Don’t Repeat Yourself) et facilitent l’extension du script à d’autres symbologies.
* La clause `if __name__ == "__main__":` permet d’importer le fichier comme module sans exécuter la logique de génération, ce qui est utile pour les tests unitaires.
* Tous les paramètres (chaîne de données, dimension X, hauteur) sont explicites, de sorte que le script sert de référence **exemple de générateur de code‑barres** pour les projets futurs.

## Questions fréquentes et cas particuliers

| Question | Réponse |
|----------|--------|
| *Et si je veux une dimension X différente ?* | Modifiez `x_dimension.pixels` avec la largeur de module souhaitée. Des valeurs plus grandes augmentent proportionnellement la taille globale du code‑barres. |
| *Puis‑je générer d’autres formats d’image ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpg`, `Bmp` ou `Gif` selon l’énumération de la bibliothèque. |
| *Que se passe‑t‑il si la chaîne de données contient des caractères invalides ?* | Le générateur lève une `ArgumentException`. Validez les données par rapport au jeu de caractères de la symbologie avant d’appeler le constructeur. |
| *Est‑il possible de définir une hauteur minimale tout en conservant le redimensionnement automatique ?* | Utilisez `gen.parameters.barcode.bar_height.min_pixels = <valeur>` (si le SDK expose une propriété `min_pixels`). Cela empêche le code‑barres de rétrécir sous une taille lisible. |
| *Dois‑je libérer le générateur ?* | La classe `BarcodeGenerator` implémente `IDisposable` en .NET ; en Python le ramasse‑miettes s’en charge, mais vous pouvez appeler `gen.dispose()` si vous créez de nombreuses instances dans une boucle. |

## Conseils pour la mise en production

* **Astuce :** Stockez les valeurs de dimension X et de hauteur dans un fichier de configuration afin de pouvoir les ajuster sans recompilation.
* **Attention à :** Utiliser une hauteur trop petite pour la symbologie sélectionnée ; les scanners pourraient ne pas lire le code‑barres.
* **Note de performance :** Générer un gros lot de codes‑barres est plus rapide lorsque vous réutilisez une seule instance de `BarcodeGenerator` et ne changez que sa propriété `code_text` entre les enregistrements.

## Conclusion

Cet **exemple de générateur de code‑barres** montre à la fois **comment créer des images de code‑barres Planet** avec dimensionnement automatique et **comment définir la hauteur du code‑barres** manuellement pour les codes RM4SCC. En suivant ce guide pas à pas, vous pouvez intégrer la création de codes‑barres dans n’importe quelle application Python, personnaliser les dimensions et produire des fichiers PNG prêts à être imprimés ou affichés numériquement.

### Prochaines étapes

* Explorez d’autres symbologies telles que `EncodeTypes.Postnet` ou `EncodeTypes.Code128` – le même schéma s’applique.
* Expérimentez **comment définir la hauteur du code‑barres** pour les QR codes ou les symboles DataMatrix ; la plupart des bibliothèques exposent une propriété `bar_height` similaire.
* Combinez le générateur avec une bibliothèque PDF pour intégrer les codes‑barres directement dans des factures ou des étiquettes d’expédition.

N’hésitez pas à adapter le script, à partager vos résultats, et à nous dire quels types de code‑barres vous ajouterez ensuite !


## Qu’allez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}