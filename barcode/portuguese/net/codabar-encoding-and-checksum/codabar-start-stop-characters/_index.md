---
date: 2026-05-24
description: Aprenda como criar um código de barras codabar com caracteres de início
  e fim usando o Aspose.BarCode para .NET. Tutorial passo a passo de geração de código
  de barras para desenvolvedores.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Caracteres de Início/Fim do Codabar
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Criar código de barras Codabar com caracteres de início/fim no Aspose.BarCode
  para .NET
url: /pt/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras Codabar com Caracteres de Início/Fim no Aspose.BarCode para .NET

## Introdução

Neste tutorial você **criará imagens de código de barras codabar** que incluem caracteres de início/fim explícitos usando Aspose.BarCode para .NET. Seja construindo um sistema de inventário de varejo, um rastreador de amostras de laboratório ou uma solução de registros médicos, a simbologia numérica do Codabar depende desses símbolos de fronteira para garantir a leitura confiável. Nos próximos minutos cobriremos tudo, desde a configuração do ambiente até a gravação de arquivos PNG, para que você possa começar a gerar códigos de barras Codabar imediatamente.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.BarCode for .NET  
- **Em qual formato posso salvar o código de barras?** PNG (`BarCodeImageFormat.Png`)  
- **Preciso de licença para desenvolvimento?** Uma versão de teste gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso mudar os símbolos de início/fim?** Sim – use `CodabarSymbol.A`, `B`, `C` ou `D`.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é Codabar e por que os caracteres de início/fim são essenciais?

Codabar é uma simbologia de código de barras numérica amplamente usada em bibliotecas, saúde e gerenciamento de inventário. Os caracteres de início e fim (A‑D ou hífen) definem os limites do código de barras, permitindo que os scanners detectem onde os dados começam e terminam com 99,9 % de precisão de leitura.

## Por que usar Aspose.BarCode para .NET?

Aspose.BarCode suporta **mais de 30 simbologias de código de barras** e pode gerar imagens de até **10.000 × 10.000 px** sem carregar todo o documento na memória. Funciona em Windows, Linux e macOS, e é compatível com .NET Framework, .NET Core e .NET 5+—oferecendo flexibilidade em todas as plataformas modernas.

## Pré-requisitos

1. **Configuração do Ambiente** – Garanta um ambiente de desenvolvimento .NET funcional. Se precisar de orientação, consulte a [documentação](https://reference.aspose.com/barcode/net/).  
2. **Biblioteca Aspose.BarCode para .NET** – Baixe e instale a biblioteca a partir da [fonte oficial](https://releases.aspose.com/barcode/net/).  
3. **Conhecimento Básico de .NET** – Familiaridade com C# e uma IDE como Visual Studio, Rider ou VS Code.  
4. **IDE** – Visual Studio, Rider ou Visual Studio Code são todas adequadas.

Agora que cobrimos os pré-requisitos, vamos mergulhar no código real.

## Como gerar um código de barras Codabar com caracteres de início/fim?

Carregue o `BarcodeGenerator`, defina o tipo de codificação como **Codabar** e passe uma string de dados que já contenha os caracteres de início/fim necessários (por exemplo, “-12345-”). Em seguida, configure a X‑Dimension, opcionalmente escolha um símbolo de início/fim diferente e, finalmente, salve a imagem como PNG. Esse fluxo de ponta a ponta cria um código de barras pronto para uso em apenas algumas linhas de C#.

### Importar Namespaces

O `BarcodeGenerator` e os tipos relacionados vivem no namespace `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Etapa 1: Inicializar o Gerador de Código de Barras

`BarcodeGenerator` é a classe central que cria imagens de código de barras. Ela recebe o tipo de simbologia e a string de dados como argumentos do construtor.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Dica profissional:** O hífen (`-`) é um dos símbolos de início/fim válidos para Codabar. Você também pode usar `A`, `B`, `C` ou `D` dependendo dos requisitos da sua aplicação.

### Etapa 2: Definir a X‑Dimension (largura do elemento do código de barras)

`XDimension` controla a largura da barra mais estreita. Valores maiores melhoram a legibilidade em impressoras de baixa resolução, enquanto valores menores economizam espaço em etiquetas de alta densidade.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por que isso importa:** Ajustar `XDimension` ajuda a atender às especificações de scanners que frequentemente exigem uma largura mínima de barra de 0,25 mm.

### Etapa 3: Definir os Caracteres de Início e Fim

Codabar suporta quatro símbolos de início/fim (A, B, C, D). Abaixo estão exemplos para cada opção. Escolha aquele que corresponde à especificação do sistema com o qual você está integrando.

#### Definindo Início A e Fim A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Definindo Início B e Fim B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Definindo Início C e Fim C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Definindo Início D e Fim D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Você pode repetir a configuração para cada símbolo que precisar gerar; o exemplo abaixo salva quatro imagens separadas—uma para cada par de início/fim.

### Etapa 4: Salvar as Imagens do Código de Barras Geradas (PNG)

`Save` grava o código de barras em um arquivo. Usando `BarCodeImageFormat.Png` produz imagens PNG sem perdas, ideais para casos de uso na web e impressão.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Cada arquivo agora contém um **exemplo de código de barras codabar** com os símbolos de início/fim correspondentes.

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Solução |
|---------|----------------|---------|
| O código de barras aparece distorcido | X‑Dimension muito baixa para a resolução da impressora escolhida | Aumente `XDimension.Pixels` (ex.: para 3 ou 4) |
| O scanner não lê o início/fim | Símbolo de início/fim errado para o sistema alvo | Verifique o símbolo exigido (A‑D) e ajuste conforme necessário |
| Arquivo PNG está vazio ou corrompido | Caminho de saída inválido ou permissões de gravação insuficientes | Garanta que `path` aponte para uma pasta existente e que seu aplicativo tenha acesso de escrita |

## Perguntas Frequentes

**Q1: O que é Codabar e por que os caracteres de início e fim são importantes?**  
R: Codabar é uma simbologia de código de barras numérica usada em inventário, bibliotecas e saúde. Os caracteres de início/fim definem os limites do código de barras, garantindo que os scanners saibam onde os dados começam e terminam.

**Q2: Posso personalizar a aparência dos códigos de barras Codabar com Aspose.BarCode para .NET?**  
R: Sim. Além da X‑Dimension, você pode alterar cores, adicionar margens e exportar para PDF ou SVG usando a mesma API.

**Q3: Existem limitações nos códigos de barras Codabar em termos de codificação de dados?**  
R: Codabar suporta principalmente dados numéricos (0‑9) mais um conjunto limitado de caracteres especiais. Não é adequado para strings alfanuméricas completas.

**Q4: Aspose.BarCode para .NET é adequado para uso comercial e como posso obter uma licença?**  
R: Sim, está pronto para produção. Adquira uma licença na [página de compra da Aspose](https://purchase.aspose.com/buy).

**Q5: Onde posso buscar ajuda ou discutir problemas relacionados ao Aspose.BarCode para .NET?**  
R: Participe da comunidade no [fórum de suporte do Aspose.BarCode para .NET](https://forum.aspose.com/c/barcode/13) para obter assistência de engenheiros da Aspose e de outros desenvolvedores.

---

**Última atualização:** 2026-05-24  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Codabar Start Stop Characters and Checksum](/barcode/net/codabar-encoding-and-checksum/)
- [How to Add Checksum to Codabar Barcodes Using Aspose.BarCode for .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Comprehensive Tutorials and Examples of Aspose.BarCode for .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}