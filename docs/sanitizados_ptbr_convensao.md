# Convenção dos arquivos sanitizados (PT-BR)

Este documento define a convenção usada para publicar workflows sanitizados no portfólio.

## Objetivo

Publicar o case técnico com clareza, sem expor segredos, dados pessoais, clientes reais ou identificadores operacionais sensíveis.

## Nomes de arquivos

- `01-entrada-validacao.sanitizado.json`: fluxo de entrada e validação.
- `02-processamento-estruturacao.sanitizado.json`: fluxo de processamento e estruturação.
- `03-distribuicao-operacional.sanitizado.json`: fluxo de distribuição operacional.
- `checagem_final_sem_dados_sensiveis.json`: checklist final de publicação.
- `sanitizados_ptbr_convensao.md`: esta convenção.

## O que deve permanecer

- Nomes das etapas do fluxo.
- Ordem lógica da automação.
- Integrações em nível de produto, por exemplo: WhatsApp, OpenAI, Google Drive, Supabase, Google Sheets e Trello.
- Tipos de validação, parsing, enriquecimento e despacho operacional.
- Estrutura geral dos nós, quando isso ajudar a demonstrar arquitetura.

## O que deve ser removido ou mascarado

- Tokens Bearer, chaves de API e credenciais OAuth.
- IDs internos de credenciais, webhooks, pastas, planilhas, boards e listas.
- Telefones, e-mails, nomes completos e identificadores de pessoas.
- Dados de clientes, como CNPJ/CPF, contato, endereço e conteúdo real de OS.
- `pinData`, payloads de teste e resultados de execução com dados reais.
- URLs privadas ou internas.

## Convenções de sanitização

- Substituir segredos por placeholders neutros, como `<TOKEN_REMOVIDO>` ou `{{TOKEN_API_MENSAGERIA_REMOVIDO}}`.
- Substituir dados pessoais por placeholders como `<NOME_REMOVIDO>`, `<EMAIL_REMOVIDO>` e `<TELEFONE_REMOVIDO>`.
- Substituir IDs privados por `<ID_REMOVIDO>`.
- Substituir nomes de clientes por descrições genéricas, como `<CLIENTE>`.
- Manter nomes técnicos dos serviços integrados quando forem relevantes para entendimento da arquitetura, evitando expor nomes internos, hosts privados ou identificadores operacionais.

## Convenção para README

- Descrever o problema operacional.
- Explicar a solução em 3 workflows.
- Citar stack e fluxo de dados.
- Destacar o resultado operacional.
- Não incluir exemplos com dados reais.

## Convenção para prints

- Tirar print apenas do canvas do n8n.
- Fechar painel lateral antes do print.
- Usar zoom que permita ler os nomes principais dos nodes.
- Mostrar conexão entre os nodes mais importantes, sem tentar capturar tudo em detalhe textual.

## Convenção para samples

Os exemplos públicos devem representar estados arquiteturais relevantes do fluxo, e não outputs isolados de nodes.

A organização recomendada é:

- `samples/entrada/`: payload validado após o workflow de entrada.
- `samples/processamento/`: dados estruturados após extração, normalização e consolidação.
- `samples/distribuicao/`: formatos preparados para comunicação, planilha, cards e persistência.

Todos os valores devem ser fictícios, anonimizados e coerentes com a estrutura real da automação.

## Regra final

Se existir dúvida sobre um dado, trate como sensível e não publique.
