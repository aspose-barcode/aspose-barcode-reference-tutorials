---
category: general
date: 2026-10-02
description: Aprenda a criar códigos de barras rm4scc em C# e a gerar códigos de barras
  postais com altura personalizada. Inclui código passo a passo para códigos de barras
  Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: pt
lastmod: 2026-10-02
og_description: Crie código de barras rm4scc em C# e aprenda a gerar código de barras
  postal com dimensões exatas. Exemplo de código completo e dicas de boas práticas.
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: Criar código de barras rm4scc com altura personalizada – Guia C#
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: Como criar código de barras rm4scc e controlar sua altura em C#
url: /pt/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras rm4scc e controlar sua altura em C#

Se você precisa **criar código de barras rm4scc** para um sistema de correspondência, este guia mostra exatamente como gerar códigos de barras postais e definir uma altura de barra precisa. Você verá tanto a abordagem padrão (altura automática) quanto a técnica de altura explícita, para que possa escolher o método que corresponde aos requisitos do seu design.

Gerar um código de barras postal é uma tarefa comum ao criar etiquetas de envio, softwares de mala direta em lote ou qualquer solução que se integre com serviços postais nacionais. Este tutorial cobre:

* **como gerar código de barras postal** para as simbologias RM4SCC e Planet  
* **gerar código de barras planet** com as mesmas configurações para comparação  
* **como definir a altura do código de barras** para um valor fixo em pixels  
* código C# completo e executável usando a biblioteca Aspose.BarCode  

Ao final do artigo você terá um programa de console pronto‑para‑executar que produz quatro arquivos PNG — dois com altura automática e dois com altura fixa de 100 px.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior (o código também funciona com .NET Framework 4.7+).  
* Visual Studio 2022 ou qualquer IDE que possa compilar projetos C#.  
* O pacote NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`).  

Nenhuma configuração adicional é necessária; a biblioteca lida com toda a renderização de imagens internamente.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e adicione as diretivas `using` necessárias. Esta etapa prepara o ambiente para a geração de códigos de barras.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*Por que isso importa*: Declarar `outputFolder` uma única vez evita repetições e facilita a alteração do caminho de destino posteriormente. A chamada `CreateDirectory` garante que a operação de gravação não falhe porque a pasta está ausente.

## Etapa 2: Como gerar código de barras postal com altura padrão

### 2.1 Criar um código de barras RM4SCC (altura automática)

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 Criar um código de barras Planet (altura automática)

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

Ambas as chamadas omitem a propriedade `BarHeight`, de modo que a biblioteca calcula a altura ideal com base nas especificações da simbologia. Esta é a maneira mais simples de **como gerar código de barras postal** quando você não tem restrições rígidas de layout.

## Etapa 3: Como definir a altura do código de barras para layout preciso

Quando um modelo de etiqueta requer um tamanho visual fixo, você deve definir explicitamente a altura das barras. O código a seguir demonstra **como definir a altura do código de barras** para 100 pixels em ambas as simbologias.

### 3.1 Código de barras RM4SCC de altura fixa

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 Código de barras Planet de altura fixa

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*Por que isso funciona*: A propriedade `BarHeight.Pixels` substitui o cálculo automático, forçando o renderizador a usar exatamente o número de pixels especificado. Isso é essencial quando o código de barras precisa alinhar‑se com outros elementos da UI ou com modelos impressos.

## Etapa 4: Verificar as imagens geradas

Depois que o programa terminar, abra os quatro arquivos PNG na `outputFolder`. Você deverá ver:

| Nome do arquivo | Altura | Simbologia |
|-----------------|--------|------------|
| `PostalRM4SCC_AutoHeight.png` | Auto‑calculada (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | Auto‑calculada (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px** (exata) | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px** (exata) | Planet |

As duas imagens “FixedHeight” têm barras com exatamente 100 px de altura, atendendo ao requisito **como definir a altura do código de barras** para um formato de etiqueta padronizado.

## Etapa 5: Armadilhas comuns e dicas de boas práticas

* **Valores de altura inválidos** – Definir `BarHeight.Pixels` com um número negativo lança uma `ArgumentException`. Sempre valide a entrada do usuário antes de atribuir o valor.  
* **Consciência de resolução** – O tamanho visual na tela também depende do DPI. Se você exportar posteriormente para PDF, considere definir `ImageResolution` para manter as dimensões físicas consistentes.  
* **X‑dimension vs. altura da barra** – `XDimension.Pixels` controla a **largura** da barra, não a altura. Esquecer de configurá‑la pode deixar o código de barras muito fino, especialmente em DPI baixo.  
* **Segurança de threads** – Instâncias de `BarcodeGenerator` **não** são thread‑safe. Crie uma nova instância por thread ou sincronize o acesso se gerar muitos códigos de barras em paralelo.

## Código‑fonte completo (executável)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

Copie o código para `Program.cs`, restaure os pacotes NuGet e execute `dotnet run`. O console confirmará a geração bem‑sucedida e os arquivos PNG aparecerão em `C:/Barcodes/`.

## Conclusão

Agora você sabe como **criar código de barras rm4scc** e **gerar código de barras planet** em C#, tanto com dimensionamento automático quanto com altura de barra definida manualmente. Ao controlar `BarHeight.Pixels` você responde à pergunta **como definir a altura do código de barras**, garantindo que seus códigos de barras postais se encaixem perfeitamente em qualquer layout de etiqueta.

Em seguida, você pode explorar:

* **como gerar código de barras postal** em outros formatos como PDF ou SVG (`BarCodeImageFormat.Pdf`, `BarCodeImageFormat.Svg`).  
* Adicionar texto legível ao humano abaixo do código de barras (`Parameters.Caption`).  
* Integrar o gerador em uma API ASP.NET Core para servir códigos de barras sob demanda.

Sinta‑se à vontade para experimentar diferentes valores de `XDimension`, cores ou imagens de fundo para combinar com a identidade visual da sua marca, mantendo a conformidade com os padrões de códigos de barras. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como gerar código de barras postal em C# com dimensões personalizadas](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [Como criar código de barras planet PNG com C# – guia passo a passo](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Como definir largura e gerar um código de barras Planet em C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}