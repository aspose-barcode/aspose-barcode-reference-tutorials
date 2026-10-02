---
category: general
date: 2026-10-02
description: Crie código de barras a partir de texto em C# usando Aspose.BarCode.
  Aprenda como gerar código de barras PDF417 e veja como gerar código de barras PDF417
  em modo compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: pt
lastmod: 2026-10-02
og_description: Crie código de barras a partir de texto em C# com Aspose.BarCode.
  Este guia mostra como gerar código de barras PDF417 e como gerar código de barras
  PDF417 em modo compacto.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Criar código de barras a partir de texto em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Como criar código de barras a partir de texto em C# com Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras a partir de texto em C# com Aspose.BarCode

Se você precisa **criar código de barras a partir de texto** em uma aplicação .NET, este guia o conduzirá por todo o processo. Você verá um exemplo pronto‑para‑executar que **gera código de barras PDF417** e também responde **como gerar código de barras PDF417** em um layout compacto.

Gerar um código de barras programaticamente elimina etapas manuais e garante consistência em todos os documentos. Ao final deste tutorial você terá um arquivo PNG contendo um código de barras PDF417 que pode ser incorporado em faturas, ingressos ou cartões de identidade.

## O que você precisará

- .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7.2+)
- Visual Studio 2022 ou qualquer editor que suporte C#
- Uma licença NuGet para **Aspose.BarCode for .NET** (uma avaliação gratuita funciona para testes)

> **Dica profissional:** Adicione o pacote NuGet via CLI para manter o projeto limpo:  
> `dotnet add package Aspose.BarCode`

## Etapa 1: Configurar um projeto de console

Crie uma nova aplicação de console e faça referência à biblioteca Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

O comando `dotnet new console` gera um arquivo `Program.cs` que substituiremos pelo exemplo completo abaixo.

## Etapa 2: Como criar código de barras a partir de texto – código principal

Abra o `Program.cs` e substitua seu conteúdo pelo código a seguir. Cada linha está comentada para explicar por que existe.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Por que cada configuração importa

| Configuração | Propósito |
|--------------|-----------|
| `EncodeTypes.Pdf417` | Seleciona a simbologia PDF417, que pode armazenar grandes quantidades de dados em uma matriz bidimensional. |
| `XDimension.Pixels = 2` | Controla a largura de cada módulo; um valor de 2 pixels equilibra legibilidade e tamanho do arquivo. |
| `Pdf417.Columns = 3` | Reduz o número de colunas, tornando o código de barras mais compacto sem perder dados. |
| `Pdf417.Truncate = true` | Ativa o modo compacto, removendo preenchimento desnecessário e encurtando o código de barras. |
| `BarCodeImageFormat.Png` | PNG preserva qualidade sem perdas, ideal para processamento adicional ou impressão. |

## Etapa 3: Gerar código de barras PDF417 – executando o exemplo

Compile e execute o projeto:

```bash
dotnet run
```

Quando a execução terminar você verá:

```
Barcode saved to CompactPdf417.png
```

Abra `CompactPdf417.png` para visualizar o resultado. A imagem contém um código de barras PDF417 que codifica a string **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: criar código de barras a partir de texto – código de barras PDF417 salvo como PNG*

## Etapa 4: Como gerar código de barras PDF417 com correção de erro personalizada (opcional)

Se o seu ambiente de leitura for ruidoso, você pode aumentar o nível de correção de erro:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Aumentar o nível de erro torna o código de barras maior, mas melhora a resistência a danos.

## Etapa 5: Armadilhas comuns e tratamento de casos extremos

1. **Caracteres inválidos** – PDF417 suporta Unicode, mas alguns leitores mais antigos podem rejeitar símbolos não‑ASCII. Teste com o hardware alvo.  
2. **Permissões de caminho de arquivo** – Certifique‑se de que o diretório onde você grava seja gravável; caso contrário, `Save` lança uma `UnauthorizedAccessException`.  
3. **Tamanho da imagem** – Valores muito altos de `XDimension` produzem arquivos PNG grandes. Mantenha o tamanho em pixels entre 1 e 4 para a maioria dos cenários de exibição em tela.

## Recapitulação

Agora você sabe como **criar código de barras a partir de texto** em C# usando Aspose.BarCode, como **gerar código de barras PDF417** com um layout compacto, e os passos exatos para **como gerar código de barras PDF417** com configurações personalizadas. O código completo e executável acima pode ser copiado para qualquer projeto .NET e adaptado a diferentes entradas de texto ou formatos de saída (por exemplo, JPEG, BMP).

## Próximos passos

- Explore outras simbologias como QR Code ou Code128 alterando `EncodeTypes`.  
- Integre o PNG gerado em um PDF usando Aspose.PDF para criação de documentos de ponta a ponta.  
- Experimente `generator.Parameters.Barcode.Pdf417.Rows` para controlar a densidade vertical.

Sinta‑se à vontade para modificar o exemplo, incorporar o código de barras em suas próprias aplicações e compartilhar seus resultados com a comunidade. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 em C# – exemplo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Como criar código de barras PDF417 em C# com modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Como gerar código de barras PDF417 em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}