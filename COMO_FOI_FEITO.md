## 🤖 Como este projeto foi criado (Aider + IA)

Os arquivos deste repositório foram gerados a partir do PDF do plano de estudos
usando o **[Aider](https://aider.chat)**, um assistente de IA que roda no terminal
e cria ou edita arquivos diretamente na pasta do projeto.

### Ambiente
| Item | Valor |
| :--- | :--- |
| Ferramenta | Aider v0.86.2 |
| Modelo | `nvidia/nemotron-3-ultra-550b-a55b:free` via OpenRouter |
| Formato de edição | `whole` (o modelo devolve o arquivo inteiro) |
| Repositório Git | Nenhum no momento da geração (pasta local) |
| Custo reportado | ~US$ 0,03 na sessão |

### Passo a passo

1. **Configuração.** O primeiro login no OpenRouter pelo Aider falhou. Depois de
   listar os modelos disponíveis (`aider --list-models openrouter/`), a sessão foi
   aberta indicando o modelo direto:
   `aider --model openrouter/nvidia/nemotron-3-ultra-550b-a55b:free`
2. **Teste de conexão.** Uma mensagem inicial confirmou que o modelo respondia em
   português.
3. **Pedido principal.** Pedi para "materializar" o plano de estudos, criando:
   `README.md`, `cronograma.md`, `anotacoes/semana-01.md` (modelo para duplicar)
   e `recursos.md`, explicando a estrutura antes de executar.
4. **Contexto faltando.** O modelo não consegue ler o PDF sozinho e pediu o
   conteúdo. Colei o texto do PDF no chat.
5. **Geração.** Com o texto em mãos, o modelo gerou os quatro arquivos, expandindo
   o resumo do PDF em cronograma diário (30 dias), entregáveis por semana e
   curadoria de recursos.
6. **Aplicação.** O Aider perguntou "Create new file?" para cada arquivo e eu
   confirmei com `y`.
7. **Revisão manual.** Depois conferi o resultado e ajustei o que precisava
   (README completo, links, estrutura).

### Prompt principal utilizado

> Materialize esse plano nesta pasta criando:
> 1. README.md com o resumo do plano
> 2. cronograma.md com o roteiro semanal (semanas 1 a 4)
> 3. uma pasta "anotacoes" com um modelo "semana-01.md" para eu duplicar
> 4. recursos.md com os materiais separados por semana
>
> Antes de criar, me explique brevemente sua estrutura. Depois execute.

### Lições aprendidas
- O Aider não lê PDF automaticamente: é preciso colar o texto no chat.
- Pedir "explique a estrutura antes de executar" ajuda a validar o plano antes
  de criar arquivos.
- Conteúdo gerado por IA precisa de revisão. Os links do `recursos.md`, por
  exemplo, devem ser conferidos um a um.
- Nos arquivos Markdown, os blocos de código (como a árvore de pastas) podem
  confundir o formato `whole` do Aider (veja o problema abaixo).
