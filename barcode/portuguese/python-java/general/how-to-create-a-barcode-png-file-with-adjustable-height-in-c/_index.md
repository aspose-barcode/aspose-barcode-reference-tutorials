---
category: general
date: 2026-08-19
description: Aprenda como gerar um arquivo PNG de código de barras em C# e ajustar
  sua altura, abordando como gerar imagens de código de barras e mudar a altura do
  código de barras facilmente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: pt
lastmod: 2026-08-19
og_description: Crie um arquivo PNG de código de barras em C# e aprenda a gerar imagens
  de código de barras, ajustar a altura do código de barras e alterar a altura para
  leituras ótimas.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Crie um arquivo PNG de código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Como criar um arquivo PNG de código de barras com altura ajustável em C#
url: /pt/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um arquivo PNG de código de barras com altura ajustável em C#

Se você precisa criar um **arquivo PNG de código de barras** em C#, este guia mostra exatamente como fazer. Você verá um exemplo completo e executável que demonstra **como gerar imagens de código de barras** e como **ajustar a altura do código de barras** para diferentes casos de uso.

Gerar um arquivo PNG de código de barras é uma necessidade comum para sistemas de inventário, terminais de ponto de venda e qualquer aplicação que precise imprimir ou exibir dados legíveis por máquina. Ao final deste tutorial você será capaz de mudar a altura do código de barras, salvar múltiplos arquivos PNG e entender o impacto da altura na confiabilidade da leitura.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* O pacote NuGet **Aspose.BarCode for .NET** (o exemplo de código usa esta biblioteca)  

Você pode adicionar o pacote pela linha de comando:

```bash
dotnet add package Aspose.BarCode
```

> **Dica profissional:** A versão de avaliação gratuita do Aspose.BarCode funciona para desenvolvimento e testes. Para produção, obtenha uma chave licenciada.

## Instalar a biblioteca de código de barras

O primeiro passo é referenciar a biblioteca no seu projeto. Adicione as diretivas `using` a seguir no topo do seu arquivo C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Esses namespaces dão acesso a `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`.

## Criar o arquivo PNG de código de barras

Agora criamos uma instância de `BarcodeGenerator` que irá gerar um **arquivo PNG de código de barras**. O exemplo usa a simbologia Databar OmniDirectional, mas você pode substituir `EncodeTypes.DatabarOmniDirectional` por qualquer tipo suportado.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

A string `"(01)12345678901231"` segue o formato do Identificador de Aplicação GS1 para um GTIN de 14 dígitos. Ajuste os dados para corresponder aos identificadores do seu produto.

## Definir a dimensão X (opcional)

A dimensão X define a largura de um único módulo do código de barras. Um valor baseado em pixels oferece controle preciso sobre o tamanho da imagem.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Um valor de `2` pixels funciona bem para a maioria das telas. Aumente se precisar de um código de barras maior ao imprimir.

## Ajustar a altura do código de barras e salvar o arquivo PNG

A propriedade **BarHeight** controla o tamanho vertical das barras. Alterar esse valor permite **ajustar a altura do código de barras** sem afetar os dados codificados.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

O arquivo `DatabarBarHeight30Pixels.png` agora é um **arquivo PNG de código de barras** com 30 pixels de altura.  

Para **alterar a altura do código de barras** e criar uma segunda imagem, basta atribuir um novo valor e chamar `Save` novamente:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG — um com 30 px e outro com 60 px — demonstrando como **ajustar a altura do código de barras** dinamicamente.

### Por que a altura da barra importa

* **Legibilidade:** Scanners esperam uma altura mínima para detecção confiável. Um código de barras muito curto pode ser ignorado, especialmente em câmeras de baixa resolução.  
* **Estética:** Ajustar a altura do código de barras aos elementos de design ao redor cria uma UI mais limpa.  
* **Restrições de impressão:** Algumas impressoras de etiquetas têm slots de altura fixa; ajustar a altura garante que o código de barras caiba.

**Melhor prática:** Mantenha a altura como múltiplo da dimensão X (por exemplo, 30 px quando a dimensão X é 2 px) para preservar a proporção e evitar distorções.

## Exemplo completo

Abaixo está o programa completo e autocontido que você pode colar em uma aplicação console e executar imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Saída esperada**

Executar o programa cria dois arquivos no diretório de trabalho do executável:

* `DatabarBarHeight30Pixels.png` – um arquivo PNG de código de barras com 30 pixels de altura  
* `DatabarBarHeight60Pixels.png` – um arquivo PNG de código de barras com 60 pixels de altura  

Abra qualquer um dos PNGs com um visualizador de imagens; você verá um código de barras Databar OmniDirectional nítido, pronto para leitura.

## Casos de borda e solução de problemas

| Situação | O que verificar | Correção recomendada |
|-----------|----------------|----------------------|
| O código de barras aparece borrado | Dimensão X muito baixa para a altura escolhida | Aumente `XDimension.Pixels` (ex.: de 2 para 3) |
| O scanner falha em código de barras de baixa altura | Altura abaixo do mínimo do scanner | Defina `BarHeight.Pixels` para pelo menos 30 px (ou conforme especificações do scanner) |
| O arquivo PNG está vazio ou corrompido | Caminho de saída inválido ou permissão de gravação negada | Use um caminho absoluto ou garanta que o app tenha acesso de escrita |
| Precisa de outra simbologia | `EncodeTypes` atual não é adequado | Substitua `EncodeTypes.DatabarOmniDirectional` por outro valor do enum (ex.: `EncodeTypes.Code128`) |

## Perguntas frequentes

**P: Posso gerar outros formatos de imagem (JPEG, BMP)?**  
R: Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, etc.

**P: Como incorporo o PNG em uma página web?**  
R: Sirva o PNG gerado via um endpoint HTTP ou converta‑o para uma string Base64 e coloque‑a no atributo `src` de uma tag `<img>`.

**P: Existe uma forma de definir a cor de fundo?**  
R: Use `generator.Parameters.Image.BackgroundColor = Color.White;` (ou qualquer `System.Drawing.Color`).

## Conclusão

Agora você sabe como **gerar um arquivo PNG de código de barras** em C# e ajustar precisamente a **altura do código de barras** para atender a requisitos de leitura ou design. Alterando a propriedade `BarHeight.Pixels` você pode **mudar a altura do código de barras** dinamicamente e produzir múltiplos ativos PNG a partir de um único código‑base.

Em seguida, explore outras opções de personalização, como cor de primeiro plano, margens e adição de texto legível por humanos. Você também pode experimentar diferentes simbologias (`EncodeTypes.Code128`, `EncodeTypes.QR`) para ampliar o leque de dados que pode codificar.

Bom código, e que seus códigos de barras sempre sejam lidos na primeira tentativa!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar e ajustar a altura do código de barras para Databar unidimensional usando Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Como gerar código de barras – Tipos de código de barras unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}