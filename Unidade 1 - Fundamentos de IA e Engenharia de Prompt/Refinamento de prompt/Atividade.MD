Entendi. Você quer que eu **faça a atividade da Aula 03**, preenchendo o que foi pedido no material, e não apenas reescrevendo o conteúdo da aula. Vou manter o tema de **Ciência da Computação**, usando como problema um assunto relacionado a **sistemas acadêmicos e requisitos**, para ficar coerente com a Aula 02.

 # Aula 03 — Refinamento de Prompts

 **Disciplina:** Tendências em Ciência da Computação\
 **Data:** 03/09/2026\
 **Duração:** 1h30\
 **Tema:** Refinamento de Prompts\
 **Metodologia:** Aula expositiva dialogada + Hands On + reflexão crítica\
 **Atividade prática:** Comparação de resultados obtidos com diferentes prompts\
 **Competência:** Ajustar e refinar prompts para obter respostas mais precisas, relevantes e adequadas ao objetivo proposto.

---

 ## 1\. Problema escolhido

 ### Contexto

 Durante o desenvolvimento de sistemas, estudantes de Ciência da Computação podem encontrar dificuldades para compreender conceitos de Engenharia de Software, principalmente quando precisam transformar uma ideia inicial em informações organizadas.

 Nesta atividade, será utilizado um sistema acadêmico como exemplo para investigar como diferentes formas de escrever um prompt podem influenciar a resposta de uma Inteligência Artificial Generativa.

 ### Problema

 Como utilizar diferentes níveis de detalhamento em prompts para obter uma explicação mais clara e adequada sobre requisitos funcionais e não funcionais de um sistema acadêmico?

 ### Objetivo

 Comparar três versões de prompts sobre requisitos de software, analisando como a inclusão de contexto, público, objetivo, formato e restrições modifica a qualidade das respostas geradas pela IA.

---

 # 2\. Prompt 1 — Versão inicial

 ### Prompt

```
Explique o que são requisitos funcionais e não funcionais em um sistema acadêmico.
```

 ### Resultado

 Requisitos funcionais são as funções que o sistema deve realizar. Em um sistema acadêmico, alguns exemplos são cadastrar alunos, cadastrar professores, registrar notas e consultar disciplinas.

 Requisitos não funcionais são características que determinam como o sistema deve funcionar. Alguns exemplos são segurança, desempenho, facilidade de uso e disponibilidade.

 Os requisitos funcionais estão relacionados às funcionalidades do sistema, enquanto os requisitos não funcionais estão relacionados às características e condições de funcionamento.

 ### Primeira impressão

 A resposta apresenta corretamente a diferença básica entre os dois tipos de requisitos. Porém, ela ainda é bastante resumida e não explica profundamente cada conceito.

 Também não existe uma definição do público que receberá a explicação, nem um formato específico para a resposta.

 ### O que funcionou?

 - A IA identificou corretamente o assunto.
- A diferença básica entre os dois tipos de requisitos foi apresentada.
- Foram utilizados exemplos relacionados a um sistema acadêmico.
- A resposta é simples de compreender.

 ### O que faltou?

 - Definição do público.
- Maior detalhamento dos conceitos.
- Exemplos mais específicos.
- Estrutura organizada.
- Explicação sobre como identificar cada tipo de requisito.
- Critérios para avaliar a qualidade da resposta.

---

 # 3\. Prompt 2 — Primeiro refinamento

 ### Alterações realizadas

 | Elemento | Alteração |
| --- | --- |
| Papel | A IA passou a atuar como professor de Engenharia de Software. |
| Público | A explicação foi direcionada a estudantes iniciantes. |
| Contexto | Foi especificado que o exemplo seria baseado em um sistema acadêmico. |
| Objetivo | O objetivo passou a ser ensinar a diferença entre os requisitos. |
| Formato | Foram solicitados subtítulos e exemplos. |
| Restrições | Foi solicitada linguagem simples e objetiva. |

 ### Prompt

```
Atue como professor de Engenharia de Software.

Explique para estudantes iniciantes de Ciência da Computação
a diferença entre requisitos funcionais e requisitos não
funcionais.

Utilize como contexto um sistema acadêmico utilizado por
alunos, professores e administradores.

Apresente:
1. a definição de requisito funcional;
2. a definição de requisito não funcional;
3. quatro exemplos de cada tipo;
4. uma explicação mostrando a diferença entre eles;
5. uma dica para identificar se um requisito é funcional
   ou não funcional.

Utilize linguagem simples, evitando termos técnicos
desnecessários.

Organize a resposta com subtítulos e listas.
```

 ### Resultado

 ## Requisitos funcionais

 Requisitos funcionais descrevem aquilo que o sistema precisa fazer. Eles representam funcionalidades ou ações que podem ser realizadas dentro da aplicação.

 Exemplos:

 1. O aluno deve conseguir consultar suas notas.
2. O professor deve conseguir registrar notas.
3. O administrador deve conseguir cadastrar usuários.
4. O aluno deve conseguir visualizar as disciplinas em que está matriculado.

 ## Requisitos não funcionais

 Requisitos não funcionais definem características ou condições relacionadas ao funcionamento do sistema.

 Exemplos:

 1. O sistema deve proteger os dados dos usuários.
2. As páginas devem carregar rapidamente.
3. A interface deve ser fácil de utilizar.
4. O sistema deve permanecer disponível durante o horário de funcionamento.

 ### Diferença

 Um requisito funcional descreve **o que o sistema deve fazer**, enquanto um requisito não funcional descreve **como o sistema deve funcionar ou quais características deve possuir**.

 ### Dica

 Uma forma simples de identificar é perguntar:

 > "Isso representa uma ação que o sistema precisa realizar?"

 Se sim, provavelmente é um requisito funcional. Caso esteja relacionado a segurança, desempenho, usabilidade, disponibilidade ou outra característica de funcionamento, provavelmente é um requisito não funcional.

 ### Análise

 O segundo prompt apresentou uma melhora significativa em relação ao primeiro. A resposta ficou mais organizada, apresentou mais exemplos e foi direcionada para estudantes iniciantes.

 Mesmo assim, ainda poderia ser melhor especificada. Por exemplo, não foi definido um critério para verificar se os exemplos realmente representam bons requisitos, nem foi solicitado que a IA apontasse possíveis ambiguidades.

---

 # 4\. Prompt 3 — Segundo refinamento

 ### Hipótese de melhoria

 Acredito que a resposta ficará mais adequada se, além de definir o papel e o público, o prompt informar exatamente o que deve ser analisado, estabelecer critérios de qualidade e exigir uma comparação estruturada.

 Também será solicitado que a IA identifique exemplos que possam gerar confusão entre requisitos funcionais e não funcionais.

 ### Prompt

```
Atue como um professor de Engenharia de Software especializado
em análise de requisitos.

CONTEXTO:

Estou realizando uma atividade acadêmica com estudantes
iniciantes de Ciência da Computação.

O exemplo utilizado será um sistema acadêmico com três
perfis principais: administrador, professor e aluno.

O sistema permite controlar usuários, disciplinas,
atividades acadêmicas e notas.

OBJETIVO:

Ensinar os estudantes a diferenciar requisitos funcionais
de requisitos não funcionais e reconhecer características
de bons requisitos.

TAREFA:

1. Explique os dois conceitos utilizando linguagem simples.
2. Apresente cinco exemplos de requisitos funcionais
   relacionados ao sistema informado.
3. Apresente cinco exemplos de requisitos não funcionais.
4. Identifique o usuário envolvido em cada requisito
   funcional.
5. Explique por que cada exemplo pertence à categoria
   escolhida.
6. Apresente dois exemplos de requisitos mal formulados
   e explique por que eles precisam ser melhorados.
7. Apresente uma regra simples que ajude um estudante
   a diferenciar os dois tipos.

FORMATO:

Utilize subtítulos.

Apresente os requisitos funcionais em uma tabela:

| ID | Requisito | Usuário | Justificativa |

Apresente os requisitos não funcionais em outra tabela:

| ID | Requisito | Categoria | Justificativa |

Depois das tabelas, crie uma seção chamada
"Exemplos que precisam de melhoria".

RESTRIÇÕES:

- Utilize linguagem adequada para estudantes iniciantes.
- Evite explicações excessivamente técnicas.
- Não invente funcionalidades que não estejam relacionadas
  ao contexto informado.
- Evite expressões vagas como "o sistema deve ser bom"
  ou "o sistema deve ser rápido".
- Seja objetivo.

CRITÉRIO DE QUALIDADE:

Os exemplos devem ser específicos, coerentes com o sistema
acadêmico e permitir que um estudante identifique claramente
a diferença entre requisitos funcionais e não funcionais.
```

 ### Resultado

 ## Conceitos

 Um **requisito funcional** descreve uma ação, serviço ou comportamento que o sistema precisa oferecer. Ele está relacionado às funcionalidades que os usuários poderão utilizar.

 Um **requisito não funcional** descreve uma característica, condição ou restrição relacionada ao funcionamento do sistema, como segurança, desempenho, disponibilidade e usabilidade.

 ### Requisitos funcionais

 | ID | Requisito | Usuário | Justificativa |
| --- | --- | --- | --- |
| RF01 | O sistema deve permitir que o administrador cadastre novos usuários. | Administrador | Representa uma funcionalidade que o sistema precisa disponibilizar. |
| RF02 | O sistema deve permitir que o professor registre as notas dos estudantes. | Professor | Trata-se de uma ação realizada pelo sistema para armazenar informações acadêmicas. |
| RF03 | O sistema deve permitir que o aluno consulte suas notas. | Aluno | O sistema precisa disponibilizar a consulta das informações acadêmicas do aluno. |
| RF04 | O sistema deve permitir que o professor cadastre atividades para suas disciplinas. | Professor | Representa uma funcionalidade utilizada pelo professor. |
| RF05 | O sistema deve permitir que o aluno visualize as atividades cadastradas em suas disciplinas. | Aluno | Define uma função que precisa estar disponível para o estudante. |

 ### Requisitos não funcionais

 | ID | Requisito | Categoria | Justificativa |
| --- | --- | --- | --- |
| RNF01 | O sistema deve impedir que usuários acessem informações que não estejam autorizados a consultar. | Segurança | Define uma condição relacionada à proteção dos dados. |
| RNF02 | As principais telas do sistema devem apresentar resposta em tempo adequado durante o uso normal. | Desempenho | Está relacionado à velocidade de funcionamento da aplicação. |
| RNF03 | A interface deve apresentar navegação simples e consistente entre as diferentes áreas do sistema. | Usabilidade | Define uma característica relacionada à facilidade de utilização. |
| RNF04 | O sistema deve permanecer disponível durante os períodos definidos pela instituição. | Disponibilidade | Estabelece uma condição de funcionamento da aplicação. |
| RNF05 | As informações acadêmicas armazenadas devem permanecer consistentes após operações de inclusão ou alteração. | Integridade | Define uma característica relacionada à confiabilidade dos dados. |

 ### Exemplos que precisam de melhoria

 **Exemplo 1:**

 > "O sistema deve ser rápido."

 Esse requisito é muito genérico. Não define o que significa "rápido" nem qual condição deve ser utilizada para avaliar o desempenho.

 Uma formulação melhor seria:

 > "As consultas de notas devem apresentar resposta em tempo adequado durante as condições normais de utilização."

 Mesmo assim, o valor exato do tempo ainda deveria ser definido com o responsável pelo sistema.

 **Exemplo 2:**

 > "O sistema deve ser seguro."

 A expressão "seguro" possui um significado amplo e pode ser interpretada de várias maneiras.

 Uma versão mais específica seria:

 > "O sistema deve restringir o acesso às informações acadêmicas de acordo com as permissões de cada perfil de usuário."

 ### Regra simples para diferenciar

 Uma maneira prática de diferenciar os requisitos é perguntar:

 **"Estou descrevendo uma função que o sistema precisa realizar?"**

 - Se a resposta for **sim**, provavelmente é um requisito funcional.
- Se estiver descrevendo uma característica, qualidade, restrição ou condição de funcionamento, provavelmente é um requisito não funcional.

---

 # 5\. Comparação entre os prompts

 | Critério | Prompt 1 | Prompt 2 | Prompt 3 |
| --- | --- | --- | --- |
| Clareza | 3 | 4 | 5 |
| Precisão | 3 | 4 | 5 |
| Relevância | 3 | 4 | 5 |
| Organização | 2 | 4 | 5 |
| Adequação ao público | 2 | 5 | 5 |
| Atendimento ao objetivo | 3 | 4 | 5 |
| Utilidade prática | 3 | 4 | 5 |
| **Total** | **19** | **29** | **35** |

 ### Análise da comparação

 O primeiro prompt apresentou uma resposta correta, mas muito básica. Ele não informava o nível de conhecimento do público nem determinava como a resposta deveria ser organizada.

 O segundo prompt apresentou melhorias importantes ao adicionar contexto, público, papel da IA, estrutura e quantidade de exemplos. Com isso, a resposta ficou mais completa e didática.

 O terceiro prompt apresentou o resultado mais adequado porque estabeleceu não apenas o conteúdo que deveria ser produzido, mas também critérios para avaliar a qualidade dos requisitos. Além disso, solicitou exemplos inadequados e suas melhorias, tornando a resposta mais útil para o aprendizado.

 Dessa forma, o **Prompt 3 foi considerado o melhor resultado**, pois apresentou maior clareza, organização, especificidade e adequação ao objetivo da atividade.

---

 # 6\. Qual modificação teve maior impacto?

 A modificação que teve maior impacto foi a inclusão de **contexto, público e critérios de qualidade**.

 No primeiro prompt, a IA precisava decidir sozinha qual nível de explicação deveria utilizar. Já no terceiro, foi informado que a atividade era destinada a estudantes iniciantes e que os exemplos deveriam ser específicos e relacionados ao sistema acadêmico.

 A definição do formato também ajudou bastante, pois as tabelas obrigaram a resposta a apresentar informações de maneira organizada.

---

 # 7\. Validação

 A resposta produzida pela IA foi analisada verificando se:

 - os requisitos funcionais realmente representam funcionalidades;
- os requisitos não funcionais representam características ou condições do sistema;
- os exemplos estão relacionados ao sistema acadêmico;
- os usuários indicados fazem sentido;
- os requisitos não são excessivamente genéricos;
- não existem funcionalidades completamente fora do contexto.

 Também foi possível perceber que alguns requisitos ainda precisam de informações fornecidas pelo cliente. Por exemplo, termos como "tempo adequado" ou "período definido pela instituição" precisam ser transformados em valores ou regras concretas durante uma análise real.

 Portanto, mesmo com um prompt bem elaborado, a resposta da IA não deve ser considerada automaticamente como especificação final do sistema.

---

 # 8\. Reflexão crítica

 ### 1\. Qual foi a principal diferença entre o prompt inicial e o refinado?

 A principal diferença foi a quantidade e a qualidade das informações fornecidas à IA. O prompt inicial apenas solicitava uma explicação, enquanto os prompts seguintes definiram contexto, público, objetivo, formato, restrições e critérios.

 ### 2\. Quais elementos tiveram maior impacto?

 Os elementos que mais contribuíram foram o contexto do sistema, a definição do público e o formato de saída. Os critérios de qualidade também ajudaram a produzir respostas mais específicas.

 ### 3\. Um prompt maior necessariamente produz uma resposta melhor?

 Não. Um prompt pode ser longo e ainda apresentar informações pouco úteis. O mais importante é fornecer instruções relevantes para a tarefa e evitar detalhes desnecessários.

 ### 4\. O que acontece quando o objetivo não está claro?

 A IA precisa interpretar o que o usuário deseja e pode produzir uma resposta genérica ou diferente daquilo que era esperado.

 ### 5\. Quais informações são indispensáveis para elaborar um bom prompt?

 É importante informar pelo menos o objetivo da tarefa, o contexto necessário, o público, as instruções principais e, quando necessário, o formato e as restrições.

 ### 6\. Como essa habilidade pode ser utilizada profissionalmente?

 O refinamento de prompts pode ajudar profissionais de Computação em atividades como documentação, programação, testes, análise de dados, pesquisa, elaboração de requisitos e estudo de novas tecnologias.

 ### 7\. Quais riscos existem ao confiar automaticamente na IA?

 A IA pode apresentar informações incorretas, incompletas ou baseadas em suposições. Uma resposta bem escrita pode transmitir uma falsa sensação de confiabilidade.

 ### 8\. Houve alguma situação em que o Prompt 3 ficou pior que o Prompt 2?

 Neste experimento, o Prompt 3 apresentou um resultado mais adequado ao objetivo. Porém, adicionar instruções demais pode prejudicar uma resposta caso existam regras contraditórias ou informações desnecessárias.

 ### 9\. Existe um ponto em que adicionar mais instruções começa a prejudicar a resposta?

 Sim. Quando o prompt possui informações excessivas, repetidas ou contraditórias, a IA pode ter dificuldade para identificar quais instruções são realmente importantes.

 ### 10\. Como verificar se a resposta está tecnicamente correta?

 É necessário comparar as informações com materiais confiáveis, livros, documentação oficial, conteúdos da disciplina e, quando possível, consultar professores ou profissionais da área.

---

 # 9\. Ética e responsabilidade

 O uso de IA nesta atividade deve ser realizado de maneira crítica e responsável.

 A ferramenta pode auxiliar na organização das ideias e na compreensão dos conceitos, mas não substitui a análise do estudante.

 Durante o exercício, foi possível perceber que uma IA pode criar requisitos plausíveis que não necessariamente correspondem às necessidades reais de um sistema.

 Por isso, os requisitos produzidos precisam ser revisados e validados antes de serem utilizados em um projeto.

 Também é importante não fornecer informações confidenciais ou dados pessoais para uma ferramenta de IA sem autorização.

 A responsabilidade pelo conteúdo utilizado no trabalho continua sendo do estudante, mesmo quando parte das informações foi produzida com auxílio de Inteligência Artificial.

---

 # 10\. Take Away

 > **Um bom prompt não é simplesmente um prompt longo. Ele precisa apresentar instruções relevantes, contexto suficiente e um objetivo claro para orientar a IA.**

 A atividade mostrou que o refinamento acontece por meio de um processo contínuo:

```
CRIAR
  ↓
TESTAR
  ↓
ANALISAR
  ↓
IDENTIFICAR PROBLEMAS
  ↓
REFINAR
  ↓
TESTAR NOVAMENTE
  ↓
COMPARAR
  ↓
VALIDAR
```

 A principal aprendizagem foi que pequenas mudanças na forma de escrever uma instrução podem alterar significativamente a resposta obtida.

 Também foi possível compreender que uma resposta mais detalhada não significa necessariamente uma resposta correta. A análise humana continua sendo necessária para verificar informações, identificar erros e decidir quais partes podem realmente ser utilizadas.

---

 # 11\. Cinco recomendações práticas

 1. **Defina claramente o objetivo** antes de escrever o prompt.
2. **Forneça contexto suficiente** para evitar que a IA precise fazer muitas suposições.
3. **Informe o público e o nível de conhecimento** para adequar a resposta.
4. **Determine formato e restrições** quando a organização da resposta for importante.
5. **Analise e valide a resposta** antes de utilizá-la como informação definitiva.

---

 # 12\. Síntese final

 A comparação das três versões demonstrou que o refinamento de prompts é um processo de melhoria contínua.

 O primeiro prompt produziu uma resposta simples e genérica. O segundo acrescentou informações sobre público, contexto e formato, aumentando a qualidade da resposta. O terceiro foi mais específico e estabeleceu critérios de qualidade, resultando em uma resposta mais completa e adequada ao objetivo.

 Assim, o experimento mostrou que a Engenharia de Prompt não consiste em simplesmente escrever comandos maiores, mas em **fornecer as informações certas para reduzir ambiguidades e orientar a Inteligência Artificial para o resultado esperado**.

 Ao mesmo tempo, a qualidade do prompt não elimina a necessidade de pensamento crítico. A resposta da IA deve ser analisada, comparada com fontes confiáveis e validada antes de ser utilizada.

 Essa versão já está **preenchida como uma atividade entregue**, seguindo as etapas da Aula 03: problema → Prompt 1 → análise → Prompt 2 → comparação → Prompt 3 → comparação final → validação → ética → reflexão → Take Away.
