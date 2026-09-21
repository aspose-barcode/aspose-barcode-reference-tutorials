---
category: general
date: 2026-08-09
description: Exemplo de código de barras Aspose mostrando como usar um gerador de
  código de barras C# para criar um Macro PDF417 com suporte total a metadados.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: pt
lastmod: 2026-08-09
og_description: O exemplo de código de barras Aspose demonstra o uso de um gerador
  de código de barras C# para produzir um código de barras Macro PDF417 que inclui
  ID do arquivo, dados de segmento, carimbo de data/hora e outros metadados.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Exemplo de código de barras Aspose – criar Macro PDF417 com C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Exemplo de código de barras Aspose: gerar Macro PDF417 em C#'
url: /pt/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo Aspose Barcode: gerar Macro PDF417 em C#

Se você precisa de um **exemplo Aspose Barcode** que cria um código de barras Macro PDF417, este guia mostra como fazer isso com um **gerador de código de barras C#**. Você verá todas as configurações necessárias, desde dimensões básicas até o conjunto completo de campos de metadados Macro PDF417, e terminará com uma imagem PNG pronta para processamento posterior.

O tutorial cobre todo o fluxo de trabalho, explica por que cada parâmetro é importante e fornece um exemplo de código pronto‑para‑executar. Nenhuma referência externa é necessária; basta copiar o código, ajustar os valores e executá‑lo imediatamente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 (ou superior) instalado  
- Visual Studio 2022 ou qualquer IDE compatível com C#  
- Uma licença válida para **Aspose.BarCode for .NET** (a versão de avaliação gratuita funciona para este exemplo)  

Adicione o pacote NuGet Aspose.BarCode ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Criar a instância do gerador de código de barras C#

O primeiro passo é instanciar `BarcodeGenerator` com o valor enum `EncodeTypes.MacroPdf417` e o texto que você deseja codificar. O texto pode conter caracteres Unicode, que a biblioteca trata automaticamente.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Por que isso importa*: `EncodeTypes.MacroPdf417` indica ao motor que ele deve produzir um símbolo Macro PDF417, que suporta dados segmentados e metadados adicionais ao nível de arquivo. A instrução `using` garante que recursos não gerenciados sejam liberados após a imagem ser salva.

## Etapa 2: Definir a aparência básica do código de barras

Um código de barras Macro PDF417 consiste em módulos quadrados. Controlar o tamanho do módulo e a contagem de colunas influencia tanto a legibilidade quanto o tamanho do arquivo.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Por que isso importa*: `XDimension.Pixels` determina a densidade visual; um valor de 2 pixels funciona bem para exibição em tela enquanto mantém a imagem pequena. Ajuste a contagem de colunas para atender às restrições do seu layout—mais colunas criam um código de barras mais largo e mais curto.

## Etapa 3: Definir os metadados específicos do Macro PDF417

Macro PDF417 estende o formato padrão PDF417 com campos que permitem a reconstrução de arquivos grandes a partir de múltiplos segmentos de código de barras. Cada campo é opcional, mas configurá‑los demonstra todo o potencial da API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Por que isso importa*:  
- `MacroPdf417FileID` vincula todos os segmentos que pertencem ao mesmo arquivo lógico.  
- `MacroPdf417SegmentID` e `MacroPdf417SegmentsCount` permitem que o decodificador reordene os fragmentos corretamente.  
- `MacroPdf417Checksum` fornece uma verificação rápida de integridade sem decodificar todo o payload.  
- `MacroPdf417FileSize` e `MacroPdf417TimeStamp` permitem que sistemas posteriores verifiquem se o arquivo reconstruído corresponde ao original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` são úteis em cenários de logística ou troca de documentos.  
- Definir `MacroPdf417Terminator` como `Set` marca este código de barras como o segmento final, o que simplifica o algoritmo de reconstrução.

## Etapa 4: Salvar a imagem do código de barras gerado

Por fim, grave o código de barras em um arquivo PNG. Você pode escolher qualquer formato suportado (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Por que isso importa*: PNG preserva os dados de pixel sem perdas, garantindo que os scanners leiam exatamente o padrão de módulos que você configurou. Alterar o formato pode afetar a qualidade visual e o tamanho do arquivo.

### Saída esperada

Executar o programa completo cria um arquivo chamado **ExtPDF417Meta.png**. Ao abrir a imagem, você verá um código de barras Macro PDF417 retangular com o texto “Åspóse.Barcóde©” codificado, e a densidade visual corresponde à dimensão X de 2 pixels que você definiu. Escanear a imagem com um leitor compatível com PDF417 retorna todos os campos de metadados definidos na Etapa 3.

## Exemplo completo em funcionamento

Copie o código abaixo para um novo projeto de console (`dotnet new console`) e substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo que exista na sua máquina.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Execute o programa (`dotnet run`). Após a execução, verifique se o arquivo PNG aparece no local especificado. Use qualquer aplicativo de leitura de código de barras que suporte Macro PDF417 para confirmar que os metadados foram incorporados corretamente.

## Variações comuns e casos de borda

- **Formatos de imagem diferentes**: Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Tiff` se seu sistema posterior preferir outro formato.  
- **Alterar o tamanho do módulo**: Valores maiores de `XDimension.Pixels` melhoram a confiabilidade de leitura em scanners de baixa resolução, mas aumentam o tamanho da imagem.  
- **Múltiplos segmentos**: Para gerar um arquivo de vários segmentos, crie uma série de códigos de barras, incremente `MacroPdf417SegmentID` para cada um e mantenha `MacroPdf417FileID` constante. Apenas o último segmento deve ter `MacroPdf417Terminator` definido.  
- **Suporte a Unicode**: O gerador codifica automaticamente caracteres Unicode; assegure‑se de que sua string de origem use codificação UTF‑8 se você a ler de um arquivo externo.  
- **Tratamento de erros**: Envolva o bloco `using` em um try‑catch para capturar `BarCodeException` em caso de parâmetros inválidos (por exemplo, contagem de colunas fora do intervalo).

## Dicas avançadas

- **Desempenho**: Reutilize uma única instância de `BarcodeGenerator` ao criar muitos códigos de barras com as mesmas configurações; altere apenas a propriedade `CodeText` entre as gravações.  
- **Estimativa de tamanho de arquivo**: O campo `MacroPdf417FileSize` deve corresponder à contagem de bytes do payload original; divergências podem causar falhas de validação em sistemas posteriores.  
- **Testes**: Valide os códigos de barras gerados tanto com o decodificador interno da Aspose (`BarCodeReader`) quanto com um scanner de terceiros para garantir interoperabilidade.

## Conclusão

Este **exemplo Aspose Barcode

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}