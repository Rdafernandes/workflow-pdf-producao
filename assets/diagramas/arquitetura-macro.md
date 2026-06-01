# Arquitetura macro da automação

Fluxo simplificado da solução ponta a ponta.

```text
┌─────────────────┐
│ PDF de OS       │
│ Evento Entrada  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Workflow 1      │
│ Entrada e       │
│ Validação       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Workflow 2      │
│ Processamento e │
│ Estruturação    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Persistência /  │
│ Organização     │
│ dos Dados       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Workflow 3      │
│ Distribuição    │
│ Operacional     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Saídas          │
│ Mensagens       │
│ Operacionais    │
└─────────────────┘
```

## Observações

Este diagrama representa a arquitetura lógica da solução publicada.

A implementação pública foi sanitizada para remover elementos internos e dados sensíveis, mantendo a organização estrutural e o comportamento geral do fluxo.
