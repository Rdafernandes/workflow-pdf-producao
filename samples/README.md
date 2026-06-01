# Samples públicos

Esta pasta contém exemplos públicos derivados da arquitetura real da automação.

Os exemplos representam estados relevantes dos dados ao longo do fluxo, usando valores fictícios e seguros para publicação.

## Estrutura

- `entrada/`: payload validado após o workflow de entrada.
- `processamento/`: dados estruturados após extração, normalização e consolidação do PDF.
- `distribuicao/`: formatos preparados para comunicação, planilha, cards e persistência.

## Arquivos disponíveis

### Entrada

- [entrada-validada.json](entrada/entrada-validada.json): payload validado enviado do Workflow 1 para o Workflow 2.

### Processamento

- [cabecalho-estruturado.json](processamento/cabecalho-estruturado.json): cabeçalho extraído e estruturado a partir da OS.
- [itens-estruturados.json](processamento/itens-estruturados.json): produtos, subitens, dimensões, matérias-primas e etiquetas operacionais.
- [payload-distribuicao.json](processamento/payload-distribuicao.json): payload consolidado enviado do Workflow 2 para o Workflow 3.

### Distribuição

- [mensagem-operacional.md](distribuicao/mensagem-operacional.md): exemplo de mensagem preparada para comunicação operacional.
- [linha-planilha.json](distribuicao/linha-planilha.json): linha preparada para controle em planilha.
- [registro-os.json](distribuicao/registro-os.json): estrutura preparada para persistência da OS.
- [item-operacional.json](distribuicao/item-operacional.json): item preparado para card ou acompanhamento operacional.

## Diretriz

Os exemplos desta pasta não representam outputs aleatórios de nodes isolados.

Cada arquivo documenta um estado arquitetural relevante da solução, ajudando o leitor a entender como a informação evolui entre entrada, processamento e distribuição.
