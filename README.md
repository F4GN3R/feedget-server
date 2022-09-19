## 💻 Projeto

API para realizar o cadastro dos feedbacks enviados em uma base de dados e disparar um email de notificação informando que um novo feedback foi submetido.

## ✨ Tecnologias

- [ ] Node
- [ ] Typescript
- [ ] Express
- [ ] Prisma
- [ ] Jest
- [ ] Nodemailer
- [ ] Conceitos de SOLID

## :hammer_and_wrench: Features

- [ ] Endpoint para envio de feedbacks (`/feedbacks`);
- [ ] Integração com banco de dados via Prisma;
- [ ] Utilização de conceitos de SOLID;
- [ ] Testes unitários;
- [ ] Disparo de email`s para endereço cadastrado;
- [ ] Verificação de regras de negócio antes de persistir os dados no DB;

## 🌎 Deploy

O serviço está disponível através [desse link](https://feedget-server-production-3c1c.up.railway.app/).

## 🔵 Executando o projeto

Node => v16.17.0

1. Instalar as dependências do projeto:

```cl
npm install
```

2. Alterar o provider do Prisma para SQLite:

```cl
{
  provider = "sqlite"
  ...
}
```

3. Criar um arquivo de variáveis `.env` na raiz do projeto com o local do SQLite:

```cl
DATABASE_URL="file:./dev.db"
```

4. Execute as migrations do Prisma para gerar as tabelas no DB:

```cl
npx prisma migrate dev -n create_feedbacks init
```

5. O prisma fornece uma ferramenta para visualização das tabelas, confirme se as colunas foram criadas corretamente executando:

```cl
npx prisma studio
```

6. Para testar o envio de e-mail utilize o serviço de sandbox de e-mail da [mailtrap.io](https://mailtrap.io/). Você deve criar uma conta e alterar as credenciais do arquivo `nodemailer-mail-adpter.ts`:

```cl
{
  host: "smtp.mailtrap.io",
  port: 2525,
  auth: {
    user: "your_user",
    pass: "your_pass",
  },
}
```

7. Execute o projeto:

```cl
npm run dev
```

8. Se tudo estiver ok, você terá umas saída semelhante a essa no terminal e a API estará pronta para receber requisições:

```cl
[INFO] 13:26:35 ts-node-dev ver. 2.0.0 (using ts-node ver. 10.9.1, typescript ver. 4.8.3)
HTTP server running
```

9. (Opcional) Para executar os testes:

```cl
npm run test
```

## 📄 Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

<br />
