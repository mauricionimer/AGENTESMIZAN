# Agentes do Mizan

Projeto do **AKCIT Camp 2026 — Agentes de IA**.

O Mizan é um software de recuperação de crédito para bancos e cooperativas. Ele
já prioriza a carteira, estima quanto cada dívida deve recuperar e mede o
resultado. Nesta etapa ganha agentes que **executam** a cobrança dentro das
regras do banco.

> O Mizan decide, mede e prova; o agente executa dentro das regras do banco.

O Mizan não é uma cobradora. O banco continua dono da relação com o cliente e
das regras; o Mizan é a ferramenta que aplica essas regras e registra cada
decisão.

## Os agentes

| Agente | O que faz | Tipo |
|---|---|---|
| Orquestrador | Recebe os eventos, decide quem age e guarda o estado de cada caso | Código |
| Triagem | Entende a intenção da mensagem do devedor | IA (modelo barato) |
| Estrategista | Divide a carteira em grupos e separa um grupo de controle sorteado | Código + modelo |
| Negociador | Conversa com o devedor e propõe acordos usando ferramentas | IA |
| Auditor | Confere cada ação contra a política do banco e tem a palavra final | Código |
| Acompanhamento | Cuida de datas, lembretes e pagamentos | Código |
| Aprendizado | Aprende com o dinheiro que entrou de fato, não com promessas | Código |
| Pessoa | Recebe o caso sempre que algo sai do previsto | Humano |

## Regras de projeto

- **Só o Negociador fala com o devedor**, e só com valores calculados pelo
  sistema: nenhum número no texto sai da cabeça da IA.
- **O Auditor é código, não IA.** Toda ação passa por ele e fica registrada a
  regra que permitiu ou bloqueou.
- **Na dúvida, uma pessoa.** Falha, contestação ou pedido do devedor levam o
  caso para uma pessoa, com resumo.
- **LGPD:** a IA recebe o mínimo (primeiro nome, valores, datas); o devedor
  pode pedir uma pessoa a qualquer momento; a primeira mensagem diz que é um
  assistente virtual.
- **Custo controlado:** teto diário por empresa; acima dele o agente para.

## Documentação

- [Fluxo dos agentes](docs/AGENTE_FLUXO.md): entradas, lógica e saídas de cada agente, com diagramas
- [Business Model Canvas](docs/BMC.md) (versão 1)
- [Roteiro da demonstração e do pitch](docs/ROTEIRO_DEMO_E_PITCH.md)
- [Levantamento das alternativas](docs/ALTERNATIVAS.md), com fontes

## Andamento

| Parte | Situação |
|---|---|
| Orquestrador, estado do caso, rastreio e controle de custo | Feito, com testes |
| Auditor com política versionada e tela de Política | Feito, com testes |
| Triagem, Negociador (14 ferramentas) e travas de saída | Feito, testado com IA simulada |
| Acompanhamento: lembretes, atrasos e pagamentos | Feito, com testes |
| Estrategista: quatro grupos e grupo sorteado | Feito, com testes |
| Telas: Conversa, Plano do dia, Política, Central de orquestração | Feito |
| Bateria de 63 cenários (181 conferências) | Feito; nota 100 com IA simulada |
| Primeira conversa com a IA de verdade e nota real da bateria | A fazer (19/10) |
| Demonstração de ponta a ponta com carteira fictícia | A fazer (20/10) |

O código do Mizan fica em repositório privado. Este repositório reúne a
documentação, o fluxo dos agentes e as entregas do AKCIT Camp.
