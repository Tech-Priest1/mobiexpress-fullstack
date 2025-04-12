Claro! Aqui está um `README.md` em formato pronto para GitHub com todas as instruções:

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

### ✅ Manter histórico após logout

Para manter o histórico mesmo após o logout:

1. **Salve o `lastUserId` no login:**

```js
await AsyncStorage.setItem('userId', userId);
await AsyncStorage.setItem('lastUserId', userId); // novo
```

2. **Altere o carregamento no `ChatScreen`:**

```js
const loadMessages = async () => {
  const userId = await AsyncStorage.getItem('userId') 
                  || await AsyncStorage.getItem('lastUserId');
  if (!userId) return;
  const saved = await AsyncStorage.getItem(`chatMessages_${userId}`);
  if (saved) setMessages(JSON.parse(saved));
};
```

### ❌ Limpar histórico no logout

Para apagar o histórico ao deslogar:

```js
const userId = await AsyncStorage.getItem('userId');
if (userId) {
  await AsyncStorage.removeItem(`chatMessages_${userId}`);
}
await AsyncStorage.removeItem('userId');
await AsyncStorage.removeItem('lastUserId');
```

---

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
```
```
- Para mais instruções viste as paginas do backend and frontend
