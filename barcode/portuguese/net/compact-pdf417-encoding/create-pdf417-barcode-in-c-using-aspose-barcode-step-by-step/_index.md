---
category: general
date: 2026-10-18
description: Aprenda a criar códigos de barras PDF417 em C# com Aspose.BarCode. Este
  tutorial cobre a geração de PDF417 básico, compacto, macro e micro, com código completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: pt
lastmod: 2026-10-18
og_description: Crie código de barras PDF417 em C# com Aspose.BarCode. Siga este guia
  para gerar códigos de barras PDF417 básicos, compactos, macro e micro passo a passo.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Criar código de barras PDF417 em C# – tutorial completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Criar código de barras PDF417 em C# usando Aspose.BarCode – guia passo a passo
url: /pt/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras PDF417 em C# usando Aspose.BarCode – guia passo a passo

Se você precisar **criar código de barras PDF417** em uma aplicação .NET, este tutorial o guiará por todo o processo. Você verá como gerar um código de barras básico, habilitar o modo compacto, adicionar metadados macro e produzir uma variante micro — tudo com explicações claras e código executável.

Gerar códigos de barras PDF417 é comum em logística, bilhetagem e gerenciamento de documentos. Ao final deste guia, você será capaz de integrar a criação de códigos de barras em qualquer projeto C# sem ferramentas externas.

## Pré-requisitos

* .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
* Visual Studio 2022 ou qualquer IDE C#
* **Aspose.BarCode for .NET** pacote NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permissão de escrita em uma pasta onde os arquivos PNG gerados serão salvos

Nenhuma configuração adicional é necessária; a biblioteca lida com todos os detalhes de codificação de baixo nível.

## Etapa 1: Criar um código de barras PDF417 básico

A primeira etapa cria um código de barras PDF417 padrão com tamanho e contagem de colunas personalizados.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Por que essas configurações são importantes**

* `XDimension.Pixels` controla o tamanho físico de cada elemento do código de barras. Um valor de 2 produz uma imagem nítida na maioria das telas e impressoras.
* `Pdf417.Columns` determina quantas colunas de dados o código de barras contém. Menos colunas reduzem a largura; mais colunas aumentam a capacidade de dados.

Executar o código cria `Pdf417Basic.png`, que se parece com um símbolo PDF417 típico com três colunas de dados e uma coluna completa de metadados no lado direito.

## Etapa 2: Habilitar modo compacto (truncado)

O modo compacto remove a coluna de metadados à direita, tornando o código de barras mais estreito. Isso é útil quando o espaço é limitado, mas os dados podem ser reconstruídos a partir das linhas restantes.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Por que truncar?**  
Quando `Truncate` está `true`, o gerador omite a coluna opcional à direita que armazena correção de erros e metadados de nível de arquivo. O código de barras resultante ocupa menos colunas e ainda pode ser lido pela maioria dos leitores PDF417.

## Etapa 3: Criar um código de barras Macro PDF417 com metadados de nível de arquivo

Macro PDF417 estende o formato padrão com identificadores de segmento, permitindo que um documento grande seja dividido em vários códigos de barras. Isso é útil para codificar strings longas ou arquivos de várias páginas.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Explicação dos campos macro**

| Propriedade | Propósito |
|-------------|-----------|
| `MacroPdf417FileID` | Identificador único para todo o arquivo; todos os segmentos compartilham este valor. |
| `MacroPdf417SegmentID` | Índice do segmento atual (começa em 1). |
| `MacroPdf417SegmentsCount` | Número total de segmentos que compõem o conjunto completo de dados. |

Um scanner que entende Macro PDF417 pode reconstituir os dados originais lendo todos os segmentos e usando esses identificadores.

## Etapa 4: Criar um código de barras Micro PDF417 para dados curtos

Micro PDF417 é uma versão compacta projetada para cargas úteis pequenas (até 90 caracteres). Ela limita a faixa de colunas a 1‑4, tornando o código de barras adequado para etiquetas diminutas ou dispositivos com área de exibição limitada.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Quando usar Micro PDF417**  
Use esta variante quando a carga útil de dados for curta e você precisar do menor código de barras possível. É ideal para etiquetas de inventário, cartões de acesso ou qualquer cenário onde o espaço de tela é escasso.

## Exemplo completo em funcionamento

Abaixo está um aplicativo de console autônomo que gera os quatro tipos de código de barras em uma única execução. Copie o código para um novo projeto C#, substitua `YOUR_DIRECTORY` por um caminho de pasta existente e execute-o.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Saída esperada**

Executar o programa cria quatro arquivos PNG na pasta especificada:

* `Pdf417Basic.png` – código de barras padrão com três colunas
* `CompactPdf417.png` – mesmos dados, coluna à direita truncada
* `MacroPdf417.png` – código de barras macro contendo metadados de segmento
* `MicroPdf417.png` – código de barras micro compacto para strings curtas

Abra qualquer imagem com um visualizador de imagens; você verá os padrões distintos do PDF417. Escaneá-los com um leitor de código de barras móvel (por exemplo, ZXing, Scandit) retorna as strings de texto originais.

## Perguntas comuns e dicas

* **E se o código de barras parecer borrado?**  
  Aumente `XDimension.Pixels` para 3 ou 4. Tamanhos de módulo maiores produzem imagens de alta resolução, ao custo de um arquivo maior.

* **Posso gerar SVG em vez de PNG?**  
  Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg` nas chamadas `Save`.

* **Preciso definir o nível de correção de erros manualmente?**  
  Aspose.BarCode escolhe automaticamente um nível ótimo. Para casos de uso especializados, você pode ajustar `Pdf417.ErrorCorrectionLevel`.

* **Como incorporar o código de barras em um documento PDF?**  
  Use `Aspose.Pdf` para adicionar o PNG ou SVG gerado como um elemento de imagem em uma página PDF.

* **A biblioteca é segura para uso em múltiplas threads?**  
  Cada instância de `BarcodeGenerator` é independente; você pode criar geradores em várias threads sem estado compartilhado.

## Conclusão

Agora você sabe como **criar código de barras PDF417** em C# usando Aspose.BarCode, cobrindo as variantes básica, compacta, macro e micro.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar código de barras pdf417 em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Como criar código de barras PDF417 em C# com modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}