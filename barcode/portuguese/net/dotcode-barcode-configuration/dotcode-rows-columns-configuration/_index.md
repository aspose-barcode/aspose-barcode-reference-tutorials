---
date: 2026-02-04
description: Aprenda a criar imagem de código de barras DotCode configurando linhas
  e colunas usando o Aspose.BarCode para .NET.
linktitle: DotCode Rows and Columns Configuration
second_title: Aspose.BarCode .NET API
title: Criar imagem de código de barras DotCode – linhas e colunas (Aspose.BarCode)
url: /pt/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras DotCode – linhas e colunas (Aspose.BarCode)

## Introdução

Bem-vindo ao mundo da geração de códigos de barras com Aspose.BarCode para .NET! Neste guia você **criará arquivos de imagem de código de barras DotCode** e aprenderá a ajustar finamente as linhas e colunas para atender aos seus requisitos exatos. Seja construindo um sistema de rotulagem para saúde, um aplicativo de rastreamento logístico ou apenas experimentando simbologias 2D, dominar esta configuração lhe dá controle preciso sobre o tamanho do código de barras e a capacidade de dados.

## Respostas Rápidas
- **O que significa “criar imagem de código de barras DotCode”?** Significa gerar um arquivo visual PNG/JPEG/etc. que codifica seus dados usando a simbologia DotCode 2‑D.  
- **Qual biblioteca lida com a geração?** Aspose.BarCode para .NET fornece uma API simples para produzir imagens DotCode de alta qualidade.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para uso em produção.  
- **Posso personalizar linhas e colunas independentemente?** Sim – você pode definir linhas, colunas ou deixar a biblioteca dimensioná‑las automaticamente.  
- **Quais formatos de saída são suportados?** PNG, JPEG, BMP, GIF, TIFF e mais via `BarCodeImageFormat`.

## O que é uma imagem de código de barras DotCode?

DotCode é um código de barras 2‑dimensional compacto que armazena grandes quantidades de dados em uma pequena área quadrada ou retangular. É amplamente usado nos setores de **saúde** e **farmacêutico** para rastrear produtos, codificar informações de pacientes e muito mais. Ao configurar linhas e colunas, você controla a densidade do código de barras e suas dimensões físicas.

## Por que configurar linhas e colunas?

* Ajustar o código de barras ao espaço limitado da etiqueta.  
* Otimizar a confiabilidade da leitura para impressoras ou scanners específicos.  
* Equilibrar o tamanho da imagem com a capacidade de dados — mais linhas/colunas significam mais dados, mas uma imagem maior.  

Agora que você entende o porquê, vamos percorrer o **como criar imagem de código de barras DotCode** com suas próprias configurações de linhas e colunas.

## Pré-requisitos

1. **Ambiente de Desenvolvimento .NET** – Visual Studio, Rider ou VS Code com o .NET SDK instalado.  
2. **Aspose.BarCode para .NET** – Baixe‑o no site oficial **[here](https://releases.aspose.com/barcode/net/)**.  
3. **Uma licença válida** (ou uma licença de avaliação temporária) para geração em nível de produção.  
4. **Conhecimento básico de C#** – você escreverá alguns trechos curtos, mas os conceitos são simples.

## Importar Namespaces

We only need one namespace for the examples:

```csharp
using Aspose.BarCode.Generation;
```

## Guia passo a passo para criar imagem de código de barras DotCode

### Etapa 1: Configurar o caminho do diretório

Primeiro, decida onde as imagens geradas serão salvas. Substitua o placeholder por uma pasta real em sua máquina.

```csharp
string path = "Your Directory Path";
```

> **Dica profissional:** Use `Path.Combine(Environment.CurrentDirectory, "Barcodes")` para construir um caminho que funcione em todas as plataformas.

### Etapa 2: Inicializar o Gerador DotCode

Crie uma instância de `BarcodeGenerator`, especifique a simbologia `EncodeTypes.DotCode` e forneça os dados que deseja codificar (por exemplo, “Aspose”).

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // All configuration and saving will happen inside this block.
}
```

### Etapa 3: Configurar colunas DotCode

Se você quiser um número fixo de colunas, defina a propriedade `Columns`. Aqui escolhemos **18 colunas** e armazenamos o resultado como um arquivo PNG.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.Columns = 18;
gen.Save($"{path}DotCodeColumns18.png", BarCodeImageFormat.Png);
```

> **Por que XDimension?** Ajustar o tamanho em pixels altera a densidade visual de cada ponto sem afetar os dados codificados.

### Etapa 4: Configurar linhas DotCode

Você também pode fixar o número de linhas enquanto deixa a biblioteca decidir a contagem de colunas (definindo `Columns = -1`). O exemplo abaixo cria um código de barras com **12 linhas**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = -1;
gen.Parameters.Barcode.DotCode.Rows = 12;
gen.Save($"{path}DotCodeRows12.png", BarCodeImageFormat.Png);
```

### Etapa 5: Configurar linhas e colunas simultaneamente

Quando precisar de controle total, defina ambas as propriedades. O trecho a seguir produz um código de barras com **29 colunas** e **26 linhas**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = 29;
gen.Parameters.Barcode.DotCode.Rows = 26;
gen.Save($"{path}DotCodeRows26Columns29.png", BarCodeImageFormat.Png);
```

> **Erro comum:** Definir tanto linhas quanto colunas com valores muito altos pode gerar uma imagem que excede as dimensões típicas de etiquetas. Teste com uma pré‑visualização antes de imprimir.

## Problemas comuns e soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| Código de barras aparece borrado | XDimension muito baixa | Aumente `XDimension.Pixels` (ex.: 12‑15). |
| Scanner não consegue ler o código de barras | Linhas/Colunas muito densas para a impressora | Reduza linhas/colunas ou use uma impressora de maior resolução. |
| Imagem não salva | String `path` inválida | Garanta que o diretório exista ou chame `Directory.CreateDirectory(path)`. |

## Perguntas Frequentes

**Q: Qual é a quantidade máxima de dados que posso armazenar em um código de barras DotCode?**  
A: Depende do número de linhas e colunas que você configurar. Mais células significam mais dados, mas também uma imagem maior.

**Q: Posso mudar as cores do código de barras?**  
A: Sim. Use `gen.Parameters.Barcode.ForeColor` e `BackColor` para definir cores personalizadas antes de salvar.

**Q: A simbologia DotCode é suportada em todas as plataformas?**  
A: Aspose.BarCode para .NET funciona no .NET Framework, .NET Core e .NET 5/6+, portanto você pode gerar imagens no Windows, Linux ou macOS.

**Q: Onde posso encontrar uma lista completa de todos os parâmetros DotCode?**  
A: A referência oficial da API fornece documentação detalhada – veja a [documentação do Aspose.BarCode](https://reference.aspose.com/barcode/net/).

**Q: Como gerar um código de barras em uma API web sem gravar no disco?**  
A: Chame `gen.Save(Stream, BarCodeImageFormat.Png)` e retorne o stream como resultado de arquivo.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras DotCode** e controlar precisamente suas linhas e colunas usando Aspose.BarCode para .NET. Ajustando as propriedades `Rows` e `Columns` você pode adaptar o tamanho do código de barras para qualquer cenário de etiqueta ou embalagem. Experimente diferentes dimensões, cores e formatos de saída para atender às necessidades do seu projeto e explore o conjunto mais amplo de recursos do Aspose.BarCode para ainda mais personalização.

Se você encontrar desafios ou quiser aprofundar, consulte os recursos oficiais:

* [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
* [Aspose.BarCode community support](https://forum.aspose.com/c/barcode/13)

---

**Última atualização:** 2026-02-04  
**Testado com:** Aspose.BarCode para .NET 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}