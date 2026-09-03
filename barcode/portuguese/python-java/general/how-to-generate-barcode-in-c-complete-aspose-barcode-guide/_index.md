---
category: general
date: 2026-07-21
description: Como gerar códigos de barras rapidamente usando Aspose.BarCode para C#.
  Aprenda a criar códigos de barras com Aspose, ajustar proporções e salvar PNGs em
  minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: pt
lastmod: 2026-07-21
og_description: Como gerar código de barras usando Aspose.BarCode para C#. Este guia
  passo a passo mostra como criar códigos de barras com Aspose, ajustar configurações
  e exportar imagens.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Como gerar código de barras em C# – Tutorial rápido do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Como gerar código de barras em C# – Guia completo do Aspose.BarCode
url: /pt/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerar Código de Barras em C# – Guia Completo do Aspose.BarCode

Já se perguntou **como gerar código de barras** em um aplicativo .NET sem lutar com código de imagem de baixo nível? Você não está sozinho. Em muitos projetos corporativos precisamos **criar código de barras com Aspose** para faturas, etiquetas de envio ou rastreamento de inventário, e a biblioteca torna isso surpreendentemente simples.

Neste tutorial, percorreremos um exemplo do mundo real que cria um código de barras DataBar Stacked Omnidirectional, ajusta sua proporção e salva dois arquivos PNG. Ao final, você terá um programa de console pronto para executar e uma compreensão clara das principais propriedades que pode controlar.

## O que Você Vai Aprender

- Configurar o Aspose.BarCode em um projeto C# (NuGet, noções básicas de licenciamento)
- Inicializar um gerador **DataBar stacked omnidirectional**
- Ajustar a X‑dimension (tamanho em pixels) e a proporção
- Salvar o código de barras como imagens PNG
- Estender o exemplo para outros tipos de código de barras ou formatos de saída

Nenhuma experiência prévia com Aspose é necessária — apenas um SDK .NET 6 (ou superior) funcional e uma IDE favorita.

## Pré-requisitos

| Requisito | Motivo |
|-------------|--------|
| .NET 6 SDK ou mais recente | Recursos modernos da linguagem e criação fácil de projetos |
| Visual Studio 2022 (ou VS Code) | IDE para construção e depuração |
| Pacote NuGet Aspose.BarCode para .NET | Biblioteca central que faz o trabalho pesado |
| Uma licença válida da Aspose (ou avaliação) | Remove a marca d'água de avaliação e desbloqueia todos os recursos |

Se ainda não instalou o pacote NuGet, execute:

```bash
dotnet add package Aspose.BarCode
```

Agora que está tudo pronto, vamos mergulhar no código.

## Etapa 1: Criar um Novo Projeto de Console

Primeiro, crie um novo aplicativo de console. Abra um terminal e digite:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Isso cria `Program.cs` e um arquivo `.csproj`. Abra o projeto no seu editor e adicione a referência ao Aspose conforme mostrado acima.

## Etapa 2: Inicializar o BarcodeGenerator

O coração do processo é a classe `BarcodeGenerator`. Solicitaremos uma simbologia **DataBar stacked omnidirectional** e forneceremos a ela uma string de exemplo GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Por que isso importa:** `EncodeTypes.DatabarStackedOmniDirectional` produz um código de barras compacto e de alta densidade, ideal para etiquetas pequenas. A string de dados segue o Identificador de Aplicação GS1 `(01)` para um valor GTIN‑14, que muitos sistemas de cadeia de suprimentos esperam.

## Etapa 3: Ajustar a Proporção e Salvar Imagens

Aspose.BarCode permite ajustar a **proporção** dos símbolos DataBar via `Parameters.Barcode.DataBar.AspectRatio`. Alterar esse valor muda a proporção visual largura‑para‑altura, o que pode ser crucial para encaixar o código de barras em uma etiqueta de tamanho fixo.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Explicação de cada linha**

- `outputPath` aponta para uma pasta onde os arquivos PNG serão armazenados. `Directory.CreateDirectory` garante que a pasta exista mesmo em uma máquina nova.
- `AspectRatio = 15` gera um código de barras relativamente alto; `AspectRatio = 30` o estica horizontalmente.
- `generator.Save(...)` grava a imagem no disco. O enum `BarCodeImageFormat.Png` assegura qualidade sem perdas.
- `Console.WriteLine` fornece feedback imediato quando você executa o programa.

### Saída Esperada

Ao executar `dotnet run`, você deverá ver algo como:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Abra os dois arquivos PNG lado a lado; você notará que a segunda imagem está visivelmente mais larga, mantendo a mesma altura. Ambas as imagens são legíveis por leitores de código de barras padrão.

## Etapa 4: Executar o Exemplo Completo

Aqui está o **código completo e executável** em um bloco para conveniência de copiar e colar:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Compile e execute:

```bash
dotnet run
```

Voilà — duas imagens PNG de código de barras perfeitamente renderizadas aparecem em `GeneratedBarcodes/`.

## Etapa 5: Extendendo o Exemplo (Opcional)

Agora que você **sabe como gerar código de barras** com Aspose, pode se perguntar: *O que mais posso ajustar?* Aqui estão algumas ideias rápidas:

| Propriedade | O que faz | Caso de uso típico |
|----------|--------------|------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Altera o tamanho do texto legível por humanos | Fonte maior para scanners portáteis |
| `generator.Parameters.Barcode.ImageFormat` | Formato de saída global (PNG, JPEG, BMP, etc.) | JPEG para tamanho amigável à web |
| `generator.Parameters.Barcode.Color` | Define a cor do primeiro plano | Categorias codificadas por cor |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Saída vetorial para escala infinita | PDFs prontos para impressão |

Para experimentar, basta adicionar as linhas correspondentes antes de cada chamada `Save`.

## Armadilhas Comuns & Dicas Profissionais

- **Posicionamento da licença:** Se usar uma licença paga, chame `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` antes de criar o gerador. Esquecer isso deixa uma marca d'água na imagem.
- **String de dados inválida:** As simbologias DataBar esperam dados numéricos GS1. Fornecer caracteres alfabéticos lançará `ArgumentException`.
- **Segurança de thread:** Instâncias de `BarcodeGenerator` **não** são seguras para uso em múltiplas threads. Crie uma nova instância por thread se estiver gerando códigos de barras em paralelo.
- **Tamanho da imagem vs. capacidade do scanner:** Um `XDimension.Pixels` muito alto pode gerar uma imagem enorme que alguns scanners têm dificuldade de ler. Teste com o hardware alvo.

## Conclusão

Acabamos de cobrir **como gerar código de barras** em C# usando Aspose.BarCode, desde a configuração do projeto até a gravação de duas imagens com diferentes proporções. As etapas principais — inicializar o gerador, configurar X‑dimension e proporção, e invocar `Save` — formam um padrão repetível que você pode aplicar a qualquer tipo de código de barras suportado pelo Aspose.

Agora você pode **criar código de barras com Aspose** para faturas, etiquetas de envio ou tags de inventário, e tem uma base sólida para explorar recursos mais avançados como cor, fontes personalizadas ou saída SVG. Sinta-se à vontade para ajustar o código, experimentar outros `EncodeTypes` e integrar o gerador aos seus serviços existentes.

Tem perguntas ou quer ver um estilo específico de código de barras? Deixe um comentário abaixo, e feliz codificação!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como Personalizar Código de Barras - Proporção do Codablock F com Aspose.BarCode para .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Como Gerar Códigos de Barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}