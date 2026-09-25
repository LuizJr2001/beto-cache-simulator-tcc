# Decisão 002 — Adoção do Simple Design System

**Status:** aceita  
**Data:** 25/09/2026  
**Escopo:** protótipo visual, componentes de interface e futura implementação

## Contexto

Durante o refinamento do protótipo do Memora foram comparadas alternativas de organização visual inspiradas em diferentes design systems. O objetivo não era copiar integralmente um sistema externo, mas encontrar uma base consistente para reduzir ruído visual, melhorar alinhamento e facilitar a implementação.

Foram avaliadas referências inspiradas em:

- Carbon Design System;
- Material 3;
- Simple Design System (SDS).

A variante baseada em SDS apresentou melhor aderência à proposta desejada para o Memora: interface acadêmica/técnica, neutra, legível e com baixa carga decorativa.

## Decisão

O **Simple Design System (SDS)** passa a ser a principal referência visual do protótipo.

A adoção vale para as três etapas principais:

1. Configurar;
2. Simular;
3. Analisar.

## Regras consolidadas

### Estrutura

- fundo geral cinza-claro;
- superfícies principais brancas;
- cartões com raio aproximado de 8 px;
- bordas discretas;
- hierarquia construída principalmente por tipografia, espaçamento e contraste.

### Cabeçalho e fluxo

- cabeçalho branco;
- marca Memora à esquerda;
- ações globais à direita;
- indicador de etapas em três botões: Configurar, Simular e Analisar;
- etapa ativa com fundo escuro.

### Controles

- botão primário escuro;
- botão secundário branco com borda;
- estado desabilitado com baixo contraste;
- textos centralizados;
- setas de selects próximas à borda direita;
- ícones de ajuda próximos ao canto direito do componente relacionado.

### Cores didáticas

A base neutra do SDS não substitui a codificação pedagógica do Memora:

- Tag — violeta;
- Conjunto — ciano;
- Deslocamento — teal;
- LENDO — azul;
- ACERTO — verde;
- FALTA — âmbar;
- ERRO — vermelho.

### Side sheets

- superfície branca;
- fundo da tela preservado com scrim;
- cards internos com raio de 8 px;
- conteúdo estático/documental;
- estrutura consistente entre telas.

## Aplicação realizada

O padrão SDS foi aplicado a:

- todas as variantes da Tela 1;
- casos inválidos e ajudas da Tela 1;
- todas as variantes da Tela 2, incluindo pré-início, microetapas, conclusão e binário;
- ajudas da Tela 2;
- todas as variantes da Tela 3;
- ajudas da Tela 3;
- demonstração binária da Tela 3.

Também foram corrigidos durante a conversão:

- alinhamentos;
- sobreposições;
- elementos fora dos containers;
- botões descentralizados;
- duplicidade visual de cabeçalhos;
- estados finais da simulação;
- espaçamento entre rótulos, helpers e campos.

## Consequências

- novos componentes devem seguir esse padrão antes de introduzir estilos próprios;
- a implementação deve priorizar consistência entre estados, não reprodução pixel a pixel do Figma;
- acessibilidade, contraste, foco e navegação por teclado ainda precisam ser validados no código;
- alterações futuras no design system devem ser registradas antes de propagá-las para todas as telas.
