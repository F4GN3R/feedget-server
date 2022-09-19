## 💻 Projeto

API para realizar o cadastro dos feedbacks enviados em uma base de dados e disparar um email de notificação informando que um novo feedback foi submetido.

## ✨ Tecnologias

- [x] Node
- [x] Typescript
- [x] Express
- [x] Prisma
- [x] Jest
- [x] Nodemailer

## 🛠 Features

- Integração com banco de dados via Prisma;
- Testes unitários;
- Integração com serviço de envio de e-mail;
- Verificação de regras de negócio antes de persistir os dados no DB;
- Utilização dos princípio de SOLID;
  - Single Responsability Principle (Princípio da Responsabilidade Única);
  - Open/Closed Principle (Princípio do “Aberto para Extensão/Fechado para Implementação);
  - Liskov Substitution Principle (Princípio da Substituição de Liskov);
  - Interface Segregation Principle (Princípio da Segregação de Interfaces);
  - Dependency Inversion Principle (Princípio da Inversão de Dependências);

## 🌎 Deploy

O serviço está disponível através [desse link](https://feedget-server-production-3c1c.up.railway.app/).

## 🚀 Executando o projeto

**Node v16.17.0 >**

1. Instalar as dependências do projeto:

```bash
npm install
```

2. Alterar o provider do Prisma para SQLite:

```cl
{
  provider = "sqlite"
  ...
}
```

3. Criar um arquivo de variáveis `.env` na raiz do projeto com a url do SQLite:

```cl
DATABASE_URL="file:./dev.db"
```

4. Execute as migrations do Prisma para gerar as tabelas no DB:

```bash
npx prisma migrate dev -n create_feedbacks init
```

5. O prisma fornece uma ferramenta para visualização das tabelas, confirme se as colunas foram criadas corretamente executando:

```bash
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

```bash
npm run dev
```

8. Se tudo estiver correto, uma saída semelhante a essa será obtida no terminal e a API estará pronta para receber requisições:

```cl
[INFO] 13:26:35 ts-node-dev ver. 2.0.0 (using ts-node ver. 10.9.1, typescript ver. 4.8.3)
HTTP server running
```

9. (Opcional) Para executar os testes:

```bash
npm run test
```

## 📓 Documentação da API

#### Cadastrar um feedback

```cl
POST /feedbacks
```

| Body         | Tipo                         | Descrição                         |
| :----------- | :--------------------------- | :-------------------------------- |
| `type`       | `"BUG" or "IDEA" or "OTHER"` | **Obrigatório**. Tipo do feedback |
| `comment`    | `string`                     | **Obrigatório**. Comentário       |
| `screenshot` | `string`                     | Imagem no formato base64          |

## 📄 Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

<br />
