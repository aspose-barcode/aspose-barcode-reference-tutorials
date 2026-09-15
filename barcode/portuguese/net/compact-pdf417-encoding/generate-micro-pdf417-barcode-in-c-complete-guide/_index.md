---
category: general
date: 2026-07-18
description: Gere código de barras micro PDF417 com Aspose.BarCode para .NET – guia
  passo a passo cobrindo colunas, linhas e saída PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: pt
lastmod: 2026-07-18
og_description: Gere código de barras micro PDF417 instantaneamente com Aspose.BarCode
  para .NET. Aprenda a controlar colunas, linhas e salvar como PNG em minutos.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Gerar Código de Barras Micro PDF417 – Tutorial Completo em C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Gerar Código de Barras Micro PDF417 em C# – Guia Completo
url: /pt/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras Micro PDF417 em C# – Guia Completo

Já se perguntou como **gerar código de barras micro pdf417** diretamente da sua aplicação C#? Você não está sozinho. Seja etiquetando inventário, codificando URLs curtas ou criando uma solução de leitura personalizada, dominar esse pequeno, porém poderoso código 2‑D pode economizar muito trabalho.

Neste tutorial vamos percorrer um exemplo real usando **Aspose.BarCode for .NET**, mostrando como ajustar colunas, linhas e tamanho do módulo, e então salvar o resultado em um arquivo PNG. Ao final, você terá um aplicativo console pronto‑para‑executar que gera três imagens de código de barras diferentes—sem mistérios.

## O que você vai precisar

- .NET 6 ou superior (o código também funciona no .NET Framework 4.7+)
- Visual Studio 2022 (ou qualquer IDE C# de sua preferência)
- O pacote NuGet **Aspose.BarCode** (`Aspose.BarCode`)
- Uma pasta gravável no disco para os PNGs de saída

Se já tem tudo isso, ótimo—vamos começar.

## Etapa 1: Configurar o Projeto e Instalar o Aspose.BarCode

Primeiro, crie um novo projeto console:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Dica profissional:** Execute `dotnet restore` após adicionar o pacote para garantir que todas as dependências sejam resolvidas.

Agora abra `Program.cs`. Vamos começar importando os namespaces necessários:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Essas duas instruções `using` nos dão acesso ao `BarcodeGenerator`, `EncodeTypes` e ao enum de formato de imagem que usaremos mais adiante.

## Etapa 2: Inicializar o Gerador MicroPdf417

O coração da operação é o objeto `BarcodeGenerator`. Alimentamos ele com o tipo de codificação **MicroPdf417** e o texto que queremos codificar—neste caso a palavra “ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Por que `MicroPdf417`? Comparado ao PDF417 de tamanho completo, a versão micro compacta mais dados em um espaço menor, ideal para etiquetas com espaço limitado.

## Etapa 3: Ajustar o Tamanho do Módulo (X‑Dimension)

O tamanho do módulo determina quantos pixels cada quadradinho do código de barras ocupa. Um valor de **2 pixels** gera uma imagem nítida e legível sem inflar o tamanho do arquivo.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Observação:** Se precisar de um código de barras maior para leitura à distância, aumente esse número para 3 ou 4.

## Etapa 4: Gerar Códigos de Barras com Diferentes Configurações de Colunas/Linhas

### 4.1 Duas Colunas, Linhas Calculadas Automaticamente

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Seis Linhas, Colunas Calculadas Automaticamente

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Quatro Colunas × Oito Linhas (Totalmente Especificado)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Cada chamada a `Save` grava um arquivo PNG no diretório de trabalho do projeto. Sinta‑se à vontade para mudar o caminho (`"YOUR_DIRECTORY/..."`) para algo como `Path.Combine(Environment.CurrentDirectory, "output")` se preferir uma pasta dedicada.

## Etapa 5: Exemplo Completo Funcional

Juntando tudo, aqui está o programa completo, pronto para copiar e colar:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Saída Esperada

A execução do programa produz três arquivos PNG:

| Nome do arquivo | Dimensões aproximadas (px) | Indicação visual |
|-----------------|----------------------------|-------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Código estreito e mais alto |
| `MicroPdf417Rows6.png` | 120 × 180 | Código mais largo e curto |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Layout quase quadrado e equilibrado |

Abra qualquer um deles em um visualizador de imagens—você verá um **Micro PDF417** nítido pronto para ser escaneado.

## Perguntas Frequentes & Casos de Borda

- **E se a pasta de saída não existir?**  
  Chame `Directory.CreateDirectory(path)` antes da primeira chamada a `Save` para evitar um `DirectoryNotFoundException`.

- **Posso mudar o formato da imagem?**  
  Claro. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`, conforme necessário.

- **Existe um limite para o comprimento do texto?**  
  O MicroPdf417 pode codificar até 1 KB de dados, mas limites práticos dependem das linhas/colunas escolhidas. Se ocorrer um erro, aumente linhas ou colunas.

- **Como incorporar o código de barras em um PDF?**  
  Use Aspose.Pdf para inserir o PNG gerado, ou troque para `BarCodeImageFormat.Pdf` para gerar um PDF diretamente.

## Dicas Profissionais para Geração de Código de Barras em C#

1. **Cache o gerador** quando precisar de muitos códigos de barras com as mesmas configurações—apenas o texto muda, economizando ciclos de CPU.  
2. **Ajuste a correção de erro** via `generator.Parameters.Barcode.Pdf417.ErrorLevel` se o ambiente de leitura for ruidoso.  
3. **Teste com scanners reais** cedo. Alguns dispositivos portáteis têm dificuldade com códigos de barras micro muito densos; ajustar `XDimension` pode fazer grande diferença.

## Conclusão

Agora você sabe como **gerar código de barras micro pdf417** usando **Aspose.BarCode for .NET**, manipular **colunas MicroPdf417** e **linhas MicroPdf417**, e salvar o resultado como arquivos PNG—tudo a partir de um único aplicativo console C# bem organizado. Experimente diferentes tamanhos de módulo, níveis de erro ou até saída em cores para atender às necessidades do seu projeto.

Em seguida, você pode explorar **geração de código de barras C#** para outras simbologias como QR, Code128 ou DataMatrix, ou incorporar as imagens diretamente em PDFs com Aspose.Pdf. O céu é o limite quando você domina o básico.

Bom código, e que seus escaneamentos sejam sempre sem erros!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como Criar Código de Barras – Compact PDF417 com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Gerar Código de Barras DataMatrix – Guia Pro com Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}