---
category: general
date: 2026-09-10
description: Crie código de barras PDF417 em C# rapidamente. Aprenda como habilitar
  o modo compacto, definir colunas e gerar um PNG com BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: pt
lastmod: 2026-09-10
og_description: Crie um código de barras PDF417 em C# ativando o modo compacto, definindo
  colunas e salvando como PNG. Siga o guia completo passo a passo.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Criar código de barras PDF417 em C# – tutorial de modo compacto
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Como criar código de barras PDF417 em C# com modo compacto
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 em C# com modo compacto

Se você precisa **criar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você verá como **ativar o modo compacto**, definir o número de colunas e salvar o resultado como uma imagem PNG usando a biblioteca BarcodeGenerator para C#.

Gerar um código de barras é uma necessidade comum para rastreamento de inventário, sistemas de bilhetagem e aplicativos de escaneamento móvel. Ao final deste tutorial você terá um exemplo autônomo e executável que produz um código de barras PDF417 compacto pronto para uso em produção.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior instalado (o código também funciona com .NET Framework 4.7+)
* Uma versão recente da biblioteca **BarcodeGenerator** (por exemplo, Aspose.BarCode for .NET)
* Uma IDE ou editor como Visual Studio 2022 ou VS Code
* Permissão de escrita em uma pasta onde o PNG será salvo

Nenhum pacote NuGet adicional é necessário além da própria biblioteca de código de barras.

## Etapa 1: Criar um gerador de código de barras PDF417

O primeiro passo é instanciar um objeto `BarcodeGenerator` com o enum `EncodeTypes.Pdf417` e o texto que você deseja codificar. Esse objeto controla todo o processo de geração.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Por que isso importa*: O valor `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417, enquanto o segundo argumento fornece a carga útil. Você pode substituir `"Compact mode"` por qualquer cadeia alfanumérica que precise codificar.

## Etapa 2: Definir a dimensão X (largura do módulo)

A dimensão X controla a largura de cada quadradinho (módulo) no código de barras. Valores menores produzem uma imagem mais compacta, o que é útil quando o espaço é limitado.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Um valor de `2` pixels é um bom equilíbrio entre legibilidade e compacidade para a maioria dos scanners baseados em tela.

## Etapa 3: Definir o número de colunas

O PDF417 pode organizar os dados em uma grade de linhas e colunas. Ajustar a contagem de colunas altera a proporção do código de barras.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Definir **como definir colunas** para `3` gera um código de barras curto e largo que se encaixa bem em uma etiqueta. Você pode experimentar valores de `1` a `30` dependendo da quantidade de dados e do scanner alvo.

## Etapa 4: Ativar o modo compacto

O modo compacto remove linhas de preenchimento desnecessárias, tornando o código de barras menor sem perder a integridade dos dados. Esta é a etapa chave para um **PDF417 compacto**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Quando `Truncate` está `true`, a biblioteca calcula automaticamente o número mínimo de linhas necessárias para armazenar os dados, por isso a imagem final parece “apertada”.

## Etapa 5: Salvar o código de barras gerado como imagem PNG

Por fim, grave o código de barras em um arquivo. PNG preserva as bordas nítidas necessárias para um escaneamento confiável.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo ao qual sua aplicação tenha permissão de escrita. Após a execução, você encontrará um arquivo `CompactPdf417.png` contendo o código de barras.

### Código‑fonte completo

Juntando todas as etapas, você obtém um programa único, pronto‑para‑executar:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Executar este programa gera `CompactPdf417.png` na mesma pasta do executável. Abra a imagem com qualquer visualizador; você deverá ver um código de barras PDF417 denso e de alto contraste pronto para escaneamento.

## Como ativar o modo compacto em outros cenários

* **Geração em lote** – Ao criar muitos códigos de barras, defina `Truncate` uma vez no gerador e reutilize‑o para cada nova carga útil.
* **Formatos de imagem diferentes** – O mesmo método `Save` funciona com `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` se precisar de outro tipo de arquivo.
* **Contagem de colunas dinâmica** – Se o comprimento da string codificada variar, calcule uma contagem de colunas ótima com base no tamanho da string e na resolução do scanner.

## Como definir colunas para casos de uso específicos

* **Impressão de etiquetas** – Use uma contagem baixa de colunas (ex.: `2`‑`5`) para manter o código de barras curto o suficiente para caber em etiquetas estreitas.
* **Escaneamento móvel** – Contagens mais altas (`10`‑`15`) produzem códigos de barras mais altos, que são mais fáceis de focar com câmeras de telefone.
* **Compromisso de correção de erros** – Mais colunas reduzem o número de linhas, o que pode afetar a correção de erros embutida no código de barras. Teste com seu scanner alvo para encontrar o ponto ideal.

## Armadilhas comuns e dicas de especialista

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| Código de barras ilegível | Dimensão X muito baixa (ex.: `1` pixel) | Aumente `XDimension.Pixels` para pelo menos `2` |
| Imagem muito grande | Colunas definidas muito altas para uma carga curta | Reduza `Pdf417.Columns` ou habilite `Truncate` |
| Arquivo PNG em branco | Pasta de saída não existe ou falta permissão de escrita | Garanta que o diretório exista e que o processo tenha direitos de escrita |
| Scanner relata “dados corrompidos” | Truncate desativado ao usar muitas colunas | Habilite `Truncate` ou diminua a contagem de colunas |

## Verificando o resultado

Você pode validar o código de barras com qualquer aplicativo scanner de PDF417 (existem muitos apps gratuitos para Android/iOS). Abra `CompactPdf417.png` no app e confirme que o texto decodificado corresponde à carga original (“Compact mode”). Se o texto divergir, verifique novamente a flag `Truncate` e as configurações de colunas.

## Próximos passos

* **Integrar com ASP.NET Core** – Retorne o PNG diretamente de uma ação de controlador ao invés de salvar no disco.
* **Adicionar texto legível** – Use `barcodeGenerator.Parameters.Barcode.CodeTextParameters` para exibir a string codificada abaixo do código de barras.
* **Explorar outras simbologias** – A mesma classe `BarcodeGenerator` suporta QR, Code128, DataMatrix e mais. Troque `EncodeTypes` para experimentá‑las.

---

### Conclusão

Agora você sabe como **criar código de barras PDF417** em C# enquanto **ativa o modo compacto**, controla **como definir colunas** e usa a API **barcode generator C#** para **gerar um código de barras** que atende a restrições de tamanho do mundo real. Aplique essas etapas a qualquer projeto .NET que precise de códigos de barras compactos e de alta densidade, e estenda o padrão a outros formatos de código de barras conforme necessário. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}