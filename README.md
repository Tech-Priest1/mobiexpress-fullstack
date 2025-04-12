

---

```markdown
# 🤖 MobiExpress Chatbot

Este projeto é um chatbot de suporte integrado ao app da MobiExpress, utilizando React Native no front-end e um backend Node.js com suporte ao modelo Gemini da Google.

---

## 📦 Estrutura do Projeto

```bash
mobiexpress/
├── backend/
├── frontend/
```

---

## 🚀 Como rodar localmente com túnel

### 🔧 Backend

No diretório `backend/`, execute:

```bash
npm run dev:tunnel
```

Esse comando:

- Inicia o servidor com `nodemon`
- Cria um túnel público com o `localtunnel`, usando um subdomínio fixo

> 🔁 O túnel será reiniciado sempre que o servidor reiniciar

---

## 💬 Histórico de mensagens no Chat

As mensagens são armazenadas localmente usando `AsyncStorage`, associadas ao `userId` do usuário.

## 📱 Frontend

No diretório `frontend/`, use:

```bash
npx expo start
```

- Certifique-se de que a variável `EXPO_PUBLIC_API_URL` aponte para o túnel criado pelo backend.
- Exemplo de `.env` no `frontend/`:

```env
EXPO_PUBLIC_API_URL=https://seu-subdominio.loca.lt
```

---

## ✅ Funcionalidades

- Login com autenticação JWT
- Chat com modelo Gemini
- Histórico local por usuário
- Cadastro e recuperação de senha
- Footer fixo com navegação

---

## 🛡️ Segurança

- Senhas são armazenadas com bcrypt
- Tokens são assinados com segredo JWT
- Comunicação segura via túnel HTTPS

---

## ✍️ Autor

Projeto criado por [Petrus Ermerson], para a MobiExpress 📱

- Para mais instruções viste as paginas do [backend](https://github.com/Tech-Priest1/samaraBackend.git) e [frontend](https://github.com/Tech-Priest1/react-nativeApp.git)


