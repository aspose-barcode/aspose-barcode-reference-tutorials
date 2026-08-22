---
category: general
date: 2026-08-22
description: Aprenda como gerar código de barras PDF417 em C# com Aspose.BarCode,
  definir o tamanho do código de barras, ajustar as colunas e habilitar o modo compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: pt
lastmod: 2026-08-22
og_description: Gere código de barras PDF417 em C# com Aspose.BarCode. Este guia mostra
  como definir o tamanho do código de barras, controlar as colunas e habilitar o modo
  compacto para uma imagem menor.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Gerar código de barras PDF417 em C# – definir tamanho, colunas e modo compacto
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Como gerar código de barras PDF417 em C# e definir o tamanho do código de barras
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# e definir o tamanho do código de barras

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia o conduzirá por todo o processo. Você verá exatamente **como gerar PDF417** com Aspose.BarCode, ajustar o **tamanho do código de barras**, e produzir um PNG compacto que pode ser incorporado em relatórios ou aplicativos móveis.

Criar um código de barras não requer um editor gráfico separado. Ao final deste tutorial você terá um método C# totalmente funcional que produz uma imagem PDF417 com as dimensões exatas que você precisa, pronta para processamento posterior.

## O que você aprenderá

* Instalar e referenciar a biblioteca Aspose.BarCode.
* Criar um gerador de código de barras PDF417 e especificar o texto codificado.
* **Definir o tamanho do código de barras** configurando a X‑dimension e a contagem de colunas.
* Habilitar o modo compacto (truncado) para reduzir o símbolo.
* Salvar o resultado como um arquivo PNG.
* Solucionar problemas comuns, como códigos ilegíveis e imagens excessivamente grandes.

### Pré-requisitos

* .NET 6.0 ou posterior (a API funciona também com .NET Framework 4.6+).
* Familiaridade básica com C# e Visual Studio (ou qualquer IDE C#).
* Uma licença válida do Aspose.BarCode (a avaliação gratuita funciona para testes).

> **Dica profissional:** Se você planeja gerar muitos códigos de barras em um loop, reutilize uma única instância de `BarcodeGenerator` e altere apenas a propriedade `CodeText`. Isso reduz as alocações de memória.

## Gerar código de barras PDF417 com Aspose.BarCode

O primeiro passo é instanciar o `BarcodeGenerator` para a simbologia PDF417. Este objeto é o ponto de entrada para todas as operações de código de barras.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Por que isso importa*: `EncodeTypes.Pdf417` indica à biblioteca que deve usar o padrão PDF417, que suporta grandes volumes de dados e correção de erros. O construtor também aceita os dados que você deseja codificar, eliminando a necessidade de uma atribuição separada de `CodeText` posteriormente.

## Definir tamanho do código de barras e contagem de colunas

Os símbolos PDF417 consistem em linhas e colunas de pequenos módulos retangulares. Controlar a largura do módulo (X‑dimension) e o número de colunas permite ajustar finamente as dimensões gerais.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explicação*:  
* **X‑dimension** (`Pixels`) determina quão largo cada módulo é. Valores menores produzem um código de barras mais compacto, enquanto valores maiores aumentam a legibilidade em scanners de baixa resolução.  
* **Columns** controla o layout horizontal. Menos colunas tornam o código de barras mais alto; mais colunas o tornam mais largo. Ajuste essas duas configurações juntas para alcançar o **tamanho do código de barras** exato que você precisa.

## Habilitar modo compacto para um código de barras menor

O PDF417 inclui um modo “compacto” (ou truncado) que remove preenchimentos desnecessários e reduz a área total. Isso é especialmente útil quando você tem espaço de tela limitado.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Por que habilitar a truncagem?*  
Quando `Truncate` está `true`, o gerador omite o padrão de parada e alguns codewords de correção de erro que não são necessários na maioria dos cenários de leitura. A imagem resultante fica aproximadamente 15‑20 % menor sem sacrificar a integridade dos dados para casos de uso típicos.

## Salvar o código de barras como imagem PNG

Depois de configurar o tamanho e o modo, grave o código de barras no disco. PNG é sem perdas, garantindo que as bordas dos módulos permaneçam nítidas.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

O arquivo `CompactPdf417.png` conterá um símbolo PDF417 nítido que corresponde às dimensões que você definiu nas etapas anteriores.

### Saída esperada

Abrir o PNG salvo deve exibir um código de barras PDF417 orientado verticalmente, consistindo de três colunas, cada módulo com 2 px de largura, e um tamanho total de aproximadamente **120 × 240 px** (largura × altura). Ler a imagem com qualquer leitor padrão de PDF417 retorna o texto original “Sample text for PDF417”.

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| Código de barras ilegível | X‑dimension muito pequena para o scanner | Aumente `XDimension.Pixels` para 3 ou 4 |
| Imagem muito larga para a UI | Muitas colunas definidas | Reduza `Pdf417.Columns` ou habilite `Truncate` |
| Exceção `ArgumentOutOfRangeException` | Contagem de colunas negativa ou zero | Garanta que `Columns` seja um inteiro positivo (mínimo 1) |
| Arquivo PNG está vazio | Caminho de saída não existe ou falta permissão de gravação | Verifique se o diretório existe e se o aplicativo tem direitos de gravação |

> **Dica profissional:** Use `barcodeGenerator.ValidateParameters()` antes de chamar `Save()` para capturar erros de configuração antecipadamente.

## Exemplo completo e executável

Abaixo está um programa de console autônomo que incorpora todas as etapas acima. Copie-o para um novo projeto C#, restaure o pacote NuGet Aspose.BarCode e execute-o para ver o resultado.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Executar o programa** produz `CompactPdf417.png` no diretório de trabalho do executável. Leia a imagem com um aplicativo móvel (por exemplo, “Barcode Scanner”) para verificar se o texto codificado corresponde à string de origem.

## Próximos passos e tópicos relacionados

* **Aumentar o nível de correção de erro** – ajuste `Pdf417.ErrorLevel` para ambientes com leituras ruidosas.  
* **Alterar a orientação** – defina `Pdf417.Rotate` para `RotationAngle.Rotate90` se precisar de um layout horizontal.  
* **Incorporar o código de barras em um PDF** – combine Aspose.PDF com Aspose.BarCode para colocar a imagem diretamente em um documento.  
* **Gerar outros códigos de barras 2‑D** – a mesma classe `BarcodeGenerator` suporta códigos DataMatrix, QR e Aztec; basta trocar `EncodeTypes.Pdf417` pela simbologia desejada.

Ao dominar as técnicas de **gerar código de barras PDF417**, você pode automatizar bilhetagem, rotulagem de inventário e transmissão segura de dados em uma ampla gama de aplicações .NET.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C#, definir **precisamente o tamanho do código de barras**, configurar colunas, habilitar o modo compacto e salvar o resultado como PNG. Aplique essas configurações para atender a qualquer restrição de UI ou requisito de leitura, e estenda a abordagem para outros formatos de código de barras conforme necessário. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 – Codificação Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Como criar código de barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}