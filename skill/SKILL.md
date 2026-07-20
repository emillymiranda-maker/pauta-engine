---
name: pauta-engine
description: >
  Transforma contexto, objetivos e repertório de um cliente em uma pauta mensal de social media
  que já nasce pronta para execução e para aprendizado — cada post com briefing completo, copy
  final e uma hipótese de engajamento falseável com métrica de leitura definida antes de publicar.
  Use SEMPRE que for criar, montar, gerar ou refazer a pauta de um cliente (mensal, quinzenal ou
  post avulso) — mesmo que a palavra "pauta" não apareça. Ative também em "monta a pauta de
  [cliente]", "cria o calendário de [mês]", "preciso do briefing de [post]", "faz os posts de
  [cliente]". Use também no fim do mês, quando chegarem as métricas, para fechar o ciclo de
  aprendizado ("como foi o mês", "lê os resultados", "o que aprendemos").
---

# Pauta Engine

Motor de produção de pauta de social media. O objetivo não é gerar temas — é gerar uma pauta que
qualquer pessoa da equipe consiga executar sem o autor por perto, e que produza aprendizado
mensurável mesmo quando o resultado é ruim.

**Premissa central:** a qualidade de uma pauta não vem da criatividade de quem escreve. Vem de
quatro insumos estruturados (contexto, memória, distribuição, hipótese) e de um gate que roda antes
da produção. Criatividade opera dentro desse esqueleto, não no lugar dele.

---

## O ciclo

```
[1] INTAKE  →  [2] MEMÓRIA  →  [3] DISTRIBUIÇÃO  →  [4] BRIEFING+HIPÓTESE  →  [5] GATE  →  produção
                    ↑                                                                          │
                    └──────────────────────  [6] LEITURA  ←───────────────────────────────────┘
```

As etapas 1 e 2 são leitura. A 3 é decisão estrutural. A 4 é escrita. A 5 é bloqueio. A 6 realimenta
a 2 — é o que impede o mês seguinte de ser uma repetição do anterior com palavras diferentes.

---

## Etapa 1 — INTAKE (obrigatória, nesta ordem)

Nunca escreva o primeiro post antes de ler, nesta sequência:

1. **`[Cliente]/CLAUDE.md`** — alinhamentos mais recentes. É o arquivo mais provável de conter algo
   que invalida o mês atual (mudança de tom, de identidade visual, de CTA, de regra de produção).
   Alinhamento de julho vence dossiê de maio, sempre.
2. **`[Cliente]/01_dossie.md`** e **`02_linha_editorial.md`** — posicionamento, personas, pilares,
   tom, proibições, hooks saturados, ângulos exclusivos ainda não usados.
3. **Memória de temas** (`[Cliente]/pautas/_memoria.md`, ver Etapa 2).
4. **Pauta do mês anterior** em `pautas/AAAA-MM/`.

Se qualquer um desses não existir, **pare e sinalize**. Não preencha a lacuna com suposição — pauta
construída sobre contexto inventado é o erro mais caro do processo, porque só aparece na aprovação
do cliente.

O que precisa estar respondido antes de seguir está em `reference/01-intake.md`.

## Etapa 2 — MEMÓRIA

A memória é o que substitui o repertório do autor. Sem ela, o processo depende de alguém lembrar o
que já foi feito — e é exatamente aí que a pauta vira dependente de uma pessoa.

Mantenha `[Cliente]/pautas/_memoria.md` com três listas vivas:

- **Temas e ângulos já publicados** — com o mês e o código do post. Um tema só volta se o dado
  justificar (ver Etapa 6), nunca por falta de ideia.
- **Ângulos exclusivos do dossiê ainda não usados** — a reserva estratégica. Todo mês deve estrear
  pelo menos um território novo enquanto houver reserva.
- **Alinhamentos datados** — o que mudou, quando, e o que isso invalida.

## Etapa 3 — DISTRIBUIÇÃO

Decida a estrutura do mês **antes** de pensar em qualquer tema. Isso evita o vício de escrever os
posts que vêm mais fácil à cabeça e descobrir no fim que o mês inteiro é topo de funil.

Fixe quatro eixos:

| Eixo | Regra |
|---|---|
| **Volume** | Conforme contrato (checar CLAUDE.md do cliente — varia, tipicamente 8–12) |
| **Pilar** | Respeitar a proporção documentada na linha editorial do cliente |
| **Funil** | Distribuir Topo/Meio/Fundo — nunca concentrar tudo num estágio, nunca 2 posts de Conversão consecutivos |
| **Dependência de produção** | Classificar cada post: autônomo (IA/material existente) ou dependente (foto nova, agenda, ação do cliente) |

**Regra de viabilidade:** se mais de 1/3 do mês depende de ação do cliente, o mês tem risco alto de
não sair. Reduza a dependência antes de escrever — não depois, quando já houver copy pronta para
jogar fora.

## Etapa 4 — BRIEFING + HIPÓTESE

É a etapa mais longa e a que mais se beneficia de sub-passos explícitos. Cada post percorre oito,
na ordem. Pular a ordem é o que produz post bonito que não serve ao slot que ele deveria ocupar.

### 4.1 — Herdar o slot

O post já chega com **pilar, estágio de funil e formato-alvo** definidos na Etapa 3. Escrever não é
decidir o que fazer: é preencher um slot com restrição conhecida. Isso inverte o vício de começar
pelas ideias que vêm fácil e descobrir no fim que falta fundo de funil.

### 4.2 — Selecionar o assunto

O assunto não é escolhido, é **derivado** de cinco fontes ordenadas por prioridade, passando por
quatro filtros bloqueantes:

**Fontes:** (1) reserva de ângulos exclusivos do dossiê · (2) dor da persona do slot + vocabulário
literal · (3) alinhamento recente · (4) território de portfólio nunca coberto · (5) benchmark do
nicho.

**Filtros:** (1) memória de temas — repetiu nos últimos 3 meses? bloqueado · (2) hooks saturados ·
(3) fronteira do afirmável · (4) produto já protagonista neste mês.

Se nenhuma fonte serve ao slot, **o slot troca de pilar** — nunca se inventa assunto para preencher
calendário. Detalhamento completo em `reference/06-selecao-de-assunto.md`.

Apoio: `copy-maestro` para ancorar o ângulo em dor, objeção e nível de consciência.

### 4.3 — Definir o formato pelo argumento

O formato-alvo da Etapa 3 é uma intenção; o argumento confirma ou corrige. O critério é a **forma
do raciocínio**, não estética:

| Se o argumento é… | Formato |
|---|---|
| Sequência, comparação, glossário, lista de sinais | Carrossel |
| Afirmação única que se sustenta sozinha | Estático |
| Demonstração, processo, movimento, bastidor | Reels |

Argumento de 4 passos espremido em estático perde o passo; afirmação única esticada em 5 slides
gera slide vazio. Se o formato mudar aqui, a Etapa 3 precisa ser reequilibrada.

### 4.4 — Escrever o hook

Headline do estático ou S1 do carrossel. Abre por **problema, norma ou dado** — nunca por
apresentação institucional. Usa o vocabulário literal da persona, não o vocabulário da categoria.
É a única linha que decide se o resto será lido.

### 4.5 — Desenvolver o corpo

Carrossel: um passo por slide, máximo 5, cada um com `Headline:` e `Subtexto:`. Reels: roteiro em
timecodes `00:00–00:06`. Estático: subtexto que completa a headline sem repeti-la.

Os passos 4.3 a 4.7 produzem a **camada de execução** — o briefing completo o bastante para o
design produzir sem perguntar nada. Formato exato em `reference/02-formato-briefing.md`.
Apoio: `roteirista-cinema-video` para o roteiro de Reels.

### 4.6 — Fechar CTA e hashtags

CTA no padrão vigente do cliente (checar alinhamentos — CTA muda). Exatamente 5 hashtags, mix de
nicho + segmento + marca.

### 4.7 — Direcionamento de produção

Declarar o modo (IA ou gravação), a referência visual e **o que não pode ser gerado** — simular
instalação real de cliente nomeado, produto que a empresa não fabrica, ambiente não verificável.
Este campo é o que determina se o post é executável sem o cliente.
Apoio: `image-prompt-generator` e `roteirista-cinema-video` convertem o direcionamento em prompt.

### 4.8 — Escrever a hipótese

**Camada de aprendizado** — três linhas obrigatórias:

```
Hipótese: [quem] vai [ação esperada] porque [razão ancorada na persona/dor]
Métrica de leitura: [métrica específica] (referência: [número ou "primeira medição"])
Se falhar: [a leitura que se faz do fracasso e o próximo teste]
```

A linha `Se falhar` é a mais importante e a mais pulada. Sem ela, um post ruim vira só um post ruim.
Com ela, vira um dado. Regras completas em `reference/03-hipotese-engajamento.md`.

**Um post sem hipótese não está pronto.** Não é campo opcional.

## Etapa 5 — GATE

Antes de entregar, rode o checklist de `reference/04-gate-revisao.md`. Ele é bloqueante: qualquer
item reprovado volta para a Etapa 4. O gate pega o que a escrita isolada não enxerga — repetição
com meses anteriores, mix desequilibrado, política comercial não confirmada, dependência de produção
não sinalizada, post sem hipótese.

Registre no fim da pauta o que o gate reprovou e como foi corrigido. Isso é o rastro que prova que
o processo rodou, e não que alguém acertou de primeira.

## Etapa 6 — LEITURA (fim do mês)

Quando as métricas chegarem, confronte cada hipótese com o resultado e classifique:

- **Confirmada** → o ângulo entra na lista de apostas seguras da memória.
- **Refutada** → aplique a linha `Se falhar` que já estava escrita. O próximo teste já está definido;
  não é preciso inventar explicação depois do fato.
- **Inconclusiva** → distribuição/alcance atrapalhou a leitura. Repita o teste antes de descartar o ângulo.

Escreva o resultado em `[Cliente]/pautas/_memoria.md`. É esse arquivo que a Etapa 1 do mês seguinte
vai ler. O ciclo fecha aqui. Procedimento em `reference/05-leitura-mensal.md`.

---

## Princípios

**Não invente informação.** Estoque, produto, prazo, frete, garantia, política comercial, nome de
cliente atendido — se não está no dossiê ou no CLAUDE.md, ou você omite ou marca como pendência
explícita. Nunca preencha por plausibilidade.

**Alinhamento recente vence documento antigo.** Um dossiê de maio pode estar errado se houve
check-in em julho.

**Prefira o post autônomo, sem sacrificar a estratégia.** Reduzir dependência do cliente é bom até o
ponto em que começa a abandonar formatos que a estratégia prioriza. Se o cliente investiu em vídeo
para reverter queda de alcance, não elimine todos os Reels em nome da conveniência — equilibre.

**Hipótese errada documentada vale mais que post bom sem hipótese.** O primeiro produz aprendizado
transferível para o próximo mês e para outras contas. O segundo produz um número que ninguém sabe
explicar.
