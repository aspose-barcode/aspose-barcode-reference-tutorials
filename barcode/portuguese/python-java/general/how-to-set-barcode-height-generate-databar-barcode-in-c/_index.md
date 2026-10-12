---
category: general
date: 2026-10-12
description: Como definir a altura do código de barras e gerar um código de barras
  DataBar em C# usando Aspose.BarCode. Siga um guia passo a passo com código completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: pt
lastmod: 2026-10-12
og_description: Como definir a altura do código de barras em C# e gerar um código
  de barras DataBar com Aspose.BarCode. Aprenda o código completo, por que cada etapa
  é importante e como alterar a altura do código de barras.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Como definir a altura do código de barras e gerar código de barras DataBar
  em C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como definir a altura do código de barras e gerar código DataBar em C#
url: /pt/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir a altura do código de barras e gerar um código DataBar em C#

Se você precisa **definir a altura do código de barras** programaticamente, este guia mostra os passos exatos. Você aprenderá a gerar um código DataBar Omni‑directional, ajustar sua altura e salvar ambas as versões como arquivos PNG.

Alterar a altura das barras de um código de barras é uma necessidade comum ao integrar códigos em recibos, etiquetas de produtos ou telas móveis. O exemplo abaixo usa a biblioteca Aspose.BarCode, que oferece suporte à gama completa de simbologias GS1 DataBar.

## O que você vai alcançar

Ao final deste tutorial você será capaz de:

* **definir a altura do código de barras** para um código DataBar Omni‑directional  
* **gerar código de barras c#** que cria duas imagens com alturas diferentes  
* entender **como criar símbolos databar** e por que a altura das barras importa  
* aplicar a lógica de **alterar a altura do código de barras** sem recriar o gerador  

Nenhuma ferramenta externa é necessária além do pacote NuGet Aspose.BarCode e de um runtime .NET 6+.

## Pré‑requisitos

* .NET 6 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer editor C#)  
* Aspose.BarCode for .NET – instale via `dotnet add package Aspose.BarCode`  

> **Dica profissional:** Use a licença de avaliação gratuita da Aspose caso não possua uma chave comercial; a API funciona da mesma forma.

## Etapa 1: Instalar o pacote Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém a classe `BarcodeGenerator` que usaremos para **gerar código de barras c#**.

## Etapa 2: Criar um gerador de código DataBar

A primeira ação concreta para **definir a altura do código de barras** é instanciar `BarcodeGenerator` com a simbologia desejada e a string de dados.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Por que isso importa:* `EncodeTypes.DatabarOmniDirectional` produz um DataBar compacto e omnidirecional que pode ser escaneado de qualquer ângulo — ideal para etiquetas pequenas.

## Etapa 3: Definir parâmetros comuns do código de barras (incluindo a altura inicial das barras)

Agora respondemos **como definir a altura do código de barras** X‑dimension e altura das barras antes de salvar a primeira imagem.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

A X‑dimension controla a largura geral de cada barra; uma configuração de 2 pixels gera uma imagem nítida e legível na maioria das telas. A etapa de **alterar a altura do código de barras** posterior reutilizará o mesmo gerador, economizando tempo e memória.

## Etapa 4: Salvar a primeira imagem do código de barras (altura de 30 pixels)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

O arquivo `DatabarHeight30.png` agora contém um código DataBar com altura de barra de 30 pixels.

## Etapa 5: Alterar apenas a altura da barra para 60 pixels

Para demonstrar **alterar a altura do código de barras**, modificamos apenas a propriedade `BarHeight`. Todas as demais configurações permanecem inalteradas, sendo a forma mais eficiente de produzir múltiplos tamanhos a partir de um único gerador.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Etapa 6: Salvar a segunda imagem do código de barras (altura de 60 pixels)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG, cada um com uma altura de barra diferente, mas com dados e X‑dimension idênticos.

## Exemplo completo, pronto para execução

Abaixo está o programa completo que você pode copiar‑colar em uma nova aplicação console (`dotnet new console`) e executar imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Saída esperada

Ao executar o programa, são gerados dois arquivos no diretório de trabalho do executável:

* `DatabarHeight30.png` – um código DataBar com barras de 30 pixels de altura.  
* `DatabarHeight60.png` – o mesmo código, porém cada barra tem o dobro da altura.

Ambas as imagens podem ser abertas em qualquer visualizador de imagens ou incorporadas diretamente em PDFs, páginas HTML ou etiquetas impressas.

## Por que ajustar a altura das barras é importante

* **Confiabilidade de leitura:** Alguns leitores têm dificuldade com barras muito curtas em mídia de baixa resolução; aumentar a altura melhora a detecção.  
* **Restrições de design:** Um aplicativo móvel pode precisar de um código compacto (30 px) enquanto um recibo impresso pode exigir um maior (60 px).  
* **Conformidade regulatória:** Certas indústrias exigem uma altura mínima de barra para símbolos GS1 DataBar.

Ao reutilizar a mesma instância de `BarcodeGenerator`, você evita a sobrecarga de reprocessar a string de dados, o que é especialmente benéfico em ambientes de alto volume.

## Variações comuns e casos de borda

| Situação | Ajuste recomendado |
|----------|--------------------|
| Necessidade de uma X‑dimension diferente | Alterar `XDimension.Pixels` antes do primeiro `Save`. |
| Desejar outra simbologia (ex.: DataBar Stacked) | Usar `EncodeTypes.DatabarStacked` ao criar o `BarcodeGenerator`. |
| Precisa incorporar o código de barras em um PDF | Utilizar `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` e adicionar o stream a uma biblioteca PDF. |
| Executando no .NET Framework 4.6 | O mesmo código funciona; basta referenciar o assembly Aspose.BarCode adequado. |

## Dicas profissionais para geração confiável de códigos de barras

* **Cache o gerador** quando gerar muitos códigos com os mesmos dados, mas tamanhos diferentes.  
* **

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}