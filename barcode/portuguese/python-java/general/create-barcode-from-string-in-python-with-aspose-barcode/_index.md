---
category: general
date: 2026-10-15
description: Crie código de barras a partir de uma string em Python usando Aspose.BarCode,
  aprenda como gerar código de barras Code 128 e salvar o PNG do código de barras
  em apenas algumas linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: pt
lastmod: 2026-10-15
og_description: Criar código de barras a partir de uma string em Python para codificar
  dados em um código de barras Code 128 e salvá‑lo como um arquivo PNG com Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Criar código de barras a partir de string em Python – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Criar código de barras a partir de uma string em Python com Aspose.BarCode
url: /pt/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras a partir de string em Python com Aspose.BarCode

Se você precisa **criar código de barras a partir de string** em Python, este guia mostra os passos exatos com Aspose.BarCode. Você aprenderá como **gerar código de barras Code 128**, ajustar sua aparência e **salvar o PNG do código de barras** no disco. A solução funciona em qualquer plataforma que suporte Python 3.9+ e requer apenas algumas linhas de código.

Gerar códigos de barras programaticamente elimina erros de digitação manual e simplifica fluxos de trabalho como rastreamento de inventário, emissão de bilhetes e impressão de etiquetas. Ao final deste tutorial você será capaz de **codificar dados em código de barras**, personalizar dimensões e armazenar a imagem onde precisar.

## Pré-requisitos

- Python 3.9 ou mais recente instalado  
- Acesso à internet para baixar o pacote Aspose.BarCode  
- Permissão de escrita no diretório onde você salvará o arquivo PNG  

Se você estiver usando um ambiente virtual (altamente recomendado), ative‑o agora.

## Instalar o pacote Aspose.BarCode para Python

A Aspose fornece uma biblioteca pure‑Python que lida com todas as simbologias de código de barras comuns, incluindo Code 128. Instale‑a com pip:

```bash
pip install aspose-barcode
```

*Dica profissional:* Fixe a versão (por exemplo, `aspose-barcode==23.9`) para evitar alterações inesperadas que quebrem a produção.

## Criar código de barras a partir de string em Python

O primeiro passo funcional é importar as classes necessárias e instanciar um gerador para a simbologia desejada. Este exemplo usa **Code 128**, que é ideal para dados alfanuméricos.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Por que isso importa:** `EncodeTypes.CODE_128` informa à biblioteca qual padrão de código de barras aplicar, enquanto o segundo argumento (`"1234567890"`) é a **string que você deseja codificar no código de barras**. Você pode substituí‑la por qualquer string ASCII de até 80 caracteres para Code 128.

## Gerar código de barras Code 128

Uma vez que o gerador está pronto, você pode produzir a imagem do código de barras na memória. A biblioteca renderiza automaticamente o código de barras com base nos dados fornecidos.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

Neste ponto `barcode_image` é uma instância de `System.Drawing.Image` (no Windows) ou um objeto de imagem compatível em outras plataformas. Você pode exibi‑la diretamente em uma GUI, incorporá‑la em um PDF ou continuar a personalizá‑la.

## Ajustar a aparência do código de barras

Ajustar finamente as propriedades visuais garante que o código de barras seja lido de forma confiável no seu ambiente específico. Ajustes comuns incluem a X‑dimension (largura da barra mais estreita) e a altura total da barra.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Por que ajustar esses valores?*  
- **Dimensão X** influencia a densidade do código de barras; um valor menor gera um código mais compacto que cabe em etiquetas pequenas.  
- **Altura da barra** afeta a legibilidade; barras mais altas são mais fáceis de serem detectadas pelos scanners à distância.

Você também pode mudar cores, adicionar margens ou incorporar texto legível por humanos via o objeto `parameters`. Consulte a documentação do Aspose.BarCode para a lista completa de opções.

## Como salvar o código de barras como PNG

Salvar a imagem gerada é o passo final no fluxo de **criar código de barras a partir de string**. A biblioteca suporta vários formatos; PNG é sem perdas e amplamente suportado.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

O método `save` grava a imagem no sistema de arquivos usando o formato que você especificar. Se o diretório de destino (`output/` neste exemplo) não existir, o Python lançará um `FileNotFoundError`. Crie o diretório previamente ou trate a exceção:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Resultado esperado:** Após executar o script, `output/barcode.png` contém um código de barras Code 128 nítido que codifica `"1234567890"`. Abrir o arquivo em qualquer visualizador de imagens mostrará um código de barras preto‑sobre‑branco pronto para leitura.

## Exemplo completo e executável

Juntando todas as peças, aqui está um script autocontido que você pode copiar, colar e executar:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Execute o script com `python create_barcode.py`. Se tudo estiver instalado corretamente, você verá:

```
Barcode saved to output/barcode.png
```

Abra o arquivo PNG e verifique que o código de barras corresponde à string original usando qualquer aplicativo de leitura de códigos de barras.

## Perguntas comuns e casos extremos

- **E se eu precisar de uma simbologia diferente?**  
  Substitua `EncodeTypes.CODE_128` por outro valor enum, como `EncodeTypes.QR`, `EncodeTypes.EAN_13` ou `EncodeTypes.PDF_417`. O restante do código permanece o mesmo.

- **Posso gerar um código de barras a partir de caracteres não‑ASCII?**  
  Code 128 suporta o conjunto completo de 128 caracteres ASCII. Para dados Unicode, considere usar QR Code (`EncodeTypes.QR`), que lida nativamente com UTF‑8.

- **Como mudar o formato da imagem?**  
  Passe um membro diferente de `BarCodeImageFormat` para `save`, por exemplo, `BarCodeImageFormat.JPEG` ou `BarCodeImageFormat.BMP`.

- **E se o diretório de saída for somente leitura?**  
  Envolva a chamada `save` em um bloco try/except e trate `PermissionError` de forma elegante, talvez solicitando ao usuário um caminho alternativo.

- **Dica de desempenho:**  
  Gerar milhares de códigos de barras em um loop pode ser intensivo para a CPU. Reutilize uma única instância de `BarcodeGenerator` e atualize apenas `generator.parameters.barcode.code_text` entre as iterações.

## Conclusão

Agora você sabe como **criar código de barras a partir de string** em Python usando Aspose.BarCode, **gerar código de barras Code 128**, personalizar seu tamanho e **salvar o PNG do código de barras** no disco. Esta solução de ponta a ponta permite que você **codifique dados em código de barras** de forma rápida e confiável, facilitando a integração de códigos de barras em sistemas de inventário, plataformas de bilhetagem ou qualquer aplicação que exija identificadores legíveis por máquina.

**Próximos passos**

- Explore outras simbologias (alternativas ao `generate code 128 barcode`) como QR ou DataMatrix.  
- Adicione lógica de tratamento de erros para tornar o script robusto para uso em produção (falhas ao `how to save barcode`).  
- Incorpore o PNG gerado em PDFs ou relatórios HTML (`generate barcode png` para web).  

Feliz codificação, e aproveite a simplicidade da geração programática de códigos de barras!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Code 128 e salvar a imagem do código de barras com Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Como gerar imagem de QR Code em Python com Aspose.Barcode – Guia completo](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Criar PNG de código de barras em Python – Guia completo do Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}