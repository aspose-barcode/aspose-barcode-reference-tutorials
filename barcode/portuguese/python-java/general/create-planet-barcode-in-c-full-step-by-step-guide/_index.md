---
category: general
date: 2026-07-18
description: Crie códigos de barras Planet rapidamente com C#. Aprenda a gerar barras
  preenchidas e vazias, definir a dimensão X e salvar imagens PNG – tudo em um único
  tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: pt
lastmod: 2026-07-18
og_description: Crie o código de barras Planet instantaneamente. Este guia mostra
  como definir a dimensão X, alternar entre barras preenchidas e vazias e exportar
  arquivos PNG com o Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Criar Planet Barcode em C# – Guia Completo de Programação
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Criar Código de Barras Planet em C# – Guia Completo Passo a Passo
url: /pt/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras Planet em C# – Guia Completo Passo a Passo

Já precisou **criar código de barras planet** imagens mas não tinha certeza de quais propriedades ajustar? Você não está sozinho. Muitos desenvolvedores se deparam com um obstáculo quando as barras preenchidas padrão não atendem ao que a especificação exige, ou quando a largura da barra deve corresponder ao DPI da impressora.  

Neste tutorial você aprenderá exatamente como **criar código de barras planet** arquivos usando a biblioteca Aspose.BarCode, como controlar os **pixels XDimension**, e como alternar entre **barras preenchidas** e **barras vazias** sem reescrever nenhum código. Ao final você terá dois arquivos PNG—um com barras sólidas e outro com barras ocas—prontos para qualquer sistema postal que espere a simbologia Planet.

## Pré-requisitos

- .NET 6.0 ou posterior (o código também funciona em .NET Framework 4.7 +)  
- Pacote NuGet Aspose.BarCode para .NET (`Install-Package Aspose.BarCode`)  
- Conhecimento básico de C# (você verá por que usamos declarações `using` mais adiante)  
- Uma pasta gravável no disco onde os PNGs serão salvos  

Se você tem isso, podemos pular direto para a implementação.

## Etapa 1 – Configurar o Projeto e Adicionar a Biblioteca

Primeiro, crie um novo aplicativo console (ou qualquer projeto C#) e faça referência à biblioteca **Planet barcode generator**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Dica profissional:** No Visual Studio, clique com o botão direito no projeto → *Gerenciar Pacotes NuGet* → procure por **Aspose.BarCode** e clique em *Instalar*. Isso lhe dá acesso ao `BarcodeGenerator` e a todos os **parâmetros do BarcodeGenerator** que você precisará.

## Etapa 2 – Inicializar o Gerador de Código de Barras Planet

Agora realmente **criar planet barcode** instância do gerador e alimentá‑la com os dados que queremos codificar (`"123456"` neste exemplo). O enum `EncodeTypes.Planet` indica à biblioteca qual simbologia usar.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Por que isso importa:** A flag `EncodeTypes.Planet` aplica automaticamente o checksum correto e as regras de layout para o código de barras postal Planet, então você não precisa calculá‑los manualmente.

## Etapa 3 – Configurar X‑Dimension (Largura da Barra)

A maioria das impressoras espera que cada barra tenha um número específico de pixels. Aqui definimos os **pixels XDimension** para `4`, que é um valor comum para impressoras térmicas de 203 dpi.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Caso extremo:** Se você estiver mirando uma impressora de 300 dpi, talvez precise de `3` ou `5` pixels em vez disso. Ajuste esse valor com base na documentação do seu dispositivo.

## Etapa 4 – Salvar a Versão com Barras Preenchidas

Por padrão o gerador produz **barras preenchidas** (retângulos pretos sólidos). Vamos gravar isso no disco:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo que seu aplicativo possa gravar. Depois que esta linha for executada, você encontrará um arquivo PNG que se parece com um clássico código de barras Planet—perfeito para testes contra um scanner postal.

## Etapa 5 – Alternar para Barras Vazias

Às vezes os serviços postais exigem o estilo “barras vazias”, onde as barras são recortadas de um fundo branco em vez de pintadas de preto. A biblioteca expõe uma troca simples:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Definir `FilledBars` como `false` indica ao renderizador que inverta a lógica de preenchimento das barras. Não é necessário criar uma nova instância de `BarcodeGenerator`; basta ajustar os **parâmetros do BarcodeGenerator** existentes.

## Etapa 6 – Salvar a Versão com Barras Vazias

Finalmente, exporte a segunda imagem:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG distintos, cada um atendendo a um requisito visual diferente.

## Exemplo Completo Funcional

Juntando todas as peças, aqui está o programa completo, pronto para copiar e colar:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Saída esperada** (no console):

```
Both Planet barcode images have been generated successfully.
```

E em `C:\Barcodes\` você verá:

- `PostalPlanetFilledBars.png` – barras pretas sólidas  
- `PostalPlanetEmptyBars.png` – barras brancas com contornos pretos  

Abra‑as em qualquer visualizador de imagens; ambos devem estar em conformidade com a especificação Planet.

## Perguntas Frequentes & Dicas

### “Posso mudar o formato da imagem?”

Absolutamente. O método `Save` aceita `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, etc. Basta substituir `BarCodeImageFormat.Png` pelo formato desejado.

### “E se eu precisar de uma altura de código de barras diferente?”

Use `planetBarcode.Parameters.Barcode.BarHeight` (em pontos) para aumentar ou diminuir o tamanho vertical. Por exemplo:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### “Existe uma maneira de adicionar uma legenda legível por humanos?”

Sim. Defina a propriedade `CodeText` em `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### “Preciso descartar o gerador?”

O `BarcodeGenerator` implementa `IDisposable`. Envolva‑o em um bloco `using` se você estiver criando muitos códigos de barras em um loop:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### “E quanto ao tratamento de erros?”

Envolva as chamadas `Save` em um bloco `try…catch` para capturar `IOException` (problemas de disco) ou `ArgumentException` (parâmetros inválidos). Exemplo:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Recapitulação

Cobremos tudo que você precisa para **criar código de barras planet** imagens em C#:

1. Inicializar o **gerador de código de barras Planet** com seus dados.  
2. Ajustar os **pixels XDimension** para corresponder às especificações da impressora.  
3. Salvar um PNG com **barras preenchidas**.  
4. Alternar `FilledBars` para produzir **barras vazias**.  
5. Salvar o segundo PNG.  

A partir daqui você pode explorar mais **parâmetros do BarcodeGenerator**, experimentar outras simbologias (`EncodeTypes.Postnet`, `EncodeTypes.Code128`, etc.), ou integrar as imagens em um fluxo de trabalho de mailing.

---

**Pronto para o próximo passo?** Tente adicionar um QR code ao mesmo documento, ou gerar um lote de códigos de barras Planet a partir de uma lista CSV usando um loop `foreach`. A API Aspose.BarCode é flexível o suficiente para lidar com operações em massa, cores personalizadas e até saída vetorial SVG.

Se encontrar algum obstáculo, deixe um comentário abaixo ou consulte a documentação oficial do Aspose.BarCode para mergulhos mais profundos em recursos avançados. Feliz codificação!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar Código de Barras com Aspose - Definir Dimensões X & Y em Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Como criar imagens de código de barras code128 em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [Como criar código de barras code128 em Java e definir altura da barra](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}