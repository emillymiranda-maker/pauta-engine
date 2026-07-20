# Referência 07 — Ecossistema de skills

O Pauta Engine não roda sozinho. Ele é o motor central de um conjunto de skills construídas para a
operação, cada uma cobrindo uma etapa do ciclo. É esse encadeamento que permite que a conta inteira
funcione sem depender do repertório de uma pessoa.

| Skill | Etapa | O que resolve |
|---|---|---|
| `onboarding-cliente` | Etapa 0 | Monta a estrutura inicial do cliente novo (CLAUDE.md, ficha, dossiê, pastas) a partir de notas de kick-off — evita dossiê incompleto, que é a causa raiz de pauta fraca |
| `alinhamento-cliente` | Alimenta 1 e 2 | Registra alinhamentos de reunião no CLAUDE.md e na memória, de forma consistente em vez de ad hoc. É o que faz "alinhamento recente vence documento antigo" ser verificável |
| `social-media-maestro` | 1 e 3 | Pesquisa de cliente, linha editorial, pilares de conteúdo, distribuição de funil e frequência — produz os insumos que a Etapa 3 consome |
| `copy-maestro` | 4.2 e 4.4 | Persona, jornada, níveis de consciência, dores e objeções. É o que ancora a escolha de ângulo e a escrita do hook em estratégia, não em gosto |
| **`pauta-engine`** | **3, 4 e 5** | **O motor: distribuição, briefing, hipótese e gate** |
| `roteirista-cinema-video` | 4.5 e 4.7 | Transforma a cena descrita no roteiro de Reels em prompt para IA de vídeo, mantendo consistência visual entre cenas |
| `image-prompt-generator` | 4.7 | Converte o direcionamento visual do briefing em prompt estruturado de imagem — fecha a ponte entre copy e produção |
| `revisor-pauta` | 5 | Segunda camada de checagem: coerência, mix, funil, repetição e viabilidade, com relatório de problemas priorizados |
| `analisador-metricas` | 6 | Lê métricas do Meta Business Suite, diagnostica, correlaciona tipo de conteúdo com resultado, gera o relatório do cliente **e registra os achados no CLAUDE.md** — é o que fecha o laço de volta para a memória |

## Por que isso importa para reuso

Uma skill isolada resolve um passo. O que torna o sistema adotável por outra pessoa é o
encadeamento: a saída de uma é a entrada da próxima, e todas escrevem nos mesmos arquivos do
cliente (`CLAUDE.md`, `01_dossie.md`, `_memoria.md`).

O ponto de fechamento é o `analisador-metricas`: ele não só produz o relatório do mês, ele **grava
os achados de volta no contexto do cliente**. Sem isso, a Etapa 6 produziria um PDF bonito que
ninguém lê na hora de montar o mês seguinte — que é exatamente o destino da maioria dos relatórios
de performance.

## Grau de acoplamento

O `pauta-engine` funciona sozinho, com os arquivos de contexto preenchidos à mão. As outras skills
são aceleradores de etapa, não dependências. Quem adotar só o motor tem o processo completo; quem
adotar o conjunto tem o processo automatizado em mais pontos.
