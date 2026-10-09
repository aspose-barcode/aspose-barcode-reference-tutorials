---
category: general
date: 2026-09-19
description: Crie código de barras PDF417 em C# e aprenda como gerar a imagem do código,
  definir as dimensões e salvar como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: pt
lastmod: 2026-09-19
og_description: Crie código de barras PDF417 em C# e descubra como gerar a imagem
  do código, definir suas dimensões e salvá‑lo como um arquivo PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Crie código de barras PDF417 e exporte PNG em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Como criar código de barras PDF417 e exportar PNG em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 e exportar PNG em C#

Se você precisa **criar código de barras PDF417** em uma aplicação .NET, este guia mostra como gerar uma imagem de código de barras, ajustar suas dimensões e salvá‑la como um arquivo PNG. Você verá um exemplo completo e executável que usa a biblioteca Aspose.BarCode, para que possa copiar o código diretamente para o seu próprio projeto.

Gerar uma imagem de código de barras é uma necessidade comum para sistemas de bilhetagem, rastreamento de inventário e cartões de embarque móveis. Ao final deste tutorial você entenderá **como gerar imagem de código de barras**, **como definir dimensões do código de barras** e **como criar arquivos PNG de código de barras** que atendam aos seus padrões de qualidade visual.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+).
* Um ambiente de desenvolvimento como Visual Studio 2022 ou VS Code.
* Uma licença válida para a biblioteca **Aspose.BarCode for .NET** (a avaliação gratuita funciona para este exemplo).
* Familiaridade básica com a sintaxe C#.

Instale o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo aplicativo de console ou adicione o código a um projeto existente. Importe os namespaces necessários no topo do arquivo:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Esses namespaces dão acesso à classe `BarcodeGenerator` e à enumeração `EncodeTypes`.

## Etapa 2: Como criar código de barras PDF417 – configuração básica do gerador

A primeira operação é instanciar um `BarcodeGenerator` com o tipo de codificação `Pdf417` e o texto que você deseja codificar. Este objeto representa o código de barras que será renderizado posteriormente.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Por que isso importa*: `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417, que é um código de barras linear empilhado capaz de armazenar grandes quantidades de dados. O segundo argumento (“Sample”) é a carga útil que aparecerá quando o código de barras for escaneado.

## Etapa 3: Como definir dimensões do código de barras – ajuste fino de densidade e layout

Um código de barras PDF417 consiste em linhas e colunas de módulos. Ajustar a dimensão X (largura do módulo) e o número de linhas/colunas permite controlar a densidade visual e o tamanho geral da imagem.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Por que isso importa*:  
* **Dimensão X** determina quão largo cada quadradinho (módulo) é. Um valor menor gera um código de barras mais compacto, mas pode ser mais difícil de ler por scanners de baixa resolução.  
* **Colunas** e **Linhas** afetam a capacidade de dados e a forma física. Aumentar as colunas deixa o código de barras mais largo; aumentar as linhas o deixa mais alto. Você pode experimentar valores até os limites mostrados nos comentários.

**Dica profissional**: Se o código de barras parecer muito denso em uma tela de alta DPI, aumente `XDimension.Pixels` para 3 ou 4. Por outro lado, para uma etiqueta pequena, você pode definir 1 pixel e reduzir a contagem de colunas.

## Etapa 4: Como gerar imagem do código de barras – renderizando para um bitmap em memória

Depois de configurar o gerador, você pode renderizar o código de barras para um objeto de imagem. Esta etapa é opcional se você precisar apenas salvar o arquivo diretamente, mas expor o bitmap permite aplicar processamento adicional (por exemplo, adicionar um logotipo ou desenhar uma borda).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` devolve um `System.Drawing.Image` que pode ser manipulado com GDI+ se desejar.

## Etapa 5: Como criar PNG do código de barras – salvando o arquivo de imagem final

Por fim, grave a imagem no disco no formato PNG. PNG preserva qualidade sem perdas, o que é ideal para aplicações de leitura.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Por que isso importa*: O método `Save` cuida da codificação e da I/O de arquivos para você. Usar `BarCodeImageFormat.Png` garante que a saída seja uma imagem portátil e sem perdas, que funciona em navegadores e dispositivos móveis.

### Exemplo completo e executável

Abaixo está o programa completo que você pode colar em `Program.cs` e executar. Substitua `YOUR_DIRECTORY` por uma pasta existente na sua máquina.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Executar o programa produz um arquivo PNG que se parece com isto:

![Exemplo de código de barras PDF417 gerado](https://example.com/placeholder-image.png "Código de barras PDF417 gerado com dimensões personalizadas salvo como PNG")

*Texto alternativo*: **Exemplo de código de barras PDF417 gerado com C# mostrando dimensões personalizadas salvo como PNG** – isso satisfaz o requisito de **criar código de barras PDF417** para acessibilidade de imagem.

## Variações comuns e casos de borda

| Situação | Ajuste recomendado |
|-----------|------------------------|
| **Etiqueta muito pequena** (ex.: 1 cm × 2 cm) | Defina `XDimension.Pixels = 1` e reduza `Columns` para 2‑3. Verifique a legibilidade pelo scanner. |
| **Impressão de alta resolução** (300 dpi ou mais) | Aumente `XDimension.Pixels` para 3‑4 e, opcionalmente, eleve `Rows` para maior capacidade de dados. |
| **Necessidade de outro formato de imagem** (JPEG, BMP) | Troque `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. |
| **Incorporação em PDF** | Use `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` em vez de PNG. |
| **Dados dinâmicos** (entrada do usuário) | Substitua a string estática `"Sample"` por uma variável, por exemplo, `userInput`. Garanta que o comprimento do texto não ultrapasse os limites do PDF417 (≈ 1 800 caracteres). |

## Lista de verificação de solução de problemas

* **Imagem em branco** – Verifique se o diretório de saída existe e se a aplicação tem permissão de gravação.  
* **Código de barras não escaneável** – Aumente `XDimension.Pixels` ou adicione mais colunas/linhas; fundos de baixo contraste também podem causar falhas.  
* **Tamanho inesperado** – Revise os valores de `Columns` e `Rows`; a biblioteca respeita os limites máximos mostrados nos comentários.  

## Próximos passos

Agora que você pode **criar código de barras PDF417**, considere explorar estes tópicos relacionados:

* **Como gerar imagem de código de barras** em outros formatos, como SVG para gráficos escaláveis na web.  
* **Como definir dimensões do código de barras** para QR Codes e simbologias DataMatrix.  
* **Como criar PNG de código de barras** com cores personalizadas ou logotipos incorporados usando `System.Drawing`.  

Essas extensões permitem construir um serviço completo de geração de códigos de barras que pode atender a aplicativos móveis, portais web e utilitários de desktop.

---

*Você aprendeu como criar um código de barras PDF417, personalizar suas dimensões, renderizar uma imagem de código de barras e salvá‑la como um arquivo PNG usando C#. Aplique os padrões mostrados aqui a outros tipos de códigos de barras e formatos de imagem para ampliar suas capacidades de automação.*

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}