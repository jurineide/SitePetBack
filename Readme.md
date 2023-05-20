<h1 align="center">Programa Soul Pet <img src="https://media.giphy.com/media/WUlplcMpOCEmTGBtBW/giphy.gif" width="30"> <br /></h1>

Este é uma api desenvolvida em linguagem de programação Back-end, voltado para gerenciamento de um petshop. O objetivo é oferecer uma solução para simplificar a gestão de informações relacionadas aos pets e seus proprietários.

<h3>Funcionalidades</h3>
O programa Soul Pet possui as seguintes funcionalidades:

- Cadastro de clientes: cadastro de clientes, incluindo informações como nome, endereço, telefone e e-mail.
- Cadastro de pets: cadastro de animais, incluindo informações como nome, tipo, porte, data de nascimento e identificação do proprietário.
- Cadastro de produtos: possui um sistema de controle de produtos, como higiene, brinquedos, conforto, alimentação, medicamentos.
- Inserção pedidos: há uma segmentação para controle de pedidos, que permite o cadastro de mesmo de acordo com quantidade, cliente e protudos solicitatos.
- Registro de agendamento: possui uma seção de agendamentos para inserção de um serviço em específico, de acordo com o pet, data e status.
- Registro de serviços: permite o registro de serviços realizados no petshop, como banho, tosa, vacinação, entre outros.

<h3>Tecnologias utilizadas e pré-requisitos</h3>
O programa Soul Pet foi desenvolvido utilizando as seguintes tecnologias:

|![](https://img.shields.io/badge/-JavaScript-black?logo=javascript&style=plastic)|![](https://img.shields.io/badge/-NodeJs-black?logo=nodedotjs&style=plastic)|![](https://img.shields.io/badge/-React-black?logo=react&style=plastic)|![](https://img.shields.io/badge/-Express-black?logo=express&style=plastic)|![](https://img.shields.io/badge/-Html-black?logo=html5&style=plastic)|
|---|---|---|---|---|
|![](https://img.shields.io/badge/-MySQL-black?logo=mysql&style=plastic)|![](https://img.shields.io/badge/-Postman-black?logo=postman&style=plastic)|![](https://img.shields.io/badge/-Git-black?logo=git&style=plastic)|![](https://img.shields.io/badge/-Bootstrap-black?logo=bootstrap&style=plastic)|![](https://img.shields.io/badge/-Css-black?logo=css3&style=plastic)

- Clientes <br />
#### Consulta todos os clientes
```http
  GET /clientes
```

#### Consulta um cliente específico
```http
  GET /clientes/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Gera relatório em pdf de todos os clientes
```http
  GET /relatorio
```

#### Insere um novo cliente
```http
  POST /clientes
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `nome` | `string` | **Obrigatório**|
| `email` | `string` | **Obrigatório**|
| `telefone` | `string` | **Obrigatório**|
| `endereco` | `foreign_key` | **Obrigatório**|

#### Atualiza os dados de um cliente específico
```http
  PUT /clientes/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um cliente
```http
  DELETE /clientes/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|


- Pets <br />

#### Consulta todos os pets
```http
  GET /pets
```

#### Consulta um pet específico
```http
  GET /pets/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Consulta todos os pets de um cliente
```http
  GET /clientes/:clienteId/pets
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `clienteID` | `number` | **Obrigatório**|

#### Insere um novo pet
```http
  POST /pets
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `nome` | `string` | **Obrigatório**|
| `tipo` | `string` | **Obrigatório**|
| `porte` | `string` | **Obrigatório**|
| `dataNasc` | `date-only` | **Obrigatório**|

#### Atualiza os dados de um pet específico
```http
  PUT /pets/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um pet
```http
  DELETE /pets/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

- Produtos <br />
#### Consulta todos os produtos
```http
  GET /produtos
```

#### Consulta um produto específico e contém o filtro de nome e categoria
```http
  GET /produtos/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Atualiza os dados de um produto específico
```http
  PUT /produto/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um produto

```http
  DELETE /produto/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|


- Pedidos <br />

#### Consulta todos os pedidos
```http
  GET /pedidos
```

#### Consulta um pedido específico
```http
  GET /pedido/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Consulta todos os pedidos de acordo com id do produto
```http
  GET /pedidos/produtos/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Consulta todos os pedidos de acordo com id do cliente
```http
  GET /pedidos/clientes/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Insere um novo pedido
```http
  POST /pedidos
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `codigo` | `string` | **Obrigatório**|
| `quantidade` | `integer` | **Obrigatório**|

#### Atualiza os dados de um pedido específico
```http
  PUT /pedido/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um pedido
```http
  DELETE /pedido/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|


- Agendamento
#### Consulta todos os agendamentos
```http
  GET /agendamentos
```

#### Consulta um agendamentos específico
```http
  GET /agendamentos/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Insere um novo agendamento
```http
  POST /agendamentos
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `petId` | `number` | **Obrigatório**|
| `servicoId` | `number` | **Obrigatório**|
| `dataAgendada` | `dateOnly` | **Obrigatório**|
| `realizada` | `text` | **Obrigatório**|

#### Atualiza os dados de um agendamentos específico
```http
  PUT /agendamentos/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um agendamento específico
```http
  DELETE /agendamentos/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

- Serviços <br />

#### Consulta todos os serviços
```http
  GET /servicos
```

#### Consulta um serviço específico
```http
  GET /servico/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Insere um novo serviço
```http
  POST /servicos
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `nome` | `string` | **Obrigatório**|
| `preco` | `string` | **Obrigatório**|

#### Atualiza os dados de um serviço específico
```http
  PUT /servico/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove um serviço
```http
  DELETE /servico/:id
```
| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `id` | `number` | **Obrigatório**|

#### Remove todos os serviços
```http
  DELETE /servicos/all
```





