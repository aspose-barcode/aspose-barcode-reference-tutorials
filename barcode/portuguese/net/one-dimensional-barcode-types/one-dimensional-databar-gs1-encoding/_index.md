---
date: 2026-03-07
description: Aprenda a criar códigos de barras unidimensionais Databar codificados
  em GS1 no .NET usando Aspose.BarCode. Este guia mostra como definir o GS1, configurar
  o gerador de códigos de barras e gerar códigos de barras rapidamente.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Criar codificação GS1 de Databar unidimensional com Aspose.BarCode
url: /pt/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Codificação GS1 de Databar Unidimensional com Aspose.BarCode

Neste tutorial você **criará códigos de barras databar unidimensionais** que atendem ao padrão GS1, usando a biblioteca Aspose.BarCode para .NET. Seja qual for a necessidade — validação GS1 rigorosa ou um código de barras mais flexível — nós guiaremos cada passo — desde a instalação da biblioteca até o tratamento de exceções de codificação — para que você possa gerar códigos de barras confiáveis em suas próprias aplicações.

## Respostas Rápidas
- **O que significa “criar databar unidimensional”?** Significa gerar um código de barras linear (1‑D) da família Databar, frequentemente usado no varejo e na logística.  
- **Como configuro a validação GS1?** Defina `IsAllowOnlyGS1Encoding` como `true` nos parâmetros do `DataBar`.  
- **Preciso de uma licença?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Onde posso baixar a biblioteca?** Na página oficial de releases da Aspose (veja os pré‑requisitos).

## O que é “criar databar unidimensional”?
Um Databar unidimensional (também conhecido como RSS) é um código de barras linear compacto que pode codificar dados numéricos, datas ou strings AI (Application Identifier). Quando combinado com a codificação GS1, o código de barras segue uma estrutura de dados reconhecida globalmente, tornando‑o ideal para varejo, saúde e cadeias de suprimentos.

## Por que usar Aspose.BarCode para .NET?
Aspose.BarCode oferece uma API fluente, suporte total ao GS1 e a capacidade de ajustar cada aspecto visual do código de barras. Ele elimina a adivinhação de codificação de baixo nível e permite que você se concentre na lógica de negócios.

## Pré‑requisitos

1. **Aspose.BarCode para .NET** – faça o download e instale a partir de [here](https://releases.aspose.com/barcode/net/).  
2. **Seu Caminho de Diretório** – substitua `"Your Directory Path"` nos exemplos por uma pasta onde você tenha permissão de gravação.

## Importando Namespaces

Adicione as instruções `using` necessárias no topo do seu arquivo C#:

```csharp
using Aspose.BarCode;
using System;
```

## Etapa 1: Inicializar o Gerador de Código de Barras

Crie uma instância de `BarcodeGenerator` e especifique a simbologia Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Etapa 2: Como definir GS1 – Gerar um código de barras com validação GS1 rigorosa

Habilite a codificação apenas GS1, atribua um codetext compatível com GS1 e salve a imagem:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Etapa 3: Geração de código de barras com Aspose – Codificação variável (sem verificação GS1)

Se precisar de um código de barras que **não** imponha regras GS1, desative a verificação:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Etapa 4: Verificação GS1 do gerador de código de barras – Tratamento de exceção

Quando `IsAllowOnlyGS1Encoding` está `true` mas o codetext não está em conformidade com GS1, Aspose lança uma exceção. O padrão a seguir mostra como capturá‑la e registrá‑la:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Armadilhas Comuns & Dicas
- **Armadilha:** Fornecer uma string não‑GS1 enquanto a verificação GS1 está ativada abortará a geração do código de barras.  
- **Dica profissional:** Valide suas strings AI antes de atribuí‑las a `CodeText` para evitar erros em tempo de execução.  
- **Sugestão:** Use caminhos absolutos ou `Path.Combine` para montar nomes de arquivos de forma segura em diferentes plataformas.

## Conclusão

Agora você sabe como **criar códigos de barras databar unidimensionais** com codificação GS1, como alternar a verificação GS1 e como tratar as exceções relacionadas — tudo usando Aspose.BarCode para .NET. Sinta‑se à vontade para explorar opções adicionais de estilo, como tamanho, cor e margens do código de barras através do objeto `Parameters.Barcode`.

Se encontrar algum problema, a documentação oficial e o fórum da comunidade são excelentes recursos:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Perguntas Frequentes

### 1. O que é codificação GS1 em códigos de barras?
A codificação GS1 é uma forma padronizada de estruturar dados (por exemplo, identificadores de produto) dentro de um código de barras, garantindo interoperabilidade entre varejistas, fabricantes e provedores de logística.

### 2. Posso personalizar a aparência dos códigos de barras gerados?
Sim. Aspose.BarCode permite ajustar tamanho, cores, margens e até adicionar texto legível por humanos via as configurações `Parameters.Barcode`.

### 3. Onde encontro recursos adicionais e documentação para Aspose.BarCode?
Você pode encontrar documentação completa e exemplos em [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). É um recurso valioso para aprendizado e solução de problemas.

### 4. Existe uma versão de avaliação disponível para Aspose.BarCode?
Sim, você pode obter uma versão de avaliação gratuita do Aspose.BarCode para .NET em [here](https://releases.aspose.com/).

### 5. Como posso comprar uma licença para Aspose.BarCode para .NET?
Para adquirir uma licença do Aspose.BarCode para .NET, visite a [purchase page](https://purchase.aspose.com/buy) no site da Aspose.

---

**Última atualização:** 2026-03-07  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}