---
category: general
date: 2026-09-19
description: Como gerar código de barras usando Aspose em C# – um guia passo a passo
  para criar códigos de barras com Aspose de forma rápida e confiável.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: pt
lastmod: 2026-09-19
og_description: Como gerar código de barras com Aspose em C#. Siga este guia para
  criar código de barras com Aspose, configurar MacroPdf417 e salvar como PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Como gerar código de barras com Aspose – guia completo em C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Como gerar código de barras com Aspose em C#
url: /pt/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras com Aspose em C#

Gerar código de barras em C# é simples quando você usa a biblioteca Aspose.BarCode. Este tutorial mostra como **criar código de barras com Aspose** passo a passo, abordando o formato MacroPdf417, configurações comuns de aparência e como salvar o resultado como uma imagem PNG.

Você aprenderá a:

* Instalar e referenciar Aspose.BarCode para .NET  
* Configurar propriedades específicas do MacroPdf417, como ID do arquivo, ID do segmento e soma de verificação  
* Ajustar opções visuais como dimensão X e contagem de colunas  
* Exportar o código de barras para um arquivo de imagem  

Nenhuma experiência prévia com Aspose é necessária — apenas um entendimento básico de C# e Visual Studio.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

| Requisito | Detalhe |
|-----------|---------|
| .NET runtime | .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider ou qualquer editor que suporte C# |
| Aspose.BarCode | Pacote NuGet `Aspose.BarCode` (versão de avaliação ou licenciada) |
| Conhecimento básico de C# | Familiaridade com instruções `using` e inicialização de objetos |

Você pode adicionar Aspose.BarCode ao seu projeto via o Gerenciador de Pacotes NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Como gerar código de barras em C# – fluxo geral

O processo consiste em quatro etapas lógicas:

1. **Criar uma instância de `BarcodeGenerator`** com o tipo de codificação desejado (MacroPdf417) e o texto que você deseja codificar.  
2. **Definir opções comuns de aparência** como dimensão X e contagem de colunas.  
3. **Configurar propriedades específicas do MacroPdf417** como ID do arquivo, ID do segmento e carimbo de data/hora.  
4. **Salvar o código de barras** em um formato de sua escolha (PNG neste exemplo).

Cada etapa é explicada em detalhe a seguir.

## Etapa 1: Criar um gerador de código de barras para MacroPdf417

A classe `BarcodeGenerator` é o ponto de entrada para todas as tarefas de criação de códigos de barras. Ao instanciá‑la, você passa dois argumentos:

* `EncodeTypes.MacroPdf417` – indica ao Aspose que deve usar a simbologia MacroPdf417.  
* A string de dados – o texto que será codificado dentro do código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Por que isso importa:** MacroPdf417 é um código de barras bidimensional que pode transportar grandes quantidades de dados e suporta recursos macro, como segmentação de arquivos, útil para transmitir arquivos grandes em partes.

## Etapa 2: Definir opções comuns de aparência do código de barras

Embora o MacroPdf417 possua muitas configurações especializadas, você ainda quer controlar a densidade visual e o layout. Os parâmetros mais comuns são:

* **X‑dimension** – a largura do módulo mais pequeno (pixel). Valores menores produzem uma imagem mais densa.  
* **Columns** – o número de colunas de dados por linha; números maiores reduzem a altura do código de barras.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Dica:** Mantenha `XDimension` entre 2 e 4 pixels para a maioria dos cenários de exibição em tela. Valores maiores melhoram a legibilidade em impressoras de baixa resolução, mas aumentam o tamanho total da imagem.

## Etapa 3: Configurar propriedades específicas do MacroPdf417

MacroPdf417 adiciona um conjunto de campos de metadados que permitem dividir um arquivo grande em vários segmentos de código de barras. As propriedades a seguir são comumente necessárias:

| Propriedade | Propósito |
|-------------|-----------|
| `MacroPdf417FileID` | Identificador único para o arquivo inteiro (máx. 8 dígitos). |
| `MacroPdf417SegmentID` | Índice do segmento atual (começa em 0). |
| `MacroPdf417SegmentsCount` | Número total de segmentos no arquivo. |
| `MacroPdf417FileName` | Nome legível do arquivo original. |
| `MacroPdf417Checksum` | Soma de verificação CCITT‑16 opcional para detecção de erros. |
| `MacroPdf417FileSize` | Tamanho do arquivo original em bytes. |
| `MacroPdf417TimeStamp` | Carimbo de data/hora da geração do arquivo. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Strings opcionais para identificar destinatário/remetente. |
| `MacroPdf417Terminator` | Determina se o código de barras é o último segmento (`Set`) ou um segmento intermediário (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Por que esses campos são úteis:**  
> *Quando você precisa enviar um documento grande por um canal de baixa largura de banda, pode dividir o documento em vários códigos de barras MacroPdf417. O receptor reconstrói o arquivo original lendo os metadados de cada segmento.*

## Etapa 4: Salvar o código de barras gerado como imagem

Aspose suporta muitos formatos de saída: PNG, JPEG, BMP, TIFF, SVG e PDF. PNG é um formato sem perdas ideal para web ou exibição em UI.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Ao executar o programa, você encontrará um arquivo PNG semelhante à ilustração abaixo.

![Código de barras MacroPdf417 gerado com Aspose em C#](placeholder-image.png){.img-fluid alt="como gerar código de barras com Aspose em C#"}

> **Saída esperada:** Um PNG de 300 × 150 pixels mostrando um código de barras MacroPdf417 que codifica o texto “Sample” junto com os metadados macro fornecidos.

## Exemplo completo, executável

Juntando tudo, aqui está o programa completo que você pode copiar, colar e executar:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Execute o programa com `dotnet run` (ou pressione **F5** no Visual Studio). Após a execução, verifique se o arquivo PNG existe e abre sem erros.

## Perguntas comuns e tratamento de casos extremos

### E se eu precisar de um formato de imagem diferente?
Aspose suporta `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` e `Pdf`. Basta substituir `BarCodeImageFormat.Png` pelo valor enum desejado.

### Como gerar múltiplos segmentos automaticamente?
Você pode colocar o código acima dentro de um loop, incrementando `MacroPdf417SegmentID` a cada iteração e atualizando a string de dados. Lembre‑se de manter `MacroPdf417SegmentsCount` constante em todos os segmentos.

### E se os dados excederem a capacidade de um único símbolo MacroPdf417?
MacroPdf417 foi projetado para cargas úteis grandes, mas todo código de barras tem um limite teórico (≈ 1,1 KB por segmento). Divida o arquivo fonte em blocos que caibam nesse limite e codifique cada bloco como um segmento separado.

### A soma de verificação precisa ser calculada manualmente?
Aspose pode gerar a soma de verificação CCITT‑16 automaticamente se você definir `MacroPdf417Checksum` como `0`. No exemplo fornecemos um valor codificado para ilustração; em código de produção você normalmente deixaria a biblioteca calculá‑la.

### Como mudar as cores de primeiro plano/fundo do código de barras?
Use as propriedades `BarColor` e `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Conclusão

Agora você sabe **como gerar código de barras** em C# usando Aspose.BarCode e, especificamente, **como criar código de barras com Aspose** para a simbologia MacroPdf417. O tutorial abordou instalação, configuração de aparência e campos específicos de macro.

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}