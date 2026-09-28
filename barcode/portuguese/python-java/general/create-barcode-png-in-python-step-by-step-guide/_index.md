---
category: general
date: 2026-08-03
description: Crie PNG de código de barras rapidamente com este guia. Aprenda como
  gerar imagem de código de barras usando Aspose.BarCode e gerar código de barras
  planetário.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode image
- generate planet barcode
- Python barcode generation
- Aspose.BarCode tutorial
language: pt
lastmod: 2026-08-03
og_description: Crie PNG de código de barras instantaneamente. Este tutorial mostra
  como gerar imagem de código de barras e gerar código de barras Planet com Aspose.BarCode.
og_image_alt: Example of a Planet barcode saved as a PNG image
og_title: Criar código de barras PNG em Python – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  headline: Create barcode PNG in Python – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  name: Create barcode PNG in Python – step‑by‑step guide
  steps:
  - name: 1. Install the Aspose.BarCode package
    text: 'Aspose provides a pure‑Python package that wraps its .NET core engine.
      Install it with `pip`:'
  - name: 2. Import required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 3. Create a barcode generator for the Planet symbology
    text: '```python # Step 1: Create a barcode generator for the Planet symbology
      with the desired data barcode_generator = BarcodeGenerator(EncodeTypes.Planet,
      "123456") ```'
  - name: 4. Set the X dimension (module width) in pixels
    text: '```python # Step 2: Set the X dimension (module width) in pixels barcode_generator.parameters.barcode.x_dimension.pixels
      = 4 ```'
  - name: 5. Define a manual bar height in pixels
    text: '```python # Step 3: Define a manual bar height in pixels barcode_generator.parameters.barcode.bar_height.pixels
      = 100 ```'
  - name: 6. Save the generated barcode as a PNG image
    text: '```python # Step 4: Save the generated barcode as a PNG image output_path
      = "output/PlanetBarHeight100.png" barcode_generator.save(output_path, BarCodeImageFormat.Png)
      print(f"Barcode saved to {output_path}") ```'
  - name: 7. Verify the output (optional)
    text: '```python from PIL import Image'
  - name: ' ## What Should You Learn Next?


      The following tutorials cover closely related topics that build on the techniques
      demonstrated in this guide. Each resource includes complete working code examples
      with step-by-step explanations to help you master additional API features and
      explore alternative implementation approaches in your own projects.

      - [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
      - [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
      - [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

      {{< /blocks/products/pf/tutorial-page-section >}}'
    text: '{{< /blocks/products/pf/main-container >}} {{< /blocks/products/pf/main-wrap-class
      >}} {{< blocks/products/products-backtop-button >}}'
  type: HowTo
tags:
- barcode
- PNG
- Python
- Aspose
title: Criar código de barras PNG em Python – guia passo a passo
url: /pt/python-java/general/create-barcode-png-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar barcode PNG em Python – guia passo a passo

Se você precisa **criar arquivos barcode PNG** a partir da sua aplicação Python, este tutorial mostra exatamente como fazer. Vamos percorrer **como gerar imagem de barcode** usando Aspose.BarCode e especificamente **gerar barcode planet** com dimensões personalizadas.

Você aprenderá como instalar a biblioteca, configurar a simbologia Planet, ajustar os parâmetros de tamanho e salvar o resultado como um PNG de alta qualidade. O guia assume conhecimento básico de Python e uma versão recente do Python 3 (3.8 ou superior). Não é necessária experiência prévia com padrões de barcode.

---

## Como criar barcode PNG com Aspose.BarCode

Esta seção contém as etapas principais necessárias para **criar barcode PNG**. Cada passo inclui um trecho de código, uma explicação do porquê é importante e dicas práticas que você pode aplicar imediatamente.

### 1. Instalar o pacote Aspose.BarCode

Aspose provides a pure‑Python package that wraps its .NET core engine. Install it with `pip`:

```bash
pip install aspose-barcode
```

*Por que esta etapa importa:* O pacote fornece a classe `BarcodeGenerator` usada ao longo do exemplo. Instalá‑lo globalmente garante que o interpretador possa localizar o assembly em tempo de execução.

### 2. Importar classes necessárias

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

*Dica:* Importe apenas os símbolos que você precisa; isso mantém o namespace limpo e acelera o carregamento do módulo.

### 3. Criar um gerador de barcode para a simbologia Planet

```python
# Step 1: Create a barcode generator for the Planet symbology with the desired data
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

*Por que isso importa:* `EncodeTypes.Planet` indica ao motor para usar o padrão de barcode Planet, enquanto o segundo argumento fornece os dados a serem codificados. Alterar a simbologia (por exemplo, `EncodeTypes.Code128`) produziria um padrão visual completamente diferente.

### 4. Definir a dimensão X (largura do módulo) em pixels

```python
# Step 2: Set the X dimension (module width) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

*Explicação:* A dimensão X controla a largura da barra estreita. Um valor de 4 pixels produz um barcode moderadamente denso que permanece legível na maioria dos dispositivos.

### 5. Definir manualmente a altura da barra em pixels

```python
# Step 3: Define a manual bar height in pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

*Por que você pode ajustar isso:* Algumas impressoras de varejo exigem barras mais altas para uma leitura confiável. A altura padrão costuma ser 50 px; aumentá‑la para 100 px melhora a legibilidade sem aumentar drasticamente o tamanho do arquivo.

### 6. Salvar o barcode gerado como imagem PNG

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "output/PlanetBarHeight100.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

*Resultado:* Um arquivo PNG chamado **PlanetBarHeight100.png** aparece na pasta `output`. PNG é sem perdas, tornando‑lo ideal para impressão e para incorporação em páginas web.

### 7. Verificar a saída (opcional)

```python
from PIL import Image

with Image.open(output_path) as img:
    img.show()   # Opens the default image viewer
    print(f"Image size: {img.size} (width, height)")
```

*Dica:* Visualizar a imagem confirma que as dimensões correspondem aos parâmetros definidos. Se o barcode parecer distorcido, revise as configurações da dimensão X ou da altura da barra.

---

## Como gerar imagem de barcode em formato PNG (configurações alternativas)

Se você precisar de um formato de imagem diferente ou quiser incorporar o barcode em um PDF posteriormente, pode alterar o enum `BarCodeImageFormat`:

```python
# Save as JPEG instead of PNG
barcode_generator.save("output/PlanetBar.jpeg", BarCodeImageFormat.Jpeg)

# Save as BMP for legacy Windows applications
barcode_generator.save("output/PlanetBar.bmp", BarCodeImageFormat.Bmp)
```

*Por que isso importa:* PNG preserva cada pixel, o que é crucial para barcodes de alto contraste. JPEG introduz artefatos de compressão que podem interferir na leitura, enquanto BMP oferece compatibilidade com ferramentas mais antigas.

---

## Gerar barcode planet com cores personalizadas (avançado)

Além do tamanho, você pode personalizar as cores de primeiro plano e de fundo:

```python
from aspose.barcode import Color

# Set foreground to dark blue and background to light gray
barcode_generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
barcode_generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

barcode_generator.save("output/PlanetColored.png", BarCodeImageFormat.Png)
```

*Dica prática:* Pares de cores de alto contraste (escuro sobre claro) maximizam a confiabilidade do scanner. Evite usar tons semelhantes para o primeiro plano e o fundo.

---

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa | Correção |
|---------|-------|-----|
| Barcode não escaneia | Dimensão X muito pequena (≤ 2 px) | Aumente `x_dimension.pixels` para pelo menos 3 px |
| Imagem aparece borrada | PNG salvo com DPI baixo | Use `barcode_generator.save(..., BarCodeImageFormat.Png, 300)` para especificar 300 DPI (se suportado) |
| Exceção `ImportError` | Aspose.BarCode não instalado | Execute `pip install aspose-barcode` no mesmo ambiente do seu script |
| Simbologia errada | Usou `EncodeTypes.Code128` em vez de `EncodeTypes.Planet` | Substitua por `EncodeTypes.Planet` ao criar o gerador |

---

## Recapitulação da solução completa

Abaixo está o script completo e executável que **cria barcode PNG** do início ao fim:

```python
# full_example.py
# -------------------------------------------------
# Demonstrates how to generate a Planet barcode PNG
# -------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create generator with Planet symbology
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# 2️⃣ Configure dimensions
generator.parameters.barcode.x_dimension.pixels = 4          # module width
generator.parameters.barcode.bar_height.pixels = 100        # bar height

# 3️⃣ Optional: set colors (uncomment to use)
# from aspose.barcode import Color
# generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
# generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

# 4️⃣ Save as PNG
png_path = os.path.join(output_dir, "PlanetBarHeight100.png")
generator.save(png_path, BarCodeImageFormat.Png)

print(f"✅ Barcode PNG created at: {png_path}")

# 5️⃣ Verify (opens the image on most OSes)
try:
    from PIL import Image
    with Image.open(png_path) as img:
        img.show()
        print(f"Image size: {img.size}")
except Exception as e:
    print(f"Verification step skipped: {e}")
```

Executar este script produz um **Planet barcode PNG** nítido que você pode incorporar em HTML, anexar a e‑mails ou imprimir em etiquetas de produto.

---

## Próximos passos e tópicos relacionados

* **Integrar com Flask ou Django** – sirva o PNG gerado diretamente de um endpoint web.  
* **Geração em lote** – percorra uma lista de IDs de produto para criar uma pasta de arquivos barcode PNG.  
* **Combinar com geração de PDF** – use `aspose-pdf` para inserir o PNG em uma fatura ou etiqueta de envio.  
* **Explorar outras simbologias** – substitua `EncodeTypes.Planet` por `EncodeTypes.QR`, `EncodeTypes.DataMatrix` ou `EncodeTypes.Code128` para atender a diferentes necessidades de negócio.

Ao dominar as etapas acima, você agora sabe **como gerar imagem de barcode** programaticamente e pode estender o padrão a qualquer padrão de barcode suportado pelo Aspose.BarCode.

###

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}