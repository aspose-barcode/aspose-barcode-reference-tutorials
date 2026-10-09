---
category: general
date: 2026-09-19
description: Como gerar código de barras em C# com um guia passo a passo. Aprenda
  a personalizar as configurações do código de barras PDF417 e criar uma imagem de
  código de barras que desenvolvedores C# podem usar instantaneamente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: pt
lastmod: 2026-09-19
og_description: Como gerar código de barras em C# com instruções detalhadas. Personalize
  os parâmetros do código de barras PDF417 e crie uma imagem de código de barras que
  projetos C# podem usar hoje.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Como gerar código de barras e personalizar o código de barras PDF417 em
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Como gerar código de barras e personalizar o código de barras PDF417 em C#
url: /pt/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras e personalizar o código de barras PDF417 em C#

Se você precisa **gerar código de barras** em uma aplicação .NET, este tutorial mostra uma solução completa e pronta‑para‑executar. Você aprenderá a personalizar as dimensões do código de barras PDF417, escolher o número de colunas e, finalmente, **criar imagem de código de barras C#** que os projetos podem incorporar diretamente.

Gerar um código de barras não requer um pipeline de compilação complexo. Ao final deste guia você terá um arquivo PNG contendo um código de barras MicroPDF417 que corresponde exatamente ao tamanho e à resolução que você precisa.

## Pré‑requisitos

Você deve ter o seguinte instalado antes de começar:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.6+)
* Visual Studio 2022 (ou qualquer editor C# de sua preferência)
* Pacote NuGet Aspose.BarCode for .NET – instale com  
  `dotnet add package Aspose.BarCode`

Nenhuma ferramenta externa adicional é necessária.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e adicione a referência ao Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Abra `Program.cs` e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Esses namespaces expõem as classes que permitem **gerar código de barras** e controlar opções específicas do PDF417.

## Etapa 2: Inicializar o gerador MicroPDF417 com o texto desejado

A primeira linha cria uma instância de `BarcodeGenerator` configurada para a simbologia MicroPDF417. O construtor recebe o tipo de codificação e a string de dados que você deseja codificar.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Por que isso importa:** MicroPDF417 é uma variante compacta do padrão PDF417 completo, ideal para etiquetas pequenas ou telas móveis. Inicializar o gerador com o `EncodeTypes` correto garante que a biblioteca use o algoritmo de codificação adequado.

## Etapa 3: Personalizar a dimensão X (largura do módulo) para maior resolução

A dimensão X controla a largura de um único módulo do código de barras (a menor barra preta ou branca). Definir um valor baixo em pixels gera uma imagem de maior resolução.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Uma dimensão X maior facilita a leitura por scanners de baixa resolução, enquanto um valor menor compacta mais dados em um espaço limitado. Ajuste esse valor conforme o ambiente de leitura.

## Etapa 4: Definir o número de colunas para controlar o tamanho do código de barras

MicroPDF417 permite de 1 a 4 colunas. Mais colunas produzem um código de barras mais curto e mais largo; menos colunas criam um código mais alto e mais estreito.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Por que isso importa:** Escolher a quantidade correta de colunas permite encaixar o código de barras em um elemento de UI ou etiqueta impressa específica sem necessidade de redimensionamento manual.

## Etapa 5: Salvar o código de barras como imagem PNG

Por fim, grave o código de barras gerado no disco. PNG preserva qualidade sem perdas, o que é importante para uma leitura nítida.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Se o diretório de destino não existir, o método `Save` lança uma `ArgumentException`. Você pode prevenir isso com uma verificação simples:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Código-fonte completo

Juntando todas as partes, aqui está o programa completo e executável:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Executar este programa gera um arquivo chamado **MicroPdf417.png** que se parece com a captura de tela abaixo (imagem omitida por brevidade). O código de barras codifica o texto *Sample* e respeita as configurações de dimensão X e colunas que você definiu.

## Personalizando outras opções do PDF417

Embora este guia foque em **personalizar código de barras pdf417** que afetam o tamanho, o Aspose.BarCode oferece muitas outras configurações que podem ser úteis:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Controla o número de linhas (altura) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Define o nível de correção de erro (mais alto = mais tolerante) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Gera um código de barras truncado (sem padrão de parada) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Escolhe compactação numérica, de texto ou de bytes | `CompactionModes.Numeric`, etc. |

**Dica profissional:** Quando precisar de um código de barras que caiba em uma largura fixa, comece aumentando `Columns` e diminuindo `XDimension`. Se o scanner relatar símbolos perdidos, eleve o `ErrorLevel` para melhorar a redundância.

## Tratamento de casos extremos

* **Texto muito longo para MicroPDF417:** A variante Micro suporta até 1 KB de dados. Se sua string exceder esse limite, troque para a simbologia completa `Pdf417` alterando `EncodeTypes.MicroPdf417` para `EncodeTypes.Pdf417`.
* **Formato de imagem não suportado:** `BarCodeImageFormat` também aceita `Jpeg`, `Bmp` e `Gif`. Escolha um formato que corresponda ao seu pipeline de processamento posterior.
* **Caminhos multiplataforma:** Use `Path.Combine` em vez de barras invertidas fixas ao direcionar Linux ou macOS.

## Verificando o código de barras

Você pode validar a imagem gerada com qualquer aplicativo de scanner de código de barras padrão (mobile ou desktop). O scanner deve retornar o texto original **Sample**. Se falhar:

1. Verifique se a dimensão X não está definida abaixo de 1 pixel (alguns scanners não conseguem resolver módulos subpixel).
2. Garanta que o arquivo de saída não esteja corrompido — execute o programa novamente e compare os tamanhos dos arquivos.
3. Aumente `ErrorLevel` para melhorar a tolerância.

## Conclusão

Agora você sabe **gerar código de barras** em C# usando Aspose.BarCode, como **personalizar código de barras pdf417** em termos de dimensões e número de colunas, e como **criar imagem de código de barras C#** que os projetos podem incorporar diretamente. O exemplo completo demonstra um fluxo de trabalho prático desde a configuração do projeto até a saída final em PNG.

Em seguida, explore outras simbologias como QR, Code128 ou DataMatrix trocando o valor do enum `EncodeTypes`. Ajustar parâmetros adicionais como `Resolution` ou `Margin` permite afinar cada código de barras para sua aplicação específica.

Bom código, e que seus códigos de barras impulsionem seu próximo projeto de automação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}