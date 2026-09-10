---
category: general
date: 2026-09-10
description: Gere código de barras PDF417 em C# rapidamente. Aprenda como gerar PDF417
  e como alterar o tamanho do código de barras com Aspose.BarCode em apenas algumas
  linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: pt
lastmod: 2026-09-10
og_description: Gere código de barras PDF417 em C# instantaneamente. Este tutorial
  mostra como gerar PDF417 e como alterar o tamanho do código de barras usando Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Gerar código de barras PDF417 em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Como gerar código de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# – guia passo a passo

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você verá um exemplo conciso, pronto‑para‑executar, que cria um código de barras PDF417, permite controlar seu tamanho e salva o resultado como uma imagem PNG.

Gerar um código de barras PDF417 é uma necessidade comum para sistemas de inventário, cartões de embarque e rastreamento de documentos. Neste tutorial também abordamos **como alterar o tamanho do código de barras** para que ele se adapte a diferentes necessidades de impressão ou exibição em tela.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior (o código também funciona com .NET Framework 4.6+)
* Visual Studio 2022 ou qualquer IDE C#
* O pacote NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Familiaridade básica com aplicações console em C#

## Configuração do projeto

1. Crie um novo projeto console:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Adicione a referência ao Aspose.BarCode (veja os pré‑requisitos).  

3. Abra `Program.cs` e substitua seu conteúdo pelo exemplo completo abaixo.

## Etapa 1: Gerar código de barras PDF417

A primeira etapa é criar uma instância de `BarcodeGenerator` configurada para a simbologia **PDF417**. Esse objeto é o ponto de entrada para todas as operações de código de barras.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Por que isso importa* – O valor enum `EncodeTypes.Pdf417` indica ao Aspose.BarCode que deve usar o padrão PDF417, enquanto o segundo argumento fornece os dados que serão codificados. O gerador agora contém um objeto de código de barras completo que você pode personalizar antes de salvar.

## Etapa 2: Como alterar o tamanho do código de barras (tamanho do módulo)

Os códigos de barras PDF417 são compostos por pequenos módulos quadrados. Ajustar o tamanho do módulo altera as dimensões gerais da imagem sem modificar os dados codificados.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Por que isso importa* – Um `XDimension` maior gera um código de barras maior, adequado para impressão de alta resolução; um valor menor é melhor para exibição em tela. O padrão costuma ser 1 px, o que pode ficar apertado em monitores modernos.

## Etapa 3: Configurar layout – colunas e linhas

O PDF417 permite definir o número de colunas e linhas, o que influencia tanto a forma do código de barras quanto sua capacidade de correção de erros.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Por que isso importa* – Mais colunas deixam o código de barras mais largo, enquanto mais linhas o deixam mais alto. Ajuste esses valores para caber no espaço disponível na sua UI ou etiqueta impressa.

## Etapa 4: Salvar a imagem do código de barras

Por fim, grave o código de barras em um arquivo. Aqui usamos PNG porque preserva bordas nítidas e suporta transparência.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Executando o programa cria `LayoutPdf417.png` na pasta de saída do projeto. A imagem ficará assim:

![gerar exemplo de código de barras PDF417 mostrando 4 colunas e 9 linhas](https://example.com/images/pdf417-sample.png){#barcode-image alt="gerar exemplo de código de barras PDF417 mostrando 4 colunas e 9 linhas"}

*Dica*: Se precisar de um formato de imagem diferente (JPEG, BMP, TIFF), substitua `BarCodeImageFormat.Png` pelo valor enum apropriado.

## Como gerar PDF417 – fontes de dados alternativas

O código acima usa a string fixa `"Layout test"`. Em cenários reais você costuma obter os dados de um banco de dados, de um arquivo ou da entrada do usuário.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

O restante das etapas (tamanho, layout, gravação) permanece inalterado. Isso demonstra **como gerar PDF417** a partir de fontes dinâmicas sem complexidade adicional.

## Armadilhas comuns e como evitá‑las

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| O código de barras aparece borrado | `XDimension` definido muito baixo para a resolução de saída | Aumente `XDimension.Pixels` ou salve em um formato vetorial como SVG (`BarCodeImageFormat.Svg`) |
| O texto não cabe no layout escolhido | Muitos caracteres para as linhas/colunas selecionadas | Reduza o número de linhas/colunas ou divida os dados em vários códigos de barras |
| O arquivo de imagem não é criado | Pasta de saída inexistente ou permissões de gravação ausentes | Garanta que o diretório exista (`Directory.CreateDirectory`) e que o aplicativo tenha os direitos adequados |

## Verificando o código de barras

Depois de gerar a imagem, você pode verificá‑la usando qualquer aplicativo scanner de PDF417 (smartphones têm scanners gratuitos) ou o leitor embutido do Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Se a saída corresponder ao texto original, o processo de **gerar código de barras PDF417** foi bem‑sucedido.

## Exemplo completo, executável

Abaixo está o programa completo que você pode copiar‑colar em `Program.cs`. Ele inclui todas as diretivas `using`, tratamento de erros e comentários.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Executando este programa imprime:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Agora você tem uma **solução completa e autônoma** para gerar códigos de barras PDF417 e controlar seu tamanho.

## Conclusão

Neste tutorial você aprendeu como **gerar código de barras PDF417** em C# usando Aspose.BarCode, como **alterar o tamanho do código de barras** ajustando a X‑dimension, e como configurar colunas e linhas para controle de layout. Você também viu como verificar o resultado programaticamente e como adaptar o código para dados dinâmicos.

Em seguida, você pode explorar:

* **Como gerar PDF417** com ajuste de nível de correção de erros (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exportação para **formatos vetoriais** (SVG, EPS) para dimensionamento infinito
* Incorporação do código de barras em um documento PDF com **Aspose.PDF**

Experimente diferentes tamanhos de módulo e opções de layout para atender aos requisitos específicos da sua UI ou impressão. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}