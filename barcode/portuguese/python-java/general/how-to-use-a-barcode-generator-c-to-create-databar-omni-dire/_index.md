---
category: general
date: 2026-08-22
description: O tutorial de gerador de código de barras em C# mostra como gerar arquivos
  PNG de código de barras, criar códigos de barras DataBar e ajustar a altura do código
  de barras em apenas alguns passos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: pt
lastmod: 2026-08-22
og_description: Guia de gerador de código de barras em C# mostra como gerar PNG de
  código de barras, criar códigos DataBar e ajustar a altura do código de barras de
  forma eficiente.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: gerador de código de barras C# – crie códigos de barras DataBar e ajuste
  a altura
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como usar um gerador de códigos de barras C# para criar códigos de barras DataBar
  omnidirecionais
url: /pt/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar um barcode generator C# para criar códigos de barras DataBar Omni‑directional

Se você precisa de um **barcode generator C#** que possa produzir imagens PNG de alta qualidade, este guia tem tudo o que você precisa. Você aprenderá como gerar arquivos PNG de código de barras, criar um código de barras DataBar Omni‑directional e ajustar a altura do código de barras sem sair do seu IDE.

Gerar códigos de barras programaticamente elimina a etapa manual de usar um editor gráfico. Ao final deste tutorial você terá dois arquivos PNG — um com altura de barra de 30 pixels e outro com altura de barra de 60 pixels — prontos para inclusão em faturas, etiquetas ou sistemas de inventário.

**Prerequisites**

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
- Uma referência ao pacote NuGet `Aspose.BarCode` (ou qualquer biblioteca que exponha uma API semelhante)
- Familiaridade básica com C# e Visual Studio ou seu IDE preferido

---

## Step 1: Set up the barcode generator C# project

Criar uma instância de **barcode generator C#** é a primeira coisa que você faz. O construtor recebe dois argumentos: o tipo de código de barras (`EncodeTypes.DatabarOmniDirectional`) e a carga de dados. Neste exemplo a carga segue o formato de Identificador de Aplicação GS1 para um GTIN de 14 dígitos.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Why this matters:** O enum `EncodeTypes.DatabarOmniDirectional` indica à biblioteca que ela deve renderizar um DataBar que pode ser lido de qualquer direção, o que é ideal para pequenas etiquetas de varejo.

---

## Step 2: Define the module dimension (X‑dimension)

A X‑dimension controla a largura de um único módulo do código de barras. Definir para 2 pixels gera uma imagem nítida e legível, mantendo o tamanho do arquivo baixo.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** Se precisar de um código de barras mais compacto para espaço limitado, diminua o valor para 1 pixel, mas teste a legibilidade com um scanner.

---

## Step 3: Generate the first PNG with a 30‑pixel bar height

A altura da barra determina quão altas as barras aparecem. Uma altura de 30 pixels é um padrão comum para etiquetas padrão.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

O arquivo `DatabarBarHeight30Pixels.png` agora contém um **generate barcode PNG** que pode ser usado diretamente em páginas web ou impresso sob demanda.

---

## Step 4: Adjust barcode height to 60 pixels and save a second PNG

Alterar a altura da barra é tão simples quanto atribuir um novo valor à mesma propriedade. Isso demonstra a capacidade de **adjust barcode height** do gerador.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Agora você tem `DatabarBarHeight60Pixels.png`, que é ideal para embalagens maiores onde o código de barras precisa ser escaneado a distância.

**Expected output**

- `DatabarBarHeight30Pixels.png` – um código de barras DataBar Omni‑directional compacto, 30 px de altura.
- `DatabarBarHeight60Pixels.png` – o mesmo código de barras, dobrado em altura para melhor visibilidade.

Ambas as imagens são arquivos PNG, preservando qualidade sem perdas e suportando transparência, se necessário.

---

## How to generate barcode PNG files in different formats

Embora este tutorial se concentre em PNG, o método `Save` aceita outros formatos como `Jpeg`, `Bmp` e `Svg`. Para **how to generate barcode** em outro formato, basta substituir `BarCodeImageFormat.Png` pelo valor do enum desejado:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Escolher SVG é útil quando você precisa de uma imagem vetorial que escala sem pixelização.

---

## Common pitfalls when you **create DataBar barcode** images

| Issue | Cause | Fix |
|-------|-------|-----|
| Código de barras aparece borrado | X‑dimension muito baixa para a resolução alvo | Aumente `XDimension.Pixels` para 3 ou 4 |
| Leitor não consegue ler o código | Altura da barra muito curta para a ótica do leitor | Use no mínimo 30 pixels ou siga as especificações do leitor |
| String de dados é rejeitada | Formatação GS1 incorreta | Garanta que a string comece com o Identificador de Aplicação correto, por exemplo, `(01)` para GTIN‑14 |

Abordar esses pontos cedo economiza tempo ao integrar códigos de barras em pipelines de produção.

---

## Advanced tip: Reusing the same generator for multiple barcodes

Se você precisa **generate barcode PNG** para um lote de produtos, reutilize a mesma instância `BarcodeGenerator` e apenas atualize a propriedade `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Esse padrão minimiza a sobrecarga de criação de objetos e mantém seu código conciso.

---

## Conclusion

Você agora tem um fluxo de trabalho completo de **barcode generator C#** que **creates DataBar barcodes**, **generates barcode PNG** files e permite **adjust barcode height** com uma única alteração de propriedade. O exemplo cobre tudo, desde a configuração do projeto até o tratamento de casos extremos, para que você possa integrar a criação de códigos de barras em qualquer aplicação .NET com confiança.

**Next steps**

- Explore outras simbologias de código de barras (`EncodeTypes.QR`, `EncodeTypes.Code128`) para ampliar sua solução.
- Combine o gerador com ASP.NET Core para servir códigos de barras sob demanda via um endpoint de API.
- Experimente opções de cor (`generator.Parameters.Barcode.ForeColor`) para fins de branding.

Happy coding, and may your scans always be swift!

## What Should You Learn Next?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}