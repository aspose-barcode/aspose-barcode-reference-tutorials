---
category: general
date: 2026-07-18
description: Crie código de barras RM4SCC em C# rapidamente; aprenda como definir
  a altura do código de barras e também gerar código de barras Planet com dimensões
  personalizadas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- generate planet barcode
- how to set barcode height
language: pt
lastmod: 2026-07-18
og_description: Crie código de barras RM4SCC em C# e descubra como definir a altura
  do código de barras. Veja também como gerar o código de barras Planet com a mesma
  biblioteca.
og_image_alt: Screenshot of a generated RM4SCC barcode with custom height in C#
og_title: Criar código de barras RM4SCC em C# – Defina a altura personalizada rapidamente
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create RM4SCC barcode in C# quickly; learn how to set barcode height
    and also generate Planet barcode with custom dimensions.
  headline: Create RM4SCC Barcode in C# – Full Guide to Set Height
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Criar código de barras RM4SCC em C# – Guia completo para definir a altura
url: /pt/python-java/general/create-rm4scc-barcode-in-c-full-guide-to-set-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras RM4SCC em C# – Guia Completo para Definir a Altura

Já precisou **criar código de barras RM4SCC** em um aplicativo .NET, mas não sabia como controlar seu tamanho? Você não está sozinho. Seja construindo um sistema de correspondência ou um painel de logística, obter a altura correta do código de barras pode ser a diferença entre uma leitura bem‑sucedida e uma falha.

Neste tutorial vamos percorrer todo o processo: desde a instalação da biblioteca, até **gerar código de barras Planet** como exemplo lado a lado, e finalmente **como definir a altura do código de barras** para ambos os tipos. Ao final, você terá um aplicativo console pronto‑para‑executar que gera arquivos PNG com as dimensões exatas que você precisa.

---

## O Que Você Precisa

- **.NET 6 SDK** (ou qualquer versão recente do .NET) – o código também funciona no .NET Framework, mas o .NET 6 é o ponto ideal.  
- **Aspose.BarCode for .NET** pacote NuGet – esta é a biblioteca que fornece a classe `BarcodeGenerator`.  
- Um conhecimento básico de C# – manteremos a sintaxe amigável para iniciantes.  
- Uma IDE ou editor de texto (Visual Studio, VS Code, Rider—escolha o que preferir).

> **Dica profissional:** Se você estiver em um pipeline CI/CD, adicione a referência NuGet no seu `.csproj` para que a compilação nunca esqueça a dependência.

---

## Etapa 1: Configurar o Projeto

Abra um terminal e crie um novo projeto console:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

É isso – seu projeto agora referencia a biblioteca que alimenta tudo que vem a seguir.

### Adicionar as Diretivas Using

Abra `Program.cs` e cole o seguinte no topo:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, for clarity
```

Esses namespaces nos dão acesso ao `BarcodeGenerator` e ao enum de formato de imagem que usaremos mais adiante.

---

## Etapa 2: Definir um Método Auxiliar para Salvar Imagens

Para evitar repetir a mesma lógica de salvamento, vamos encapsulá‑la em um pequeno método. Isso também demonstra **como definir a altura do código de barras** mais adiante.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string fileName)
{
    // Ensure the output directory exists
    var dir = System.IO.Path.GetDirectoryName(fileName);
    if (!System.IO.Directory.Exists(dir))
        System.IO.Directory.CreateDirectory(dir);

    // Save as PNG – you can switch to JPEG, BMP, etc.
    generator.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved: {fileName}");
}
```

> **Por que isso importa:** Centralizar a lógica de salvamento significa que você só precisa mudar o formato ou a pasta em um único lugar caso os requisitos mudem.

---

## Etapa 3: Gerar um Código de Barras Planet (a parte “gerar código de barras planet”)

Antes de mergulharmos nos detalhes do RM4SCC, vamos criar um **código de barras Planet**. Isso fornece uma verificação visual rápida de que a biblioteca está funcionando.

```csharp
// Create a Planet barcode with default height
var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // X‑dimension controls the narrow bar width; 4 px is a good default
    XDimension = { Pixels = 4 }
};
SaveBarcode(planetDefault, "output/PlanetDefault.png");

// Create a Planet barcode with an explicit 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    XDimension = { Pixels = 4 },
    BarHeight = { Pixels = 100 } // <-- how to set barcode height
};
SaveBarcode(planetFixed, "output/PlanetHeight100.png");
```

**Saída esperada:** Dois arquivos PNG aparecem na pasta `output` — um com a altura calculada automaticamente pela biblioteca, o outro exatamente 100 px de altura.

---

## Etapa 4: Criar Código de Barras RM4SCC – Objetivo Principal

Agora, a estrela do show: **criar código de barras RM4SCC**. RM4SCC é o Royal Mail 4‑State Code, amplamente usado no sistema postal do Reino Unido.

```csharp
// RM4SCC with default (auto) height
var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    XDimension = { Pixels = 4 }
};
SaveBarcode(rm4sccDefault, "output/RM4SCCDefault.png");

// RM4SCC with an explicit 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    XDimension = { Pixels = 4 },
    BarHeight = { Pixels = 100 } // <-- how to set barcode height
};
SaveBarcode(rm4sccFixed, "output/RM4SCCHeight100.png");
```

**O que você verá:**  
- `RM4SCCDefault.png` – a biblioteca decide uma altura confortável com base na dimensão X.  
- `RM4SCCHeight100.png` – um código de barras nítido de 100 pixels de altura pronto para impressão em envelopes.

> **Por que definir a altura?** Algumas impressoras de etiquetas exigem uma altura mínima de barra para leitura confiável. Ao fixar a altura, você garante conformidade em diferentes dispositivos.

---

## Etapa 5: Entendendo as Configurações de Altura (Respondendo “como definir a altura do código de barras”)

Tanto os exemplos Planet quanto RM4SCC usam a mesma propriedade:

```csharp
generator.BarHeight.Pixels = <desiredHeight>;
```

- **`BarHeight`** é um objeto `BarHeight` que agrupa várias unidades de medida (pixels, milímetros, polegadas).  
- **`.Pixels`** é a unidade mais direta para saída orientada a tela, mas você também pode usar `.Millimeters` ou `.Inches` se estiver direcionando mídia impressa.

### Casos de Borda & Dicas

| Situação | Abordagem Recomendada |
|-----------|----------------------|
| **Dimensão X muito pequena (ex.: 1 px)** | Aumente `BarHeight` para manter o código de barras legível. |
| **Impressão em impressoras de etiquetas de alta resolução** | Use `.Millimeters` para dimensionamento independente de dispositivo. |
| **Tipos de código de barras misturados em uma única imagem** | Defina `BarHeight` *depois* de `XDimension` para cada gerador, evitando herança acidental. |
| **Dados dinâmicos (ex.: códigos inseridos pelo usuário)** | Envolva a criação do gerador em um método que aceita parâmetros `code` e `height`. |

---

## Etapa 6: Exemplo Completo Funcional

Abaixo está um programa único e autocontido que você pode copiar‑colar em `Program.cs`. Ele inclui tudo, desde a configuração do projeto até a gravação das imagens.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

class Program
{
    static void Main()
    {
        string outputDir = "output/";

        // Helper ensures folder exists and logs the save
        void Save(BarcodeGenerator gen, string file) => SaveBarcode(gen, file);

        // ---------- Planet barcode ----------
        var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            XDimension = { Pixels = 4 }
        };
        Save(planetDefault, $"{outputDir}PlanetDefault.png");

        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 } // how to set barcode height
        };
        Save(planetFixed, $"{outputDir}PlanetHeight100.png");

        // ---------- RM4SCC barcode ----------
        var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            XDimension = { Pixels = 4 }
        };
        Save(rm4sccDefault, $"{outputDir}RM4SCCDefault.png");

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 } // how to set barcode height
        };
        Save(rm4sccFixed, $"{outputDir}RM4SCCHeight100.png");

        Console.WriteLine("All barcodes generated!");
    }

    static void SaveBarcode(BarcodeGenerator generator, string fileName)
    {
        var dir = System.IO.Path.GetDirectoryName(fileName);
        if (!System.IO.Directory.Exists(dir))
            System.IO.Directory.CreateDirectory(dir);

        generator.Save(fileName, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved: {fileName}");
    }
}
```

Execute com:

```bash
dotnet run
```

Você deverá ver a saída no console confirmando cada arquivo salvo, e a pasta `output` conterá quatro PNGs correspondentes aos nomes mostrados acima.

---

## Conclusão

Agora você sabe **como criar código de barras RM4SCC** em C# e controlar suas dimensões com apenas algumas atribuições de propriedade. Também cobrimos **gerar código de barras Planet** como verificação rápida, e exploramos as nuances de **como definir a altura do código de barras** para diferentes cenários de impressão.

Próximos passos? Experimente trocar o enum `EncodeTypes` por outras simbologias (Code128, QR, DataMatrix) e experimente `BarHeight` em milímetros para impressoras de alta resolução. Se precisar incorporar o código de barras em um PDF, combine Aspose.BarCode com Aspose.PDF — outra combinação poderosa.

Tem perguntas ou quer compartilhar suas próprias adaptações? Deixe um comentário abaixo e feliz codificação!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}