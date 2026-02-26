---
name: verificacao-formulas-norma
description: "Auditar exaustivamente fórmulas e cálculos de relatórios contra norma técnica em PDF, com rastreabilidade por cláusula/equação/página, recálculo numérico e classificação de não conformidades. Usar quando o usuário pedir validação de conformidade matemática/normativa, revisão técnica de equações, ou criação de parecer de aderência a norma anexada."
---

# Verificação exaustiva de fórmulas contra norma

Siga este fluxo para auditar relatórios técnicos com fórmulas usando uma norma PDF como fonte oficial.

## Fluxo obrigatório

1. Confirmar insumos: relatório + norma em PDF.
2. Extrair todas as fórmulas do relatório (texto, tabelas, anexos e fórmulas implícitas).
3. Criar IDs únicos (`F-001`, `F-002`, ...).
4. Mapear cada fórmula para referência na norma (item/equação/página).
5. Validar cada fórmula em 7 dimensões:
   - estrutura algébrica;
   - definição de variáveis;
   - unidades e consistência dimensional;
   - condições de aplicação e limites;
   - coeficientes/constantes normativas;
   - regra de arredondamento;
   - sequência de cálculo.
6. Recalcular resultados quando houver dados suficientes.
7. Classificar divergências por severidade: Crítica, Alta, Média, Baixa.
8. Registrar pendências como `Não verificável com os dados fornecidos` quando faltar informação.
9. Marcar ambiguidades normativas como `Interpretação incerta` sem inventar conteúdo.
10. Entregar relatório final em Markdown com tabelas rastreáveis.

## Critérios de decisão por fórmula

Para cada `F-xxx`, atribuir um estado:

- **Conforme**: fórmula e aplicação numérica aderentes à norma.
- **Não conforme**: existe desvio técnico (algébrico, semântico, dimensional, procedimental ou numérico).
- **Não verificável**: dados insuficientes para concluir.
- **Interpretação incerta**: norma ambígua para o caso específico.

## Modelo de saída obrigatório

## 1) Resumo Executivo

- Total de fórmulas identificadas
- Conformes
- Não conformes
- Não verificáveis
- Interpretação incerta
- Risco global do relatório (Baixo/Médio/Alto)
- Top 5 achados críticos

## 2) Matriz Mestra de Verificação

| ID | Local no relatório | Fórmula do relatório | Referência da norma (item/equação/página) | Estado | Tipo de desvio | Severidade | Evidência objetiva | Correção proposta |
|---|---|---|---|---|---|---|---|---|

Tipos de desvio aceitos: álgebra, variável, unidade, condição, coeficiente, arredondamento, cálculo, rastreabilidade.

## 3) Caderno de Recálculo (por fórmula)

Para cada fórmula com dados suficientes, listar:

1. Dados de entrada
2. Equação normativa aplicada
3. Substituição numérica
4. Passo a passo do cálculo
5. Resultado recalculado
6. Resultado do relatório
7. Diferença absoluta
8. Diferença percentual
9. Veredito técnico

## 4) Não conformidades e plano corretivo

| ID | Problema | Severidade | Impacto técnico | Ação corretiva | Prioridade |
|---|---|---|---|---|---|

## 5) Pendências

- Itens não auditáveis
- Dados faltantes para fechamento
- Próxima ação para concluir auditoria

## Checklist de completude antes de finalizar

- Cobrir 100% das fórmulas identificadas.
- Citar referência normativa para cada fórmula (ou justificar ausência).
- Atribuir severidade para cada não conformidade.
- Executar todos os recálculos possíveis.
- Explicitar limites da auditoria e suposições adotadas.
