2023-09-25 20:08
Tags: #nodejs 

---
Это обычная закодирована строка которая состоит из трёх частей:
- **Header** (заголовок) - определяет то как должна вычисляться подпись, определяет алгоритм хеширования
- **Payload** (Полезные данные) - храниться полезные данные, может быть id пользователя, его роли, userName... любые данные.
- **Signature** (Подпись) - шифруются данные и по этому ключу сервер сможет расшифровать эти данные.

![[JWT.jpg]]

#### Есть два вида токенов:
- Access - токен доступа
- Refresh - перезаписывает access токен

![[JWT_token.jpg]]

---
### Links
[[Node.js]]
