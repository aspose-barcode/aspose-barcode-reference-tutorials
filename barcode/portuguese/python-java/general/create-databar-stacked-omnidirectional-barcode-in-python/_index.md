---
category: general
date: 2026-07-30
description: Crie um código de barras Databar Stacked Omnidirectional em Python. Siga
  este guia passo a passo para configurar a proporção, XDimension e exportar PNG usando
  um gerador de códigos de barras em Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: pt
lastmod: 2026-07-30
og_description: Crie um código de barras Databar Stacked Omnidirectional em Python.
  Este tutorial mostra como definir XDimension, ajustar a proporção do DataBar e salvar
  como PNG com BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Crie Código de Barras Databar Empilhado Omnidirecional – Tutorial em Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Criar código de barras Databar empilhado omnidirecional em Python
url: /pt/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie Databar Stacked Omnidirectional Barcode em Python

Já precisou **criar databar stacked omnidirectional** barcode em Python mas não sabia por onde começar? Você não está sozinho—muitos desenvolvedores encontram essa dificuldade quando começam a usar a classe `BarcodeGenerator`. A boa notícia é que todo o processo é bastante simples depois que você entende as propriedades principais.

Neste guia vamos percorrer um exemplo completo e executável que usa um **python barcode generator** para definir o XDimension, ajustar a proporção do DataBar e, finalmente, exportar dois arquivos PNG. Ao final você terá uma compreensão sólida de como gerar símbolos stacked omnidirectional de alta qualidade para qualquer projeto de inventário ou logística.

## O que você aprenderá

- Como instanciar um gerador **databar stacked omnidirectional** com um payload GTIN‑14.  
- Por que o **tamanho em pixels do XDimension** importa para a confiabilidade da leitura.  
- O impacto da **proporção do DataBar** na largura versus altura das linhas.  
- Como salvar o resultado como um arquivo **BarCodeImageFormat PNG**.  
- Dicas para reutilizar o mesmo objeto gerador para produzir múltiplas variantes sem consumo extra de memória.

### Pré-requisitos

- Python 3.8+ (a biblioteca que usamos é pure‑Python, não requer wheels compilados).  
- O pacote `barcode-generator` (instale via `pip install barcode-generator`).  
- Uma pasta onde você tenha permissão de escrita – o script gravará duas imagens PNG lá.

Se você está confortável com importações básicas de Python e código orientado a objetos, está pronto para começar.

## Crie Databar Stacked Omnidirectional Barcode – Visão geral das etapas

Abaixo dividimos o fluxo de trabalho em seis etapas pequenas. Cada etapa é um trecho de código autocontido que você pode copiar‑colar em um REPL ou arquivo de script. Sinta‑se à vontade para experimentar—alterar a proporção ou o XDimension mudará instantaneamente o estilo visual.

---

## Etapa 1: Crie o Gerador Databar Stacked Omnidirectional

A primeira coisa que fazemos é **criar databar stacked omnidirectional** generator instance, passando o enum `EncodeTypes` apropriado e a string de dados.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Por que isso importa:** A flag `EncodeTypes.DatabarStackedOmniDirectional` indica à biblioteca que deve produzir um símbolo stacked omnidirectional, que é a única variante DataBar capaz de codificar até 14 dígitos e ainda ser legível de qualquer ângulo.

---

## Configure o tamanho em pixels do XDimension

O **tamanho em pixels do XDimension** controla o módulo menor (a barra preta mais fina). Um valor de `2` pixels funciona bem na maioria dos cenários de exibição em tela.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Dica profissional:** Se você planeja imprimir o código de barras em alta DPI, aumente esse valor para 3 ou 4 para evitar bordas borradas.

---

## Ajuste a proporção do DataBar (15)

A **proporção do DataBar** determina quão larga cada linha é em comparação com sua altura. Uma proporção de `15` gera linhas mais largas, que muitos scanners preferem para captura rápida em movimento.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Por que 15?** A especificação oficial da GS1 recomenda uma proporção entre 10 e 20 para símbolos stacked omnidirectional. Escolhemos `15` como um padrão equilibrado.

---

## Exporte o código de barras como PNG usando BarCodeImageFormat

Agora que o gerador está configurado, persistimos a imagem. O enum `BarCodeImageFormat.Png` garante saída sem perdas, perfeito para processamento posterior.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **O que você verá:** Abra o PNG resultante; você deverá notar um código de barras limpo, de alto contraste, com linhas relativamente largas.

---

## Altere a proporção do DataBar para 30

Às vezes você precisa de linhas mais altas em vez de mais largas—talvez para caber em um rótulo estreito. Trocar a **proporção do DataBar** para `30` deixa cada linha mais alta.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Caso extremo:** Proporções muito altas (ex.: >40) podem fazer o código de barras exceder alturas típicas de rótulos, então teste em uma impressora real antes de confirmar.

---

## Exporte o código de barras novamente com a nova proporção

Por fim, reutilizamos o mesmo objeto `barcode_generator` para gravar um segundo PNG. Não há necessidade de recriar o gerador—basta mudar a propriedade e chamar `Save` novamente.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Resultado:** Agora você tem dois arquivos PNG—um com linhas largas (`AR15`) e outro com linhas altas (`AR30`). Compare‑os lado a lado para decidir qual funciona melhor no seu setup de scanner.

---

## Exemplo completo em funcionamento

Juntando tudo, aqui está o script completo que você pode executar imediatamente. Substitua `YOUR_DIRECTORY` por um caminho absoluto na sua máquina.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Saída esperada** (no seu console):

```
✅ Two PNG files created – AR15 and AR30
```

E dois arquivos de imagem aparecem na pasta de destino, prontos para testes de leitura.

---

## Conclusão

Acabamos de **criar databar stacked omnidirectional** barcodes em Python, ajustar o **tamanho em pixels do XDimension**, experimentar duas configurações diferentes de **proporção do DataBar** e exportar os resultados como arquivos **BarCodeImageFormat PNG**. Todo o fluxo cabe em algumas linhas, mas oferece controle total sobre as características visuais que mais importam para os scanners.

O que vem a seguir? Tente trocar o payload por outro GTIN, brinque com cores convertendo o PNG para uma imagem baseada em paleta, ou gere um relatório PDF que incorpore ambos os PNGs lado a lado. A classe `BarcodeGenerator` é flexível o suficiente para lidar com todos esses cenários, então sinta‑se livre para experimentar.

Tem dúvidas sobre um caso de uso específico ou encontrou um erro? Deixe um comentário abaixo, e ficarei feliz em ajudar. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}