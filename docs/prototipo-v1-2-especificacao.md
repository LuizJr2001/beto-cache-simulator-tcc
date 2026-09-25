# Especificação visual do protótipo V1.2

**Atualização:** 25/09/2026  
**Figma:** https://www.figma.com/design/Zm8dzyoG0yhkbEkC01Zvu0?node-id=92-2

Este documento consolida a especificação visual mais recente do Beto após revisão do legado, questionário com usuários, inspeção heurística de Nielsen e refinamentos sucessivos no Figma.

> Importante: este documento descreve a **especificação de interface e comportamento esperado**. Não significa que todos os itens já estejam implementados no código.

## 1. Estrutura geral

O protótipo mantém o fluxo:

1. **Configurar**
2. **Simular**
3. **Analisar**

A proposta reduz a densidade visual sem remover conteúdo didático, usando agrupamento, scroll local e divulgação progressiva.

## 2. Tela 0 — comparação legado × proposta

A tela de comparação foi atualizada para refletir o estado atual da proposta:

- estado inicial antes da primeira simulação;
- três mapeamentos explicitados;
- vias configuráveis/fixas conforme o mapeamento;
- ajuda contextual estática;
- cache com scroll;
- visualização Decimal/Binário;
- estados LENDO, ACERTO e FALTA;
- tela de configuração inválida;
- análise antes/depois e fluxo genérico de substituição.

## 3. Configuração

### 3.1 Mapeamentos

Foram especificados três estados:

- **Direto:** 1 linha por conjunto, fixa; política de substituição não se aplica.
- **Associativo por conjunto:** vias por conjunto configuráveis; exemplo de 4 vias = 8 conjuntos.
- **Totalmente associativo:** 1 conjunto; todas as 32 linhas são vias; valor fixo.

A decomposição do endereço muda conforme o mapeamento.

### 3.2 Casos inválidos

A tela de erro foi redesenhada para evitar sobreposição e mostrar:

- campo inválido com borda vermelha;
- mensagem inline próxima ao campo;
- resumo de pendências;
- decomposição indisponível;
- execução bloqueada.

Exemplos representados:

- total de células não potência de 2;
- número de vias incompatível com o total de linhas;
- endereços negativos, fora do intervalo ou não numéricos.

### 3.3 Ajuda contextual

Os side sheets da Tela 1 foram padronizados como conteúdo **estático e documental**:

1. regra/limitação;
2. exemplo didático fixo;
3. efeito na simulação.

O campo **Endereços a acessar** usa esse mesmo nome na ajuda contextual.

Também existem:

- **Glossário**;
- **Ajuda rápida**;
- link **GitHub**;
- link externo para o Beto original.

## 4. Simulação

### 4.1 Estado antes de iniciar

Foi criada a tela **2.0 — Antes de iniciar**, com:

- progresso 0/21;
- acertos e faltas em zero;
- taxa de acerto indisponível;
- cache vazia;
- histórico vazio;
- botão **Iniciar** habilitado;
- ações dependentes da execução desabilitadas.

### 4.2 Cache

A cache principal agora possui:

- scroll vertical;
- conjunto atual destacado;
- várias linhas visíveis simultaneamente;
- colunas de conjunto, via, validade, tag, bloco, LRU e ação;
- seletor Decimal/Binário.

O botão **Ver cache completa** foi removido por redundância e a antiga Tela 2.B foi removida.

### 4.3 Estados de acesso

O histórico e os microestados usam semântica consistente:

- **LENDO** — âmbar;
- **ACERTO** — verde;
- **FALTA** — vermelho.

O resultado não depende apenas da cor: há texto e símbolo.

### 4.4 Ajuda da simulação

As ajudas de Estado LRU, Memória cache e Histórico foram padronizadas como documentação estática:

- interpretação;
- exemplo didático;
- por que isso é útil.

Nenhuma delas depende do acesso atual.

## 5. Análise

A Tela 3 mantém os dados dinâmicos necessários:

- endereço analisado;
- estado antes/depois;
- bloco que sai;
- bloco que entra;
- atualização de recência.

A explicação didática foi simplificada para um fluxo estático de quatro passos:

1. **Localizar conjunto**
2. **Verificar acerto**
3. **Aplicar política**
4. **Atualizar cache**

Isso evita lógica textual excessivamente dinâmica na implementação.

As ajudas 3.1–3.4 também foram padronizadas com:

- regra/interpretação;
- exemplo didático fixo;
- por que isso é útil.

## 6. Legibilidade e consistência

A V1.2 usa:

- Inter como família principal;
- IBM Plex Mono para binários e valores técnicos;
- textos principais ampliados;
- botões globais homogêneos;
- side sheets com cards consistentes;
- alinhamento e espaçamento revisados;
- correções de overflow e sobreposição em telas 1, 2 e 3.

## 7. Relação com issues

A especificação visual se relaciona diretamente com:

- #25 — validação dos parâmetros;
- #26 — validação dos endereços;
- #28 — estado LRU e linha candidata;
- #29 — reorganização visual e ajuda contextual;
- #30 — preservação do bloco removido antes da mutação;
- #31 — regressão dos mapeamentos e políticas;
- #32 — load/store, dirty bit e políticas de escrita permanecem como trabalho futuro.

## 8. Status

A V1.2 está consolidada como **especificação visual para revisão da orientadora e posterior implementação**.

Ainda dependem de código e testes:

- validações reais;
- regras condicionais dos mapeamentos;
- atualização dinâmica da cache;
- cálculo e atualização de LRU;
- histórico;
- fluxo LENDO → ACERTO/FALTA;
- persistência/atualização dos estados;
- testes de regressão.
