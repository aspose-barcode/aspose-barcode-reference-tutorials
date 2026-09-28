---
category: general
date: 2026-07-18
description: Gere código de barras com texto usando Aspose.BarCode para .NET. Aprenda
  como gerar códigos de barras PDF417, definir opções de macro e exportar imagens
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: pt
lastmod: 2026-07-18
og_description: Gere código de barras com texto em C# rapidamente. Este tutorial passo
  a passo mostra como gerar códigos de barras PDF417, configurar as definições de
  macro e salvar como PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Gerar código de barras com texto – Criação de Macro Master PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Gerar código de barras com texto – Guia completo de PDF417 Macro
url: /pt/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras com texto – Guia Completo de Macro PDF417

Já se perguntou **como gerar PDF417** códigos de barras que também incorporam texto personalizado? Neste tutorial você verá exatamente como **gerar código de barras com texto** usando Aspose.BarCode para .NET, e percorreremos cada configuração necessária para um símbolo Macro PDF417. Sem enrolação, apenas um exemplo completo e executável que você pode inserir em seu projeto hoje.

Cobriremos:

* O pacote NuGet necessário e as diretivas `using`.  
* Como criar um gerador de código de barras que inclui caracteres Unicode.  
* Definir o tamanho do módulo, a contagem de colunas e os IDs específicos de macro.  
* Salvar o resultado como um arquivo PNG e verificar a saída.  

Ao final, você terá uma imagem PNG pronta de um código de barras Macro PDF417 que pode ser incorporada em faturas, ingressos ou qualquer documento que precise de um segmento legível por máquina.

---

## Pré-requisitos

Antes de mergulharmos, certifique‑se de que você tem:

| Requisito | Motivo |
|-------------|--------|
| **.NET 6.0** ou posterior | Aspose.BarCode suporta .NET Standard 2.0+, então o .NET 6 oferece o runtime mais recente. |
| **Visual Studio 2022** (ou qualquer IDE C#) | Para edição e depuração facilitadas. |
| **Aspose.BarCode for .NET** pacote NuGet | A biblioteca que realmente cria o código de barras. Instale‑a com `dotnet add package Aspose.BarCode`. |
| **Permissão de gravação** na pasta de saída | O método `Save` precisa escrever o arquivo PNG. |

Se algum desses lhe for desconhecido, faça uma pausa e resolva‑os—caso contrário o código lançará exceções óbvias.

---

## Etapa 1 – Instalar e importar a biblioteca

Primeiro, adicione o pacote NuGet ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

Em seguida, traga os namespaces necessários para o escopo:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Dica profissional:** Se você estiver usando o Visual Studio, clique com o botão direito no projeto → *Manage NuGet Packages* → procure por *Aspose.BarCode* e instale a versão estável mais recente.

---

## Etapa 2 – Criar o gerador de código de barras com seu texto personalizado

A tarefa *principal* é **gerar código de barras com texto** que contenha caracteres especiais como “Å” e “©”. O construtor recebe o tipo de codificação e a string de dados bruta:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Por que isso importa: `EncodeTypes.MacroPdf417` indica ao Aspose que queremos a versão macro, que permite dividir uma mensagem grande em vários símbolos. A string de texto pode ser qualquer sequência UTF‑8; o Aspose lida com a conversão internamente.

---

## Etapa 3 – Ajustar a aparência básica (tamanho do módulo)

O “módulo” de um código de barras é o menor quadrado preto‑ou‑branco. Definir seu tamanho em pixels controla as dimensões gerais da imagem sem alterar a densidade dos dados:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se precisar de uma imagem maior para impressão, aumente esse valor para 4 ou 6. Apenas lembre‑se de que módulos maiores aumentam o tamanho final do PNG.

---

## Etapa 4 – Configurar opções específicas do Macro PDF417

Macro PDF417 adiciona dois identificadores que permitem a um scanner juntar vários símbolos. Normalmente você define:

| Propriedade | O que faz |
|----------|--------------|
| `Columns` | Número de colunas de dados por símbolo (afeta a largura). |
| `MacroPdf417FileID` | ID único para todo o arquivo macro (deve ser ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Índice do segmento atual (0‑254). |

Aqui está o código:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Observação de caso extremo:** `MacroPdf417FileID` deve ser o mesmo para todos os segmentos do mesmo arquivo lógico. Se você gerar vários segmentos, reutilize o mesmo ID ou terminará com símbolos não relacionados que não podem ser combinados.

---

## Etapa 5 – Salvar o código de barras como imagem PNG

Agora que tudo está configurado, grave a imagem no disco:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

O método `Save` cria automaticamente o PNG, tratando DPI e profundidade de cor para você. Após a execução, abra o arquivo para ver algo como isto:

![Exemplo de geração de código de barras com texto](/images/barcode-example.png){.center alt="Exemplo de geração de código de barras com texto"}

Se você não vir um código de barras, verifique novamente se a pasta existe e se sua aplicação tem permissão de gravação.

---

## Exemplo Completo, Pronto‑para‑Executar

Copie o trecho completo abaixo para um novo aplicativo console (`dotnet new console`) e execute‑o. Ele produzirá o PNG na pasta `C:\Barcodes` (crie a pasta primeiro).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Saída esperada** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

E o PNG exibirá um símbolo Macro PDF417 compacto contendo o texto “Åspóse.Barcóde©”.

---

## Perguntas Frequentes & Armadilhas

| Pergunta | Resposta |
|----------|--------|
| *Posso usar um formato de imagem diferente?* | Absolutamente—substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`. PNG é sem perdas, por isso usamos como padrão. |
| *E se eu precisar de mais de um segmento?* | Crie um novo `BarcodeGenerator` para cada segmento, mantenha `MacroPdf417FileID` idêntico e incremente `MacroPdf417SegmentID` (0‑254). |
| *Meu texto contém emojis—eles funcionarão?* | Aspose.BarCode suporta UTF‑8, então a maioria dos emojis funciona. Apenas garanta que o scanner de destino possa decodificá‑los; muitos scanners industriais lidam apenas com dados alfanuméricos. |
| *O código de barras está muito largo para a minha etiqueta.* | Reduza `Columns` ou aumente o tamanho do módulo. Menos colunas produzem um símbolo mais estreito, mas podem exigir uma impressora de DPI mais alto. |
| *Preciso de uma licença?* | Uma licença de avaliação gratuita funciona para testes, mas adiciona uma pequena marca d'água. Para produção, adquira uma licença para remover a marca d'água e desbloquear todos os recursos. |

---

## Próximos Passos

Agora que você sabe **como gerar PDF417** códigos de barras com texto personalizado, pode querer:

* **Decodificar** o código de barras em um aplicativo móvel usando `BarCodeReader` do Aspose.BarCode.  
* **Combinar** múltiplos segmentos macro em um único documento PDF para impressão em lote.  
* **Explorar outras simbologias** (QR, DataMatrix) com padrões de parâmetros semelhantes.  
* **Ajustar o nível de correção de erro** via `Pdf417.ErrorCorrectionLevel` para ambientes mais adversos.

Cada um desses tópicos se baseia nos mesmos conceitos centrais que você acabou de aprender, então a transição será tranquila.

---

## Conclusão

Percorremos uma solução completa, de ponta a ponta, que permite **gerar código de barras com texto** e, especificamente, **como gerar símbolos Macro PDF417** usando Aspose.BarCode para .NET. Ao definir a dimensão X, a contagem de colunas e os IDs de macro, você obtém controle total sobre tamanho, layout e manipulação de múltiplos segmentos. O PNG resultante pode ser impresso, incorporado em PDFs ou enviado a um scanner sem necessidade de conversões adicionais.

Experimente, ajuste os parâmetros e deixe o código de barras trabalhar para o seu caso de negócio. Se encontrar algum obstáculo, a documentação da Aspose e os fóruns da comunidade são excelentes recursos complementares. Feliz codificação!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como Gerar Códigos de Barras PDF417 – Codificação Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Como gerar código de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Como Gerar Código de Barras - Tipos de Código de Barras Unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}