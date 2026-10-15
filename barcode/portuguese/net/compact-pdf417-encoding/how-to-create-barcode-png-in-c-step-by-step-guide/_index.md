---
category: general
date: 2026-10-15
description: Criar PNG de código de barras em C# com um exemplo compacto de PDF417
  – aprenda como definir colunas, ajustar dimensões e gerar a imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: pt
lastmod: 2026-10-15
og_description: Crie um PNG de código de barras em C# com um exemplo compacto de PDF417.
  Este guia mostra como definir colunas, ajustar dimensões e salvar a imagem.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Criar código de barras PNG em C# – tutorial completo de programação
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Como criar PNG de código de barras em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar barcode PNG em C# – guia passo a passo

Se você precisa **criar barcode PNG** a partir de código C#, este tutorial mostra uma solução completa em apenas algumas linhas. Você verá como definir colunas, ajustar o tamanho do módulo e salvar um barcode PDF417 compacto como imagem PNG — tudo com um único exemplo fácil de entender.

Gerar barcodes programaticamente elimina a etapa manual de usar um editor gráfico e permite incorporar barcodes diretamente em notas fiscais, ingressos ou etiquetas de inventário. Nas seções a seguir, abordaremos tudo o que você precisa saber para **como criar barcode** imagens, por que cada configuração importa e como adaptar o código para diferentes casos de uso.

## Pré-requisitos

* .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
* Uma referência a uma biblioteca de barcode que suporte PDF417, como **Aspose.BarCode for .NET** ou **IronBarcode**. O exemplo usa Aspose.BarCode, que pode ser instalado via NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Familiaridade básica com a sintaxe C# e Visual Studio (ou qualquer IDE de sua preferência).

> **Dica profissional:** Se você prefere uma alternativa gratuita, a biblioteca de código aberto **ZXing.Net** também suporta PDF417, mas os nomes das propriedades diferem ligeiramente. Os conceitos mostrados aqui permanecem os mesmos.

## Como criar barcode PNG em C# (passo principal)

O núcleo da solução é um objeto `BarcodeGenerator` configurado para codificação PDF417. As seções a seguir detalham cada linha de código, explicam **como definir colunas** e mostram por que as configurações afetam o tamanho final do PNG.

### Etapa 1: Inicializar o gerador de barcode com o texto desejado

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Por que isso importa*: O enum `EncodeTypes.Pdf417` indica à biblioteca que deve produzir um barcode bidimensional empilhado. O construtor também aceita os dados que você deseja codificar, portanto não é necessário chamar `SetData` separadamente.

### Etapa 2: Definir a dimensão do módulo (X) em pixels

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

A **dimensão X** controla a densidade visual do barcode. Um valor menor gera uma imagem mais compacta, o que é útil quando você precisa de um PNG compacto para telas móveis ou espaço de impressão limitado.

### Etapa 3: Definir o número de colunas para o barcode PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Esta linha demonstra **como definir colunas**. O PDF417 pode escolher automaticamente a contagem ideal de colunas, mas defini‑la explicitamente fornece uma largura previsível, especialmente ao incorporar o PNG em um layout de tamanho fixo.

### Etapa 4: Habilitar o layout compacto truncando o barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Quando `Truncate` está true, a biblioteca remove linhas finais que não contêm dados, reduzindo a altura total da imagem sem perder informações.

### Etapa 5: Salvar a imagem do barcode como PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

O método `Save` grava o barcode no disco no formato especificado. PNG é sem perdas, tornando‑o ideal para aplicações de leitura que exigem detecção precisa de bordas.

### Exemplo completo e executável

Juntando tudo, aqui está um programa autônomo que você pode copiar, colar e executar:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Saída esperada** – Após executar o programa, você encontrará `CompactPdf417.png` na pasta de execução. A imagem contém um barcode PDF417 de três colunas que é compacto o suficiente para caber em uma etiqueta padrão de 2 × 2 cm, permanecendo totalmente legível.

![Create barcode PNG example](placeholder.png){alt="Criar barcode PNG usando C#"}

## Como definir colunas para diferentes tamanhos de dados (palavra‑chave secundária)

O número de colunas influencia tanto a largura quanto a legibilidade do barcode:

| Colunas | Largura aproximada (px) | Caso de uso típico |
|--------|--------------------------|--------------------|
| 1‑2    | Estreita, alta           | Etiquetas pequenas, impressões semelhantes a RFID |
| 3‑5    | Equilibrada              | Etiquetas de uso geral |
| 6‑9    | Larga, curta             | Grandes cartazes ou embalagens |

Se sua string de dados crescer, a biblioteca pode aumentar automaticamente a contagem de linhas para manter o barcode dentro do limite de colunas. Contudo, forçar uma contagem de colunas muito baixa pode fazer o barcode ficar excessivamente alto, o que pode não caber em uma impressora de recibos. Ajuste a contagem de colunas com base nas restrições físicas do seu meio de saída.

## Como criar imagens de barcode em outros formatos (palavra‑chave secundária)

Embora PNG seja o formato mais comum para web e mobile, você pode precisar **como criar barcode** imagens em JPEG, BMP ou SVG para fluxos de trabalho especializados:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Escolher o formato correto depende do consumidor downstream:

* **PNG** – sem perdas, ideal para scanners.
* **JPEG** – tamanho de arquivo menor, aceitável quando artefatos de compressão leves são toleráveis.
* **SVG** – perfeito para impressão de alta resolução ou dimensionamento de UI.

## Exemplo de barcode em C#: tratamento de erros e casos extremos

Um **exemplo robusto de barcode em C#** deve antecipar problemas em tempo de execução:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Por que envolver em `try/catch`?* Caracteres inválidos no texto, dimensões não suportadas ou problemas de permissão de escrita lançarão exceções. Tratá‑las de forma elegante impede que sua aplicação trave durante o processamento em lote.

## Estendendo o exemplo: adicionando um logotipo ou fundo

Muitos cenários reais exigem sobreposição de logotipo ou fundo colorido. A API Aspose.BarCode permite combinar o barcode com um bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Esta técnica mantém o fluxo de trabalho **criar barcode PNG** intacto enquanto enriquece a identidade visual da imagem final.

## Resumo

Neste guia demonstramos como **criar barcode PNG** arquivos em C# usando uma configuração compacta de PDF417. Você aprendeu:

* O código exato necessário para inicializar um `BarcodeGenerator`.
* **Como definir colunas** e por que a contagem de colunas importa para tamanho e legibilidade.
* Como ajustar a dimensão X e habilitar truncamento para um PNG mais compacto.
* Formas de salvar a imagem em PNG, JPEG ou SVG.
* Padrões de tratamento de erros para um **exemplo de barcode em C#** pronto para produção.
* Extensões opcionais como sobreposição de logotipo e personalização de fundo.

Agora você tem um trecho pronto para executar que pode integrar a geradores de faturas, sistemas de bilhetagem ou ferramentas de gerenciamento de inventário. Experimente diferentes valores de colunas, tamanhos de módulo ou tipos de barcode (por exemplo, QR, Code128) para ver como a imagem muda.

## Próximos passos

* Explore outros tipos de codificação (`EncodeTypes.QR`, `EncodeTypes.Code128`) para cobrir mais casos de uso.
* Combine a geração de barcode com bibliotecas de criação de PDF (por exemplo, **iTextSharp**) para incorporar o PNG diretamente em documentos.
* Investigue dimensionamento dinâmico: calcule a contagem ótima de colunas com base no comprimento da string de entrada e nas dimensões da etiqueta alvo.

Feliz codificação, e aproveite a simplicidade de gerar programaticamente barcodes PNG nítidos em C#!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar barcode PDF417 e salvá‑lo como PNG em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Como criar barcode PDF417 e definir seu tamanho em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Como criar barcode PDF417 em C# com modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}