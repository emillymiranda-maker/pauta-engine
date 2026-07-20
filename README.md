# Pauta Engine

**Como transformar contexto, objetivos e repertório do cliente em uma pauta mensal que já nasce
pronta para execução e para aprendizado.**

Entrega para a quest Q-2026-002 · V4-79 — *Pauta de social media*.

🔗 **[Fluxograma do processo](https://emillymiranda-maker.github.io/pauta-engine/)**
📁 **[Workflow executável (a skill)](skill/SKILL.md)**
📄 **[Evidência de output real](caso/02-pauta-agosto.md)**

---

## O problema

Pauta de social media é quase sempre um dos dois extremos: uma lista de temas que o design não
consegue produzir sem perguntar, ou um calendário bonito que ninguém sabe explicar depois — quando
o mês vai bem, inventa-se uma razão; quando vai mal, culpa-se o algoritmo. Nos dois casos o mês
seguinte não aprende nada.

E há um terceiro problema, mais silencioso: a pauta boa costuma depender de quem a escreve. O
processo existe na cabeça de uma pessoa. Quando ela sai de férias, a qualidade cai — o que prova
que nunca houve processo, só repertório.

## A tese

A qualidade de uma pauta não vem da criatividade de quem escreve. Vem de **quatro insumos
estruturados** — contexto, memória, distribuição e hipótese — e de **um gate que roda antes da
produção**. A criatividade opera dentro desse esqueleto, não no lugar dele.

Disso saem duas propriedades que a maioria dos processos de pauta não tem:

**Executável sem o autor.** O repertório vira arquivo. A memória de temas é contada, não lembrada.
Um substituto abre quatro arquivos e produz o mês.

**Falseável.** Cada post carrega uma hipótese de engajamento com métrica declarada **antes** de
publicar, e uma leitura pré-comprometida do fracasso. Post ruim vira dado em vez de ruído.

---

## O ciclo

```
[1] INTAKE  →  [2] MEMÓRIA  →  [3] DISTRIBUIÇÃO  →  [4] BRIEFING+HIPÓTESE  →  [5] GATE  →  produção
                    ↑                                                                          │
                    └──────────────────────  [6] LEITURA  ←───────────────────────────────────┘
```

| # | Etapa | Entrada | Saída | Decisão humana |
|---|---|---|---|---|
| 1 | **Intake** | Dossiê, linha editorial, alinhamentos datados | Contexto verificado | Aceitar lacuna ou parar e perguntar ao cliente |
| 2 | **Memória** | Pautas anteriores, vereditos, reserva de ângulos | Lista de temas queimados e territórios livres | Autorizar repetição de tema quando o dado justificar |
| 3 | **Distribuição** | Contrato, pilares, funil, capacidade de produção | Estrutura do mês, antes de qualquer tema | Aceitar o nível de dependência do cliente |
| 4 | **Briefing + hipótese** | Estrutura + contexto | 8–12 posts com copy final e hipótese | Escrita, ângulo, escolha da métrica |
| 5 | **Gate** | Pauta completa | Aprovação ou devolução | Julgar exceção legítima vs. desvio |
| 6 | **Leitura** | Métricas do mês | Vereditos + mudança de distribuição | Distinguir refutada de inconclusiva |

**A etapa 6 é a que fecha o circuito.** Sem ela o sistema entrega execução mas não aprendizado, e a
pauta do mês 7 é a do mês 1 com sinônimos.

---

## Dentro da etapa 4 — como um post é construído

A etapa mais longa do ciclo tem oito sub-passos. Percorrê-los fora de ordem é o que produz post
bonito que não serve ao slot que deveria ocupar.

| # | Sub-passo | O que decide |
|---|---|---|
| 4.1 | Herdar o slot | Pilar, funil e formato-alvo já vêm da etapa 3 — escrever é preencher, não escolher |
| 4.2 | **Selecionar o assunto** | 5 fontes ordenadas, 4 filtros bloqueantes |
| 4.3 | Formato pelo argumento | A forma do raciocínio decide, não a estética |
| 4.4 | Hook | Abre por problema, norma ou dado — nunca institucional |
| 4.5 | Corpo | Um passo por slide; timecodes no Reels |
| 4.6 | CTA + hashtags | CTA no padrão vigente; exatamente 5 tags |
| 4.7 | Direção de produção | IA ou gravação, e o que **não** pode ser gerado |
| 4.8 | Hipótese | As três linhas, antes de publicar |

### A seleção de assunto (4.2)

É a pergunta mais decisiva do processo e a que mais costuma ser respondida por intuição — motivo
pelo qual a pauta acaba dependendo de quem escreve. Aqui o assunto **não é escolhido, é derivado**.

**5 fontes, em ordem de prioridade:** (1) reserva de ângulos exclusivos do dossiê · (2) dor da
persona do slot + vocabulário literal · (3) alinhamento recente · (4) território de portfólio nunca
coberto · (5) benchmark do nicho.

**4 filtros bloqueantes:** (1) memória de temas — repetiu nos últimos 3 meses? bloqueado ·
(2) hooks saturados · (3) fronteira do afirmável · (4) produto já protagonista neste mês.

Se nenhuma fonte serve ao slot, **o slot troca de pilar** — nunca se inventa assunto para preencher
calendário. É assim que nasce o post genérico que não serve a ninguém.

Detalhamento: [`skill/reference/06-selecao-de-assunto.md`](skill/reference/06-selecao-de-assunto.md)

---

## Ecossistema de skills

O Pauta Engine é o motor central de nove skills construídas para a operação. A saída de uma é a
entrada da próxima, e todas escrevem nos mesmos arquivos do cliente.

| Skill | Etapa | O que resolve |
|---|---|---|
| `onboarding-cliente` | 0 | Estrutura do cliente novo a partir do kick-off — evita o dossiê incompleto, causa raiz de pauta fraca |
| `alinhamento-cliente` | alimenta 1 e 2 | Registra alinhamentos de reunião no contexto — torna verificável a regra "alinhamento recente vence documento antigo" |
| `social-media-maestro` | 1 e 3 | Pesquisa, linha editorial, pilares e distribuição de funil |
| `copy-maestro` | 4.2 e 4.4 | Persona, jornada, consciência, dores e objeções — ancora ângulo e hook |
| **`pauta-engine`** | **3, 4 e 5** | **O motor: distribuição, seleção de assunto, briefing, hipótese e gate** |
| `roteirista-cinema-video` | 4.5 e 4.7 | Roteiro de Reels em prompt de vídeo, com consistência entre cenas |
| `image-prompt-generator` | 4.7 | Direcionamento visual do briefing → prompt estruturado |
| `revisor-pauta` | 5 | Segunda camada: coerência, mix, funil, repetição, viabilidade |
| `analisador-metricas` | 6 | Lê métricas, correlaciona conteúdo com resultado **e grava os achados de volta no contexto** |

O ponto de fechamento é o `analisador-metricas`: ele não só produz o relatório do mês, ele escreve
os achados de volta no contexto do cliente. Sem isso, a etapa 6 geraria um PDF bonito que ninguém
lê na hora de montar o mês seguinte — que é o destino da maioria dos relatórios de performance.

O motor funciona sozinho, com os arquivos de contexto preenchidos à mão. As demais são aceleradores
de etapa, não dependências.

Detalhamento: [`skill/reference/07-ecossistema-de-skills.md`](skill/reference/07-ecossistema-de-skills.md)

---

## A peça central: hipótese de engajamento

Cada post recebe três linhas obrigatórias, escritas antes de publicar:

```
Hipótese: [quem] vai [ação observável] porque [razão ancorada em dor documentada]
Métrica de leitura: [uma métrica] (referência: [número anterior] ou [primeira medição])
Se falhar: [interpretação pré-comprometida] → [próximo teste]
```

A terceira linha é a que quase todo mundo pula, e é a que faz o sistema funcionar. Escrita depois
do resultado, ela é racionalização. Escrita antes, ela é o plano de setembro já decidido.

E ela precisa separar as duas causas possíveis de fracasso — **o tema não interessa** ou **o formato
não serviu ao tema** — porque as correções são opostas. Trocar uma quando o problema era a outra
queima mais um mês.

Regras completas: [`skill/reference/03-hipotese-engajamento.md`](skill/reference/03-hipotese-engajamento.md)

---

## O caso

Conta B2B industrial, nicho de conformidade sanitária, **partindo do zero absoluto**: sem audiência
herdada, sem histórico de conteúdo, sem acervo de material. Cliente anonimizado sob o alias
Vedaplan.

O ponto de partida importa mais que o resultado. Não havia repertório prévio — do cliente nem do
operador — que pudesse explicar a performance. O que sobra é o processo.

| Etapa | Arquivo |
|---|---|
| 1 — Intake | [`caso/00-contexto.md`](caso/00-contexto.md) |
| 2 — Memória | [`caso/01-memoria.md`](caso/01-memoria.md) |
| 3, 4 e 5 — Pauta completa + gate | [`caso/02-pauta-agosto.md`](caso/02-pauta-agosto.md) |
| 6 — Leitura e loop | [`caso/03-leitura-e-loop.md`](caso/03-leitura-e-loop.md) |

**Primeiro mês completo:** views +541%, alcance +654%, 91 toques no botão de orçamento.

**Pauta de agosto:** 8 posts com copy final · 3 ângulos exclusivos estreados · 5 reprovações do gate
registradas com correção · **0 de 8 posts dependem de ação do cliente** · 8 de 8 com hipótese.

---

## Como outra pessoa repete isto

1. Copie `skill/` para `.claude/skills/pauta-engine/` no seu workspace
2. Garanta que o cliente tem `CLAUDE.md`, `01_dossie.md` e `02_linha_editorial.md` preenchidos —
   o gabarito do que precisa estar respondido está em
   [`skill/reference/01-intake.md`](skill/reference/01-intake.md)
3. Crie `[Cliente]/pautas/_memoria.md` (modelo: [`caso/01-memoria.md`](caso/01-memoria.md))
4. Peça: *"monta a pauta de [cliente] para [mês]"*
5. No fim do mês, com as métricas em mãos: *"lê os resultados de [mês]"*

Sem os arquivos do passo 2, o sistema **para e pergunta** em vez de inventar contexto. Esse
comportamento é intencional: pauta construída sobre suposição é o erro mais caro do processo,
porque só aparece na aprovação do cliente.

---

## Limitações conhecidas

- **A etapa 6 nunca rodou com dados de agosto.** As consequências de setembro estão
  pré-comprometidas por escrito, mas o ciclo completo ainda não fechou uma volta inteira com este
  formato de hipótese. Isso é declarado no próprio caso.
- **A hipótese depende de referência.** No primeiro mês de uma conta não há número anterior; o post
  vira linha de base. O sistema funciona, mas só produz veredito a partir do segundo mês.
- **Métricas entram à mão.** A leitura mensal ainda é alimentada por exportação do Meta Business
  Suite, não por API. Automatizar isso é o próximo passo óbvio.
- **O gate é uma checagem assistida, não um teste automatizado.** Ele não roda sozinho em CI — é uma
  lista bloqueante que um humano ou o agente percorre.
- **Não cobre distribuição paga.** Se o alcance vem de impulsionamento, a hipótese fica
  inconclusiva por construção — o sistema sabe disso e classifica assim, mas não separa orgânico de
  pago automaticamente.
- **Validado em profundidade numa conta B2B industrial.** O esqueleto foi aplicado em outras contas
  da carteira, mas o caso documentado aqui é um só.
