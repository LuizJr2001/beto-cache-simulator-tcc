# Beto — Simulador Educacional de Memória Cache

O **Beto** é um simulador web, interativo, gratuito e de código aberto, desenvolvido para apoiar o ensino de memória cache e hierarquia de memória em disciplinas de Arquitetura e Organização de Computadores.

Este repositório mantém a evolução do simulador no contexto do Trabalho de Conclusão de Curso **“Avaliação e aprimoramento de um simulador educacional de memória cache para apoio ao ensino de hierarquia de memória”**, de Luiz Carlos dos Santos Júnior.

## Objetivo do projeto

O trabalho não propõe reconstruir o Beto do zero. Seu objetivo é avaliar a ferramenta existente, identificar lacunas técnicas e de Interação Humano-Computador (IHC), priorizar requisitos e implementar melhorias que tornem a simulação mais robusta, clara e útil para estudantes.

As principais frentes previstas são:

- validar configurações e apresentar mensagens de erro didáticas;
- melhorar a organização visual e corrigir desalinhamentos da interface;
- tornar explícita a decomposição dos endereços em *tag*, índice/conjunto e deslocamento;
- registrar o histórico dos acessos e destacar *hits*, *misses* e substituições;
- exibir metadados internos, como estado LRU e bit de validade;
- avaliar operações de leitura e escrita, políticas de escrita e *dirty bit*;
- oferecer estatísticas, exportação de resultados e comparação entre configurações, conforme a viabilidade técnica;
- avaliar a usabilidade e a experiência de uso por inspeção heurística e levantamento de requisitos com estudantes.

## Funcionalidades atuais

O Beto permite configurar e acompanhar, em tempo real ou passo a passo:

- mapeamento direto, totalmente associativo e associativo por conjunto;
- políticas de substituição FIFO, LRU e aleatória;
- parâmetros da memória principal, dos blocos e da cache;
- sequências de endereços de acesso;
- execução por meio dos controles *play*, *pause*, *stop* e *step*;
- visualização de acertos e faltas de cache.

## Tecnologias

- HTML5
- CSS3
- JavaScript

O simulador não exige instalação: abra [`docs/index.html`](docs/index.html) em um navegador ou acesse a versão publicada pelo GitHub Pages deste repositório.

## Estrutura do repositório

```text
.
├── docs/               # aplicação web publicada pelo GitHub Pages
├── tcc/                # material acadêmico do Trabalho de Conclusão de Curso
├── CONTRIBUTING.md     # convenções de branches, commits e contribuição
├── WORKFLOW.md         # metodologia, Kanban, issues e rastreabilidade
├── LICENSE
└── readme.md
```

## Fluxo de desenvolvimento

O planejamento das atividades utiliza **Kanban no GitHub Projects**, com requisitos, defeitos e tarefas acadêmicas registrados como issues. Consulte [WORKFLOW.md](WORKFLOW.md) para configurar o quadro, escrever e priorizar issues, definir critérios de aceitação e manter a rastreabilidade entre pesquisa, implementação e validação.

A branch `main` representa a versão estável do projeto. O desenvolvimento deve ocorrer em branches curtas, criadas a partir dela e nomeadas com um prefixo descritivo:

| Prefixo | Uso | Exemplo |
|---|---|---|
| `feature/` | nova funcionalidade ou melhoria | `feature/validacao-configuracoes` |
| `bugfix/` | correção de defeito não crítico | `bugfix/atualizacao-enderecos` |
| `hotfix/` | correção crítica e urgente | `hotfix/falha-simulacao` |
| `docs/` | alteração exclusivamente documental | `docs/guia-contribuicao` |
| `refactor/` | refatoração sem mudança funcional | `refactor/logica-mapeamento` |
| `test/` | criação ou ajuste de testes | `test/politica-lru` |

Os nomes devem usar letras minúsculas e palavras separadas por hífen.

## Padrão de commits

O projeto adota o padrão [Conventional Commits 1.0.0](https://www.conventionalcommits.org/pt-br/v1.0.0/):

```text
<tipo>(escopo opcional): <descrição curta>
```

Exemplos:

```text
feat(cache): exibe estado lru por linha
fix(config): valida valores que não são potências de dois
docs: atualiza instruções de contribuição
refactor(mapping): simplifica cálculo do índice
test(lru): cobre substituição em conjunto cheio
```

Os tipos mais usados são `feat`, `fix`, `docs`, `refactor`, `test`, `style`, `perf`, `build`, `ci`, `chore` e `revert`. Mudanças incompatíveis devem usar `!` após o tipo/escopo ou incluir `BREAKING CHANGE:` no rodapé do commit.

Consulte [CONTRIBUTING.md](CONTRIBUTING.md) para as convenções técnicas e [WORKFLOW.md](WORKFLOW.md) para a metodologia completa de organização do trabalho.

## Origem e licença

O Beto foi originalmente desenvolvido por Leandro Gabriel e colaboradores. O projeto original está disponível em [leo150250/simuladorCache](https://github.com/leo150250/simuladorCache).

Este projeto é distribuído sob a licença [MIT](LICENSE).
