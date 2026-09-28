---
category: general
date: 2026-08-09
description: Crie imagens de códigos de barras com um gerador de códigos de barras
  em C# e aprenda a gerar múltiplos códigos de barras com proporções personalizadas
  em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: pt
lastmod: 2026-08-09
og_description: Crie imagem de código de barras usando um gerador de códigos de barras
  em C#. Este tutorial mostra como gerar múltiplos códigos de barras, ajustar proporções
  e salvar arquivos PNG de forma eficiente.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Crie imagem de código de barras com gerador de códigos de barras C# – guia
  rápido
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Criar imagem de código de barras com gerador de código de barras C# – guia
url: /pt/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras com gerador de código de barras C# – guia

Se você precisa **criar imagem de código de barras** rapidamente, este guia mostra como fazer isso com um gerador de código de barras C#. Você aprenderá a gerar múltiplos códigos de barras, alterar a proporção e salvar cada imagem como um arquivo PNG.

Gerar imagens de códigos de barras é uma tarefa comum ao construir sistemas de inventário, terminais de ponto de venda ou etiquetas de envio. Ao final deste tutorial você terá dois arquivos PNG prontos para uso que demonstram diferentes proporções, e entenderá como estender a abordagem para qualquer número de códigos de barras.

## Prerequisites

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte C#)  
* Uma referência a uma biblioteca de códigos de barras que suporte DataBar Stacked Omnidirectional (por exemplo, **Aspose.BarCode for .NET**). Os trechos de código usam a API Aspose, mas os conceitos se aplicam a qualquer biblioteca com propriedades semelhantes.

Você não precisa de um banco de dados ou servidor web separado — esta é uma aplicação console simples.

## Passo 1: Configurar o projeto console

Crie um novo projeto console e adicione a biblioteca de códigos de barras via NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

O comando `dotnet add package` obtém a versão estável mais recente do **Aspose.BarCode**, que fornece a classe `BarcodeGenerator` usada posteriormente.

## Passo 2: Escrever o programa completo

Abra *Program.cs* e substitua seu conteúdo pelo exemplo completo abaixo. O programa cria uma **imagem de código de barras**, altera a proporção e salva dois arquivos PNG.

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
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Por que cada parte importa

* **Create barcode image** – O construtor `BarcodeGenerator` inicializa o objeto com a simbologia e os dados desejados.  
* **c# barcode generator** – A propriedade `Parameters` fornece controle total sobre as opções de renderização; definir `XDimension.Pixels` garante que cada barra fique nítida na tela.  
* **generate multiple barcodes** – Ao alterar `DataBar.AspectRatio` entre as gravações, a mesma instância do gerador produz duas imagens distintas sem recriar o objeto, o que é mais eficiente.

## Passo 3: Executar o programa e visualizar os resultados

Execute a aplicação:

```bash
dotnet run
```

Você deverá ver uma saída no console semelhante a:

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Abra a pasta `BarcodeOutputs`. Você encontrará dois arquivos PNG:

* **DatabarAspectRatio15.png** – um código de barras compacto adequado para etiquetas de altura limitada.  
* **DatabarAspectRatio30.png** – um código de barras mais alto que muitos scanners leem de forma mais confiável à distância.

Ambas as imagens estão prontas para serem incorporadas em PDFs, impressas em recibos ou enviadas para um aplicativo móvel.

## Passo 4: Estender a solução para gerar qualquer número de códigos de barras

O padrão mostrado acima escala facilmente:

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – O loop itera sobre um array de proporções, criando uma **imagem de código de barras** distinta para cada valor.  
* Ajuste o `EncodeTypes` ou a string codificada para gerar QR codes, Code 128 ou outras simbologias sem alterar a lógica circundante.

## Dicas práticas e armadilhas comuns

| Tip | Explanation |
|-----|-------------|
| **Reutilizar o mesmo gerador** | Reinicializar o `BarcodeGenerator` para cada imagem adiciona sobrecarga desnecessária. Alterar os parâmetros entre chamadas de `Save` é mais rápido e consome menos memória. |
| **Validar a pasta de saída** | Sempre chame `Directory.CreateDirectory` antes de salvar; caso contrário, `Save` lança uma `DirectoryNotFoundException`. |
| **Escolher uma X‑dimension apropriada** | Valores de pixel muito baixos (ex.: 1) podem tornar o código de barras ilegível em telas de baixa resolução. Valores entre 2 e 3 funcionam bem na maioria das impressoras. |
| **Prestar atenção à codificação** | O GS1 DataBar espera um prefixo `(01)` para GTIN. Se você omitir os parênteses, a biblioteca pode gerar um código de barras inválido. |
| **Testar com um scanner real** | A inspeção visual não é suficiente. Teste os arquivos PNG com o hardware de scanner real que você pretende usar. |

## Saída esperada (descrição visual)

*Ambos os arquivos PNG exibem um código de barras DataBar Stacked Omnidirectional escuro sobre fundo claro. A versão com proporção 15 é mais curta, enquanto a versão com proporção 30 é aproximadamente duas vezes mais alta.*

Se você incorporar as imagens em um documento, elas serão renderizadas nítidas porque definimos `XDimension.Pixels = 2`.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras** usando um **gerador de código de barras C#**, e pode **gerar múltiplos códigos de barras** ajustando a proporção ou qualquer outro parâmetro. O exemplo completo e executável demonstra boas práticas, como reutilizar a instância do gerador, lidar com diretórios de saída e verificar a criação dos arquivos.

Em seguida, você pode explorar:

* Adicionar cores personalizadas com `generator.Parameters.Barcode.Color` (palavra‑chave secundária: **c# barcode generator**)  
* Exportar para outros formatos como JPEG ou SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Integrar a lógica de criação de códigos de barras em uma Web API para servir imagens sob demanda (palavra‑chave secundária

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar Barcode PNG – Proporção do DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [tutorial de gerador de barcode c# – Personalizar proporções de código 16K com Aspose.BarCode para .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}