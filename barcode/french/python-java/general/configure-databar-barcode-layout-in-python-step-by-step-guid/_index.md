---
category: general
date: 2026-08-12
description: Configurez rapidement la mise en page du code‑barres Databar en Python.
  Apprenez à définir les colonnes, les lignes et à enregistrer les images avec la
  bibliothèque de génération de codes‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: fr
lastmod: 2026-08-12
og_description: Configurez la mise en page du code‑barres Databar en Python pour contrôler
  les colonnes, les lignes et la sortie d’image. Suivez ce guide pour une solution
  prête à l’emploi.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configurer la mise en page du code‑barres Databar en Python – tutoriel complet
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Configurer la mise en page du code‑barres Databar en Python – guide étape par
  étape
url: /fr/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurer la mise en page du code‑barres Databar en Python – guide étape par étape

Si vous devez **configurer la mise en page du code‑barres Databar en Python**, ce guide vous accompagne tout au long du processus. Vous verrez comment définir le nombre de colonnes ou de lignes pour un code‑barres Databar Expanded Stacked et comment enregistrer l’image résultante avec un seul appel à la bibliothèque de génération de code‑barres.

Contrôler la mise en page est essentiel lorsque vous intégrez des codes‑barres sur des emballages étroits, des reçus ou des écrans mobiles. Dans les sections ci‑dessous, nous couvrirons les importations requises, les deux options de mise en page (colonnes et lignes) et les meilleures pratiques pour enregistrer une image PNG nette.

## Ce dont vous aurez besoin

* Python 3.8 ou plus récent
* `aspose.barcode` (ou tout package compatible de génération de code‑barres) installé  
  ```bash
  pip install aspose-barcode
  ```
* Permission d'écriture sur un dossier où les fichiers PNG seront stockés

Aucun outil externe supplémentaire n'est requis — la bibliothèque gère le rendu, le redimensionnement et l'encodage d'image en interne.

## Comment configurer la mise en page du code‑barres Databar en Python

Le cœur de la solution est la classe `BarcodeGenerator`. Elle accepte une énumération `EncodeTypes` qui identifie la symbologie du code‑barres — dans ce cas `EncodeTypes.DatabarExpandedStacked`. Après avoir créé le générateur, vous pouvez ajuster la mise en page en définissant les propriétés `columns` ou `rows` sur l'objet paramètre `data_bar`.

### Étape 1 : Importer les classes requises

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Ces importations vous donnent accès au générateur, à l'énumération des types Databar et à la constante de format d'image PNG.

### Étape 2 : Créer un générateur de code‑barres pour Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Pourquoi cette étape ?*  
`EncodeTypes.DatabarExpandedStacked` indique à la bibliothèque de produire la symbologie **Databar Expanded Stacked**, qui prend en charge des chaînes numériques plus longues tout en conservant une empreinte compacte. Le deuxième argument est la donnée à encoder ; il peut s'agir de n'importe quelle chaîne qui respecte la spécification Databar.

### Étape 3 : Définir le nombre de colonnes (mise en page horizontale)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** est la phrase clé pour cette opération. Lorsque vous augmentez le nombre de colonnes, le code‑barres s'étend horizontalement, ce qui peut être utile pour des étiquettes larges. La bibliothèque recalcule automatiquement la largeur du module afin de maintenir la taille globale cohérente.

#### Astuce pro
Le nombre maximal de colonnes pour Databar Expanded Stacked est de 8. Définir une valeur supérieure à cette limite la limitera au maximum, mais il est préférable de valider votre entrée au préalable.

### Étape 4 : Enregistrer l'image du code‑barres avec la mise en page en colonnes

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** est l'action qui écrit le code‑barres rendu sur le disque. PNG est sans perte, ce qui préserve les bords nets nécessaires à un scan fiable.

### Étape 5 : Créer un second générateur pour le même type de code‑barres (mise en page en lignes)

Si vous préférez une pile verticale, vous travaillez avec des lignes au lieu des colonnes. Le code ci‑dessous réutilise la même valeur mais crée une nouvelle instance `BarcodeGenerator` afin d'éviter de mélanger les paramètres de colonnes et de lignes.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Étape 6 : Définir le nombre de lignes (mise en page verticale)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** organise les modules du code‑barres verticalement. Une mise en page à trois lignes réduit la hauteur de chaque pile individuelle, rendant le code‑barres adapté aux reçus étroits ou aux écrans mobiles.

#### Cas limite
Si vous définissez `rows` à 1, la bibliothèque génère un Databar à une seule ligne (équivalent à un Databar standard). Les valeurs inférieures à 1 sont ignorées et réinitialisées à la valeur par défaut (1 ligne).

### Étape 7 : Enregistrer l'image du code‑barres avec la mise en page en lignes

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Encore une fois, nous **save barcode image** en utilisant PNG pour garder la sortie nette.

## Exemple complet exécutable

Assembler toutes les pièces vous fournit un script autonome que vous pouvez intégrer dans n'importe quel projet Python.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Sortie attendue**

L'exécution du script crée deux fichiers PNG :

* `output/ExpandedCols4.png` – un code‑barres étiré sur quatre colonnes
* `output/ExpandedRows3.png` – un code‑barres compressé en trois lignes

Les deux images peuvent être ouvertes avec n'importe quel visualiseur d'images ou importées directement dans des factures PDF, des modèles d'étiquettes ou des pages web.

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| *Que faire si le code‑barres apparaît flou ?* | Augmentez la résolution de l'image en définissant `barcode_generator.parameters.image_width` et `image_height` avant d'appeler `save`. |
| *Puis-je utiliser d'autres formats d'image ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins. |
| *Y a-t-il une limite de longueur des données ?* | Databar Expanded Stacked prend en charge jusqu'à 74 caractères numériques. Dépasser cette limite déclenche une `ArgumentException`. |
| *Comment changer la couleur du premier plan ?* | Utilisez `barcode_generator.parameters.barcode.color = Color.Blue` (importez `System.Drawing.Color`). |
| *Puis-je combiner colonnes et lignes ?* | Non. L'API considère les colonnes et les lignes comme des modes de mise en page mutuellement exclusifs. Choisissez‑en un par instance de code‑barres. |

## Prochaines étapes

Maintenant que vous pouvez **configurer la mise en page du code‑barres Databar**, envisagez d'explorer ces sujets connexes :

* **Add text captions** – utilisez `barcode_generator.parameters.barcode.code_text` pour afficher la valeur encodée sous l'image.
* **Embed the barcode in a PDF** – combinez le PNG généré avec `aspose.pdf` pour créer des documents imprimables.
* **Dynamic sizing** – calculez le nombre optimal de colonnes ou de lignes en fonction des dimensions de l'étiquette à l'exécution.
* **Batch processing** – parcourez un CSV de codes produit pour générer automatiquement une bibliothèque d'images de code‑barres.

Expérimentez différentes valeurs de colonnes et de lignes pour voir comment elles affectent la fiabilité du scan sur vos appareils cibles. Plus vous testez, mieux vous comprendrez les compromis entre la taille du code‑barres, la lisibilité et les contraintes d'espace.

---

*Bon codage ! Si vous avez trouvé ce tutoriel utile, partagez‑le avec vos collègues ou laissez un commentaire sur les défis de mise en page que vous avez rencontrés.*

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Créer une image de code‑barres c# – Configurer les lignes & colonnes de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Ajustement de la hauteur du code‑barres Databar unidimensionnel](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}