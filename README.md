# Testes automatizados com Cypress

👋 Seja bem-vindo(a)!

# Sobre a aplicação

A aplicação se chama Central de Atendimento ao Cliente TAT (https://cac-tat.s3.eu-central-1.amazonaws.com/index.html) e foi desenvolvida usando HTML, CSS e JavaScript.

## Funcionalidades da aplicação

A aplicação CAC TAT é um formulário para simular o envio de mensagens à uma central de atendimento ao cliente.

Sendo cliente do sistema CAC TAT
Quero enviar uma mensagem através do formulário da central de atendimento ao cliente
Para que seja registrado meu atendimento nessa central

### Critérios de Aceite

* Ter os seguintes campos obrigatórios por default (Nome - tipo texto, Sobrenome - tipo texto, Email **com validacão**, Como podemos te ajudar? - área de texto)
* Se checkbox Telefone marcado input do número do telefone passa a ser obrigatório
* Se checkbox Telefone desmarcado input do número do telefone deixa de ser obrigatório
* Se clicar no link Politica de privacidade a mesma será direcionada para nova aba do navegador 
* Após envio do formulário com sucesso todos os campos voltam ao seu padrão

### Casos de testes

Contexto: 
    Dado que esteja na página do Formulário CAC TAT

CT01 - Validar envio formulário com sucesso
    Quando preencher todos os campos do formulário
    E clicar no botão Enviar
    Então sistema apresenta de envio de sucesso 

CT02 - Validar envio formulário sem preenchimento 
    Quando clicar no botão Enviar
    Então sistema apresenta mensagem "Valide os campos obrigatórios"

CT03 - Validar email formato invalido
    Quando preencher todos os campos do formulário
    E informar no campo email um formato invalido
    E clicar no botão Enviar
    Então sistema apresenta mensagem "Valide os campos obrigatórios"

CT04 - Validar contato preferencial - Telefone marcado
    Quando preencher todos os campos do formulário
    E não informar campo telefone
    E marcar opção Telefone em contato preferencial
    E clicar no botão Enviar
    Então sistema apresenta mensagem "Valide os campos obrigatórios"

CT05 - Validar Produto - YouTube
    Quando preencher todos os campos do formulário
    E selecionar a opção You tube na combox Produto
    E clicar no botão Enviar
    Então sistema apresenta de envio de sucesso 

CT06 - Validar Tipo de atendimento - Feedback
    Quando preencher todos os campos do formulário
    E selecionar a opção Feedback em tipo de atendimento
    E clicar no botão Enviar
    Então sistema apresenta de envio de sucesso 

CT07 - Validar limpeza do Formulário após envio
    Quando preencher todos os campos do formulário
    E clicar no botão Enviar
    Então sistema apresenta de envio de sucesso 

CT08 - Validar direcionamento de link
    Dado que esteja na página de formulário
    Quando clicar no link CAC TAT - Política de privacidade
    Então sistema ira direcionar para uma nova aba do navegador
    E Politica de privacidade será apresentada

# Pré-requisitos

Antes de começar, garanta que os seguintes sistemas estejam instalados em seu computador.

- git - Utilizei - git version 2.41.0.windows.3
- Node.js - Utilizei - v20.11.0
- npm - Utilizei - 10.3.0