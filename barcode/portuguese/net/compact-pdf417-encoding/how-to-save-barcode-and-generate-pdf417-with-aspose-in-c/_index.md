---
category: general
date: 2026-09-29
description: Como salvar código de barras usando Aspose.BarCode em C# e aprender a
  gerar PDF417 com metadados de macro. Siga o guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: pt
lastmod: 2026-09-29
og_description: Como salvar código de barras usando Aspose.BarCode em C# é simples.
  Este tutorial mostra como gerar PDF417 com metadados de macro e definir todos os
  parâmetros necessários.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Como salvar código de barras com Aspose – Guia de geração PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Como salvar código de barras e gerar PDF417 com Aspose em C#
url: /pt/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como salvar código de barras e gerar PDF417 com Aspose em C#

Salvar código de barras usando Aspose.BarCode em C# é uma necessidade comum quando você precisa incorporar dados em um arquivo de imagem. Este guia orienta você através do processo completo de geração de um código de barras PDF417 com macro‑metadata e salvamento do resultado como uma imagem PNG. Ao final, você saberá **como gerar PDF417**, **como definir opções do PDF417** e, mais importante, **como salvar arquivos de código de barras** programaticamente.

Você verá um exemplo completo e executável que cobre cada passo — desde a adição do pacote NuGet Aspose.BarCode até a configuração dos campos macro, como ID do arquivo, contagem de segmentos e checksum. Nenhuma documentação externa é necessária; o código pode ser copiado para um novo projeto de console e executado imediatamente. O tutorial assume que você tem o Visual Studio 2022 (ou posterior) e o .NET 6.0 instalados.

## Pré-requisitos

- .NET 6.0 SDK (ou qualquer versão .NET suportada pelo Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code ou sua IDE C# preferida
- **Aspose.BarCode for .NET** pacote NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Conhecimento básico de sintaxe C# e aplicações console

> **Dica profissional:** Use a licença de avaliação gratuita para desenvolvedores da Aspose se ainda não possuir uma licença comercial. A avaliação funciona sem alterações no código.

## Como salvar código de barras – exemplo completo

O código a seguir cria um código de barras **Macro PDF417**, preenche todos os campos macro e salva a imagem como `ExtPDF417Meta.png`. Todas as diretivas `using` necessárias estão incluídas para que você possa colar o trecho diretamente em `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Por que cada passo importa

1. **Criando o gerador** – O construtor `BarcodeGenerator` recebe o tipo de código de barras (`EncodeTypes.MacroPdf417`) e os dados a codificar. Macro PDF417 é uma variante especial que transporta informações de transferência de arquivos, por isso preenchemos os campos macro posteriormente.
2. **Configurações de aparência** – `XDimension.Pixels` controla a largura da barra estreita; ajustá-lo altera o tamanho geral da imagem sem afetar a integridade dos dados. `Pdf417.Columns` define o layout da matriz do código de barras.
3. **Metadados macro** – Essas propriedades (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) são essenciais quando você precisa dividir um arquivo grande em múltiplos segmentos de código de barras. Defini‑las corretamente garante que um scanner possa reconstruir o arquivo original.
4. **Salvando a imagem** – O método `Save` grava o código de barras gerado no disco. Você pode escolher qualquer formato suportado (`Png`, `Jpeg`, `Bmp`, etc.). Esta linha demonstra a operação exata de **como salvar código de barras** solicitada.

> **Pergunta comum:** *E se eu precisar de um formato de imagem diferente?*  
> Altere `BarCodeImageFormat.Png` para `BarCodeImageFormat.Jpeg` (ou qualquer outro valor de enumeração suportado) e ajuste a extensão do arquivo conforme necessário.

## Como gerar PDF417 com metadados macro

Se você precisar apenas de um PDF417 regular (sem dados macro), pode pular a seção macro e manter o gerador básico:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

O código acima ilustra **como gerar PDF417** rapidamente. Observe que o enum `EncodeTypes.Pdf417` seleciona a versão sem macro.

## Como definir PDF417 – opções avançadas

Aspose.BarCode expõe muitos parâmetros específicos do PDF417. Aqui estão alguns que você pode precisar:

| Propriedade | Descrição | Valores típicos |
|-------------|-----------|-----------------|
| `Pdf417.Columns` | Número de colunas por linha | 1‑30 (default 3) |
| `Pdf417.Rows` | Número de linhas (calculado automaticamente se 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Nível de correção de erro (0‑8) | 2‑4 for balanced size/robustness |
| `Pdf417.RowsPerStrip` | Linhas por faixa para códigos de barras grandes | 0 (auto) |
| `Pdf417.Pdf417MacroFileID` | Identificador do arquivo ao usar macro | Any 32‑bit integer |

Definir esses valores segue o mesmo padrão mostrado na **Etapa 2** do exemplo principal. Ajuste‑os antes de chamar `Save`.

## Saída esperada

Executar o programa completo cria `ExtPDF417Meta.png` no diretório de trabalho do executável. A imagem contém um código de barras PDF417 de alta resolução com todos os campos macro incorporados. Escanear a imagem com um scanner compatível com PDF417 (ou um aplicativo móvel) retornará a string de dados original `"Åspóse.Barcóde©"` junto com os metadados macro (ID do arquivo, ID do segmento, etc.).

![Código de barras salvo como PNG – exemplo de como salvar código de barras](ExtPDF417Meta.png "Como salvar código de barras como PNG com metadados macro PDF417")

*Texto alternativo da imagem:* **como salvar código de barras como PNG com metadados macro PDF417** (corresponde à palavra‑chave principal).

## Conclusão

Neste tutorial você aprendeu **como salvar código de barras** usando Aspose.BarCode, **como gerar PDF417**, **como definir parâmetros do PDF417** e **como gerar código de barras com Aspose** para cenários regulares e habilitados para macro.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Como gerar imagem de código de barras PDF417 em C# com Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Como gerar código de barras em C# com Aspose.BarCode e adicionar metadados](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}