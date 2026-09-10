---
category: general
date: 2026-07-27
description: Crie imagem de código de barras postal em C# rapidamente — aprenda como
  gerar código de barras postal, gerar código de barras planetário e como definir
  a altura do código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: pt
lastmod: 2026-07-27
og_description: Crie imagem de código de barras postal em C# e domine como gerar código
  de barras postal, gerar código de barras Planet e como definir a altura do código
  de barras para resultados perfeitos.
og_image_alt: Sample PNG showing Planet and RM4SCC postal barcodes generated with
  Aspose.BarCode
og_title: Criar Imagem de Código de Barras Postal em C# – Guia Completo de Programação
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  headline: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  name: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  steps:
  - name: Why set `XDimension`?
    text: '`XDimension` is the pixel width of the smallest bar. If you leave it at
      the library’s default (usually 1 px), the barcode can look cramped on high‑resolution
      screens. Setting it to **4 px** gives a nicely spaced image that prints cleanly
      on most printers.'
  - name: What does `BarHeight.Pixels` actually do?
    text: When you **set barcode height**, you override the library’s automatic calculation.
      By default Aspose.BarCode chooses a height that keeps the barcode square‑ish,
      which is fine for many use‑cases. However, postal standards sometimes demand
      a minimum bar height (e.g., 100 px for high‑resolution printin
  - name: Edge Cases & Common Pitfalls
    text: '- **Zero or negative height** – the library throws `ArgumentException`.
      Always validate user input. - **Non‑integer pixel values** – the property is
      an `int`, so fractions are rounded down automatically. - **Changing DPI after
      setting height** – the visual size changes, but the pixel count stays the'
  - name: Expected Output
    text: 'When you open the generated PNG files you’ll see:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- postal
title: Criar imagem de código de barras postal em C# – Guia completo passo a passo
url: /pt/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie Imagem de Código de Barras Postal em C# – Guia Completo Passo a Passo

Já precisou **criar imagem de código de barras postal** em C# mas não sabia quais propriedades ajustar? Você não está sozinho. Seja construindo um sistema de etiquetas de envio ou apenas experimentando com simbologias postais, dominar as chamadas de API corretas torna tudo muito mais fácil.

Neste tutorial vamos percorrer **como gerar imagens de código de barras postal** nos formatos Planet e RM4SCC, e vamos mostrar **como definir a altura do código de barras** para que as barras fiquem exatamente como esperado. Ao final, você terá um aplicativo console pronto‑para‑executar que gera quatro arquivos PNG – dois com alturas padrão e dois com altura de barra explícita de 100 px.

## O que você vai precisar

- **.NET 6.0** ou superior (o código também compila no .NET Framework 4.6+ )  
- **Aspose.BarCode for .NET** – o pacote NuGet que fornece `BarcodeGenerator`  
- Uma pasta no disco onde os arquivos PNG podem ser salvos (substitua `YOUR_DIRECTORY` no exemplo)  

Se você nunca usou o Aspose.BarCode antes, obtenha-o no NuGet:

```bash
dotnet add package Aspose.BarCode
```

É só isso – sem DLLs extras, sem dependências nativas. Vamos começar.

## Crie Imagem de Código de Barras Postal – Inicialize o Gerador

A primeira coisa a fazer é criar uma instância de `BarcodeGenerator`. Esse objeto é o ponto de entrada para *qualquer* código de barras que você queira renderizar. Você passa dois argumentos ao construtor:

1. O **tipo de codificação** (`EncodeTypes.Planet` ou `EncodeTypes.RM4SCC`)  
2. A **string de dados** (o código postal numérico, por exemplo `"123456"`)

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        const string outputFolder = @"C:\Temp\Barcodes";

        // Ensure the folder exists
        System.IO.Directory.CreateDirectory(outputFolder);

        // ---------- Planet barcode with default height ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // X‑dimension controls the width of the narrowest bar (in pixels)
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetDefaultPath = System.IO.Path.Combine(outputFolder, "PlanetDefault.png");
        planetDefaultPath = System.IO.Path.ChangeExtension(planetDefaultPath, "png");
        planetGenerator.Save(planetDefaultPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with default height ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccDefaultPath = System.IO.Path.Combine(outputFolder, "RM4SCCDefault.png");
        rm4sccGenerator.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
```

### Por que definir `XDimension`?

`XDimension` é a largura em pixels da menor barra. Se você deixá‑la no padrão da biblioteca (geralmente 1 px), o código de barras pode ficar apertado em telas de alta resolução. Definir **4 px** gera uma imagem bem espaçada que imprime de forma limpa na maioria das impressoras.

## Como gerar Código de Barras Postal – Tipos Planet e RM4SCC

Agora que temos um gerador, vamos falar sobre os *dois* tipos de simbologias postais mais comuns: **Planet** (usado no Reino Unido) e **RM4SCC** (usado nos EUA). A única diferença no código é o valor do enum `EncodeTypes`. Todo o resto – como salvar, DPI ou formato PNG – permanece igual.

```csharp
        // ---------- Planet barcode with explicit 100 px height ----------
        var planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        // Here we answer the “how to set barcode height” question.
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string planetHeightPath = System.IO.Path.Combine(outputFolder, "PlanetHeight100.png");
        planetHeightGenerator.Save(planetHeightPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with explicit 100 px height ----------
        var rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string rm4sccHeightPath = System.IO.Path.Combine(outputFolder, "RM4SCCHeight100.png");
        rm4sccHeightGenerator.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
    }
}
```

### O que `BarHeight.Pixels` realmente faz?

Ao **definir a altura do código de barras**, você sobrescreve o cálculo automático da biblioteca. Por padrão, o Aspose.BarCode escolhe uma altura que mantém o código de barras quase quadrado, o que funciona para muitos casos. Contudo, normas postais às vezes exigem uma altura mínima de barra (por exemplo, 100 px para impressão de alta resolução). A propriedade `BarHeight.Pixels` permite atender a essas especificações com precisão.

## Como definir a altura do código de barras – Controlando a altura das barras para padrões postais

Se você está se perguntando **como definir a altura do código de barras** para um DPI de impressora específico, pode combinar `BarHeight.Pixels` com as configurações de `Resolution`:

```csharp
        // Example: 300 DPI, 1 inch tall => 300 px
        planetHeightGenerator.Parameters.ImageResolution = 300;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 300; // 1‑inch bar at 300 DPI
```

> **Dica profissional:** Sempre teste algumas alturas diferentes na sua impressora alvo. Muito alta e o código de barras pode exceder a área imprimível da etiqueta; muito baixa e os scanners podem não detectar a zona silenciosa.

### Casos de borda e armadilhas comuns

- **Altura zero ou negativa** – a biblioteca lança `ArgumentException`. Sempre valide a entrada do usuário.  
- **Valores de pixel não inteiros** – a propriedade é um `int`, então frações são arredondadas para baixo automaticamente.  
- **Alterar DPI após definir a altura** – o tamanho visual muda, mas a contagem de pixels permanece a mesma. Se precisar de um tamanho físico (por exemplo, 1 cm), calcule `pixels = DPI * cm / 2.54`.

## Exemplo completo – Todas as etapas combinadas

Abaixo está o programa completo, pronto para copiar e colar. Ele inclui tratamento de erros, criação de pasta e comentários que explicam cada linha. Execute‑o a partir de um projeto console e você obterá quatro arquivos PNG em `C:\Temp\Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            const string outputFolder = @"C:\Temp\Barcodes";
            Directory.CreateDirectory(outputFolder);

            try
            {
                // 1️⃣ Planet barcode – default (automatic) height
                var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string planetDefaultPath = Path.Combine(outputFolder, "PlanetDefault.png");
                planetDefault.Save(planetDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetDefaultPath}");

                // 2️⃣ RM4SCC barcode – default (automatic) height
                var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string rm4sccDefaultPath = Path.Combine(outputFolder, "RM4SCCDefault.png");
                rm4sccDefault.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccDefaultPath}");

                // 3️⃣ Planet barcode – explicit 100 px height
                var planetHeight = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetHeight.Parameters.Barcode.XDimension.Pixels = 4;
                planetHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string planetHeightPath = Path.Combine(outputFolder, "PlanetHeight100.png");
                planetHeight.Save(planetHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetHeightPath}");

                // 4️⃣ RM4SCC barcode – explicit 100 px height
                var rm4sccHeight = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccHeight.Parameters.Barcode.XDimension.Pixels = 4;
                rm4sccHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string rm4sccHeightPath = Path.Combine(outputFolder, "RM4SCCHeight100.png");
                rm4sccHeight.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccHeightPath}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Something went wrong: {ex.Message}");
            }
        }
    }
}
```

### Saída esperada

Ao abrir os arquivos PNG gerados, você verá:

| Arquivo | Simbologia | Altura | Observações visuais |
|---------|------------|--------|----------------------|
| `PlanetDefault.png` | Planet | Automática (≈ 50 px) | Fina |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como gerar código de barras – Tipos de código de barras unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)
- [Como gerar código de barras – Configuração do Code 39 com Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Como gerar códigos DataMatrix (ECC 200) com Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}