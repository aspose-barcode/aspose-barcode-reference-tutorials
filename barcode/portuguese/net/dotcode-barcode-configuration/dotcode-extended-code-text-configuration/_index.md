---
date: 2026-01-27
description: Aprenda a criar texto de código estendido para DotCode usando Aspose.BarCode
  para .NET – um guia passo a passo para gerar códigos de barras DotCode com texto
  de código estendido.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Como criar texto de código estendido do DotCode com Aspose.BarCode para .NET
url: /pt/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar dotcode extended codetext com Aspose.BarCode para .NET

## Introdução

No âmbito da geração e gerenciamento de códigos de barras, o Aspose.BarCode para .NET destaca‑se como uma solução versátil e eficiente. Seja para gerar códigos de barras para produtos, inventário ou qualquer outra aplicação, o Aspose.BarCode para .NET tem tudo o que você precisa. Neste tutorial abrangente, vamos **create dotcode extended codetext** e explorar por que essa capacidade é essencial para ambientes modernos ricos em dados. O DotCode é um código de barras matricial bidimensional que pode codificar dados textuais e binários, tornando‑o uma ferramenta valiosa em diversos setores.

## Respostas rápidas
- **O que significa “create dotcode extended codetext”?** Significa construir um código de barras DotCode que inclui FNC1, ECICodetext, texto simples e separadores de símbolos em uma única carga estendida.  
- **Qual biblioteca é necessária?** Aspose.BarCode for .NET.  
- **Preciso de licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico.

## Como criar dotcode extended codetext

A seguir, um guia conciso, passo a passo, que mostra exatamente como construir o código de texto estendido e renderizar a imagem do código de barras.

## Pré‑requisitos

Antes de mergulharmos no guia passo a passo, há alguns pré‑requisitos que você precisa ter preparados para acompanhar efetivamente:

1. Aspose.BarCode for .NET: Certifique‑se de que a biblioteca Aspose.BarCode for .NET está instalada e pronta. Caso contrário, você pode baixá‑la na [documentação do Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).

2. Ambiente de desenvolvimento: Você deve ter um ambiente de desenvolvimento .NET funcional, de preferência o Visual Studio, instalado em seu sistema.

Com esses pré‑requisitos em ordem, podemos prosseguir com a geração do DotCode Extended Code Text.

## Importar Namespaces

Primeiro, você precisa importar os namespaces necessários ao seu projeto .NET para acessar as funcionalidades exigidas da biblioteca Aspose.BarCode. Veja como fazer isso:

```csharp
using Aspose.BarCode.Generation;
```

Agora que cobrimos os pré‑requisitos, vamos dividir o processo de geração do DotCode Extended Code Text em um guia passo a passo.

## Etapa 1: Definir o caminho do diretório

Nesta etapa, você precisa especificar o caminho do diretório onde deseja salvar a imagem gerada do DotCode Extended Code Text.

```csharp
string path = "Your Directory Path";
```

Substitua `"Your Directory Path"` pelo caminho real em seu sistema.

## Etapa 2: Criar DotCode Extended Code Text

Para criar o DotCode Extended Code Text, siga estas sub‑etapas:

### 2.1 Adicionar identificador de formato FNC1

O identificador de formato FNC1 é usado para indicar o início de um novo campo de dados. É uma parte essencial do DotCode Extended Code Text.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Adicionar ECICodetext

O ECICodetext é onde você pode codificar caracteres especiais e texto internacional. Neste exemplo, codificamos `"犬Right狗"` usando codificação UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Adicionar Plain Codetext

Você também pode adicionar texto simples ao DotCode Extended Code Text. Aqui, adicionamos `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Adicionar separador de símbolo FNC3

O separador de símbolo FNC3 é usado para separar diferentes seções do código.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Adicionar inicialização do leitor FNC3

Esta etapa adiciona as informações de inicialização do leitor FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Gerar Codetext

Agora, gere o DotCode Extended Codetext chamando o método `GetExtendedCodetext` no objeto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Etapa 3: Gerar imagem DotCode

Para gerar o DotCode Extended Code Text como uma imagem, siga estas sub‑etapas:

#### 4.1 Inicializar o Barcode Generator

Inicialize o `BarcodeGenerator` com os parâmetros apropriados. Neste caso, usamos `EncodeTypes.DotCode` e o codetext gerado.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

E pronto! Você gerou com sucesso o DotCode Extended Code Text usando o Aspose.BarCode para .NET.

## Conclusão

O Aspose.BarCode para .NET é uma ferramenta poderosa que simplifica a geração de códigos de barras. Neste tutorial, focamos em como **create dotcode extended codetext**, que é essencial em vários setores, especialmente onde a codificação de caracteres multilíngues e especializados é necessária. Seguindo os passos descritos acima, você pode criar facilmente o DotCode Extended Code Text para suas necessidades específicas.

Se precisar de mais orientação ou tiver dúvidas, não hesite em visitar a [documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/) ou participar da comunidade no [fórum de suporte do Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Perguntas Frequentes

### Q1: Para que o DotCode é usado?

A1: O DotCode é usado para codificar dados textuais e binários e é comumente aplicado em setores como saúde e logística para rastreamento e codificação de dados.

### Q2: Posso personalizar a aparência dos códigos de barras DotCode?

A2: Sim, o Aspose.BarCode para .NET oferece opções para personalizar a aparência dos códigos de barras DotCode, incluindo tamanho e modo de codificação.

### Q3: O Aspose.BarCode para .NET é compatível com vários frameworks .NET?

A3: Sim, o Aspose.BarCode para .NET é compatível com uma ampla gama de frameworks .NET, garantindo flexibilidade e facilidade de integração.

### Q4: Como obtenho uma licença temporária para o Aspose.BarCode para .NET?

A4: Você pode obter uma licença temporária no [site da Aspose](https://purchase.aspose.com/temporary-license/) para avaliação e testes.

### Q5: O Aspose.BarCode para .NET é adequado para geração de códigos de barras em nível empresarial?

A5: Absolutamente, o Aspose.BarCode para .NET foi projetado para atender às necessidades tanto de geração de códigos de barras em pequena escala quanto em nível empresarial, oferecendo escalabilidade e confiabilidade.

## Perguntas Frequentes

**Q: Posso usar o código de barras gerado em um aplicativo móvel?**  
A: Sim. A imagem PNG produzida pelo gerador pode ser incorporada no iOS, Android ou em qualquer aplicação móvel multiplataforma.

**Q: E se eu precisar codificar dados binários em vez de texto?**  
A: Use o método `AddECICodetext` com o `ECIEncodings` apropriado (por exemplo, `ECIEncodings.Base64`) para incorporar cargas binárias.

**Q: Como altero o tamanho do código de barras sem afetar a legibilidade?**  
A: Ajuste a propriedade `XDimension.Pixels`; valores maiores aumentam o tamanho do módulo, enquanto valores menores tornam o código de barras mais compacto.

**Q: Existe uma maneira de adicionar uma zona silenciosa ao redor do código de barras?**  
A: Sim. Defina `gen.Parameters.Barcode.Margin` para especificar a zona silenciosa desejada em pixels.

**Q: A biblioteca suporta .NET 8?**  
A: As versões mais recentes do Aspose.BarCode são compatíveis com .NET 8; basta referenciar a versão adequada do pacote NuGet.

---

**Última atualização:** 2026-01-27  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}