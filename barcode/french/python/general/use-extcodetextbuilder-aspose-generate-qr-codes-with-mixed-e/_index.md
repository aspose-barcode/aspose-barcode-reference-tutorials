---
category: general
date: 2026-07-18
description: Utilisez extcodetextbuilder d’Aspose pour créer des codes QR qui combinent
  du texte ASCII simple et du texte russe en UTF‑8. Apprenez la génération de codes
  QR avec Aspose.Barcode en Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: fr
lastmod: 2026-07-18
og_description: Utilisez extcodetextbuilder d'Aspose pour mélanger des fragments simples
  et encodés en UTF‑8 dans un QR Code. Suivez ce guide étape par étape pour Aspose.Barcode
  en Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: Utilisez ExtCodeTextBuilder Aspose – Créez des QR codes avec du texte ECI
  mixte
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Utiliser ExtCodeTextBuilder Aspose : générer des codes QR avec du texte ECI
  mixte'
url: /fr/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# utilisez extcodetextbuilder aspose – Créez des QR Codes avec du texte ECI mixte

Vous vous êtes déjà demandé comment **utiliser extcodetextbuilder aspose** pour intégrer à la fois du texte anglais simple et des caractères cyrilliques dans un même QR Code ? Vous n’êtes pas seul. De nombreux développeurs se heurtent à un mur lorsqu’ils doivent mélanger des données ASCII et non‑ASCII, surtout lorsque le lecteur cible attend des marqueurs ECI (Extended Channel Interpretation) corrects.  

Dans ce tutoriel, nous parcourrons les étapes exactes pour créer un QR Code contenant « HELLO123 » **et** le mot russe « Привет », le tout avec l’API Python d’Aspose.Barcode. À la fin, vous disposerez d’un script prêt à l’exécution, comprendrez pourquoi chaque appel est important, et saurez comment ajuster le processus pour d’autres langues ou formats de données.

## Ce que vous allez apprendre

- Comment **initialiser ExtCodetextBuilder** et ajouter des fragments simples ainsi que des fragments encodés en ECI.  
- Pourquoi la valeur d’encodage ECI `3` correspond à UTF‑8 et comment cela influence la lecture.  
- La séquence exacte pour configurer un **générateur de QR Code** avec Aspose.Barcode.  
- Comment enregistrer l’image résultante et vérifier le contenu mixte.  

**Prérequis** – vous avez besoin de Python 3.8+, du package `aspose-barcode` installé (`pip install aspose-barcode`), et d’un dossier où vous pouvez écrire des images. Rien d’autre.

---

## utilisez extcodetextbuilder aspose pour créer un texte de code mixte

La première chose dont nous avons besoin est une instance `ExtCodetextBuilder`. Pensez‑y comme à un pattern builder qui concatène différentes parties de texte tout en insérant automatiquement les bons marqueurs ECI en arrière‑plan.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Pourquoi c’est important :**  
- `add_plain_codetext` conserve les données telles quelles, ce qui est parfait pour les chiffres ou les lettres anglaises.  
- `add_eci_codetext` insère un segment ECI (`[ECI:3]`) avant la chaîne fournie, indiquant à tout lecteur compatible que les octets suivants sont en UTF‑8. Sans cela, le scanner interpréterait les octets cyrilliques comme du bruit.

> **Astuce :** Si vous avez besoin d’un autre jeu de caractères, modifiez la valeur `eci_encoding` selon le tableau ECI (par ex., `26` pour ISO‑8859‑1).  

---

## Initialise la génération de QR Code avec Aspose.Barcode

Maintenant que nous disposons d’un `extended_codetext` correctement formaté, nous pouvons le transmettre au générateur de QR Code. Aspose.Barcode abstrait la création bas‑niveau de la matrice QR, vous laissant vous concentrer sur les données.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Que se passe‑t‑il ici ?**  
- `BarcodeGenerator()` crée un nouvel objet générateur avec les paramètres par défaut (taille, résolution, etc.).  
- `set_symbology` indique au moteur que nous voulons un QR Code plutôt qu’un Code128, par exemple.  

Si vous avez besoin d’un niveau de correction d’erreurs plus élevé, vous pouvez appeler `qr_generator.parameters.barcode.qr_error_level = ...` avant d’assigner le texte de code.

---

## Assignez le texte de code étendu au générateur QR

Avec le générateur prêt, l’étape suivante consiste simplement à fournir la chaîne mixte que nous avons construite précédemment.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Pourquoi ne pas utiliser `set_codetext` ?**  
`set_codetext` traite l’entrée comme du texte simple, en supprimant tout marqueur ECI. `set_extended_codetext` préserve les octets bruts, y compris le segment ECI, garantissant que le scanner voit le bon changement de langue.

---

## Enregistrez l’image du QR Code et vérifiez le résultat

Enfin, nous écrivons le QR Code sur le disque. Aspose.Barcode prend en charge PNG, JPEG, BMP, et plus ; le PNG est une valeur sûre car il conserve les données sans perte.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Vous devriez maintenant disposer d’un fichier PNG à l’emplacement indiqué. Ouvrez‑le avec n’importe quelle application de lecture de QR qui supporte l’ECI (la plupart des smartphones modernes le font). Scannez une première fois – vous verrez « HELLO123 ». Scannez de nouveau (ou utilisez un scanner qui affiche les données brutes) – vous obtiendrez également « Привет ». Les deux parties apparaissent comme une charge utile unique, exactement comme nous l’avons construite.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Texte alternatif de l’image : exemple de QR code use extcodetextbuilder aspose montrant du texte ECI mixte*

---

## Script complet, prêt à l’exécution

En rassemblant le tout, voici le programme complet que vous pouvez copier‑coller dans un fichier nommé `qr_mixed_eci.py` :

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Exécutez‑le avec :

```bash
python qr_mixed_eci.py
```

Vous verrez un message dans la console confirmant le chemin d’enregistrement, et le PNG apparaîtra exactement où vous l’avez indiqué.

---

## Questions fréquentes & cas particuliers

### Et si mon scanner ne reconnaît pas la partie cyrillique ?
Assurez‑vous que l’application de lecture indique un support ECI. Le matériel plus ancien peut ignorer le segment ECI et traiter les octets comme ISO‑8859‑1, ce qui produit des caractères illisibles.

### Puis‑je ajouter plus de deux fragments ?
Absolument. Appelez `add_plain_codetext` ou `add_eci_codetext` autant de fois que nécessaire. Le builder les concatène dans l’ordre d’appel.

### Comment modifier la taille du QR Code ou la couleur du premier plan ?
Utilisez l’objet `qr_generator.parameters` :

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Existe‑t‑il un moyen d’embedder des données binaires (par ex., un petit fichier) avec du texte ?
Oui. Utilisez `add_binary_codetext` avec un tableau d’octets, et associez‑le à un ECI approprié si le binaire représente un jeu de caractères spécifique. Le builder gérera les changements de mode nécessaires.

---

## Conclusion

Vous savez maintenant **comment utiliser extcodetextbuilder aspose** pour créer des QR Codes qui mêlent harmonieusement du texte ASCII simple et du texte russe encodé en UTF‑8. En exploitant `ExtCodetextBuilder`, en définissant le bon **encodage ECI**, et en injectant le résultat dans un **générateur QR Code Aspose.Barcode**, vous obtenez une image unique conforme aux standards qui fonctionne avec les scanners modernes.  

À partir d’ici, essayez de remplacer `eci_encoding=3` par d’autres identifiants de langue, ou expérimentez avec des fragments simples supplémentaires pour construire des charges utiles multilingues. Vous pouvez également explorer les options `BarCodeImageFormat` pour générer du SVG ou du PDF si vous avez besoin de graphiques vectoriels.  

Bon codage, et n’hésitez pas à laisser un commentaire si vous rencontrez des difficultés — votre retour aide à améliorer ces guides !

## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer un code‑barres Java - Définir le texte du code avec Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Créer un code‑barres aspose .net - Configurer le texte du DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Encodage du texte du code Aztec avec Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}