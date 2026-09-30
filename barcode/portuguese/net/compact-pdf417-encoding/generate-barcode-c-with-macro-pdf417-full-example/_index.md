---
category: general
date: 2026-08-19
description: Gerar código de barras C# usando Aspose.BarCode para criar um Macro PDF417
  com texto personalizado e salvar como um arquivo de imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: pt
lastmod: 2026-08-19
og_description: Gere código de barras em C# com Aspose.BarCode, aprenda a gerar PDF417,
  adicione texto personalizado e salve o arquivo de imagem do código de barras.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Gerar código de barras C# – Guia Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Gerar código de barras C# com Macro PDF417 – exemplo completo
url: /pt/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras C# com Macro PDF417 – exemplo completo

Se você precisa **gerar código de barras C#** no formato Macro PDF417, este guia mostra uma solução pronta‑para‑executar. Você verá **como gerar pdf417**, incorporar texto personalizado e **gerar arquivo de imagem do código de barras** em um único programa autônomo.

O tutorial cobre tudo, desde a instalação da biblioteca Aspose.BarCode até a configuração dos metadados do Macro PDF417, para que você possa copiar o código diretamente para o seu projeto e ver o resultado imediatamente.

## Pré‑requisitos

Antes de começar, verifique se você tem:

- .NET 6.0 SDK ou superior (o código também funciona com .NET Framework 4.7+)
- Visual Studio 2022 (ou qualquer IDE que suporte C#)
- Uma licença do Aspose.BarCode for .NET (a avaliação gratuita funciona para testes)
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** Instale o pacote NuGet via CLI para evitar incompatibilidades de versão:  
> `dotnet add package Aspose.BarCode`

## Etapa 1: Configurar o projeto e importar a biblioteca

Crie um novo aplicativo de console e adicione as diretivas `using` necessárias.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Por que esta etapa é importante:**  
O namespace `Aspose.BarCode.Generation` fornece a classe `BarcodeGenerator`, que é o ponto de entrada para criar qualquer tipo de código de barras, incluindo Macro PDF417. Importar `System` dá acesso ao `DateTime` para metadados de timestamp.

## Etapa 2: Criar um gerador Macro PDF417 com texto personalizado

Substitua o comentário marcador pelo código de inicialização do gerador. Isso demonstra **criar código de barras texto personalizado** ao mesmo tempo em que seleciona o tipo de codificação correto.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Explicação:**  
- `EncodeTypes.MacroPdf417` indica ao Aspose que deve produzir um código PDF417 que suporta recursos de macro (segmentação de arquivo, checksum etc.).  
- O texto `"Åspóse.Barcóde©"` mostra que caracteres Unicode são totalmente suportados, o que costuma ser necessário em aplicações internacionais.

## Etapa 3: Configurar a aparência e os metadados do Macro PDF417

Ajuste finamente as dimensões do código de barras e defina os campos específicos da macro necessários para o tratamento de arquivos segmentados.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Por que essas configurações são importantes:**

| Configuração | Finalidade |
|--------------|------------|
| `XDimension.Pixels` | Controla a densidade visual; 2 px produzem uma imagem clara e legível. |
| `Columns` | Determina quantas colunas de dados aparecem por linha, afetando o tamanho do código. |
| `MacroPdf417FileID` | Identifica de forma única o arquivo lógico entre todos os segmentos. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Permite a reconstrução do arquivo original a partir de múltiplos códigos de barras. |
| `MacroPdf417FileName` | Nome legível armazenado dentro do código para processamento posterior. |
| `MacroPdf417Checksum` | Fornece detecção de erros usando o algoritmo CRC‑16 CCITT. |
| `MacroPdf417FileSize` | Ajuda o decodificador a saber quando o arquivo completo foi recebido. |
| `MacroPdf417TimeStamp` | Registra quando o código de barras foi gerado, útil para auditoria. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Campos opcionais que podem ser usados em fluxos de trabalho empresariais. |
| `MacroPdf417Terminator` | Indica que este segmento é o final (`Set`). |

## Etapa 4: Salvar o código de barras como arquivo de imagem

Por fim, grave o código de barras em um arquivo PNG para que você possa visualizá‑lo ou incorporá‑lo em outro lugar.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**O que você verá:**  
Uma imagem PNG chamada `ExtPDF417Meta.png` contendo um código de barras Macro PDF417 que codifica o texto personalizado e todos os campos de metadados definidos acima. A imagem pode ser aberta com qualquer visualizador padrão ou inserida em PDFs, relatórios ou páginas web.

## Código‑fonte completo (pronto para copiar)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Saída esperada

Ao executar o programa, ele imprime:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Abrir `ExtPDF417Meta.png` mostra um código de barras Macro PDF417 limpo que é escaneado corretamente por qualquer leitor PDF417, preservando o texto personalizado `"Åspóse.Barcóde©"` e os metadados de macro que você definiu.

## Perguntas frequentes e casos de borda

- **Posso gerar em outro formato de imagem?**  
  Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`, conforme necessário.

- **E se meus dados excederem um único código de barras?**  
  O Macro PDF417 foi projetado para segmentação. Ajuste `MacroPdf417SegmentsCount` e `MacroPdf417SegmentID` para cada parte e, depois, concatene os resultados escaneados.

- **O suporte a Unicode é garantido?**  
  Aspose.BarCode oferece suporte total a Unicode. Certifique‑se de que seu arquivo‑fonte esteja salvo com codificação UTF‑8 para evitar corrupção de caracteres.

- **Preciso de licença para produção?**  
  Uma versão licenciada remove a marca d'água de avaliação e fornece funcionalidade completa. A avaliação funciona para testes e aprendizado.

## Conclusão

Agora você sabe como **gerar código de barras C#** para um Macro PDF417, **como gerar pdf417** com metadados avançados, **criar código de barras texto personalizado** e **gerar arquivo de imagem do código de barras** usando Aspose.BarCode. O exemplo completo e executável demonstra cada passo necessário — desde a configuração do projeto até a gravação da imagem PNG final.

### Próximos passos

- Experimente outras configurações do PDF417, como `ErrorCorrectionLevel` e `CompactPdf417`, para símbolos menores.  
- Integre o código de barras gerado em um relatório PDF usando Aspose.PDF.  
- Explore geração em lote: percorra uma coleção de arquivos e produza uma série de códigos de barras Macro PDF417 segmentados.

Sinta‑se à vontade para adaptar o código ao seu fluxo de trabalho e tornar a geração de códigos de barras uma parte fluida das suas aplicações C#. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui código completo e funcional com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}