---
category: general
date: 2026-10-05
description: Exemplo de gerador de código de barras em C# que mostra como gerar código
  de barras Planet e criar imagem de código de barras em C#. Siga este guia passo
  a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: pt
lastmod: 2026-10-05
og_description: Exemplo de gerador de código de barras em C# mostra como gerar código
  de barras planet e criar imagem de código de barras em C#. Obtenha uma solução completa
  e executável.
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: Exemplo de gerador de código de barras em C# – gere código de barras Planet
  rapidamente
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar um exemplo de gerador de código de barras em C# com simbologia Planet
url: /pt/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo de gerador de código de barras em C# – gerar código Planet e criar imagem de código de barras

Se você precisa de um **exemplo de gerador de código de barras** em C#, este guia mostra exatamente como gerar um código Planet e criar uma imagem de código de barras em C# em apenas algumas linhas de código. Você verá uma solução completa, pronta‑para‑executar, que pode ser inserida em qualquer projeto .NET.

Um código Planet é usado pelos serviços postais para codificar informações de roteamento. Ao final deste tutorial você entenderá por que a biblioteca determina automaticamente a altura do código de barras, como controlar a dimensão X e como salvar o resultado como um arquivo PNG. Nenhuma ferramenta externa é necessária — apenas o pacote Aspose.BarCode for .NET e um ambiente de desenvolvimento .NET.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* O pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)  

Você pode instalar o pacote pela linha de comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Inicializar o gerador de código de barras para codificação Planet

A primeira etapa em qualquer **exemplo de gerador de código de barras** é criar uma instância `BarcodeGenerator` e especificar o tipo de codificação. Para um código Planet você usa `EncodeTypes.Planet` e passa a string de dados que deseja codificar.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**Por que isso importa:** O enum `EncodeTypes.Planet` indica à biblioteca que deve usar a simbologia Planet, que possui um padrão de módulo fixo exigido pelos padrões postais. Fornecer os dados (`"123456"` neste caso) garante que o código de barras contenha o código de roteamento numérico correto.

## Etapa 2: Configurar a dimensão X (largura do módulo) em pixels

A dimensão X controla a largura de cada módulo individual (a barra mais estreita). Ajustá‑la altera o tamanho geral do código de barras sem afetar a legibilidade.

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Por que isso importa:** Uma dimensão X maior produz um código de barras maior, o que pode ser útil ao imprimir em envelopes grandes. A biblioteca escala automaticamente a altura para manter a proporção correta dos códigos Planet.

## Etapa 3: Salvar a imagem do código de barras no disco

Por fim, você salva a imagem gerada. A biblioteca determina a altura ideal, portanto você só precisa especificar o caminho de saída e o formato.

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**Por que isso importa:** Salvar como PNG preserva as bordas nítidas do código de barras, o que é essencial para uma leitura confiável. O método `Save` também suporta outros formatos (JPEG, BMP, TIFF) caso você precise de uma saída diferente.

### Saída esperada

Depois de executar o código, você encontrará um arquivo chamado **PlanetAutoHeight.png** em `C:\Barcodes`. A imagem terá aparência semelhante à ilustração abaixo (texto alternativo: *exemplo de gerador de código de barras mostrando um código de barras Planet*).

![Código de barras Planet gerado pelo exemplo C#](/images/planet-barcode-example.png){alt="exemplo de gerador de código de barras mostrando um código de barras Planet"}

## Etapa 4: Opcional – personalizar cores de primeiro plano e fundo

Se sua aplicação requer um estilo visual diferente, você pode alterar as cores do código de barras antes de salvar.

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**Dica:** Sempre teste o código de barras personalizado com um scanner real para confirmar que as alterações de cor não afetam a legibilidade.

## Etapa 5: Tratamento de erros e validação

A biblioteca Aspose.BarCode lança `ArgumentException` se os dados não atenderem aos requisitos da simbologia Planet (por exemplo, caracteres não numéricos). Envolva o código de geração em um bloco try‑catch para fornecer feedback claro.

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**Por que isso importa:** Códigos Planet aceitam apenas dados numéricos de comprimentos específicos. A validação adequada evita falhas em tempo de execução e economiza tempo durante os testes de integração.

## Exemplo completo e executável

Juntando todas as etapas você obtém um programa autocontido que pode copiar, colar e executar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

Compile e execute o programa:

```bash
dotnet run
```

Você deverá ver a mensagem no console confirmando a localização do arquivo, e o arquivo PNG conterá o código Planet gerado.

## Variações comuns e casos de borda

| Variação | Como implementar | Quando usar |
|-----------|------------------|------------|
| **Comprimento de dados diferente** | Alterar o segundo argumento em `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` | Serviços postais que exigem números de roteamento mais longos |
| **Resolução mais alta** | Definir `generator.Parameters.ImageResolution = 300;` antes de `Save` | Impressão em impressoras de alta DPI |
| **Formato de imagem diferente** | Usar `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff` | Quando PNG não for adequado ao seu fluxo de trabalho |
| **Nome de arquivo dinâmico** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | Processamento em lote de múltiplos códigos de barras |

## Dicas avançadas para um gerador de código de barras robusto

* **Reutilize a instância do gerador** ao criar muitos códigos de barras com as mesmas configurações; altere apenas `EncodeTypes` ou a string de dados para melhorar o desempenho.  
* **Valide a entrada** antes de passá‑la para `BarcodeGenerator`. Uma expressão regular simples como `^\d{6,9}$` garante que os dados estejam em conformidade com os requisitos Planet.  
* **Libere recursos** se você gerar milhares de imagens em um serviço de longa duração. O `BarcodeGenerator` implementa `IDisposable`, portanto encapsule‑o em um bloco `using` quando apropriado.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## Conclusão

Este **exemplo de gerador de código de barras** demonstra como **gerar código Planet** e **criar imagem de código de barras em C#** usando Aspose.BarCode for .NET. Você aprendeu como inicializar o gerador, definir a dimensão X, personalizar cores opcionalmente, tratar erros de validação e salvar o resultado como um arquivo PNG. Com o código-fonte completo fornecido, você pode integrar a geração de códigos Planet em qualquer aplicação C# imediatamente.

Em seguida, você pode explorar outras simbologias como QR, Code128 ou DataMatrix — cada uma segue o mesmo padrão de criar um `BarcodeGenerator`, configurar parâmetros e chamar `Save`. Os mesmos princípios se aplicam, facilitando a expansão das suas capacidades de geração de códigos de barras em uma ampla variedade de cenários de negócios. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [create planet barcode image – Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}