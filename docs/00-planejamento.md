# Planejamento do repositório

## Objetivo

Organizar uma automação real de processamento de ordens de serviço em PDF como um case técnico público de portfólio, preservando a arquitetura da solução sem expor dados sensíveis do ambiente produtivo.

## Diretrizes do case

Este repositório foi estruturado para demonstrar:

- decomposição de uma automação operacional em workflows encadeados;
- separação clara entre entrada, processamento e distribuição;
- tratamento de PDFs de ordens de serviço;
- integração entre mensageria, armazenamento, planilhas e banco de dados;
- documentação técnica voltada para leitura externa;
- cuidado com sanitização e privacidade.

## Escopo publicado

A versão pública contém:

- documentação técnica em `docs/`;
- workflows sanitizados em `workflows/sanitizados/`;
- diagramas e capturas em `assets/`;
- estrutura reservada para exemplos públicos em `samples/`.

## Fora do escopo público

Não fazem parte deste repositório:

- workflows originais de produção;
- credenciais ou tokens;
- payloads reais de execução;
- PDFs reais de clientes;
- dados pessoais, documentos, telefones ou endereços reais;
- URLs privadas, IDs internos ou referências sensíveis de ambiente.

## Critério de evolução

Novos materiais só devem ser adicionados quando ajudarem a entender a arquitetura do case sem comprometer privacidade ou transformar a documentação em detalhe artificial de implementação.

A prioridade é documentar estados arquiteturais relevantes do fluxo, não outputs isolados de nodes.
