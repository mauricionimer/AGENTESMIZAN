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
| Estrategista | Quem cobrar e o sorteio do grupo de comparação: código. Como abordar cada devedor (tom, oferta, adiar), com o bandit do Mizan como conselheiro | Código + IA |
| Triagem | Entende intenção, emoção, urgência e ironia da mensagem; regras de segurança vencem a IA | IA (modelo barato) |
| Negociador | Conversa com o devedor, propõe acordos e tira dúvidas com lei e súmula citadas, usando 16 ferramentas | IA |
| Acompanhamento | Em cada data, escolhe de um cardápio fechado (lembrar, oferecer nova data, chamar uma pessoa...) e escreve a mensagem | IA, com mensagem pronta como reserva |
| Supervisor | Resume o caso para a equipe e revisa o tom em conversa delicada; não libera nada | IA |
| Cientista | Compara agente e grupo sorteado e propõe o próximo passo; contas e selo de evidência em código | IA interpreta, código calcula |
| Auditor | Confere cada ação contra a política do banco e tem a palavra final | Código, de propósito |
| Pessoa | Recebe o caso sempre que algo sai do previsto e aprova as recomendações do Cientista | Humano |

Os agentes se coordenam por um **caderno do caso**: cada um anota o que
decidiu e por quê, e os outros leem antes de agir. Todo agente com IA tem um
caminho em código para quando a IA falha, e cada um liga e desliga sozinho,
sem deploy.

## Regras de projeto

- **A IA decide; o código impede o proibido.** Toda mensagem ao devedor passa
  pelas travas: valor só se calculado pelo sistema, nenhum número da cabeça da
  IA, nenhuma ameaça.
- **Nenhuma lei sem fonte.** Toda lei, artigo ou súmula que o agente cita vem
  da base de conhecimento, com o texto oficial; citação sem fonte é barrada.
- **Nada de dizer que fez sem ter feito.** "Agendei", "registrei" ou
  "transferi" só saem se a ferramenta rodou de verdade; pagamento, só o banco
  confirma.
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
| Triagem, Negociador (16 ferramentas) e travas de saída | Feito; testado com IA simulada e com IA de verdade (Gemini, 16/10) |
| Agenda dos agentes e atendimento com pessoa em dia e hora | Feito, com testes (16/10) |
| Base de conhecimento do devedor (RAG com fonte) e trava de citação | Feito, com testes e busca medida (16/10) |
| Acompanhamento: lembretes, atrasos e pagamentos | Feito, com testes |
| Estrategista: quatro grupos e grupo sorteado | Feito, com testes |
| Agentes que pensam com IA: caderno do caso, Triagem com emoção e ironia, Acompanhamento, Estrategista com bandit, Supervisor, Cientista | Feito (17/10), com testes e cada um testado com IA de verdade (Gemini) |
| Telas: Conversa (com o caderno do caso), Plano do dia (com o raciocínio da IA), Agenda, Política, Laboratório, Central | Feito |
| Bateria de 86 cenários (245 conferências), 105 scripts de teste | Feito; nota 100 com IA simulada (prova as travas, não o modelo) |
| Primeira conversa com a IA de verdade | Feito (16/10, Gemini): manipulação, lei com fonte, agenda e atendimento |
| Nota real da bateria com a IA de verdade | A fazer (19/10) |
| Demonstração de ponta a ponta com carteira fictícia | A fazer (20/10) |

O código do Mizan fica em repositório privado. Este repositório reúne a
documentação, o fluxo dos agentes e as entregas do AKCIT Camp.
