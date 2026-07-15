---
category: general
date: 2026-07-15
description: Gere código de barras PDF417 rapidamente com C#. Aprenda a gerar o código
  de barras a partir de texto, ajustar o tamanho do código de barras e definir dimensões
  personalizadas do código de barras em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: pt
lastmod: 2026-07-15
og_description: Gere código de barras PDF417 em C# instantaneamente. Este guia mostra
  como gerar o código de barras a partir de texto, ajustar o tamanho do código de
  barras e aplicar dimensões personalizadas ao código de barras.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Gerar Código de Barras PDF417 em C# – Tutorial Completo de Programação
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Gerar código de barras PDF417 em C# – Guia completo passo a passo
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras PDF417 em C# – Guia Completo Passo a Passo

Já precisou **gerar código de barras PDF417** mas não tinha certeza de quais configurações ajustar? Você não está sozinho—muitos desenvolvedores encontram o mesmo obstáculo quando começam a trabalhar com códigos de barras 2‑D. A boa notícia? Com algumas linhas de C# você pode transformar qualquer string em uma imagem PDF417 escaneável, controlar seu tamanho exato e até definir um layout personalizado de colunas‑linhas.

Neste tutorial, vamos percorrer como **gerar código de barras a partir de texto**, ajustar o tamanho do código de barras e definir dimensões personalizadas — tudo usando a popular biblioteca Aspose.BarCode. Ao final, você terá um exemplo pronto‑para‑executar que pode ser inserido em qualquer projeto .NET.

![Exemplo de geração de código de barras PDF417](https://example.com/og-image.png "Exemplo de geração de código de barras PDF417")

## O que você vai construir

- Um código de barras PDF417 que codifica a string `Åspóse.Barcóde©`.
- Controle preciso sobre a X‑dimension (largura em pixels de cada módulo).
- Um layout personalizado de 4 colunas e 9 linhas.
- Um arquivo PNG salvo no disco.

Sem serviços externos, sem truques de varinha mágica—apenas código C# puro que você pode compilar agora mesmo.

## Pré-requisitos

- .NET 6.0 ou posterior (o código funciona também no .NET Framework 4.8).
- Visual Studio 2022 ou qualquer IDE que suporte C#.
- Aspose.BarCode para .NET (versão de avaliação gratuita ou licenciada). Instale via NuGet:

```bash
dotnet add package Aspose.BarCode
```

É isso—uma vez que o pacote esteja referenciado, você está pronto para prosseguir.

## Etapa 1 – Gerar Código de Barras PDF417 com Dados de Texto

A primeira coisa que precisamos é uma instância de `BarcodeGenerator` que saiba que estamos lidando com a simbologia PDF417 e o texto exato que queremos codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Por que isso importa:**  
> `EncodeTypes.Pdf417` indica à biblioteca que use o formato PDF417 2‑D, enquanto o segundo argumento é a carga útil de **gerar código de barras a partir de texto**. Tudo o que você passar aqui se torna os dados armazenados na matriz do código de barras.

## Etapa 2 – Ajustar o Tamanho do Código de Barras (X‑Dimension)

Se você já imprimiu um código de barras que parecia muito pequeno em um recibo, conhece a frustração de o scanner não reconhecê‑lo. A propriedade `XDimension` controla a largura de um único módulo (o menor quadrado preto ou branco) em pixels.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Dica profissional:**  
> Um valor de 2 px funciona bem na maioria dos cenários de exibição em tela. Para impressões de alta resolução, você pode aumentá‑lo para 3 ou 4 px. Apenas lembre‑se de que dimensões X maiores aumentam o tamanho geral da imagem.

## Etapa 3 – Definir Dimensões Personalizadas do Código de Barras (Colunas e Linhas)

O PDF417 permite que você defina quantas colunas e linhas o código de barras deve ocupar. É aqui que as **dimensões personalizadas do código de barras** entram em ação. Alterar esses valores pode ajudá‑lo a encaixar o código de barras em um espaço de UI apertado ou atender a um tamanho de etiqueta específico.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **O que está acontecendo nos bastidores?**  
> A biblioteca redistribui os dados codificados pela grade especificada. Menos colunas resultam em códigos de barras mais altos; mais linhas os tornam mais curtos. Brinque com os números até que o equilíbrio visual pareça adequado para sua aplicação.

## Etapa 4 – Salvar a Imagem do Código de Barras

Agora que configuramos tudo, simplesmente pedimos ao gerador que escreva um arquivo PNG. PNG é sem perdas, portanto a nitidez dos módulos permanece intacta.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Ao executar o programa, você deverá ver um arquivo em `C:\Barcodes\CustomLayout.png` que se parece com a captura de tela acima. Escaneá‑lo com qualquer leitor compatível com PDF417 retornará a string original `Åspóse.Barcóde©`.

## Exemplo Completo Funcional

Abaixo está o programa completo que você pode copiar‑colar em um aplicativo de console. Ele inclui todas as diretivas using e o tratamento de erros que você esperaria em código de produção.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Saída Esperada

Executar o código imprime:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…e cria um PNG que pode ser aberto em qualquer visualizador de imagens. Se você escaneá‑lo com um aplicativo móvel (por exemplo, “Barcode Scanner” no iOS/Android), o texto decodificado deverá ser exatamente **Åspóse.Barcóde©**.

## Perguntas Frequentes & Casos Limite

| Pergunta | Resposta |
|----------|----------|
| **Posso usar um formato de imagem diferente?** | Sim—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` ou `Svg` são todos suportados. Basta mudar o segundo argumento de `Save`. |
| **E se meu texto contiver caracteres Unicode?** | Aspose.BarCode suporta totalmente UTF‑8, então o exemplo com `Å` e `©` funciona pronto para uso. |
| **Como altero o nível de correção de erro?** | Use `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (níveis 0‑8). Níveis mais altos aumentam a redundância, mas também o tamanho. |
| **Preciso de fundo transparente—posso fazer isso?** | Defina `generator.Parameters.Barcode.Image.TransparentBackground = true;` antes de salvar. |
| **Existe uma maneira de incorporar o código de barras diretamente em um PDF?** | Claro. Substitua a chamada `Save` por `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` e você obterá um PDF de uma página contendo o código de barras. |

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# a partir de qualquer string, **ajustar o tamanho do código de barras** e aplicar **dimensões personalizadas do código de barras** para atender às necessidades do seu layout. O fluxo de quatro etapas—inicializar, dimensionar, layout, salvar—cobre o fluxo de trabalho principal para a maioria dos cenários de códigos de barras 2‑D.

Qual o próximo passo? Experimente trocar `EncodeTypes.Pdf417` por `EncodeTypes.QR` ou `EncodeTypes.Code128` para ver como a API se adapta. Experimente diferentes valores de `XDimension`, brinque com a matriz de colunas/linhas ou incorpore a imagem em um relatório PDF. As possibilidades são praticamente infinitas, e agora você tem uma base sólida para construir.

Tem mais perguntas ou descobriu um truque inteligente ao brincar com PDF417? Deixe um comentário abaixo—vamos manter a conversa rolando. Feliz codificação!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como Gerar Código de Barras - Tipos de Código de Barras Unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)
- [Gerar Código de Barras DataMatrix – Guia Profissional com Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}