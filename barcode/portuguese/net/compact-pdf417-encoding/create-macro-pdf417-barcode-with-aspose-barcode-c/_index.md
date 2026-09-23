---
category: general
date: 2026-09-22
description: Crie código de barras macro PDF417 usando Aspose.BarCode em C#. Aprenda
  passo a passo como gerar o código de barras com Aspose, configurar metadados e salvar
  como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: pt
lastmod: 2026-09-22
og_description: Crie um código de barras macro PDF417 usando Aspose.BarCode em C#.
  Este guia mostra como gerar o código de barras com Aspose, definir os metadados
  da macro e exportar a imagem.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Criar código de barras macro PDF417 com Aspose.BarCode (C#) – guia passo
  a passo
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Criar código de barras macro PDF417 com Aspose.BarCode (C#)
url: /pt/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar macro PDF417 barcode com Aspose.BarCode (C#)

Se você precisar **criar código de barras macro PDF417** em uma aplicação .NET, este tutorial mostra exatamente como fazer isso com Aspose.BarCode. Você verá um exemplo completo e executável que **gera código de barras com Aspose**, configura todos os campos específicos da macro e salva o resultado como uma imagem PNG.

Códigos de barras são frequentemente usados para inventário, envio ou rastreamento de documentos, e a variante Macro PDF417 permite incorporar metadados adicionais ao nível de arquivo dentro do próprio código de barras. Ao final deste guia, você será capaz de gerar um código de barras macro PDF417 completo que está em conformidade com o padrão ISO/IEC 15438.

## O que você precisará

* .NET 6.0 SDK ou posterior (o código funciona com .NET Core e .NET Framework)
* Visual Studio 2022 (ou qualquer IDE C#)
* Uma conexão à internet compatível com NuGet para baixar o pacote Aspose.BarCode
* Familiaridade básica com a sintaxe C#

Esses pré-requisitos garantem que o código compile sem configuração adicional.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

A biblioteca Aspose.BarCode fornece a classe `BarcodeGenerator` usada ao longo deste tutorial.

```bash
dotnet add package Aspose.BarCode
```

Executar o comando adiciona a versão estável mais recente ao seu arquivo de projeto (`*.csproj`). O pacote inclui suporte para PDF417, Macro PDF417 e muitas outras simbologias.

## Etapa 2: Criar um novo projeto de console (opcional)

Se preferir começar do zero, gere um aplicativo de console:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

O `Program.cs` gerado hospedará o código de geração do código de barras.

## Etapa 3: Inicializar o gerador de código de barras

O gerador é criado com o valor enum `EncodeTypes.MacroPdf417` e o texto que você deseja codificar. O Aspose.BarCode lida automaticamente com caracteres Unicode, portanto você pode incluir letras acentuadas ou símbolos diretamente.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Por que isso importa
`EncodeTypes.MacroPdf417` indica à biblioteca para usar a versão macro do PDF417, que adiciona a capacidade de incorporar metadados ao nível de arquivo (ID do arquivo, contagem de segmentos, etc.). O texto `"Åspóse.Barcóde©"` demonstra que o gerador codifica corretamente caracteres UTF‑8.

## Etapa 4: Definir dimensões básicas do código de barras

O PDF417 permite controlar o número de colunas e a dimensão X (a largura de um único módulo). Ajustar esses valores influencia o tamanho físico do código de barras e a confiabilidade da leitura.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Valores menores produzem um código de barras mais denso; valores maiores facilitam a leitura por scanners de baixa resolução.
* **Columns** – Controla o número de colunas de dados; valores típicos variam de 1 a 30.

## Etapa 5: Configurar metadados Macro PDF417

O Macro PDF417 contém campos adicionais que descrevem o arquivo que o código de barras representa. Cada campo é opcional, mas configurá‑los melhora a interoperabilidade com scanners que compreendem o formato macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Explicação de cada campo

| Propriedade | Propósito | Faixa típica |
|-------------|-----------|--------------|
| **MacroPdf417FileID** | Identificador único para o arquivo lógico que pode ser dividido em vários códigos de barras. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Índice do segmento atual (começa em 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Número total de segmentos que compõem o arquivo completo. | 1‑99 |
| **MacroPdf417FileName** | Nome legível do arquivo. | Até 255 caracteres |
| **MacroPdf417Checksum** | Checksum opcional para detecção de erros. | 0‑65535 |
| **MacroPdf417FileSize** | Tamanho do arquivo original em bytes. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Carimbo de data/hora da criação ou modificação do arquivo. | Qualquer `DateTime` |
| **MacroPdf417Addressee** | Identificador do destinatário (ex.: departamento ou máquina). | String livre |
| **MacroPdf417Sender** | Identificador da origem (ex.: nome da empresa). | String livre |
| **MacroPdf417Terminator** | Indica se este segmento é o último. | `Set` ou `Unset` |

**Dica profissional:** Se você dividir um arquivo grande em vários códigos de barras, garanta que o `SegmentID` de cada segmento seja sequencial e que `SegmentsCount` permaneça constante em todos os segmentos. Os scanners dependem desses valores para reconstruir o arquivo original.

## Etapa 6: Salvar a imagem do código de barras

O Aspose.BarCode suporta muitos formatos de saída (PNG, JPEG, BMP, SVG, etc.). PNG oferece qualidade sem perdas, o que é ideal para testes e documentação.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Executar o programa cria um arquivo chamado `ExtPDF417Meta.png` no diretório de saída do projeto (`bin/Debug/net6.0/`). Abra a imagem com qualquer visualizador para verificar se o código de barras foi renderizado corretamente.

## Etapa 7: Verificar o código de barras gerado (opcional)

Se você possui um aplicativo de scanner PDF417 (mobile ou desktop), escaneie o PNG salvo. O scanner deve retornar:

* O texto codificado `"Åspóse.Barcóde©"`
* Todos os campos macro que você configurou (ID do arquivo, ID do segmento, etc.)

Para verificação automatizada, o Aspose.BarCode também oferece a classe `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Este trecho demonstra como ler de volta os metadados macro programaticamente, confirmando que **gerar código de barras com Aspose** funciona de ponta a ponta.

## Casos limites e boas práticas

| Situação | Manipulação recomendada |
|----------|--------------------------|
| **Caracteres Unicode** | Garanta que a string de origem seja UTF‑8 (padrão no .NET). O Aspose.BarCode codifica Unicode automaticamente, mas verifique o conjunto de caracteres do scanner. |
| **Tamanho de arquivo grande** | O Macro PDF417 divide arquivos em até 99 segmentos. Se o arquivo exceder 400 KB, aumente `SegmentsCount` e gere vários códigos de barras, cada um com um `SegmentID` sequencial. |
| **Precisão do timestamp** | Use `DateTime.UtcNow` para tempo universal; alguns scanners esperam UTC. |
| **Validação de checksum** | Forneça um checksum correto se você planeja validar a integridade no lado receptor. |
| **Formatos de imagem diferentes** | Use `BarCodeImageFormat.Svg` para gráficos vetoriais quando precisar de códigos de barras escaláveis infinitamente. |
| **Desempenho** | Reutilize uma única instância de `BarcodeGenerator` ao gerar muitos códigos de barras; altere apenas os `Parameters` entre as iterações. |

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar, colar e executar sem modificações (desde que o pacote NuGet esteja instalado).



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Exemplo de código de barras Aspose: gerar Macro PDF417 em C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Criar metadados de código de barras PDF417 em C# – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Como gerar imagem de código de barras PDF417 em C# com Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}