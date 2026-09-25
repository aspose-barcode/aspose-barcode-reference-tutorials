---
category: general
date: 2026-08-22
description: Como alterar o tamanho do código de barras em C# usando o gerador DataBar
  Stacked Omni‑Directional. Aprenda a definir a dimensão X e a proporção para a saída
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: pt
lastmod: 2026-08-22
og_description: Como mudar o tamanho do código de barras em C# com o gerador DataBar
  Stacked Omni‑Directional. Siga o guia passo a passo para ajustar a dimensão X e
  a proporção.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Como mudar o tamanho do código de barras em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como alterar o tamanho do código de barras em C# com DataBar Stacked
url: /pt/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como alterar o tamanho do código de barras em C# com DataBar Stacked

Se você precisa **alterar o tamanho do código de barras** em uma aplicação .NET, este guia mostra os passos exatos usando o gerador de código de barras DataBar Stacked Omni‑Directional. Você verá como controlar a dimensão X em pixels, ajustar a proporção do código de barras e salvar o resultado como um arquivo PNG.

Alterar o tamanho do código de barras costuma ser necessário quando o espaço da etiqueta impressa é limitado ou quando uma imagem de alta resolução é exigida para canais digitais. Este tutorial cobre tudo o que você precisa, desde a inicialização do gerador até a produção de duas imagens com tamanhos diferentes.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior instalado  
* Uma referência ao pacote NuGet **Aspose.BarCode for .NET**  
* Familiaridade básica com a sintaxe C#  

Nenhuma configuração adicional é necessária; o código funciona no Windows, Linux ou macOS.

## Como alterar o tamanho do código de barras em C# – passo a passo

As seções a seguir dividem o processo em etapas discretas e reutilizáveis. Cada etapa explica **por que** o código é necessário, não apenas **o que** ele faz.

### Etapa 1: Criar um gerador de código de barras DataBar Stacked Omni‑Directional

O objeto gerador contém todas as configurações do código de barras. Ao passar `EncodeTypes.DatabarStackedOmniDirectional` e dados de exemplo, você cria um código de barras válido pronto para personalização adicional.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Por que isso importa* – A classe **gerador de código de barras C#** encapsula o algoritmo de codificação. Começar com um gerador válido garante que as alterações de tamanho subsequentes afetem o tipo correto de código de barras.

### Etapa 2: Definir o tamanho básico do módulo (dimensão X) em pixels

A dimensão X define a largura de um único módulo do código de barras. Ajustá‑la altera a largura e a altura gerais proporcionalmente.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Por que isso importa* – Uma dimensão X maior produz um código de barras maior, útil para impressoras de baixa resolução. Por outro lado, um valor menor cria um código de barras compacto adequado para etiquetas pequenas.

### Etapa 3: Alterar a proporção do código de barras para 15 e salvar a imagem

A **proporção do código de barras** controla a relação altura‑largura. Uma proporção de 15 gera um código de barras relativamente alto.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Por que isso importa* – Diferentes dispositivos de leitura têm requisitos ótimos de proporção. Definir a proporção para 15 demonstra como **alterar o tamanho do código de barras** modificando a altura enquanto a largura permanece definida pela dimensão X.

#### Saída esperada

O arquivo `DatabarAspectRatio15.png` mostra um código de barras DataBar Stacked Omni‑Directional que é mais alto que o padrão. A largura do código reflete a dimensão X de 2 pixels, e a altura segue a proporção 15.

### Etapa 4: Alterar a proporção do código de barras para 30 e salvar a nova imagem

Aumentar a proporção para 30 torna o código de barras ainda mais alto, ilustrando a flexibilidade dos ajustes de tamanho.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Por que isso importa* – Ao trocar o valor da **proporção do código de barras**, você vê instantaneamente como **alterar o tamanho do código de barras** sem recriar o gerador. Isso economiza tempo de processamento em cenários de lote.

#### Saída esperada

O arquivo `DatabarAspectRatio30.png` é visivelmente mais alto que a imagem anterior, confirmando que a proporção influencia diretamente a altura do código de barras.

### Etapa 5: Verificar as imagens geradas

Abra os arquivos PNG em qualquer visualizador de imagens. Você deverá ver dois códigos de barras com largura idêntica (controlada pela dimensão X) mas alturas diferentes (controladas pela proporção). Se as imagens parecerem borradas, aumente os pixels da dimensão X; se estiverem muito altas, diminua a proporção.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Por que isso importa* – A verificação programática garante que as alterações de tamanho foram aplicadas corretamente, o que é crucial para pipelines de build automatizados.

## Variações comuns e casos de borda

| Situação | Ajuste | Motivo |
|-----------|------------|--------|
| **Etiquetas muito pequenas** | Defina `XDimension.Pixels = 1` e `AspectRatio = 10` | Reduz a pegada total mantendo a legibilidade |
| **Impressão de alta resolução** | Defina `XDimension.Pixels = 4` e `AspectRatio = 20` | Aumenta a densidade de pixels para saída nítida |
| **Formato de imagem diferente** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` | Útil quando o suporte a PNG é limitado |
| **Dados dinâmicos** | Passe uma string variável ao construtor `BarcodeGenerator` | Gera códigos de barras para cada produto automaticamente |

Quando precisar gerar muitos códigos de barras com tamanhos variados, encapsule as etapas em um método:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Chamar `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` produz um código de barras com tamanho personalizado em uma única linha de código.

## Dicas avançadas para alterações de tamanho confiáveis

* **Sempre defina a dimensão X antes da proporção.** Alterar a proporção primeiro pode gerar escalonamento inesperado se a dimensão X permanecer com um valor padrão não ideal.  
* **Use uma pasta de saída consistente.** Codificar `"YOUR_DIRECTORY"` funciona para demonstrações, mas em produção prefira `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Valide o tamanho da imagem gerada.** Pequenas alterações na dimensão X podem não ser perceptíveis na tela; conferir as dimensões em pixels garante que a mudança entrou em vigor.  

## Conclusão

Agora você sabe **como alterar o tamanho do código de barras** em C# usando o gerador DataBar Stacked Omni‑Directional. Ao ajustar os **pixels da dimensão X** e a **proporção do código de barras**, você pode produzir imagens PNG que se encaixam em qualquer tamanho ou requisito de resolução de etiqueta. O exemplo completo e executável acima demonstra todo o fluxo, desde a criação do gerador até a verificação do tamanho.

### O que explorar a seguir

* **Cores personalizadas** – experimente `barcodeGenerator.Parameters.Barcode.ForeColor` e `BackColor` para combinar com as diretrizes da marca.  
* **Tipos de código de barras diferentes** – substitua `EncodeTypes.DatabarStackedOmniDirectional` por `EncodeTypes.QR` ou `EncodeTypes.Code128` para ver como os parâmetros de tamanho variam entre simbologias.  
* **Processamento em lote** – combine o método `GenerateDatabar` com uma importação CSV para criar milhares de códigos de barras automaticamente.

Sinta‑se à vontade para adaptar os trechos de código à arquitetura do seu projeto e deixe os ajustes de tamanho do código de barras melhorar a confiabilidade de leitura e o design visual. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}