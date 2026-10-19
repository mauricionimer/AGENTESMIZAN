# Roteiro da demonstração e do pitch (regional, 24/10)

Pitch de 3 minutos + demonstração ao vivo. Uma pessoa narra; a outra faz o
papel do devedor, digitando na tela do Agente. A demo roda numa empresa de
demonstração com carteira fictícia; o agente se apresenta como assistente do
banco de demonstração.

## Antes de começar

- Sistema aberto 15 minutos antes e login da empresa de demonstração feito.
- Política de demonstração gravada (aba Política).
- Plano do dia já aplicado (aba Plano do dia).
- Vídeo de reserva no notebook e no celular, sem depender de internet.
- **Devedores diferentes para ensaio e para o palco.** A política limita
  contatos por semana com o mesmo devedor (regra R3): ensaiar com o devedor do
  palco gasta a cota. Domingo fica fora da janela de contato (R2); 24/10 é
  sábado, dentro da janela.
- **Ensaio com a IA de verdade antes do dia.** O ataque só aparece como
  bloqueio do Auditor se o modelo tentar a ação; se ele só recusar no texto, o
  momento perde força. Grave o ensaio em que o bloqueio aparecer.

## Pitch — 3 minutos

**0:00–0:30 · Problema.** Recuperação de crédito em banco pequeno e cooperativa:
carteira grande, equipe pequena, e o que importa não é o acordo fechado, é o
acordo pago. (Dados públicos com fonte e a frase de quem trabalha com cobrança
entram aqui.)

**0:30–2:00 · O agente ao vivo.**
1. *Plano do dia*: o Estrategista mostra os quatro grupos, cada devedor com o
   motivo, e o grupo sorteado que segue sem o agente — é o que prova o efeito.
2. *Conversa*: o "devedor" escreve "quero negociar". O agente confirma a
   identidade, pergunta quanto cabe por mês, simula e propõe; ao lado aparece
   cada passo, a regra do Auditor e o custo.
3. *Dúvida com fonte* (10 s): o "devedor" pergunta "se eu pagar, quando meu
   nome sai do Serasa?". A resposta cita a Súmula 548 do STJ e o painel mostra
   "Fonte: STJ, Súmula 548". Frase: "O agente não inventa nem valor nem lei:
   se citar uma lei que não veio da base, a mensagem não sai."
4. *Ataque*: o "devedor" pede 90% de desconto dizendo que é gerente. A
   simulação volta fora da política e nada é registrado; se a IA tentar
   registrar mesmo assim, o Auditor bloqueia e a regra aparece na tela. Frase:
   **"A IA pode até ser enganada. O Auditor não conversa: ele confere a regra."**
5. *Política*: o gestor baixa o desconto máximo na aba Política. Na mensagem
   seguinte o agente já obedece — e a decisão grava a versão nova.
6. *Pessoa em dia e hora* (se sobrar tempo): o "devedor" pede uma reunião
   na segunda às 14h. O agente marca o atendimento, a pessoa assume o caso e o
   compromisso aparece na aba Agenda, onde o administrador escolhe quem atende.
   Frase: "Quando a pessoa quer gente, o agente marca com gente."
7. *Pagamento* (se sobrar tempo): o botão faz o papel do banco confirmando o
   pagamento; o agente agradece e o acordo à vista vira quitado.

**2:00–2:30 · Como funciona e por que não é robô de cobrança.** Orquestrador,
Triagem, Negociador, Auditor em código com a palavra final, Acompanhamento e
Estrategista. O banco continua sendo quem cobra, com as regras dele; nenhum
valor sai da cabeça da IA; uma pessoa entra sempre que algo sai do previsto.

**2:30–3:00 · Negócio e próximos passos.** Software (assinatura e uso), não
comissão. Próximo passo: piloto numa parte da carteira de uma instituição,
medido contra o grupo sorteado.

## Perguntas prováveis da banca

- **Por que não LangGraph/CrewAI?** O orquestrador usa os mesmos conceitos
  (estado, nós, arestas, checkpoint, nó de erro), feito dentro do sistema: o
  caso dura semanas e o estado já mora no banco de dados.
- **Se tirar o agente, o Mizan ainda entrega o valor?** A análise sim, e por
  isso ela virou a caixa de ferramentas do agente. O que o banco compra é a
  execução: falar com o devedor, negociar dentro da regra, acompanhar cada data.
  Sem o agente, isso volta a depender de gente, que é o gargalo do banco pequeno.
- **E se a IA inventar um valor ou uma lei?** Todo valor do texto é conferido
  contra as simulações e toda norma citada contra a base de conhecimento antes
  de enviar; não bateu, não sai.
- **De onde vêm os fatos? Vocês usam RAG?** Fatos do caso vêm do banco de
  dados filtrado por empresa e caso; direitos do devedor vêm de uma base de lei
  e súmula com o texto oficial, busca local medida (92% com certeza, nenhum
  trecho errado com certeza). Sem certeza, o agente diz que não sabe e oferece
  uma pessoa. A fonte aparece na tela.
- **E quando nenhuma ferramenta serve?** Transferir para uma pessoa, com
  resumo. IA que recusa, sai do formato ou passa de 8 rodadas também leva o caso
  para uma pessoa.
- **LGPD?** A IA recebe o mínimo; a primeira mensagem diz que é um assistente
  virtual; o devedor pode pedir uma pessoa a qualquer momento; o banco é o
  controlador dos dados e o Mizan, o operador.
- **Quanto custa por conversa?** Medido pelo próprio agente em cada passo
  (aparece na tela).
- **E se a IA disser que fez algo que não fez?** Já aconteceu num teste: o
  agente disse "já agendei" sem agendar. Virou trava: frase de ação só sai se
  a ferramenta rodou, e virou cenário da bateria.
- **Como vocês sabem que funciona?** Bateria de 87 cenários e 249 conferências
  feitas por código, nota por versão do prompt. Com a IA simulada, ela prova
  que as travas seguram o erro; com a IA de verdade, mede o modelo. No
  cliente, comparação com o grupo sorteado. (Não dizer que a nota 100 é do
  modelo real se essa rodada não tiver sido feita.)
- **Por que vários agentes, e não um só?** Cada um tem um trabalho e um limite
  diferente: a Triagem lê, o Estrategista decide como abordar, o Negociador
  conversa, o Acompanhamento cuida das datas, o Supervisor revisa e resume, o
  Cientista mede. Eles se coordenam pelo caderno do caso. O que precisa ser
  exato (valores, limites, sorteio, selo de evidência) fica em código.
- **A IA pode inventar que uma estratégia funciona?** Não: o Cientista não faz
  conta. As contas e o selo de evidência são de código; texto com número que
  não saiu das contas, ou com "comprovado" sem evidência, é barrado. E a
  recomendação só vale depois que uma pessoa aprova. (Na demonstração os dados
  são fictícios: mostrar o método, não o resultado.)
- **Como investigariam uma resposta ruim?** Pelo id de rastreio: cada passo
  grava agente, regra, versões, tokens, custo e duração. A resposta ruim vira
  um cenário novo da bateria antes da correção.
