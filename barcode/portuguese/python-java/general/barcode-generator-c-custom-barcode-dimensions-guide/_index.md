---
category: general
date: 2026-07-21
description: Tutorial de gerador de código de barras em C# mostrando como definir
  dimensões personalizadas do código de barras, ajustar a altura em pixels do código
  de barras e mudar rapidamente a altura da imagem do código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- custom barcode dimensions
- barcode pixel height
- barcode image height
- change barcode height
language: pt
lastmod: 2026-07-21
og_description: O gerador de código de barras c# permite que você controle cada pixel.
  Aprenda a definir dimensões personalizadas do código de barras, ajustar a altura
  dos pixels e mudar a altura do código de barras sem esforço.
og_image_alt: Screenshot of barcode generator c# output with custom dimensions
og_title: Gerador de código de barras c# – Domine dimensões personalizadas em minutos
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  headline: Barcode generator c# – Custom barcode dimensions guide
  type: TechArticle
- description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  name: Barcode generator c# – Custom barcode dimensions guide
  steps:
  - name: What if I need a different **barcode image height** than the default?
    text: 'You can control the overall canvas size via `GeneratorParameters.ImageHeight.Pixels`.
      For example:'
  - name: How does `XDimension` affect scanning reliability?
    text: A smaller `XDimension` creates thinner bars, which can look sharper but
      may be harder for low‑resolution scanners. As a rule of thumb, keep `XDimension`
      ≥ 2 px for 300 dpi printing and ≥ 3 px for 200 dpi.
  - name: Can I switch from PNG to another format without changing code?
    text: 'Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`,
      `Bmp`, etc. Just replace the enum value:'
  - name: What if I need to generate dozens of barcodes with varying heights?
    text: 'Wrap the height‑changing logic in a loop:'
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Gerador de código de barras C# – Guia de dimensões personalizadas de código
  de barras
url: /pt/python-java/general/barcode-generator-c-custom-barcode-dimensions-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerador de código de barras c# – Guia de dimensões personalizadas de código de barras

Já se perguntou como fazer um **barcode generator c#** produzir exatamente o tamanho que você precisa? Você não está sozinho. Seja imprimindo etiquetas de produtos na linha de produção ou gerando tags no estilo QR para um sistema de inventário, obter as dimensões corretas é crucial.

Neste tutorial, percorreremos um exemplo completo, pronto‑para‑executar, que mostra como definir **custom barcode dimensions**, ajustar a **barcode pixel height** e, finalmente, **change barcode height** em tempo real. Sem referências vagas — apenas o código que você pode copiar, colar e executar hoje.

## O que você aprenderá

- Como instanciar um **barcode generator c#** para a simbologia DataBar Omnidirectional.  
- A diferença entre **barcode pixel height** e **barcode image height** geral.  
- Duas maneiras práticas de **change barcode height** sem recriar o gerador.  
- Dicas para salvar a imagem nas dimensões exatas que você precisa.

Você só precisa de um runtime .NET recente (4.7+ ou .NET 6) e da biblioteca Aspose.BarCode for .NET (ou qualquer API compatível). Se já os tem, vamos mergulhar.

## Etapa 1: Configurar o projeto e importar a biblioteca

Primeiro, crie um novo aplicativo console (ou adicione o código a um existente). Em seguida, adicione o pacote NuGet:

```bash
dotnet add package Aspose.BarCode
```

Agora importe os namespaces que você precisará:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing;   // only if you manipulate the bitmap later
```

> **Dica profissional:** Se você estiver usando o Visual Studio, o gerenciador NuGet cuidará da referência para você — sem necessidade de procurar DLLs manualmente.

## Etapa 2: Criar uma instância de barcode generator c# com um código DataBar Omnidirectional

A classe **barcode generator c#** é seu ponto de entrada. Vamos codificar um valor GTIN‑14 simples:

```csharp
// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Neste ponto, o gerador sabe *o que* codificar, mas não *quão* grandes as barras devem ser. É aí que entram as **custom barcode dimensions**.

## Etapa 3: Definir custom barcode dimensions – foco na barcode pixel height

Duas propriedades controlam o tamanho vertical:

| Propriedade | O que faz | Faixa típica |
|-------------|-----------|--------------|
| `XDimension.Pixels` | Largura de uma única barra (o “módulo”) | 1‑5 px é comum |
| `BarHeight.Pixels` | Altura das próprias barras | 30‑100 px dependendo da DPI de impressão |

Vamos definir uma largura modesta de 2 pixels e uma **barcode pixel height** de 30 px:

```csharp
// Step 3: Apply custom barcode dimensions
generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel tall bars
```

Por que 30 px? Em uma impressora de 300 dpi, 30 px equivale a aproximadamente 0,1 polegadas — perfeito para a maioria das etiquetas de varejo. Aumente se precisar de um impacto visual maior.

## Etapa 4: Salvar a imagem do código de barras com a barcode image height desejada

Ao chamar `Save`, a biblioteca adiciona automaticamente preenchimento para acomodar a **barcode image height** (a altura total do bitmap). A imagem final será mais alta que 30 px devido às zonas silenciosas e a qualquer legenda que você possa habilitar. Veja como gravar o primeiro PNG:

```csharp
// Step 4: Export the first image (30‑pixel bar height)
string output30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
generator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 30‑pixel barcode to {output30}");
```

Abra o arquivo resultante e você verá um DataBar nítido com uma **barcode image height** ligeiramente maior que 30 px — exatamente o que a maioria dos scanners espera.

## Etapa 5: Alterar a barcode height sem reconstruir o gerador

Alterar a altura das barras é tão fácil quanto ajustar uma única propriedade. Não é necessário recriar a instância `BarcodeGenerator`:

```csharp
// Step 5: Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
generator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 60‑pixel barcode to {output60}");
```

Observe que modificamos apenas `BarHeight.Pixels`. Isso demonstra a capacidade de **change barcode height** — rápida, econômica em memória e perfeita para processamento em lote onde cada etiqueta pode precisar de um tamanho diferente.

## Saída esperada

Executar o programa completo produz dois arquivos PNG:

- `DatabarBarHeight30Pixels.png` – as barras têm 30 px de altura, a imagem total tem cerca de 40 px de altura (incluindo zonas silenciosas).  
- `DatabarBarHeight60Pixels.png` – as barras têm 60 px de altura, a imagem total tem cerca de 70 px de altura.

Ambas as imagens contêm os mesmos dados codificados, portanto qualquer scanner que leia a primeira também lerá a segunda sem alterações de configuração.

## Código-fonte completo – copie, cole e execute

```csharp
// ------------------------------------------------------------
// Barcode generator c# – Custom dimensions demo
// ------------------------------------------------------------
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Omnidirectional
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set custom barcode dimensions (X‑dimension & bar height)
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
        generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel bars

        // 3️⃣ Save first image – demonstrates barcode pixel height = 30
        string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(path30, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 30‑pixel barcode to {path30}");

        // 4️⃣ Change barcode height – now 60 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Save second image – demonstrates change barcode height
        string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(path60, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 60‑pixel barcode to {path60}");
    }
}
```

> **Nota:** Substitua `YOUR_DIRECTORY` por um caminho de pasta real que seu aplicativo possa gravar. No Windows, algo como `@"C:\\Temp"` funciona bem.

## Perguntas comuns & tratamento de casos extremos

### E se eu precisar de uma **barcode image height** diferente do padrão?

Você pode controlar o tamanho total da tela via `GeneratorParameters.ImageHeight.Pixels`. Por exemplo:

```csharp
generator.Parameters.ImageHeight.Pixels = 120; // forces total image height
```

Isso é útil quando você precisa encaixar o código de barras em um modelo de etiqueta pré‑desenhado.

### Como o `XDimension` afeta a confiabilidade da leitura?

Um `XDimension` menor cria barras mais finas, que podem parecer mais nítidas, mas podem ser mais difíceis para scanners de baixa resolução. Como regra geral, mantenha `XDimension` ≥ 2 px para impressão a 300 dpi e ≥ 3 px para 200 dpi.

### Posso mudar de PNG para outro formato sem alterar o código?

Com certeza. O método `Save` aceita `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp`, etc. Basta substituir o valor do enum:

```csharp
generator.Save(@"path\barcode.jpg", BarCodeImageFormat.Jpeg);
```

### E se eu precisar gerar dezenas de códigos de barras com alturas variadas?

Envolva a lógica de alteração de altura em um loop:

```csharp
int[] heights = {30, 45, 60, 75};
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($@"YOUR_DIRECTORY\BarHeight{h}.png", BarCodeImageFormat.Png);
}
```

Dessa forma você **change barcode height** programaticamente para cada iteração sem reinstanciar o gerador.

## Recapitulação

Acabamos de ver como um **barcode generator c#** pode ser ajustado para produzir **custom barcode dimensions**, manipular **barcode pixel height** e **change barcode height** em tempo real. O exemplo completo mostra a inicialização, ajustes de propriedades e duas gravações que ilustram a diferença visual.

Pronto para o próximo passo? Experimente combinar essas configurações com legendas de texto, cores de fundo ou até mesmo incorporar o código de barras em um PDF usando Aspose.PDF. Os mesmos princípios se aplicam — basta ajustar os parâmetros relevantes.

Se você achou este guia útil, dê uma estrela no GitHub, compartilhe com colegas ou deixe um comentário abaixo com seus próprios experimentos. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar Altura Personalizada de Código de Barras – Códigos de Barras Unidimensionais](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Ajuste de Altura de Código de Barras Databar Unidimensional](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [tutorial de barcode generator c# – Personalizar Proporções de Código 16K com Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}