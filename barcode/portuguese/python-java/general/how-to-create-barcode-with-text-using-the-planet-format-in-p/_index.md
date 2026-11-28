---
category: general
date: 2026-11-27
description: Aprenda a criar códigos de barras com texto e gerar códigos de barras
  planetários em Python — guia passo a passo para saída PNG de alta resolução.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: pt
lastmod: 2026-11-27
og_description: Crie um código de barras com texto e gere o código de barras planetário
  em Python. Siga este guia completo para gerar um PNG em alta resolução.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Crie código de barras com texto em Python – gere código de barras Planet
  facilmente
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Como criar código de barras com texto usando o formato Planet em Python
url: /pt/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras com texto usando o formato Planet em Python

Se você precisa **criar código de barras com texto** para um sistema de correspondência, este tutorial mostra exatamente como fazer isso. Você verá um exemplo conciso, de ponta a ponta, que gera um código de barras Planet, ajusta a resolução e salva o resultado como uma imagem PNG.

Gerar códigos de barras é uma necessidade comum para aplicações de logística, inventário e bilhetagem. Neste guia você aprenderá não apenas **como gerar códigos de barras**, mas também por que cada etapa de configuração importa e como evitar armadilhas típicas.

## O que você aprenderá

* Configurar o gerador de código de barras Planet com texto personalizado.
* Ajustar a X‑dimension para aumentar a nitidez da imagem.
* Salvar o código de barras como um arquivo PNG que pode ser impresso ou exibido na web.
* Estender o exemplo para outros tipos de código de barras ou formatos de saída.

**Pré-requisitos**

* Python 3.8 ou superior.
* O pacote `aspose-barcode` (ou qualquer biblioteca compatível que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).
* Familiaridade básica com scripts Python.

Você pode instalar o pacote necessário com:

```bash
pip install aspose-barcode
```

---

## Etapa 1: Criar código de barras com texto – inicializar o gerador

A primeira coisa que você deve fazer é criar uma instância de `BarcodeGenerator` que saiba qual simbologia usar e qual texto codificar. Para um código de barras Planet, o valor enum `EncodeTypes.Planet` indica à biblioteca que deve seguir a especificação USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Por que isso importa:**  
O objeto `BarcodeGenerator` encapsula todas as configurações do código de barras. Fornecer o texto no momento da construção garante que o valor codificado seja imutável ao longo do restante do processo, o que elimina incompatibilidades acidentais posteriormente.

---

## Etapa 2: Ajustar configurações – como gerar código de barras com resolução mais alta

Um código de barras de baixa resolução pode parecer borrado quando impresso em uma impressora de etiquetas. A X‑dimension (largura do módulo) controla o tamanho de cada barra individual. Definir para 4 pixels produz uma imagem nítida e de alta resolução, adequada para a maioria das impressoras modernas.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Explicação:**  
* `gen.parameters.barcode.x_dimension.pixels` mapeia diretamente para a largura física de um único módulo.  
* Um valor de **4** significa que cada barra tem quatro pixels de largura, o que corresponde aproximadamente a 0,127 mm a 300 dpi — bem dentro da faixa recomendada para códigos de barras USPS Planet.  

**Dica profissional:** Se você precisar de um DPI diferente, calcule a largura em pixels de acordo (por exemplo, 2 pixels para 150 dpi, 8 pixels para 600 dpi).

---

## Etapa 3: Salvar a imagem – gerar código de barras Planet como PNG

Agora que o gerador está configurado, você pode renderizar o código de barras para um arquivo de imagem. PNG é sem perdas, garantindo que o padrão exato dos módulos seja preservado.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Resultado:**  
Executar o script cria um arquivo chamado `PostalPlanetBarHeightNone.png` que contém um código de barras Planet codificando a string “123456”. As dimensões da imagem serão aproximadamente 200 × 100 pixels, dependendo da X‑dimension que você escolheu.

---

## Opcional: Verificar o código de barras visualmente

Você pode abrir rapidamente o PNG gerado com qualquer visualizador de imagens para confirmar que o código de barras está nítido e o texto legível está presente abaixo do padrão.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Se a imagem aparecer borrada, reveja a **Etapa 2** e aumente a X‑dimension até que as barras estejam claramente definidas.

---

## Variações comuns e casos de borda

| Situação | Ajuste |
|-----------|------------|
| **Comprimento de texto diferente** | Códigos de barras Planet suportam até 12 caracteres numéricos. Se você exceder isso, a biblioteca lançará uma exceção. |
| **Formato de saída alternativo** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` para outros casos de uso. |
| **Cores personalizadas de primeiro plano/fundo** | Use `gen.parameters.barcode.barcode_color = Color.Blue` e `gen.parameters.barcode.back_color = Color.White`. |
| **Sem texto legível por humanos** | Defina `gen.parameters.barcode.hide_code_text = True` para gerar um código de barras sem a legenda inferior. |
| **Geração em lote** | Itere sobre uma lista de strings, crie um novo `BarcodeGenerator` para cada uma e salve-as em arquivos com nomes exclusivos. |

Essas variações permitem que você **gere arquivos de código de barras planet** que atendam a uma ampla gama de requisitos de negócios.

---

## Script completo – pronto para executar

Abaixo está o script completo e autônomo que você pode copiar, colar e executar. Ele inclui todas as importações, tratamento de erros e comentários.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Explicação do script**

* A função `create_planet_barcode` encapsula as três etapas principais, tornando o código reutilizável.
* A validação de entrada garante que você esteja seguindo a especificação Planet (apenas numérico, máximo 12 dígitos).
* A função cria a pasta de saída automaticamente, portanto você não precisa gerenciar diretórios manualmente.
* Após a geração, o script abre a imagem usando Pillow (`PIL`) para verificação imediata.

---

## Conclusão

Agora você sabe como **criar código de barras com texto** e **gerar arquivos de código de barras planet** em Python. O guia abordou a inicialização, ajuste de resolução e saída de arquivo, juntamente com personalizações opcionais e casos de borda comuns.  

A partir daqui você pode:

* Substituir `EncodeTypes.Planet` por outras simbologias (por exemplo, `EncodeTypes.Code128`) para reutilizar o mesmo padrão.
* Integrar a função em um serviço web que retorne imagens de códigos de barras sob demanda.
* Experimentar o processamento em lote para produzir milhares de códigos de barras para correspondência em massa.

Sinta-se à vontade para adaptar o script às necessidades do seu projeto e compartilhar seus resultados nos comentários. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras em Python – guia completo passo a passo](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Criar PNG de código de barras em Python – guia passo a passo](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Como criar PNG de código de barras Planet com Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}