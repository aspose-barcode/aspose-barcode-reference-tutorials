---
category: general
date: 2026-08-22
description: Aprenda como definir dimensões para códigos de barras Mailmark em C#
  e salvá‑los como imagens PNG. Inclui código completo, explicações e dicas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: pt
lastmod: 2026-08-22
og_description: Como definir dimensões para códigos de barras Mailmark em C# e exportá-los
  como arquivos PNG. Siga o exemplo completo e evite armadilhas comuns.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Como definir dimensões para códigos de barras Mailmark em C# – guia passo
  a passo
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Como definir dimensões para códigos de barras Mailmark em C#
url: /pt/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir dimensões para códigos de barras Mailmark em C#

Se você precisa **definir dimensões** para um código de barras Mailmark em C#, este guia mostra os passos exatos. Você verá como configurar a X‑dimension e a altura das barras, e então salvar o código de barras como uma imagem PNG sem ferramentas adicionais.

Gerar códigos de barras postais é uma tarefa rotineira ao desenvolver software de etiquetas de correspondência, mas o tamanho padrão frequentemente não corresponde ao impressor ou aos requisitos de layout. Ao final deste tutorial você será capaz de controlar o tamanho do código de barras com precisão e produzir dois tipos válidos de Mailmark (C‑type e L‑type) prontos para impressão.

**O que você aprenderá**

* Como definir a X‑dimension (largura do módulo) e a altura das barras para um `BarcodeGenerator`.
* Como salvar o código de barras gerado como um arquivo PNG usando `BarCodeImageFormat`.
* Armadilhas comuns, como caminhos de pasta inválidos ou valores de dimensão não suportados.
* Dicas para reutilizar a mesma configuração em vários códigos de barras.

## Pré-requisitos

* .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.6+).
* O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).
* Familiaridade básica com a sintaxe C# e I/O de arquivos.

> **Dica profissional:** Instale o pacote com o comando CLI  
> `dotnet add package Aspose.BarCode` para manter seu projeto organizado.

## Etapa 1: Definir a pasta de saída

Antes de criar qualquer código de barras, você deve decidir onde os arquivos PNG serão gravados. Usar um caminho absoluto evita surpresas em diferentes máquinas.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Por que isso importa*: Se a pasta não existir, `Save` lança um `IOException`. A chamada `Directory.CreateDirectory` é idempotente — não faz nada se a pasta já existir.

## Etapa 2: Criar um código de barras Mailmark tipo C e **definir dimensões**

O Mailmark tipo C codifica uma string alfanumérica de 20 caracteres. Após inicializar o gerador, você pode **definir dimensões** através do objeto `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Por que escolher esses valores?

* **X‑dimension** controla a largura da barra mais estreita (um “módulo”). Um valor de `4` pixels produz um código de barras que é facilmente legível pela maioria das impressoras a laser, mantendo o tamanho do arquivo modesto.
* **BarHeight** determina o tamanho vertical das barras. `50` pixels é uma altura comum para etiquetas de correspondência padrão, mas você pode aumentá-la para formatos maiores.

> **Caso extremo:** Algumas impressoras exigem uma altura mínima de barra de 30 px. Definir a altura abaixo da capacidade da impressora pode causar códigos de barras ilegíveis.

## Etapa 3: Criar um código de barras Mailmark tipo L e **definir dimensões**

O tipo L usa uma string de dados mais longa (até 30 caracteres). A mesma abordagem de definição de dimensões se aplica.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Reutilizando a configuração

Se você gerar muitos códigos de barras com dimensões idênticas, considere extrair a configuração para um método auxiliar:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Chamar `ApplyStandardDimensions(mailmarkC)` e `ApplyStandardDimensions(mailmarkL)` reduz a duplicação e torna futuras alterações (por exemplo, mudar para módulos de 5 pixels) uma edição de uma linha.

## Etapa 4: Verificar os arquivos PNG gerados

Após executar o programa, abra os dois arquivos PNG em qualquer visualizador de imagens. Você deverá ver dois códigos de barras Mailmark distintos, cada um com 4 px por módulo e 50 px de altura.

*Saída esperada*

| Nome do arquivo               | Dimensões aproximadas (px) |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × module × N modules |
| `PostalMailmarkLType.png`     | 4 px × module × N modules |

A largura exata depende do comprimento dos dados codificados, mas a altura será consistentemente **50 px** porque definimos `BarHeight.Pixels`.

## Armadilhas comuns e como evitá‑las

| Problema                              | Sintoma                                      | Solução |
|---------------------------------------|----------------------------------------------|-----|
| Caminho de pasta inválido             | `IOException: Could not find a part of the path` | Use `Path.Combine` com `Environment.SpecialFolder` ou verifique a string do caminho. |
| X‑dimension definido como 0 ou negativo | O código de barras aparece como um bloco sólido | Garanta que `XDimension.Pixels` seja um inteiro positivo (mínimo 1). |
| `EncodeTypes.Mailmark` não suportado  | `ArgumentException` at generator construction | Confirme que você tem uma versão recente da biblioteca Aspose.BarCode que inclui suporte a Mailmark. |
| Salvando com formato de imagem errado | Arquivo PNG corrompido                       | Use `BarCodeImageFormat.Png` (ou `Jpeg` se precisar de um formato diferente). |

## Expandindo o exemplo

* **Tamanhos diferentes** – Altere `XDimension.Pixels` para 3 para um código de barras mais compacto, ou aumente `BarHeight.Pixels` para 70 para etiquetas maiores.
* **Geração em lote** – Percorra uma coleção de strings de dados, aplicando as mesmas configurações de dimensão a cada iteração.
* **Outros formatos de imagem** – Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` se seu fluxo de trabalho exigir.

## Conclusão

Agora você sabe **como definir dimensões** para códigos de barras Mailmark em C# e exportá-los como arquivos PNG. Ao configurar `XDimension.Pixels` e `BarHeight.Pixels` você controla o tamanho visual tanto dos códigos de barras tipo C quanto tipo L, garantindo que atendam às especificações da impressora e às restrições de layout.  

A partir daqui, você pode experimentar diferentes valores de dimensão, integrar o código em um sistema maior de etiquetas de correspondência ou gerar lotes de códigos de barras para operações de envio em massa.

---

*Próximos passos*: explore as **dimensões do BarcodeGenerator** para códigos QR, ou leia a documentação do Aspose.BarCode sobre **definir DPI** para impressões de alta resolução. Se precisar incorporar o código de barras em um PDF, combine esta abordagem com a biblioteca **Aspose.PDF** para uma solução completa de ponta a ponta.

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como definir borda para personalização de código de barras ITF-14](/barcode/english/net/itf-14-barcode-customization/)
- [Como configurar códigos de barras Patch Code com Aspose.BarCode para .NET](/barcode/english/net/patch-code-configuration/)
- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}