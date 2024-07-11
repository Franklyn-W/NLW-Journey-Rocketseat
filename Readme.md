# Plann.er
O projeto Journey tem como objetivo ajudar o usuário a organizar viagens à trabalho ou lazer. O usuário pode criar uma viagem com nome, data de início e fim. Dentro da viagem o usuário pode planejar sua viagem adicionando atividades para realizar em cada dia. Projeto de desenvolvimento de um organizador de viagens.

##Ferramentas utilizadas
* Editor de código: VSCode
* Linguagem: Java
* Framework: Spring Boot
* Dependencias do Spring Boot
  * Spring Web
  * Flyway
  * Dev Tools
  * Lombok
  * H2 Databse

Esse projeto foi realizado durante um bootcamp realizado pela Rocketseat em 3 aulas.

### Requisitos

1. O usuário cadastra uma viagem informando o local de destino, data de início, data de término, e-mails dos convidados e também seu nome completo e endereço de e-mail;
2. O criador da viagem recebe um e-mail para confirmar a nova viagem através de um link. Ao clicar no link, a viagem é confirmada, os convidados recebem e-mails de confirmação de presença e o criador é redirecionado para a página da viagem;
3. Os convidados, ao clicarem no link de confirmação de presença, são redirecionados para a aplicação onde devem inserir seu nome (além do e-mail que já estará preenchido) e então estarão confirmados na viagem;
4. Na página do evento, os participantes da viagem podem adicionar links importantes da viagem como reserva do AirBnB, locais para serem visitados, etc...
5. Ainda na página do evento, o criador e os convidados podem adicionar atividades que irão ocorrer durante a viagem com título, data e horário;
6. Novos participantes podem ser convidados dentro da página do evento através do e-mail e assim devem passar pelo fluxo de confirmação como qualquer outro convidado

### Aula 01

- [x]  Criar projeto usando [Spring Initializr](https://start.spring.io/)
    - Spring Web
    - Flyway
    - Dev Tools
    - Lombok
    - JPA
    - H2 Database
- [x]  Configurar banco de dados na aplicação
- [x]  Criar migration para criação da tabela `trips`
    - Arquivos de Migration representam mudanças na estrutura do nosso banco de dados
        - criar uma tabela
        - alterar tabela, removendo campo, adicionando um campo
        - instalacao de driver
        - inserção em massa, de dados default
    - Arquivos de migration ⇒ scripts SQL, rodar comandos no banco
- [x]  Criar entidades que irá representar uma `Trip`
- [x]  Criar repository da entidade viagem
- [x]  Criar endpoint de cadastro de viagem **POST** `/trips`
- [x]  Criar endpoint de consulta de viagem **GET** `/trips/{tripId}`

### Aula 02

- [x]  Criar endpoint de atualização de viagem **PUT** `/trips/{tripId}`
- [x]  Criar endpoint confirmação de viagem **GET** `/trips/{tripId}/confirm`
- [x]  Criar tabela de `Participant`
- [x]  Criar entidade que irá representar um`Participant`
- [x]  Criar repository da entidade participante
- [x]  Criar endpoint confirmação de participante **POST** `/participants/{participantId}/confirm`
- [x]  Criar endpoint para convidar participante **POST** `/trips/{tripId}/invites`
- [x]  Criar endpoint para consultar participantes **GET** `/trips/{tripId}/participants`

### Aula 03
- [x]  Criar tabela de `Activities`
- [x]  Criar entidade que irá representar uma `Activity`
- [x]  Criar repository da entidade atividade
- [x]  Criar endpoint para cadastro de atividade **POST** `/trips/{tripId}/activities`
- [x]  Criar endpoint para consultar atividades de uma viagem **GET** `/trips/{tripId}/invites`
- [x]  Criar tabela de `Links`
- [x]  Criar entidade que irá representar um `Link`
- [x]  Criar repository da entidade links
- [x]  Criar endpoint para criação de link **POST** `/trips/{tripId}/links`
- [x]  Criar endpoint para consultar links de uma viagem **GET** `/trips/{tripId}/links`


## Features extras (A serem feitas quando estiver com mais experiencia com Spring ^^)

- [ ]  Adicionar uma validação nos campos de data
    - [ ]  A data de começo da viagem, é inferior a data de término viagem
    - [ ]  A data de uma atividade está entre as datas da viagem
        
        **Exemplo:**
        Viagem entre os dias 20 á 25 de julho no Rio de Janeiro
        
        ⇒ Atividade 19 de julho
        
        ⇒ Atividade 21 de julho
        
- [ ]  Extração do core das trips pra dentro de uma classe Service
- [ ]  Mapeamento das exceções da nossa aplicação
    - [ ]  Com tratativas de erro personalizadas

