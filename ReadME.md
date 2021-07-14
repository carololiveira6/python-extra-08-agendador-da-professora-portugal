## **Table of Contents**


- [Extra - Agendador da Professora Portugal](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1esj4slvm0)
- [Objetivo](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f33pqfa47)
- [Preparativos](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f33pqfa48)
- [Arvore de diretórios](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5ec8thu0) 
- [Models](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5gp8fn92) 
  - [class CsvManipulator](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5gp8fn93)
  - [class Appointment](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5gp8fn94)
- [Rotas](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1egvsckqv3) 
  - [GET /appointments](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5eemg98ab)
  - [POST /appointments](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5ge4uvl0)
  - [DELETE /appointments/](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5gp8fn96)
  - [PATCH /appointments/](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5gp8fn97)
  - [GET /check_available_times](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1f5ge4uvl1)
- [Entregáveis](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1egvoav555j) 
  - [Repositório](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1egvrpv6k1l4)
- [Critérios de aceitação](https://npepa32v9l.execute-api.us-east-1.amazonaws.com/v2/?project_id=19989138&filename=python/outubro-20/2b_ee_01_professora-portugal.html&ref=master#mcetoc_1esj6ecle3)
# **Extra - Agendador da Professora Portugal**
Você recebeu a proposta de desenvolver um aplicativo para uma professora particular, e portanto deverá criar o back-end. A principal ideia do aplicativo é ajudar sua cliente a se organizar com os agendamentos de seus alunos, já que atualmente o tempo que o mesmo gasta para revisar e fazer anotações está a prejudicando bastante. Cada agendamento só poderá ser feito no intervalo de trabalho da professora, que é das 08:00 as 18:59. Horários quebrados sempre serão agendados para um horário anterior mais proximo multiplo de 20 se possível. Exemplo: Um agendamento com horário 14:29 deverá ser persistido na base de dados como 14:00, assim como um agendamento para as 18:59 deverá ser persistido como 18:40. Não deve ser possivel agendar dois horários no mesmo dia na mesma hora, assim como não deverá ser permitido agendar horários fora do horário de trabalho.

Seu cliente enviou o seguinte texto para explicar o que espera do produto final:

|<p>**Preciso de um aplicativo que me ajude a me organizar. Meu nome é Isabel Rainha de Portugal, sou professora de matemática, física e química. Pela alta quantidade de agendamentos, a boa e velha agenda não tem dado mais conta de me ajudar com a organização das datas, além disso, é tanta papelada para cada aluno que as vezes acabo me perdendo. Hoje tenho mais de 45 alunos que preciso encaixar em horários sempre muito apertados, muitas vezes gasto muito tempo com esse tipo de atividade, porque preciso fazê-la algumas vezes por dia.** </p><p>**Seria interessante poder saber quais horários estão disponíveis para certo dia, quais alunos estão agendados para certo dia, e uma listagem dos agendamentos para determinado dia em ordem de horário.**</p>|
| - |
# **Objetivo**
Exercitar a criação de rotas em Flask, obtenção de dados por url params, manipulação de datas e ordenamento, manipulação de arquivos csv, estrutura básica de herança simples entre classes.
# **Preparativos**
**Leia atentamente toda a entrega**. Você deverá seguir a seguinte estrutura de diretórios abaixo. Todas as rotas devem estar com a assinatura no formato especificado. Utilize o Insomnia para testar os retornos das rotas. Você deverá usar como base de dados um arquivo csv chamado **appointments.csv** (esse deverá ser exatamente o nome dele). **Não esqueça de adicionar o venv e o appointments.csv ao gitignore !!**
# **Arvore de diretórios**
.

├── agendador

│   ├── \_\_init\_\_.py

│   └── models

│       ├── \_\_init\_\_.py

│       ├── appointment\_model.py

│       └── csv\_manipulator\_model.py

│── .env.example

│── .gitignore

└── requirements.txt
# **Models**
Cada model deve ser definida no seu respectivo arquivo. A classe Appointment ficará em **appointment\_model.py**, enquanto a classe CsvManipulator ficará em **csv\_manipulator\_model.py**. As descrições de retorno são dicas de em quais rotas cada método deve ser utilizado. Sinta-se livre para adicionar algum método auxiliar que achar necessário, mas todoas os métodos descritos devem ser criados exatamente como dito nas assinaturas e devem retornar o exato pedido nos exemplos de retorno.


- ## **class CsvManipulator**
Por questões didáticas, a classe CsvManipulator servirá como pai da classe Appointment. Ela ficará responsável integralmente pela manipulação da abertura de csv, tanto para escrita e leitura, quanto para fornecer um id unico nunca utilizado nos registros do csv.

- **Métodos estáticos**: 
  - write\_in\_csv(filepath, fieldnames, info\_list): 
    - Parametros: 
      - filepath: Uma **string** com o nome do arquivo csv a ser escrito.
      - fieldnames: Uma **lista** contendo os fieldnames dos dados a serem escritos no csv.
      - info\_list: Uma **lista** contendo todos os dados a serem escritos no csv.
    - **Procedimento**: 
      - Deve escrever a lista de dados passada por parametro em um arquivo csv utilizando o modo de abertura **w.**
    - **Retorno:** 
      - O método não possui retorno
  - read\_all\_csv(filepath): 
    - **Parâmetros**: 
      - filepath: Uma **string** com o nome do arquivo csv a ser lido.
    - **Procedimentos**: 
      - Caso o arquivo não exista, retornar uma **lista vazia**.
      - Caso o arquivo exista, retornar uma **lista** contendo todos os registros do csv, tratando os casos que necessitem serem convertidos para inteiro (chaves id e numero\_classe)
    - Retorno: 
      - [Exemplo de retorno](https://gitlab.com/-/snippets/2119420)
- **Método de instancia**: 
  - find\_unique\_id(filepath): 
    - **Parâmetros**: 
      - filepath: Uma **string** contendo o nome do arquivo csv para pesquisa de id única.
    - **Procedimentos**: 
      - Caso o arquivo não exista, retornar a id 1.
      - Caso o arquivo exista, deverá retornar uma id unica considerando a id de maior numero escrita no csv.
    - **Retorno**: 
      - Um **inteiro** representando a id unica processada do csv.
- ## **class Appointment**
A classe Appointment herdará da classe CsvManipulator. Ela será responsável por instanciar um agendamento, além de gerenciar a lógica de criação, deleção,  atualização e obtenção dos dados nos formatos adequados que cada rota necessita.

- **Atributos de instância**: 
  - filepath: Uma string contendo o nome do arquivo csv a ser persistido.
  - id: Um inteiro denotando uma id unica.
  - data: Uma string no formato dd/mm/yyy representando a data do agendamento.
  - horario: Uma string no formato HH:MM (de 00h a 23h).
  - nome: Uma string representando o nome do aluno agendado.
  - dificuldade: Uma string representando a descrição do propósito do agendamento.
  - numero\_classe: Um inteiro representando o numero da classe do aluno.
- **Métodos estáticos**: 
  - update\_appointment(filepath, id, data\_to\_update): 
    - **Parâmetros**: 
      - filepath: Uma **string** contendo o nome do arquivo csv para atualização.
      - id: Um **inteiro** denotando a id especifica do registro a ser atualizado.
      - data\_to\_update: Um dicionário contendo as alterações.
    - **Procedimentos**: 
      - Caso o id não exista, retornar uma **lista vazia**.
      - Caso o id exista, atualizar os campos pertinentes.
    - **Retorno**: 
      - Deverá retornar uma **lista vazia** caso a id nao exista.
      - Deverá retornar um **dicionário** representando o registro já atualizado caso o id exista.
  - delete\_appointment(filepath, id): 
    - **Parâmetros**: 
      - filepath: Uma string contendo o nome do arquivo para deleção do registo.
      - id: Um inteiro denotando a id específica do registro a ser deletado.
    - **Procedimentos**: 
      - Caso o id não exista, retornar uma **lista vazia**.
      - Caso o id exista, atualizar os campos pertinentes.
    - **Retorno**: 
      - Retornar a **lista** de agendamentos atualizada caso a deleção tenha sucesso.
      - Retornar uma **lista vazia** caso a deleção falhe.
  - get\_appointments(filepath, data): 
    - **Parâmetros**: 
      - filepath: Uma **string** contendo o nome do arquivo para obtenção dos registros.
      - data: Uma **string** no formato **dd/mm/yyyy** representando a data para pesquisa dos registros.
    - **Procedimentos**: 
      - Deve processar a data recebida por parâmetro e retornar uma **lista de dicionários ordenada de forma ascendente por horário**.
      - Caso não exista agendamentos, retornar uma **lista vazia**.
  - check\_available\_times(filepath, data): 
    - **Parâmetros**: 
      - filepath: Uma **string** contendo o nome do arquivo para obtenção dos horários disponíveis.
      - data: Uma **string** no formato **dd/mm/yyyy** representando a data para pesquisa de horários disponíveis.
    - **Procedimentos**: 
      - Deve processar os dados recebidos por parâmetro de forma a retornar uma **lista de strings** contendo os horários disponíveis para agendamento em determinado dia.
    - **Retornos**: 
      - Retornar uma **lista de strings** contendo todos os horários disponíveis em determinado dia. [Exemplo de retorno](https://gitlab.com/-/snippets/2119334) considerando um horário **08:20 agendado** para a data **19/05/2021**.
- **Método de instância**: 
  - create\_appointment(): 
    - **Procedimentos**: 
      - Verificar se o horário do atributo horario está compreendido no horário de trabalho da professora (08:00 -> 19:00).
      - Caso o horario esteja disponivel, processar o atributo horario para arredondá-lo para o **anterior multiplo de 20 mais próximo**. Exemplos: 
        - 08:39 **->** 08:20
        - 18:59 **->** 18:40
        - 08:02 **->** 08:00
      - Caso o horário esteja dentro do período laboral da professora, verificar se existe algum agendamentos já cadastrado no dia e horario especificado nos atributos.
      - **Passado pelos procedimentos anteriores**, deverá **escrever na base de dados csv** o **agendamento atual** da classe, retornando como especificado em retorno.
    - **Retornos**: 
      - Se o horário nao estiver comprendido no horario de trabalho, retornar o exatamente o [seguinte dicionário](https://gitlab.com/-/snippets/2119250).
      - Se o horário ja estiver ocupado, retornar [exatamente o seguinte dicionário](https://gitlab.com/-/snippets/2119258).
      - Caso o agendamento consiga ser escrito na base de dados csv, deve-se retornar um dicionário como [neste exemplo](https://gitlab.com/-/snippets/2119256).
# **Rotas**
Todas as rotas deverão ser definidas no arquivo \_\_init\_\_.py do diretório **agendador**, seguindo o modelo de assinatura exatamente igual ao especificado. Os dados deverão ser persistidos e resgatados da base de dados em csv **appointments.csv**.
- ## **GET /appointments**
  - **URL Params**: 
    - A rota **/appointments** deverá poder receber o *url params* **data** no seguinte formato exemplificado: **/appointments?data=11/05/2020** (**atenção** para data no formato **dd/mm/yyyy**). 
  - **Procedimentos**: 
    - Caso não seja passado nenhum *url param*, deverá retornar uma **lista** com todos os agendamentos por **ordem de id**, caso não tenha agendamentos retornar uma **lista vazia** com código de status **200 - OK**.
    - Caso seja passado uma data como *url param*, deverá retornar uma **lista** com **apenas** os agendamentos da **data especificada**, **por ordem de horário ascendente** ( 08:00 até 18:40 ). Caso não haja agendamentos no dia, retornar uma **lista vazia** com código de status **200 - OK**.
  - **Retornos**: 
    - [Exemplo](https://gitlab.com/-/snippets/2118817) de retorno sem url param com código de status **200 - OK**
    - [Exemplo](https://gitlab.com/-/snippets/2118819) de retorno com url param data com código de status **200 - OK**
- ## **POST /appointments**
  - **Procedimentos**: 
    - Todo agendamento deverá ter um **id unico nunca utilizado antes** ao ser persistido no csv.
    - Caso um horário fora do período de trabalho da professora seja enviado na requisição, voce deve retornar o seguinte dicionário no exato [formato especificado](https://gitlab.com/-/snippets/2119250) com o código de status **422 - Unprocessable Entity**. 
    - Caso o horario da requisição seja válido, mas o horário da data que foi enviado pelo body da requisição ja esteja agendado para outro atendimento, deverá retornar um dicionário no exato [formato especificado](https://gitlab.com/-/snippets/2119258) com o código de status **422 - Unprocessable Entity**.
    - Todo horário quebrado, estando dentro do horario de atendimento, deverá ser formatado para um **horario anterior multiplo de 20 mais próximo**. Exemplo: Se a requisição envia um horario 16:59, o que deverá ser persistido no csv é o horario 16:40. Caso o horário passado seja 08:02, o horário persistido deve ser 08:00 e assim por diante. O status code retornado deve ser **201 - Created**
    - Deverá persistir os dados no **appointsments.csv** a partir do body json que virá da requsição no [seguinte formato](https://gitlab.com/-/snippets/2118822). Já o csv, deve seguir o [seguinte formato.](https://gitlab.com/-/snippets/2119240)
  - **Retornos**: 
    - [Formato do retorno](https://gitlab.com/-/snippets/2119256) do seguinte [exemplo de post](https://gitlab.com/-/snippets/2118822) com código de status **201 - Created**
    - [Formato do retorno](https://gitlab.com/-/snippets/2119250) quando o horario especificado não está compreendido no horário de atendimento da professora com o código de status **422 - Unprocessable Entity**
    - [Formato do retorno](https://gitlab.com/-/snippets/2119258) quando o horario da data especificado ja contem um agendamento marcado na base de dados csv com o código de status **422 - Unprocessable Entity**
- ## **DELETE /appointments/<int:id>**
  - **Procedimentos**: 
    - Caso o id passado por parâmetro nao exista na base de dados, retornar uma string vazia com o status code **404 - Not Found**.
    - Caso o id passado exista, deletar o registro referente a esse id da base de dados csv e retornar uma **string vazia** com o status code **204 - No Content**.
  - Retornos: 
    - Retornar uma **string vazia** com o status code de acordo com os procedimentos descritos.
- ## **PATCH /appointments/<int:id>**
  - Procedimentos: 
    - Caso o id passado por parâmetro nao exista na base de dados, retornar uma string vazia com o status code **404 - Not Found**.
    - Caso o id passado exista, fazer o update do registro referente a esse id da base de dados csv e retornar uma **o registro atualizado** com o status code **200 - OK**.
  - Retornos: 
    - [Formato do retorno](https://gitlab.com/-/snippets/2119404) caso o id passado exista
- ## **GET /check\_available\_times**
  - **URL Params**: 
    - A rota **/check\_available\_times** deverá poder receber o *url params* **data** no seguinte formato exemplificado: **/check\_available\_times?data=19/05/2020** (**atenção** para data no formato **dd/mm/yyyy**).
  - **Procedimentos**: 
    - Caso não seja passado o *url param* **data**, voce deve considerar a data atual para buscar os horários disponíveis na base de dados csv.
    - Processar os horários de agendamento disponíveis na data especificada, considerando o horário de atendimento das 08:00 as 18:59.
    - Os horários disponíveis devem ser retornados no formato de **lista de strings**, seguindo o formato de agendamento de 20 em 20 minutos.
  - **Retorno**: 
    - [Formato do retorno](https://gitlab.com/-/snippets/2119334) partindo do ponto em que há um agendamento marcado as **08:20 desse dia** com código de status **200 - OK**.
    - Se não houver nenhum agendamento marcado para o dia especifico, retornar todos os horários disponíveis com código de status **200 - OK**.
## -----
# **Entregáveis**
## **Repositório**
- Link do **repositório** do **GitLab**
- **Código fonte:** 
  - arquivos com a mesma estrutura apresentada no inicio do projeto.
- **Privacidade** 
  - Incluir **ka-br-out-2020-correcoes** como reporter.
-----
# **Critérios de aceitação**

|**pts**|**Dado**|**Quando**|**É esperado**|
| :-: | :-: | :-: | :-: |
|1|GET /appointments|Acessada a rota|**Retorne de acordo com os procedimentos e retornos descritos no enunciado**|
|1|POST /appointment|Acessada a rota|**Retorne de acordo com os procedimentos e retornos descritos no enunciado**|
|1|PATCH /appointments|Acessada a rota|**Retorne de acordo com os procedimentos e retornos descritos no enunciado**|
|1|DELETE /appointments|Acessada a rota|**Retorne de acordo com os procedimentos e retornos descritos no enunciado**|
|1|GET /check\_available\_times|Acessada a rota|**Retorne de acordo com os procedimentos e retornos descritos no enunciado**|


**Boa diversão Dev 🦊**


