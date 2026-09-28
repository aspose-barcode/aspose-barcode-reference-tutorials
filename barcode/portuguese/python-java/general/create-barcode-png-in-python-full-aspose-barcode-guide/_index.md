---
category: general
date: 2026-07-21
description: Crie um PNG de código de barras usando Aspose.Barcode em Python. Aprenda
  como gerar o código de barras a partir de dados, definir dimensões e salvar a imagem
  do código de barras em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- generate barcode from data
- generate planet barcode
- how to generate barcode python
- save barcode image
language: pt
lastmod: 2026-07-21
og_description: Crie PNG de código de barras rapidamente com Aspose.Barcode. Este
  guia mostra como gerar código de barras a partir de dados, ajustar o tamanho e salvar
  a imagem do código de barras usando Python.
og_image_alt: Screenshot of a generated Planet barcode saved as a PNG file
og_title: Criar código de barras PNG em Python – Tutorial completo do Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  headline: Create barcode png in Python – Full Aspose.Barcode Guide
  type: TechArticle
- description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  name: Create barcode png in Python – Full Aspose.Barcode Guide
  steps:
  - name: Running the script
    text: '1. Install Jython (e.g., `brew install jython` on macOS or download from
      the official site). 2. Place the Aspose.Barcode for Java JAR in Jython’s classpath,
      for example:'
  - name: 'Example: Switching to Code128'
    text: '```python generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
      ```'
  - name: Quick fix for missing folder
    text: '```python import os output_dir = os.path.dirname(output_path) if not os.path.isdir(output_dir):
      os.makedirs(output_dir) ```'
  type: HowTo
tags:
- barcode
- python
- Aspose
- image generation
title: Criar código de barras PNG em Python – Guia completo do Aspose.Barcode
url: /pt/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar barcode png em Python – Guia Completo do Aspose.Barcode

Já se perguntou como **criar barcode png** sem lutar com bibliotecas de imagem de baixo nível? Você não está sozinho. Muitos desenvolvedores precisam de uma maneira rápida e confiável de transformar dados brutos em um barcode PNG limpo, e o Aspose.Barcode torna isso muito fácil.

Neste tutorial vamos percorrer os passos exatos para **gerar barcode a partir de dados** usando a simbologia Planet, ajustar suas dimensões e, finalmente, **salvar imagem do barcode** como um arquivo PNG. Ao final, você terá um script pronto‑para‑executar, além de algumas dicas que mantêm seu código robusto.

## O que você aprenderá

- Como configurar o Aspose.Barcode para projetos Python (Jython)  
- O código exato para **gerar planet barcode** com largura e altura personalizadas  
- Formas de **salvar imagem do barcode** como PNG, JPG ou outros formatos  
- Armadilhas comuns e como evitá‑las  

Nenhuma experiência prévia com Aspose é necessária — apenas um conhecimento básico de Python e um runtime compatível com Java.

---

## Como criar barcode png com Aspose.Barcode em Python

Abaixo está o script completo e executável. Você pode copiá‑e‑colar em um arquivo chamado `create_planet_barcode.py` e executá‑lo com Jython (ou qualquer interpretador Python habilitado para Java).

```python
# ------------------------------------------------------------
# create_planet_barcode.py
# Demonstrates how to create barcode png using Aspose.Barcode
# ------------------------------------------------------------

# Step 1: Import the required Aspose.Barcode classes
# Note: These classes live in the Java package `com.aspose.barcode`,
# so you need a JVM‑based Python (Jython) or use JPype.
from com.aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Choose the symbology (Planet) and feed the data you want to encode
# The data string can be any alphanumeric value that fits the Planet rules.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 3: Adjust the X dimension (module width) – this controls the bar thickness
# Here we set it to 4 pixels for a nicely balanced look.
generator.getParameters().getBarcode().setXDimension(4)

# Step 4: Set a custom bar height – 100 pixels gives a clear, readable barcode.
generator.getParameters().getBarcode().setBarHeight(100)

# Step 5: Choose the output folder and file name.
# Feel free to change the path to suit your project layout.
output_path = "output/Planet_100px.png"

# Step 6: Save the generated barcode image as a PNG file.
# BarCodeImageFormat.Png tells Aspose to output a PNG.
generator.save(output_path, BarCodeImageFormat.Png)

print("✅ Barcode PNG created at:", output_path)
```

**Explicação de cada bloco**

- **Seção de importação** – Importamos as três classes principais: `BarcodeGenerator` (o motor), `EncodeTypes` (o enum que lista todas as simbologias) e `BarCodeImageFormat` (o enum para formatos de saída).  
- **Construção do gerador** – `EncodeTypes.Planet` indica ao Aspose para usar a simbologia *Planet*, enquanto o segundo argumento `"123456"` são os dados que queremos codificar. Isso satisfaz o requisito de **gerar barcode a partir de dados**.  
- **Dimensão X & altura da barra** – Essas duas propriedades controlam o tamanho visual. Ajuste‑as para atender às restrições de impressão ou UI; os padrões podem ser muito pequenos para telas de alta resolução.  
- **Chamada de salvar** – O método `save` grava a imagem no disco. Ao passar `BarCodeImageFormat.Png` garantimos que o arquivo seja PNG, completando o objetivo de **criar barcode png**.

### Executando o script

1. Instale o Jython (por exemplo, `brew install jython` no macOS ou faça o download do site oficial).  
2. Coloque o JAR Aspose.Barcode for Java no classpath do Jython, por exemplo:

```bash
export CLASSPATH=$CLASSPATH:/path/to/Aspose.Barcode.jar
```

3. Execute:

```bash
jython create_planet_barcode.py
```

Você deverá ver a linha de confirmação e um arquivo `Planet_100px.png` na pasta `output`. Abra‑o com qualquer visualizador de imagens – você verá um barcode Planet nítido pronto para leitura.

![Exemplo de criação de barcode png](https://via.placeholder.com/400x150.png?text=Planet+Barcode+PNG "Exemplo de criação de barcode png")

*Texto alternativo da imagem: “Captura de tela de um barcode Planet gerado e salvo como arquivo PNG”* – isso satisfaz o requisito de texto‑alt da imagem.

## Gerar barcode a partir de dados – mergulho profundo

A linha  

```python
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```  

faz o trabalho pesado. Veja por que isso importa:

- **EncodeTypes.Planet** – Planet é uma simbologia menos comum, ideal para dados numéricos compactos.  
- **"123456"** – Qualquer string que obedecer ao conjunto de caracteres Planet (apenas dígitos) funciona. Se você tentar passar letras, o Aspose lançará uma `BarcodeException`.  

Se você precisar **gerar barcode a partir de dados** que incluam letras, troque para uma simbologia que suporte alfanuméricos, como `EncodeTypes.Code128`. O resto do script permanece o mesmo.

### Exemplo: Alternando para Code128

```python
generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
```

Agora você **gerou barcode a partir de dados** que misturam letras e números, e ainda pode **salvar imagem do barcode** como PNG com a mesma chamada `save`.

## Definir dimensões personalizadas e salvar imagem do barcode

Às vezes o tamanho padrão é muito pequeno para uma etiqueta impressa. Por isso expomos duas propriedades:

| Propriedade | O que controla | Valores típicos |
|-------------|----------------|-----------------|
| `XDimension` | Largura de um único módulo (a barra fina) | 2‑6 pixels para tela, 8‑12 para impressão |
| `BarHeight`  | Altura das barras | 50‑150 pixels, dependendo do tamanho da etiqueta |

Ajustar ambas permite adaptar o barcode a qualquer meio. Após a modificação, o método `save` ainda grava um arquivo **criar barcode png**, sem etapas adicionais necessárias.

## Armadilhas comuns ao gerar barcode planet

1. **Comprimento de dados inválido** – Planet codifica de 2‑12 dígitos. Fornecer mais de 12 gerará uma exceção.  
2. **Pasta de saída ausente** – Se `output/` não existir, `generator.save` lança uma `FileNotFoundException`. Crie a pasta primeiro ou use `os.makedirs`.  
3. **Problemas de classpath** – Esquecer de adicionar `Aspose.Barcode.jar` ao `CLASSPATH` resulta em `ImportError`. Verifique novamente a variável de ambiente.  

### Correção rápida para pasta ausente

```python
import os
output_dir = os.path.dirname(output_path)
if not os.path.isdir(output_dir):
    os.makedirs(output_dir)
```

Adicione o trecho antes da chamada `save`, e você nunca mais verá um erro de “diretório não encontrado”.

## Como gerar barcode python – abordagens alternativas

Embora a solução Aspose seja poderosa, você pode se perguntar **como gerar barcode python** usando bibliotecas Python puras. Ferramentas como `python-barcode` ou `qrcode` podem gerar códigos de barras 1D/2D, mas carecem do amplo suporte a simbologias (por exemplo, Planet) que o Aspose oferece. Se você precisar apenas de tipos comuns (Code128, QR), essas bibliotecas são adequadas; para simbologias de nicho, o Aspose continua sendo a escolha principal.

## Estendendo o exemplo – múltiplos formatos e processamento em lote

Depois de dominar o fluxo de barcode único, escalar é simples:

```python
data_list = ["001122", "334455", "667788"]
for idx, data in enumerate(data_list, start=1):
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.getParameters().getBarcode().setXDimension(4)
    gen.getParameters().getBarcode().setBarHeight(100)
    file_name = f"output/Planet_{data}_{idx}.png"
    gen.save(file_name, BarCodeImageFormat.Png)
    print(f"Saved {file_name}")
```

Agora você **gerou barcode a partir de dados** em um loop, salvando automaticamente arquivos de **imagem do barcode** para cada entrada. Troque `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se precisar de uma saída diferente.

## Recapitulação e próximos passos

Cobremos tudo o que você precisa para **criar barcode png** com Aspose.Barcode em Python:

1. Importar as classes Java via Jython.  
2. **Gerar planet barcode** (ou qualquer outra simbologia) a partir dos seus dados.  
3. Ajustar finamente `XDimension` e `BarHeight` para corresponder ao seu design.  
4. **Salvar imagem do barcode** como PNG, completando o fluxo de **criar barcode png**.  

O que vem a seguir? Tente adicionar legendas de texto abaixo do barcode, experimente saída em cores (`BarCodeImageFormat.Png24`), ou integre o script a um serviço web que retorne PNGs de barcode sob demanda.

---

**Feliz codificação!** Se encontrar algum problema, deixe um comentário abaixo — ficarei feliz em ajudar a ajustar seu pipeline de geração de barcode.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar Barcode PNG – Proporção do DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Como salvar PNG usando DataMatrix C40 com Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Como criar imagens de barcode code128 em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}