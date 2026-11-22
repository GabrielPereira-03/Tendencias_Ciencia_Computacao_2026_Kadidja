# Assistente Virtual de SLA — projeto de estudo relacionado à VERT Analytics

**Disciplina:** Tendências em Ciência da Computação  
**Unidade:** 4 — Aplicações e Limitações  
**Semestre:** 2026.2  
**Estudante:** Gabriel Tavares  
**Tema:** Chatbot para consulta, cálculo e acompanhamento de SLA em chamados de TI  
**Situação:** aplicação com funcionalidades implementadas na versão 2.0 e uma demonstração experimental da versão 3.0. Não há, neste registro, comprovação de implantação ou homologação corporativa.

> **Sobre o material:** este texto descreve um projeto técnico de estudo relacionado a rotinas de atendimento da VERT Analytics. Não é uma documentação oficial da empresa. O código-fonte está em um repositório privado; por isso, esta pasta não contém credenciais, informações reais de chamados, dados de clientes ou configurações de acesso a sistemas internos.

---

## 1. Por que pensamos em um chatbot para SLA?

No atendimento de TI, acompanhar um chamado não significa olhar somente se ele está aberto ou fechado. Também é necessário considerar **quando foi aberto, qual é a prioridade, qual regra de SLA se aplica e em quais intervalos o prazo ficou ativo ou suspenso**.

Parte desse trabalho envolve consultar registros no sistema de chamados, interpretar o histórico de eventos e calcular o tempo consumido. Quando muitas consultas são repetidas durante a rotina, faz sentido estudar uma maneira de reunir essas informações em uma interface mais direta.

A ideia do nosso projeto é permitir que a pessoa faça perguntas sobre um chamado ou solicite um relatório pelo próprio chat, sem precisar repetir manualmente todo o cálculo.

**SLA (Service Level Agreement)** é o acordo de nível de serviço usado para definir, entre outras coisas, prazos e critérios de atendimento. Um cálculo incorreto pode levar a uma conclusão errada sobre o cumprimento desses prazos. Por isso, o chatbot precisa respeitar as regras utilizadas pela calculadora, e não inventar resultados.

## 2. O que compõe o projeto?

O chatbot faz parte de uma aplicação maior, chamada **SLA Engine**, que reúne uma calculadora, consultas de chamados, relatórios e uma interface conversacional.

| Componente | Papel no projeto |
|---|---|
| **Interface em Streamlit** | Apresenta as telas da calculadora e do assistente no navegador |
| **Python** | Interpreta pedidos e executa as rotinas do sistema |
| **Consulta ao OTRS/MySQL** | Busca registros e históricos de chamados quando a integração está configurada e disponível |
| **Motor de cálculo de SLA** | Considera metas, períodos contabilizados e regras de horário |
| **PostgreSQL** | Guarda o histórico de interações e as associações de comandos ensinadas ao assistente na versão 2.0 |
| **Geração de relatórios** | Produz PDFs de chamados e períodos na versão integrada; a demonstração 3.0 também gera Excel |
| **Docker** | Organiza os serviços e as dependências do ambiente de execução |

A ligação com o banco de chamados é usada para **consultar** informações. O objetivo não é permitir que o chatbot altere o status de um ticket ou edite dados operacionais no OTRS.

## 3. Como funciona uma pergunta enviada ao chat?

O funcionamento pode ser entendido em seis etapas:

```text
Usuário escreve uma pergunta
          |
          v
1. O texto é normalizado (minúsculas, acentos e espaços)
          |
          v
2. O sistema procura nº de chamado, contrato e período
          |
          v
3. Identifica a intenção por regras e palavras-chave
          |
          v
4. Usa o contexto recente e escolhe a função adequada
          |
          v
5. Consulta os dados e calcula o resultado, se necessário
          |
          v
6. Responde no chat ou disponibiliza um relatório
```

Por exemplo, ao informar o número de um chamado, o assistente pode direcionar a solicitação para a rotina de consulta individual. Se a pessoa perguntar em seguida **“quando atinge os marcos?”**, o sistema usa o chamado da conversa para calcular os marcos previstos.

Já um pedido de relatório por período segue outro caminho: são identificados os filtros de data e contrato; depois, a aplicação consulta os registros correspondentes e monta o arquivo.

### O que significa “entender” a pergunta neste projeto?

Este ponto é importante para a disciplina: **o assistente atual não utiliza um modelo generativo para interpretar livremente qualquer mensagem**. Seu mecanismo principal é uma combinação de normalização de texto, expressões regulares, palavras-chave, comandos cadastrados e regras de direcionamento.

Isso permite reconhecer perguntas conhecidas de forma relativamente previsível, mas também limita o entendimento de frases novas ou ambíguas. A inclusão de um modelo de linguagem mais avançado é uma possibilidade de evolução, **não uma funcionalidade que já esteja integrada à versão principal**.

## 4. Funcionalidades presentes na versão 2.0

A versão principal contém rotinas para as seguintes situações:

| Solicitação | O que o sistema procura entregar |
|---|---|
| **Consultar um chamado** | Dados gerais, severidade, meta de SLA, tempo consumido, percentual utilizado e situação |
| **Ver marcos do SLA** | Projeções ou indicação de atingimento dos pontos de 25%, 50%, 75% e 100% da meta |
| **Ver períodos contabilizados** | Intervalos usados para compor o tempo de SLA do chamado |
| **Consultar notas** | Apontamentos registrados no histórico, com tratamento para ignorar algumas mensagens automáticas |
| **Gerar informativo** | Texto estruturado para comunicação de acompanhamento do chamado |
| **Gerar PDF individual** | Relatório de auditoria com informações do ticket e cálculo |
| **Consultar um contrato** | Resumo de volume e situação de chamados em um intervalo recente |
| **Gerar PDF por período** | Relatório consolidado a partir de filtros de contrato e datas |
| **Consultar memória do assistente** | Estatísticas das interações e das regras registradas |
| **Cadastrar novas expressões** | Associação de uma frase a uma intenção que o sistema já conhece |

A presença dessas rotinas no código **não garante que todas estejam disponíveis em qualquer computador**: consultas e relatórios dependem de bibliotecas, configuração e acesso autorizado aos dados.

### Como o cálculo de SLA entra nessa conversa?

Quando um chamado é consultado, o programa lê informações como abertura, prioridade e alterações de estado. A partir desses registros, identifica intervalos contabilizáveis e aplica regras de SLA ligadas ao contrato e à severidade.

O resultado inclui o tempo acumulado, a meta contratada e o percentual consumido. Para as projeções, o sistema estima quando cada marco será atingido, usando o tempo já gasto e o calendário considerado.

Uma dificuldade real desse tipo de solução é decidir **quais estados do chamado devem interromper ou retomar a contagem**. Essa regra depende do contrato. Não basta assumir que toda alteração para “pendente” representa uma pausa válida.

## 5. Exemplos de interação

Os exemplos abaixo são **ilustrativos**, sem dados reais de clientes ou chamados. Um número fictício pode não existir no banco e, nesse caso, a consulta não terá resultado.

**Exemplo A — consulta de chamado**

```text
Usuário: 1234567
Assistente: procura o chamado e, se encontrado, apresenta os dados e o SLA.

Usuário: Quando atinge os marcos?
Assistente: apresenta os marcos estimados de 25%, 50%, 75% e 100%.

Usuário: Gere um PDF.
Assistente: prepara o relatório do mesmo chamado.
```

**Exemplo B — relatório consolidado**

```text
Usuário: Relatório PDF de TODOS mês atual
Assistente: interpreta o período e tenta gerar um PDF consolidado.
```

**Exemplo C — comando não reconhecido**

Quando a intenção não é identificada, o assistente informa que não compreendeu a solicitação. A mensagem pode ser registrada como uma falha de interpretação, para revisão posterior.

Esses exemplos mostram o fluxo esperado no código. Não são registros de testes executados para esta entrega acadêmica.

## 6. Memória e comandos personalizados

O projeto usa dois tipos de contexto, que não devem ser confundidos.

**Contexto da conversa:** a interface mantém, durante a sessão, o último chamado ou contrato pesquisado. Assim, perguntas posteriores podem aproveitar essa informação sem repetir todos os dados.

**Memória no PostgreSQL:** há tabelas para registrar a mensagem recebida, a intenção identificada, a entidade relacionada e a data da interação. Outra tabela guarda associações entre expressões e intenções.

O comando de ensino permite cadastrar uma expressão alternativa para uma função existente. Por exemplo, uma frase de atalho pode ser vinculada à rotina de relatório por período.

Isso é uma forma de **personalização de comandos por regras**, não um treinamento automático de modelo de inteligência artificial. O sistema não aprende a executar uma habilidade completamente nova apenas porque o usuário escreveu uma frase.

Como mensagens podem conter referências a chamados ou outras informações, o histórico deve ser tratado com atenção: tempo de retenção, acesso, necessidade de registro e proteção de dados precisam ser definidos antes de um uso corporativo.

## 7. O que existe na demonstração 3.0?

Além da aplicação principal, o projeto tem uma branch experimental chamada `develop-v3`, com **um ambiente de demonstração separado**.

Nessa versão de testes há uma interface com dashboard, calculadora, área de relatórios e um assistente voltado a pedidos de relatório. Ela utiliza **dados fictícios**, sem consulta ao OTRS e sem autenticação corporativa.

Na demonstração, o assistente consegue interpretar pedidos limitados de relatórios por contrato e período e disponibilizar arquivos em **PDF ou Excel**. Também foi iniciado um motor de SLA independente, com funções de contagem de tempo, tratamento de pausas e previsão de vencimento, acompanhado de testes unitários.

**É importante não misturar as duas situações:**

| Situação | O que está documentado |
|---|---|
| **Versão 2.0** | Assistente integrado à calculadora, com consultas condicionadas à conexão de dados e relatórios PDF |
| **Demonstração 3.0** | Interface e relatórios PDF/Excel com dados sintéticos, sem integração corporativa |
| **Integração definitiva da 3.0** | Ainda depende de validação de regras, segurança, permissões e homologação |

O novo motor da versão 3.0 **ainda não substitui automaticamente o cálculo da aplicação principal**. Antes disso, é necessário comparar os resultados e conferir as regras de cada contrato.

## 8. Relação com a Unidade 4 — agentes e ética

O [guia da professora](../Guia_A1_Agentes_de_IA_e_%C3%89tica%20%28Tendencias%29%20%281%29.pdf) apresenta quatro camadas para analisar a arquitetura de um agente. Podemos usar esse modelo para **estudar** nosso chatbot, mesmo que sua implementação atual seja baseada em regras:

| Camada estudada | Exemplo no projeto |
|---|---|
| **Perceptiva** | Receber a mensagem digitada no chat |
| **Cognitiva** | Extrair dados e identificar a intenção da solicitação |
| **Decisória** | Selecionar a função de consulta, cálculo ou relatório |
| **Executiva** | Executar a função permitida e apresentar o resultado |

O exemplo ajuda a compreender uma arquitetura de atendimento, mas não significa que o chatbot já tenha autonomia ampla de decisão.

Também podemos relacionar o projeto a três preocupações da unidade:

**Privacidade:** chamados e notas técnicas podem conter dados pessoais ou informações de trabalho. Um chat não deve expor registros a quem não tem permissão.

**Confiabilidade:** uma resposta com o percentual de SLA calculado incorretamente pode levar a decisões operacionais equivocadas. O cálculo precisa ser auditável e comparado com casos de referência.

**Responsabilidade humana:** o assistente serve como apoio. Antes de utilizar seus resultados em decisões oficiais ou comunicações externas, é necessário validar as regras e os dados usados.

Como referência complementar para organizar futuras etapas do projeto, também foi disponibilizado o [fluxo de desenvolvimento de chatbots do SerproBots](https://serprobots.estaleiro.serpro.gov.br/docs/dev/), que aborda levantamento da necessidade, modelagem, testes e melhoria contínua.

## 9. Limitações identificadas

Na análise dos arquivos do projeto, alguns pontos merecem atenção:

- **Linguagem natural limitada:** expressões não previstas podem ser interpretadas incorretamente ou não ser reconhecidas.
- **Dependência das regras contratuais:** prioridades, calendários, feriados e critérios de pausa precisam ser conferidos com os responsáveis.
- **Precisão das datas:** fuso horário e intervalos de contagem precisam ser tratados de maneira consistente.
- **Segurança e autorização:** antes de disponibilizar consultas reais a mais usuários, autenticação e permissões por contrato devem ser aplicadas também nas funções de acesso a dados.
- **Privacidade da memória:** não convém guardar todas as mensagens indefinidamente sem critérios de necessidade e retenção.
- **Estado da versão 3.0:** testes com dados fictícios não comprovam que a integração com o ambiente corporativo está pronta.

Essas limitações não anulam a proposta. Elas ajudam a definir o que precisa ser testado e corrigido antes de ampliar o uso.

## 10. Ideias de melhorias futuras

Registrar as ideias de melhoria faz parte do projeto: mostra que a solução foi analisada criticamente e que já existem caminhos para evoluí-la. Para não confundir planejamento com entrega, todas as propostas desta seção estão marcadas como **futuras**.

| Prioridade sugerida | Melhoria proposta | Resultado esperado |
|---|---|---|
| **Alta** | Autenticação corporativa e permissões por contrato | Cada pessoa acessa somente dados autorizados |
| **Alta** | Gestão segura de credenciais, conexões protegidas e auditoria de acesso | Reduzir riscos de exposição de informações |
| **Alta** | Validar e unificar as regras de SLA em um motor testável | Evitar cálculos divergentes entre calculadora, chatbot e relatórios |
| **Alta** | Testes com casos de SLA revisados por responsáveis | Verificar pausas, feriados, horários e casos de exceção |
| **Média** | Ampliar relatórios para Excel e CSV na aplicação integrada | Facilitar análises e acompanhamento dos chamados |
| **Média** | Melhorar as mensagens quando faltarem dados ou uma consulta falhar | Tornar as respostas mais claras e úteis |
| **Média** | Criar feedback sobre respostas e correções | Identificar comandos confusos e erros recorrentes |
| **Média** | Dashboard de indicadores e alertas de SLA | Oferecer visão gerencial sem depender somente do chat |
| **Média** | Política de retenção e limpeza do histórico | Evitar armazenamento desnecessário de mensagens |
| **Em estudo** | Avaliar IA generativa para interpretar perguntas mais variadas | Aumentar flexibilidade sem perder regras, rastreabilidade e limites |
| **Em estudo** | Encaminhamento para revisão humana de consultas sensíveis | Não automatizar decisões que exijam validação profissional |

A ordem acima é uma proposta de organização, não um cronograma aprovado. Em uma evolução real, **segurança e validação do cálculo devem vir antes de novas funcionalidades de IA**.

## 11. Como avaliar uma próxima versão

Antes de chamar uma nova funcionalidade de concluída, seria importante verificar se:

1. As respostas sobre SLA coincidem com casos de referência revisados.
2. Consultas e relatórios respeitam o perfil e a autorização de cada usuário.
3. Perguntas ambíguas ou incompletas produzem mensagens claras, sem inventar resultados.
4. PDFs e planilhas exibem corretamente o período e os filtros usados.
5. O histórico registra somente dados necessários e possui regras de acesso e retenção.
6. Os testes cobrem falhas de conexão, chamadas inexistentes, pausas e limites de prazo.

Na branch de demonstração existem arquivos de testes automatizados para partes do motor e da interface. Isso é um avanço técnico, mas ainda não substitui a homologação com dados e critérios reais.

## 12. Reflexão

O projeto mostra como um chatbot pode ser mais do que uma caixa de mensagens: ele pode funcionar como uma interface para recursos que já existem em um sistema. No nosso caso, a parte mais importante não é produzir uma resposta bonita, e sim **entregar informações de SLA que possam ser conferidas**.

Também ficou evidente que existem limites. Uma frase escrita de outra maneira pode não ser compreendida. Uma regra de pausa errada pode alterar o resultado do cálculo. E um relatório correto, se chegar a uma pessoa sem autorização, continua sendo um problema.

Por isso, o objetivo das próximas etapas não é apenas tornar o assistente mais inteligente. É fazer com que ele seja **mais confiável, seguro e fácil de usar**, respeitando as regras do serviço e a responsabilidade de quem trabalha com os chamados.

---

### Referências utilizadas neste registro

- **Projeto privado SLA Engine / Assistente Virtual:** leitura da documentação e das implementações das versões 2.0 e experimental 3.0. O código e os dados operacionais não foram copiados para o portfólio público.
- **Material da disciplina:** [Guia de Estudos A1 — Criação de Agentes de IA e Ética Aplicada](../Guia_A1_Agentes_de_IA_e_%C3%89tica%20%28Tendencias%29%20%281%29.pdf).
- **SerproBots:** [Fluxo de desenvolvimento de chatbots](https://serprobots.estaleiro.serpro.gov.br/docs/dev/).
