---
category: general
date: 2026-08-12
description: Gere código de barras Aspose com Aspose.BarCode e aprenda como gerar
  PDF417 com texto personalizado em alguns passos fáceis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: pt
lastmod: 2026-08-12
og_description: Gerar código de barras Aspose usando Aspose.BarCode. Este tutorial
  mostra como gerar PDF417 com texto personalizado, metadados de macro e salvar o
  resultado como PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Gerar código de barras aspose – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Gerar código de barras Aspose – guia completo em C#
url: /pt/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras aspose – guia completo em C#

Se você precisa **gerar código de barras aspose** para um símbolo MacroPdf417, este tutorial o guiará por todo o processo. Você verá como configurar opções específicas de macro, incorporar texto personalizado e salvar o código de barras como imagem PNG.

Gerar um código de barras com Aspose.BarCode elimina cálculos manuais e garante conformidade com a especificação PDF417. Nas etapas abaixo, você também aprenderá **como gerar pdf417** com metadados personalizados, como ID do arquivo, contagem de segmentos e timestamps. Ao final do guia, você terá um exemplo de código pronto para uso que pode ser inserido em qualquer projeto .NET.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior (o código também funciona com .NET Framework 4.7+)
* Uma licença válida do Aspose.BarCode para .NET (a avaliação gratuita funciona para testes)
* Visual Studio 2022 ou qualquer IDE C# de sua preferência
* Familiaridade básica com a sintaxe C# e conceitos de orientação a objetos

Nenhum pacote NuGet adicional é necessário além do **Aspose.BarCode**.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra seu projeto no Visual Studio e execute o seguinte comando no Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém a classe `BarcodeGenerator` usada ao longo deste tutorial.

## Etapa 2: Criar um gerador de código de barras para MacroPdf417

A primeira linha cria uma instância de `BarcodeGenerator` que tem como alvo a simbologia **MacroPdf417** e incorpora o texto personalizado que você deseja codificar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Por que isso importa*: O enum `EncodeTypes.MacroPdf417` indica ao Aspose que o código de barras deve ser tratado como um símbolo PDF417 habilitado para macro, o que permite dividir grandes volumes de dados em vários segmentos. A string `"Åspóse.Barcóde©"` demonstra que o gerador lida corretamente com caracteres Unicode.

## Etapa 3: Definir o tamanho básico do módulo

O tamanho do módulo controla a densidade visual do código de barras. Um valor de pixel `2` gera uma imagem nítida que imprime bem em impressoras de etiquetas padrão.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Aumentar o valor torna o código de barras maior, enquanto diminuí‑lo pode causar problemas de leitura em dispositivos de baixa resolução.

## Etapa 4: Configurar opções de layout específicas do macro PDF417

MacroPdf417 requer vários parâmetros adicionais. Essas configurações permitem dividir os dados em múltiplos arquivos, identificar cada segmento e verificar a integridade.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Por que isso importa*: A propriedade `Columns` influencia a largura do código de barras, enquanto os campos de macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permitem que sistemas downstream remontem os dados originais corretamente.

## Etapa 5: Adicionar metadados de macro adicionais

Aspose.BarCode permite incorporar campos de macro opcionais, como checksum, tamanho do arquivo, timestamp e informações de remetente/destinatário. Esses campos são úteis para trilhas de auditoria e detecção de erros.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Por que isso importa*: O checksum protege contra erros de transmissão, enquanto o timestamp e os campos de remetente fornecem contexto para o processamento posterior. Definir `MacroPdf417Terminator` como `Set` sinaliza que este é o segmento final da série de macro.

## Etapa 6: Salvar o código de barras como imagem PNG

Por fim, grave o código de barras gerado no disco. PNG preserva qualidade sem perdas, o que é ideal para leitura.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Quando o código terminar, o arquivo `ExtPDF417Meta.png` conterá um código de barras MacroPdf417 de alta resolução que codifica o texto personalizado e todos os metadados de macro.

### Saída esperada

Abrir `ExtPDF417Meta.png` mostra um código de barras orientado verticalmente com linhas e colunas claramente definidas. Ler a imagem com qualquer leitor PDF417 devolve a string original **Åspóse.Barcóde©** e os campos de macro configurados (ID do arquivo, ID do segmento, checksum, etc.).

## Como gerar pdf417 sem opções de macro (cenário alternativo)

Se você precisar apenas de um código de barras PDF417 padrão, omita as propriedades de macro e mantenha a configuração básica:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Este trecho demonstra **como gerar pdf417** rapidamente quando a funcionalidade de macro não é necessária.

## Armadilhas comuns e dicas avançadas

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| Código de barras muito pequeno para leitura | X‑dimension definido como 1 pixel ou colunas muito altas | Use ao menos `2` pixels para `XDimension` e mantenha colunas entre `3` e `9` para tamanhos típicos de etiquetas |
| Caracteres Unicode aparecem como � | Incompatibilidade de codificação no arquivo do projeto | Garanta que o arquivo do projeto esteja salvo como UTF‑8 e que o arquivo‑fonte contenha o BOM correto |
| Campos de macro são ignorados pelo scanner | `MacroPdf417Terminator` não definido para o último segmento | Defina `MacroPdf417Terminator = Pdf417MacroTerminator.Set` no segmento final |
| Arquivo de imagem corrompido | Stream de saída não fechado corretamente | Use a instrução `using` (conforme mostrado) para garantir a liberação do gerador |

## Exemplo completo e executável

Copie o código a seguir para uma nova aplicação console e execute-o. O programa cria o código de barras, salva‑o e exibe o caminho de saída no console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Executar o programa exibe uma linha semelhante a:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abra o arquivo para verificar a saída visual.

## Conclusão

Agora você sabe como **gerar código de barras aspose** para a simbologia MacroPdf417, incorporar texto Unicode personalizado, configurar metadados de macro e exportar o resultado como imagem PNG. O mesmo padrão permite que você **como gerar pdf417** sem opções de macro, e pode adaptar o código para outros formatos de código de barras suportados pelo Aspose.BarCode.

Em seguida, explore tópicos relacionados, como **criar código de barras texto personalizado** para QR codes, adicionar filtros de cor com parâmetros `Color` ou incorporar códigos de barras diretamente em documentos PDF usando Aspose.PDF. Experimente diferentes valores de `XDimension` e contagens de colunas para ajustar finamente o código de barras ao seu impressor ou scanner específico.

Bom desenvolvimento e aproveite a confiabilidade que o Aspose.BarCode traz às suas soluções de código de barras .NET!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}