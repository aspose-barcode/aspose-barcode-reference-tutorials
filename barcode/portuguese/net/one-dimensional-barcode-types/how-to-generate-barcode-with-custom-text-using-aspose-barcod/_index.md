---
category: general
date: 2026-10-28
description: Como gerar código de barras com texto personalizado usando Aspose.BarCode
  – guia passo a passo para desenvolvedores .NET criarem imagens de código de barras
  Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: pt
lastmod: 2026-10-28
og_description: Como gerar código de barras com texto personalizado em .NET usando
  Aspose.BarCode. Siga este guia completo para criar e salvar um código de barras
  Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Como gerar código de barras com texto personalizado – tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Como gerar código de barras com texto personalizado usando Aspose.BarCode para
  .NET
url: /pt/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras com texto personalizado usando Aspose.BarCode para .NET

Gerar código de barras com texto personalizado é uma necessidade frequente quando você precisa incorporar identificadores, timestamps ou outros metadados diretamente em um código visual. Este tutorial mostra como gerar um código de barras Macro PDF417 que contém texto personalizado e um conjunto completo de metadados, usando a biblioteca **Aspose.BarCode** para .NET.

Você aprenderá como configurar o gerador, aplicar texto personalizado, definir campos específicos do Macro PDF417 e salvar o resultado como uma imagem PNG. Nenhuma ferramenta externa é necessária — apenas o pacote NuGet Aspose.BarCode e um ambiente de desenvolvimento .NET.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* Pacote NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Esses pré‑requisitos garantem que o código compile e execute sem configuração adicional.

## Etapa 1: Instalar o pacote Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente do Aspose.BarCode ao seu projeto, dando acesso à classe `BarcodeGenerator` e a todos os parâmetros relacionados.

## Etapa 2: Criar um novo aplicativo console

Crie um aplicativo console mínimo que hospedará a lógica de geração do código de barras:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Por que cada linha importa

* **EncodeTypes.MacroPdf417** – seleciona a simbologia Macro PDF417, que suporta dados segmentados e metadados.  
* **XDimension.Pixels** – controla o tamanho de cada módulo; um valor de 2 pixels produz uma imagem clara e escaneável.  
* **Pdf417.Columns** – reduz a largura geral, tornando o código de barras mais compacto para etiquetas impressas.  
* **MacroPdf417* properties** – incorporam informações ao nível de arquivo (ID, contagem de segmentos, timestamps, etc.) diretamente no código de barras. Essa capacidade é exclusiva do Macro PDF417 e costuma ser usada em logística ou sistemas de gerenciamento de documentos.  
* **Save(..., BarCodeImageFormat.Png)** – grava um arquivo PNG sem perdas, preservando as bordas nítidas do código de barras para leitura confiável.

## Etapa 3: Executar o programa e verificar a saída

Compile e execute o aplicativo console:

```bash
dotnet run
```

O programa cria `ExtPDF417Meta.png` no diretório de trabalho do projeto. Ao abrir o arquivo, você verá um código de barras Macro PDF417 que codifica o texto **“Åspóse.Barcóde©”** juntamente com os metadados fornecidos.

**Saída esperada** – uma imagem PNG semelhante à mostrada abaixo:

![exemplo de saída de como gerar código de barras imagem PNG mostrando um código de barras Macro PDF417](ExtPDF417Meta.png)

*O texto alternativo da imagem (“exemplo de saída de como gerar código de barras imagem PNG”) reforça a palavra‑chave principal para acessibilidade e SEO.*

## Variações comuns e casos de borda

### Usando um tipo de código de barras diferente

Se precisar **gerar código de barras texto personalizado** para um QR code em vez de Macro PDF417, substitua `EncodeTypes.MacroPdf417` por `EncodeTypes.QR`. A estrutura dos demais parâmetros permanece a mesma, mas códigos QR não suportam campos de metadados Macro.

### Manipulando caracteres Unicode

O exemplo já inclui caracteres Unicode (`Å`, `ó`, `©`). Aspose.BarCode lida com entrada UTF‑8 nativamente, mas você deve garantir que o arquivo‑fonte esteja salvo com codificação UTF‑8 para evitar avisos de compilação.

### Salvando em outros formatos de imagem

Aspose.BarCode suporta BMP, JPEG, TIFF e SVG além de PNG. Altere o valor do enum `BarCodeImageFormat` conforme necessário:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Conjuntos de dados grandes

Macro PDF417 pode dividir dados em vários segmentos. Quando o texto ultrapassa a capacidade de um único segmento, incremente `MacroPdf417SegmentID` e mantenha `MacroPdf417SegmentsCount` consistente em todas as partes geradas. Essa abordagem é essencial para cenários **create barcode aspose** onde a carga útil é maior que um único código de barras pode conter.

### Tratamento de erros

Envolva a lógica de geração em um bloco try‑catch para expor problemas em tempo de execução, como caminhos de arquivo inválidos ou caracteres não suportados:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Dicas avançadas para geração confiável de códigos de barras

* **Valide o código de barras** após a criação usando `BarCodeReader`. Esta etapa extra confirma que os dados codificados correspondem às suas expectativas.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Mantenha a X‑dimension entre 2 – 4 pixels** para a maioria dos scanners. Valores menores podem gerar imagens ilegíveis em dispositivos de baixa resolução.

* **Evite nomes de arquivo muito longos** em `MacroPdf417FileName`. A especificação limita o campo a 32 caracteres.

* **Use timestamps consistentes** (UTC) ao gerar múltiplos segmentos para simplificar o processamento posterior.

## Conclusão

Agora você sabe **como gerar código de barras** com texto personalizado usando Aspose.BarCode para .NET, como configurar metadados Macro PDF417 e como salvar o resultado como uma imagem PNG. O exemplo completo e executável demonstra cada passo necessário — desde a instalação do pacote NuGet até o tratamento de caracteres Unicode e a gravação da saída.

A partir daqui, você pode:

* **Gerar código de barras texto personalizado** para outras simbologias (QR, DataMatrix, etc.)  
* **Criar fluxos de trabalho Create barcode Aspose** que processam em lote milhares de imagens  
* Integrar o código de geração de código de barras em serviços ASP.NET Core, serviços Windows ou Azure Functions  

Experimente diferentes parâmetros, explore campos de metadados adicionais e incorpore o código de barras em seus pipelines de automação de documentos. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}