---
category: general
date: 2026-10-15
description: Crie PNG de código de barras rapidamente usando C#. Aprenda como gerar
  código de barras, alterar linhas, configurar as definições do código de barras e
  gerar código de barras PDF417 em um único tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: pt
lastmod: 2026-10-15
og_description: Crie PNG de código de barras em C# rapidamente. Este tutorial mostra
  como gerar código de barras, alterar linhas, configurar o código de barras e gerar
  código de barras PDF417 com código limpo.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Criar código de barras PNG com PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Criar código de barras PNG com PDF417 em C# – guia completo
url: /pt/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar barcode PNG com PDF417 em C# – guia completo

Se você precisar **criar barcode PNG** a partir de código C#, este guia mostra exatamente como fazer isso. Vamos percorrer a geração de um barcode PDF417, alterar linhas e configurar todos os parâmetros principais antes de salvar o resultado como uma imagem PNG.

Você aprenderá como **gerar barcode** imagens programaticamente, ajustar o layout para corresponder ao seu design e entender as opções para configurar a aparência de um barcode. Nenhuma ferramenta externa é necessária — apenas a biblioteca Aspose.BarCode (ou qualquer pacote de barcode .NET compatível) e algumas linhas de código.

## O que você precisará

- .NET 6.0 ou posterior (o exemplo usa .NET 6, mas qualquer versão recente do .NET funciona)
- Uma referência ao pacote NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Familiaridade básica com C# e Visual Studio (ou sua IDE preferida)

> **Dica profissional:** Se você preferir uma alternativa gratuita, a mesma superfície de API está disponível na biblioteca de código aberto `ZXing.Net`; porém, os trechos de código abaixo têm como alvo o Aspose.BarCode porque ele fornece controles diretos de layout PDF417.

## Etapa 1: Configurar o projeto e adicionar a biblioteca de barcode

Crie um novo aplicativo console e adicione o pacote NuGet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Em seguida, abra `Program.cs` e adicione as diretivas `using` necessárias:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Esses namespaces expõem a classe `BarcodeGenerator` e a enumeração `EncodeTypes` que você usará para **gerar PDF417 barcode** imagens.

## Etapa 2: Criar barcode PNG – gerador básico

A primeira linha executável cria uma instância `BarcodeGenerator` configurada para codificação PDF417. Este é o núcleo de **como gerar barcode** imagens.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Por que isso importa:** A flag `EncodeTypes.Pdf417` indica à biblioteca qual simbologia usar. O segundo argumento (`"Layout test"`) é o texto bruto que será codificado no barcode.

## Etapa 3: Como configurar barcode – definir tamanho do módulo

Um módulo (ou dimensão X) define o menor elemento imprimível do barcode. Ajustá-lo altera o tamanho geral da imagem sem afetar a densidade dos dados.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Definir `Pixels = 2` gera um resultado compacto e de alta resolução **criar barcode PNG** que funciona bem para miniaturas da web e impressão.

## Etapa 4: Como alterar linhas – personalizar o layout PDF417

PDF417 permite controlar explicitamente o número de colunas e linhas. Esta é a etapa que responde **como alterar linhas** em um barcode.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Caso extremo:** Se você solicitar mais linhas do que os dados exigem, a biblioteca adicionará automaticamente linhas de preenchimento. Por outro lado, solicitar linhas demais poucas pode causar uma exceção porque os dados não cabem.

## Etapa 5: Salvar o barcode gerado como um arquivo PNG

Finalmente, grave a imagem no disco. Isso completa o fluxo de trabalho **criar barcode PNG**.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

Ao executar o programa, você verá um arquivo chamado `Pdf417_4x9.png` na pasta do projeto. A imagem contém um barcode PDF417 com exatamente 4 colunas e 9 linhas, renderizado com módulos de 2 pixels.

### Exemplo completo executável

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Saída esperada** (console):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Abra o arquivo PNG e você verá um barcode PDF417 limpo pronto para leitura.

## Como gerar barcode com dados diferentes

Se você precisar **gerar barcode** para outra string, basta substituir o segundo argumento do construtor `BarcodeGenerator`:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Os mesmos passos de configuração (tamanho do módulo, linhas, colunas) se aplicam, permitindo reutilizar o código para múltiplas cargas úteis.

## Como alterar linhas dinamicamente com base no comprimento do conteúdo

Às vezes, o número de linhas deve se adaptar ao comprimento do texto codificado. Você pode calcular uma contagem segura de linhas antes de criar o gerador:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Este trecho garante que você nunca solicite menos de três linhas (mínimo da biblioteca) enquanto aumenta para dados mais longos.

## Como configurar barcode para diferentes formatos de imagem

Embora o tutorial se concentre em PNG, você pode mudar para JPEG, BMP ou TIFF alterando a enum `BarCodeImageFormat`:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG continua sendo a melhor escolha para qualidade sem perdas, especialmente quando o barcode será impresso.

## Armadilhas comuns e solução de problemas

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| Barcode aparece borrado | Dimensão X muito grande ou redimensionamento da imagem após salvar | Mantenha `XDimension.Pixels` ≤ 3 para uso em tela, ou aumente a escala com um formato vetorial (PDF) |
| Scanner não consegue ler o barcode | Poucas linhas para o comprimento dos dados | Aumente `Pdf417.Rows` ou deixe a biblioteca dimensionar automaticamente omitindo a configuração explícita de linhas |
| `ArgumentOutOfRangeException` on save | Diretório de saída não existe | Garanta que `outputPath` aponte para uma pasta válida ou crie-a com `Directory.CreateDirectory` |

## Resumo

Este tutorial demonstrou como **criar barcode PNG** arquivos em C# usando a simbologia PDF417. Você aprendeu:

- **Como gerar barcode** com a classe `BarcodeGenerator`  
- **Como alterar linhas** e colunas para controlar o layout  
- **Como configurar barcode** configurações como tamanho do módulo e formato da imagem  
- Como **gerar PDF417 barcode** e salvá-lo como uma imagem PNG

Agora você tem um bloco de código reutilizável que pode adaptar para diferentes cargas de dados, formatos de imagem ou requisitos de layout.

## Próximos passos

- Experimente `Pdf417.ErrorCorrectionLevel` para melhorar a confiabilidade da leitura em impressões de baixa qualidade.  
- Combine múltiplos barcodes em um único PDF usando Aspose.PDF para geração em lote de etiquetas.  
- Explore outras simbologias (`EncodeTypes.Code128`, `EncodeTypes.QR`) trocando o valor da enum — isso está alinhado com a palavra‑chave secundária **generate pdf417 barcode** enquanto demonstra capacidades mais amplas.

Feliz codificação, e aproveite criar barcodes PNG nítidos para cada aplicação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar barcode PDF417 e exportar PNG em C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [Como gerar barcodes PDF417 em C# com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Como criar barcode PNG com proporção personalizada em C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}