---
category: general
date: 2026-09-29
description: Crie código de barras RM4SCC em C# com um exemplo completo e aprenda
  a gerar código de barras Planet usando a mesma biblioteca. Inclui opções de altura
  automática e fixa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- barcode generator example c#
- how to generate planet barcode
language: pt
lastmod: 2026-09-29
og_description: Crie código de barras RM4SCC em C# com um exemplo pronto para executar.
  O guia também mostra como gerar código de barras Planet, abordando alturas de barra
  automáticas e fixas.
og_image_alt: Screenshot showing a generated RM4SCC barcode created with C#
og_title: Criar código de barras RM4SCC em C# – tutorial completo do gerador
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create RM4SCC barcode C# with a full code example and learn how to
    generate Planet barcode using the same library. Includes auto and fixed height
    options.
  headline: Create RM4SCC barcode C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
title: Criar código de barras RM4SCC C# – guia passo a passo
url: /pt/python-java/general/create-rm4scc-barcode-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras RM4SCC C# – guia passo a passo

Se você precisa **criar código de barras RM4SCC C#** rapidamente, este guia mostra um exemplo completo e executável. Você também verá um **exemplo de gerador de código de barras C#** que demonstra **como gerar código de barras Planet** no mesmo projeto.  

O código usa a biblioteca Aspose.BarCode for .NET, que suporta ambos os padrões postais (RM4SCC, Planet) e uma ampla variedade de simbologias lineares e 2‑D. Ao final deste tutorial você será capaz de:

* Gerar um código de barras RM4SCC com cálculo automático de altura.  
* Gerar o mesmo código de barras com altura de barra fixa.  
* Criar um código de barras Planet usando etapas de configuração idênticas.  

Nenhum serviço externo é necessário — tudo roda localmente em qualquer ambiente .NET 6+.

## Prerequisites

| Requisito | Por que é importante |
|-------------|----------------|
| .NET 6 SDK or later | A biblioteca tem como alvo .NET Standard 2.0+, portanto .NET 6 garante compatibilidade. |
| Visual Studio 2022 (or any IDE) | Fornece IntelliSense e gerenciamento de projetos simplificado. |
| Aspose.BarCode for .NET NuGet package | Contém `BarcodeGenerator`, `EncodeTypes` e suporte a formatos de imagem. |

Instale o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto e as importações

Crie um novo projeto de console e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The tutorial code starts here.
```

Esses namespaces expõem `BarcodeGenerator`, `EncodeTypes` e o enum `BarCodeImageFormat` usado mais adiante.

## Etapa 2: Criar código de barras RM4SCC – altura automática

O primeiro exemplo mostra como **criar código de barras RM4SCC C#** sem especificar a altura da barra. A biblioteca determina automaticamente a altura ideal com base na dimensão X.

```csharp
            // Create a Planet (postal) barcode generator – auto height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // Define the module width (X‑dimension) in pixels
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Optional: comment out the next line to keep automatic height
            // rm4sccAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image as PNG
            rm4sccAuto.Save("RM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
* `EncodeTypes.RM4SCC` informa ao gerador para usar a simbologia postal RM4SCC.  
* `XDimension.Pixels` controla a largura da barra estreita; 4 px é uma escolha comum para renderização em tela.  
* Quando `BarHeight.Pixels` é omitido, a Aspose calcula uma altura que atende à especificação RM4SCC, garantindo legibilidade para scanners postais.

## Etapa 3: Criar código de barras RM4SCC – altura fixa

Às vezes um sistema de design requer uma altura de barra específica. O código a seguir fixa a altura em 100 px:

```csharp
            // Create a RM4SCC barcode generator – fixed height
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // X‑dimension stays the same
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

            // Explicitly set the bar height to 100 px
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image
            rm4sccFixed.Save("RM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

**Por que você pode usar uma altura fixa:**  
Diretrizes de design frequentemente determinam um peso visual uniforme entre diferentes códigos de barras. Ao definir `BarHeight.Pixels`, você garante uma aparência consistente independentemente da simbologia subjacente.

## Etapa 4: Criar código de barras Planet – altura automática

O **exemplo de gerador de código de barras C#** funciona da mesma forma para o código postal Planet. Troque o valor de `EncodeTypes` e reutilize a mesma lógica de configuração:

```csharp
            // Create a Planet barcode generator – auto height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Same X‑dimension as before
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Keep automatic height (comment out the line below if you want auto)
            // planetAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the PNG file
            planetAuto.Save("Planet_AutoHeight.png", BarCodeImageFormat.Png);
```

**Como gerar código de barras Planet:**  
A única mudança é o valor do enum `EncodeTypes.Planet`. Todos os demais parâmetros (dimensão X, altura opcional) se comportam de forma idêntica, razão pela qual este tutorial serve como um **exemplo de gerador de código de barras C#** para vários formatos postais.

## Etapa 5: Criar código de barras Planet – altura fixa

Se você precisar de uma altura específica para o código de barras Planet, aplique a mesma propriedade usada para RM4SCC:

```csharp
            // Create a Planet barcode generator – fixed height
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // fixed 100 px

            planetFixed.Save("Planet_FixedHeight.png", BarCodeImageFormat.Png);
```

## Etapa 6: Executar e verificar a saída

Feche o método `Main` e as chaves da classe:

```csharp
        }
    }
}
```

Compile e execute o projeto:

```bash
dotnet run
```

Após a execução você encontrará quatro arquivos PNG na pasta do projeto:

* `RM4SCC_AutoHeight.png`
* `RM4SCC_FixedHeight.png`
* `Planet_AutoHeight.png`
* `Planet_FixedHeight.png`

Cada imagem contém um código de barras claro e legível. Abra qualquer arquivo para verificar se as barras foram renderizadas com a largura esperada (4 px) e altura (automática ou 100 px).  

![Código de barras RM4SCC gerado com C#](rm4scc_example.png "Captura de tela mostrando um código de barras RM4SCC gerado com C#")

*Texto alternativo da imagem:* **Captura de tela mostrando um código de barras RM4SCC gerado com C#** (corresponde ao requisito de alt da imagem OG).

## Dicas profissionais e armadilhas comuns

| Situação | Recomendação |
|-----------|----------------|
| **Dimensão X incorreta** | Mantenha `XDimension.Pixels` entre 2 px e 6 px para a maioria das impressoras. Valores menores podem causar borrão. |
| **Altura da barra ignorada** | Certifique‑se de *descomentar* a linha `BarHeight.Pixels`; deixar o comentário fará com que a altura automática seja usada. |
| **String de dados inválida** | RM4SCC e Planet aceitam apenas caracteres numéricos (0‑9). Fornecer letras dispara uma `ArgumentException`. |
| **Saída de alta resolução** | Use `BarCodeImageFormat.Tiff` ou `Pdf` para impressão sem perdas. |
| **Performance** | Reutilize uma única instância de `BarcodeGenerator` se precisar criar muitos códigos de barras com as mesmas configurações; altere apenas a propriedade `CodeText` entre as gravações. |

## Conclusão

Agora você sabe como **criar código de barras RM4SCC C#** e **como gerar código de barras Planet** usando um padrão de código conciso e reutilizável. O tutorial abordou cenários de altura automática e fixa, forneceu um esqueleto de projeto pronto para execução e destacou as melhores práticas para geração confiável de códigos de barras.

Em seguida, considere explorar outras simbologias postais como **POSTNET** ou **USPS Intelligent Mail** — a mesma API `BarcodeGenerator` se aplica, então você pode estender este **exemplo de gerador de código de barras C#** com mudanças mínimas. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerador de código de barras C# – criar exemplo de código de barras Planet e RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Criar código de barras RM4SCC C# e definir altura do código de barras](/barcode/english/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/)
- [Criar código de barras Planet em C# – Guia completo passo a passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}