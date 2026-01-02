---
date: 2026-01-02
description: Aprenda a usar o gerador de código de barras Aztec com Aspose.BarCode
  para .NET – guia passo a passo sobre como definir o modo de símbolo Aztec (Auto,
  FullRange, Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: gerador de código de barras aztec – dominando o modo de símbolo Aztec com Aspose.BarCode
  para .NET
url: /pt/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – Dominando o Modo de Símbolo Aztec com Aspose.BarCode para .NET

Se você deseja incorporar recursos poderosos de geração de códigos de barras em suas aplicações .NET, o **barcode generator aztec** da Aspose.BarCode para .NET é uma solução fantástica. Neste tutorial vamos mergulhar profundamente no Modo de Símbolo Aztec, mostrar **como definir opções aztec** e guiá‑lo através de exemplos práticos de código que você pode inserir diretamente em seu projeto.

## Respostas Rápidas
- **Qual é a classe principal?** `BarcodeGenerator` de `Aspose.BarCode.Generation`.
- **Quais Modos de Símbolo estão disponíveis?** Auto, FullRange, Compact e Rune.
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.
- **Posso alterar o texto do código?** Sim, defina `gen.CodeText` antes de salvar.
- **Quais formatos de imagem são suportados?** PNG, JPEG, BMP, GIF, TIFF e mais.

## O que é um barcode generator aztec?
O barcode generator aztec cria códigos Aztec bidimensionais, um código de matriz compacto que pode armazenar uma grande quantidade de dados em um espaço pequeno. É ideal para ingressos móveis, URLs e dados binários onde o espaço é limitado.

## Por que usar Aspose.BarCode para .NET?
- **Suporte total ao .NET** – funciona com .NET Framework, .NET Core e .NET 5/6.
- **Conjunto rico de recursos** – múltiplos modos de símbolo, correção de erros e ampla personalização.
- **Sem dependências externas** – gera códigos de barras completamente em‑processo.
- **Multiplataforma** – roda no Windows, Linux e macOS.

## Pré‑requisitos

- Conhecimento prático de desenvolvimento .NET.  
- Visual Studio instalado em sua máquina.  
- Uma cópia do Aspose.BarCode para .NET. Você pode baixá‑la [aqui](https://releases.aspose.com/barcode/net/).

Agora que você está pronto, vamos explorar as opções do Modo de Símbolo Aztec.

## Como definir o Modo de Símbolo Aztec com o barcode generator aztec

### Importando Namespaces

Primeiro, adicione o namespace necessário no topo do seu arquivo C#:

```csharp
using Aspose.BarCode.Generation;
```

Com o namespace importado, você pode começar a criar códigos de barras Aztec.

### Etapa 1: Configurando o Barcode Generator

Inicialize o gerador com o tipo de codificação Aztec e forneça o texto que deseja codificar:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Dica profissional:** Use uma string compatível com UTF‑8 para caracteres internacionais, como mostrado acima.

### Etapa 2: Definindo o Modo de Símbolo para Auto

O modo **Auto** permite que a biblioteca decida o tamanho ideal com base no comprimento dos dados:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

O PNG gerado será salvo na pasta que você especificou.

### Etapa 3: Definindo o Modo de Símbolo para FullRange

Se você quiser que a biblioteca use toda a gama de tamanhos de símbolo Aztec, escolha **FullRange**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Etapa 4: Definindo o Modo de Símbolo para Compact

Para um código de barras mais compacto que ainda mantém boa legibilidade, use **Compact**:

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Etapa 5: Definindo o Modo de Símbolo para Rune

O modo **Rune** foi projetado para casos de uso especiais onde um estilo visual diferente é necessário:

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| A imagem do código de barras está em branco | Verifique se `path` aponta para um diretório gravável existente. |
| Caracteres não suportados | Use apenas caracteres suportados pelo padrão Aztec ou altere para codificação UTF‑8. |
| Tamanho do símbolo incorreto | Experimente `AztecSymbolMode.Auto` para que a biblioteca escolha o melhor tamanho. |

## Perguntas Frequentes

**P: Qual é o objetivo do Modo de Símbolo Aztec na geração de códigos de barras?**  
R: Ele permite controlar a densidade visual e o nível de correção de erros do código Aztec, adaptando o código de barras ao seu espaço e requisitos de legibilidade.

**P: Posso alterar o texto do código para códigos Aztec no Aspose.BarCode para .NET?**  
R: Sim, basta atribuir uma nova string a `gen.CodeText` antes de chamar `Save`.

**P: Existe uma versão de avaliação gratuita do Aspose.BarCode para .NET?**  
R: Sim, você pode baixar uma avaliação gratuita [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar a documentação completa do Aspose.BarCode para .NET?**  
R: A referência completa da API está disponível [aqui](https://reference.aspose.com/barcode/net/).

**P: Como posso obter uma licença temporária para o Aspose.BarCode para .NET?**  
R: Uma licença temporária pode ser solicitada através [deste link](https://purchase.aspose.com/temporary-license/).

## Conclusão

Neste guia cobrimos tudo o que você precisa saber para usar o **barcode generator aztec** com Aspose.BarCode para .NET, desde a configuração do gerador até o domínio de cada Modo de Símbolo (Auto, FullRange, Compact, Rune). Com esses exemplos, você agora pode incorporar códigos Aztec versáteis em qualquer aplicação .NET de forma rápida e confiável.

Se tiver mais dúvidas, sinta‑se à vontade para participar da comunidade Aspose.BarCode no [fórum de suporte](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-02  
**Testado com:** Aspose.BarCode 24.10 para .NET  
**Autor:** Aspose