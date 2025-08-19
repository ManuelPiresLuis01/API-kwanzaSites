
# API de Envio de Formulário por Email

Esta é uma API simples em **Node.js** usando **Express** e **Nodemailer** para enviar mensagens de formulários de contato por email.

---

## Tecnologias usadas

- Node.js
- Express
- Nodemailer
- Body-parser
- CORS
- dotenv

---

## Instalação

1. Clone este repositório:
```bash
git clone <URL_DO_REPOSITORIO>
cd <NOME_DO_REPOSITORIO>
````

2. Instale as dependências:

```bash
npm install
```

3. Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

```env
PORT=5000
EMAIL_USER=seuemail@gmail.com
EMAIL_PASS=senha_do_app_email
TO_EMAIL=destino@gmail.com
```

> ⚠️ **Importante:** Utilize uma senha de aplicativo se estiver usando Gmail.

---

## Estrutura da API

* **POST /send** - Envia o formulário de contato por email.

### Corpo da requisição (JSON):

```json
{
  "name": "Seu Nome",
  "email": "seuemail@gmail.com",
  "phone": "+244 955 791 520",
  "message": "Sua mensagem aqui"
}
```

### Respostas possíveis:

* **200 OK** - Mensagem enviada com sucesso

```json
{ "message": "Mensagem enviada com sucesso!" }
```

* **400 Bad Request** - Campos obrigatórios não preenchidos

```json
{ "message": "Todos os campos são obrigatórios" }
```

* **500 Internal Server Error** - Erro ao enviar a mensagem

```json
{ "message": "Erro ao enviar a mensagem" }
```

---

## Como rodar a API localmente

```bash
npm start
```

A API estará disponível em:

```
http://localhost:5000/send
```

---

## Observações

* Certifique-se de que as variáveis de ambiente estão corretas.
* Esta API pode ser integrada a qualquer frontend que envie requisições POST com o JSON no formato descrito.
* Para produção, configure variáveis de ambiente seguras no seu servidor ou serviço de hospedagem (Vercel, Railway, Heroku, etc.).

---

