---
category: general
date: 2026-10-12
description: Criar imagem de código de barras em C# usando Aspose.BarCode em minutos.
  Este exemplo passo a passo de gerador de código de barras em C# mostra como definir
  proporções e salvar arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: pt
lastmod: 2026-10-12
og_description: Crie imagem de código de barras c# instantaneamente. Siga este exemplo
  de gerador de código de barras c# para produzir códigos de barras PNG de alta qualidade
  com proporções personalizadas.
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: Criar imagem de código de barras c# – guia rápido com Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Como criar imagem de código de barras em C# com Aspose.BarCode
url: /pt/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras C# com Aspose.BarCode

Se você precisa **criar imagem de código de barras c#** rapidamente, este guia o conduz por um exemplo completo e executável. Seja construindo um sistema de etiquetas de envio ou um scanner de inventário, os passos abaixo mostram exatamente como configurar um código de barras DataBar Stacked Omnidirectional, ajustar seus parâmetros visuais e salvar o resultado como um arquivo PNG.

Você também verá um **exemplo de gerador de código de barras c#** que demonstra a alteração da proporção de aspecto em tempo real, permitindo produzir múltiplas variações sem reescrever o código. Nenhuma documentação externa é necessária — basta copiar, colar e executar.

## O que você precisará

* .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
* O pacote NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Uma pasta onde os arquivos PNG gerados serão gravados (substitua `YOUR_DIRECTORY` no código)

Esses pré-requisitos garantem que o **exemplo de gerador de código de barras c#** seja executado em qualquer máquina de desenvolvimento moderna com Windows, Linux ou macOS.

## Como criar imagem de código de barras c# usando Aspose.BarCode

O processo consiste em quatro etapas curtas: instanciar o gerador, definir o tamanho do módulo, configurar a proporção de aspecto e, finalmente, salvar a imagem. Cada etapa é explicada para que você entenda *por que* isso importa, não apenas *o que* digitar.

### Etapa 1 – Inicializar o gerador de código de barras

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**Por que isso importa:** O construtor `BarcodeGenerator` recebe dois argumentos: a simbologia do código de barras (`EncodeTypes.DatabarStackedOmniDirectional`) e a string de dados bruta. O prefixo `(01)` informa ao scanner que os 14 dígitos seguintes representam um identificador GTIN‑14, que é um requisito comum no varejo e na logística.

### Etapa 2 – Definir o tamanho do módulo (dimensão X)

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** A dimensão X controla a largura da barra mais fina (o “módulo”). Um valor de `2` pixels produz um código de barras nítido e de alta resolução que permanece legível após o redimensionamento. Se precisar de um código de barras maior para um cartaz, aumente esse valor proporcionalmente.

### Etapa 3 – Salvar a primeira imagem com proporção de aspecto 15

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Por que isso importa:** Os símbolos DataBar suportam uma *proporção de aspecto* que influencia a relação altura‑largura. Uma proporção de `15` é o padrão para muitas aplicações de varejo e produz um código de barras compacto, quase quadrado, que cabe facilmente em etiquetas pequenas.

### Etapa 4 – Alterar a proporção de aspecto para 30 e salvar uma segunda imagem

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**Por que isso importa:** Aumentar a proporção de aspecto para `30` estica o código de barras verticalmente, melhorando a legibilidade em scanners de baixa resolução ou em etiquetas que são mais altas que largas. Como a mesma instância `BarcodeGenerator` é reutilizada, você evita alocar um novo objeto para cada variação — um padrão eficiente para processamento em lote.

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar para uma aplicação console. Ele inclui as diretivas `using` necessárias, tratamento de erros e comentários que explicam cada linha.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### Saída esperada

Executar o programa cria dois arquivos PNG:

| Nome do arquivo | Proporção de aspecto | Uso típico |
|-----------------|----------------------|------------|
| `DatabarAspectRatio15.png` | 15 | Etiqueta de varejo padrão |
| `DatabarAspectRatio30.png` | 30 | Etiqueta alta ou scanner de baixa resolução |

Ambas as imagens contêm um código de barras DataBar Stacked Omnidirectional nítido que codifica o valor GTIN‑14 `12345678901231`. Você pode abrir os PNGs em qualquer visualizador de imagens para verificar a qualidade visual.

![Sample barcode image created with C# using Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="Imagem de exemplo de código de barras criada com C# usando Aspose.BarCode"}

*O texto alternativo acima inclui a palavra‑chave principal, ajudando tanto os motores de busca quanto os leitores de tela.*

## Considerações adicionais e dicas de boas práticas

* **Formatos suportados** – `BarCodeImageFormat` suporta PNG, JPEG, BMP, GIF e TIFF. PNG é sem perdas, tornando‑a a escolha mais segura para a leitura posterior.
* **Personalização de cores** – Você pode alterar as cores de primeiro plano/fundo via `generator.Parameters.Barcode.ForegroundColor` e `BackgroundColor`. Isso é útil ao imprimir em mídia colorida.
* **Geração em lote** – Para grandes inventários, envolva a lógica de salvamento em um loop `foreach` que lê os dados do produto de um arquivo CSV. Reutilizar a mesma instância `BarcodeGenerator` reduz a pressão de memória.
* **Tratamento de erros** – O bloco `try/catch` no exemplo completo captura problemas como strings de dados inválidas ou erros de permissão de gravação, que são comuns quando o diretório de destino não existe.
* **Desempenho** – Definir `XDimension.Pixels` antes da primeira chamada `Save` garante que o renderizador calcule o tamanho do bitmap apenas uma vez por mudança de proporção de aspecto.

## Conclusão

Agora você sabe como **criar imagem de código de barras c#** com Aspose.BarCode, ajustar a dimensão X, alternar proporções de aspecto e salvar arquivos PNG em um único bloco de código reutilizável. Este **exemplo de gerador de código de barras c#** cobre as variações mais comuns que você encontrará ao gerar símbolos DataBar Stacked Omnidirectional para aplicações de varejo ou logística.

## O que vem a seguir?

* Explore outras simbologias como `EncodeTypes.Code128` ou `EncodeTypes.QR` para ampliar sua solução.
* Experimente `generator.Parameters.Barcode.ImageMargin` para adicionar espaço em branco ao redor do código de barras.
* Integre os PNGs gerados em faturas PDF usando Aspose.PDF, ou incorpore‑os diretamente em relatórios HTML.

Sinta‑se à vontade para adaptar o código ao seu fluxo de trabalho específico — seja precisando de uma única imagem por produto ou de uma exportação em massa de milhares de códigos de barras, o padrão mostrado aqui escala de forma eficiente.

---

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar imagem de código de barras com Aspose.Barcode em C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Exemplo de Gerador de Código de Barras em C# – Definir Colunas, Linhas e Exportar Imagem](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Como criar imagem de código de barras postal em C# usando Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}