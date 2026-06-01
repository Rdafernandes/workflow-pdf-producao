# Arquitetura

## Visão da arquitetura
A arquitetura do projeto foi dividida em três workflows principais, cada um com uma responsabilidade bem definida dentro do processo.

Essa divisão ajuda a separar entrada, processamento e distribuição, reduzindo acoplamento e facilitando manutenção, análise e publicação segura de uma versão sanitizada.

## Bloco 1 — Entrada e validação
O primeiro workflow funciona como porta de entrada da automação.

Ele recebe a solicitação inicial, valida regras básicas da mensagem recebida, verifica se o envio atende ao padrão esperado e encaminha somente entradas válidas para o próximo estágio.

## Responsabilidade do bloco 1
As funções esperadas desse bloco incluem:
- receber o evento inicial;
- identificar remetente e contexto de entrada;
- verificar se existe documento;
- validar se o arquivo recebido é um PDF;
- validar padrão de nome do arquivo;
- encaminhar apenas entradas aceitas.

Esse bloco atua como filtro e proteção do processo.

## Bloco 2 — Processamento do PDF
O segundo workflow concentra o núcleo técnico da automação.

Ele identifica a OS, evita reprocessamento indevido, baixa o PDF, extrai o texto, interpreta o conteúdo, organiza o arquivo e prepara os dados estruturados para as etapas seguintes.

## Responsabilidade do bloco 2
As funções esperadas desse bloco incluem:
- extrair o número da OS;
- verificar se a OS já foi tratada;
- fazer download do PDF;
- extrair o conteúdo textual;
- montar o cabeçalho da OS;
- interpretar os itens e subitens;
- enriquecer a leitura com regras internas;
- criar pasta para a OS;
- enviar o PDF para armazenamento;
- preparar payload estruturado para o próximo workflow.

Esse é o bloco mais denso da arquitetura.

## Bloco 3 — Distribuição operacional
O terceiro workflow recebe os dados já estruturados e transforma isso em ações operacionais.

A partir desse ponto, o sistema organiza mensagens, controles, registros e desdobramentos necessários para acompanhamento interno.

## Responsabilidade do bloco 3
As funções esperadas desse bloco incluem:
- montar mensagem operacional;
- preparar linha para planilha;
- localizar posição de atualização;
- registrar ou atualizar dados em base estruturada;
- explodir itens para acompanhamento individual;
- criar cards operacionais;
- consolidar dados para controle logístico e produtivo.

Esse bloco aproxima o dado extraído do uso real pela operação.

## Fluxo de ponta a ponta
A sequência macro da arquitetura pode ser entendida assim:

1. Entrada do documento.
2. Validação inicial.
3. Encaminhamento ao processamento.
4. Identificação da OS.
5. Extração e estruturação dos dados.
6. Organização do arquivo.
7. Distribuição operacional.
8. Registro em controles internos.

## Camadas lógicas
A arquitetura pode ser lida em quatro camadas:

### Camada de entrada
Responsável por receber e validar o evento inicial.

### Camada de interpretação
Responsável por transformar o PDF em dados utilizáveis.

### Camada de organização
Responsável por armazenar, nomear e consolidar a OS de forma estruturada.

### Camada de distribuição
Responsável por enviar a informação tratada para os pontos de uso operacional.

## Estratégia de modularidade
A separação em workflows permite:
- manutenção por etapa;
- rastreamento mais simples de falhas;
- evolução gradual da automação;
- documentação mais clara;
- sanitização mais controlada.

Essa abordagem também ajuda a evitar que todo o processo fique concentrado em um único fluxo difícil de revisar.

## Publicação sanitizada
A versão pública deste case apresenta a arquitetura em nível técnico e conceitual, preservando a lógica da solução sem expor detalhes sensíveis do ambiente real.

Credenciais, endpoints privados, IDs internos, regras sensíveis e identificadores operacionais foram removidos ou substituídos por placeholders.
