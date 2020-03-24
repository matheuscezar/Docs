## Descrição da API do Serviço de Autenticação

#### 0: Observações Gerais:
0.1: ROLES de usuário: 
<br>0.1.1: **ROLE_GUEST**, 
<br>0.1.2: **ROLE\_COLLAB19\_CITIZEN**, 
<br>0.1.3: **ROLE\_COLLAB19\_MERCHANT**, 
<br>0.1.4: **ROLE\_COLLAB19\_HEALTHAGENT**
<br>0.2: HTTP Status Code:
<br>0.2.1: **400** (requisição mal formada - possível erro no front), 
<br>0.2.2: **401** (credenciais não reconhecidas), 
<br>0.2.2: **403** (acesso negado, possível falta de autorização no perfil para acesso a dado), 
<br>0.2.2: **404** (dado não encontrado), 
<br>0.2.3: **409** (conflito de registro já existente)
<br>0.2.4: **417** (erro não mapeado a priori)
<br>0.2.5: **500** (erro interno do servidor, possível erro no back)
<br>
<br>
<br>
#### 1: Crair um usuário: 
1.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X POST \
	--data '{ "email": "julio@email.com", "username": "julio", "password": "123456", "roles": [{ "role": "ROLE_COLLAB19_CITIZEN" }, { "role": "ROLE_AUTH_USER" }, { "role": "ROLE_GUEST" }] }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/public/Account
</code>
</pre>
<br>1.2: HTTP Response:
<br>1.2.1: Status Code: [ 201, 400, 409, 417 ] 
<br>1.2.2: Body:
<br>1.3: Regras:
<br>
<br>
<br>
#### 2: Autenticação de usuário: 
2.1: console: 
<pre>
<code>
curl \
	--insecure \
	-X POST \
	-H "Content-Type: application/x-www-form-urlencoded" \
	-H "Authorization: Basic c2xpbmdib29fYXV0aF9jbGllbnQ6MXdxMiNSRSQ1eXQ2JklVKg==" \ 
	-d "grant_type=password&username=julio&password=123456" \
	https://localhost:8443/Collab19/OAuth/v0.0.1/oauth/token
</code>
</pre>
<br>2.2: HTTP Response:
<br>2.2.1: Status Code: [ 200, 401, 403 ] 
<br>2.2.2: Body: 
<pre><code>
{
  "access_token" : "",
  "token_type" : "",
  "refresh_token" : "",
  "expires_in" : ,
  "scope" : "",
  "jti" : ""
}
</code></pre>
<br>2.3: Regras: --
<br>
<br>
<br>
#### 3: Recupera o cadastro de um usuário 
3.1: console: 
<pre>
<code>
curl \
	-H "Accept: application/json" \
	-X GET \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/{username}
</code>
</pre>
<br>3.2: HTTP Response:
<br>3.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>3.2:2: Body: retorna um objeto do tipo Account (Ver definição no 'Data Model.md')
<br>3.3: Regras: 
<br>
<br>
<br>
#### 4: Atualizar um usuário 
4.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-H "Accept: application/json" \
	-X PUT \
	-d '{ "id": 1, "email": "julio@email.com", "username": "julio", "password": "123456" }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/{username}
</code>
</pre>
<br>4.2: HTTP Response: 
<br>4.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>4.2.2: Body: retorna um objeto do tipo Account (Ver definição no 'Data Model.md')
<br>4.3: Regras: 
<br>4.3.1: só o próprio usuário pode alterar seu próprio cadastro
<br>4.3.2: só é possível atualizar o valor do atributo e-mail para um objeto de classe Account
<br>
<br>
<br>
#### 5: Associar uma nova role a um usuário 
5.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-H "Accept: text/plain" \
	-X PUT \
	-d '{ "username": "julio", "roles": [ "ROLE_COLLAB19_MERCHANT" ] }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/associateRole
</code>
</pre>
<br>5.2: HTTP Response:
<br>5.2.1: Status Code: [ 200, 400, 401, 404, 417 ]
<br>5.2.2: Body: 
<br>5.3: Regras: --
<br>
<br>
<br>
#### 6: Desassociar uma role de um usuário 
6.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-H "Accept: text/plain" \
	-X PUT \
	-d '{ "username": "julio", "roles": [ "ROLE_COLLAB19_MERCHANT" ] }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/disassociateRole
</code>
</pre>
<br>6.2: HTTP Response:
<br>6.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>6.2.2: Body: 
<br>6.3: Regras: --
<br>
<br>
<br>
#### 7: Verificar a associação de uma ou mais roles a um usuário
7.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-H "Accept: application/json" \
	-X POST \
	-d '{ "roles": [ "ROLE_COLLAB19_MERCHANT" ] }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/hasRoles
</code>
</pre>
<br>7.2: HTTP Response:
<br>7.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>7.2.2: Body: um array com as roles que não deram match
<br>7.3: Regras: --
<br>
<br>
#### 8: Recuperar a lista de roles de um usuário
8.1: console: 
<pre>
<code>
curl \
	-H "Accept: application/json" \
	-X GET \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/{username}/getRoles
</code>
</pre>
<br>8.2: HTTP Response:
<br>8.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>8.2.2: Body: um array com todas as roles da conta
<br>8.3: Regras: --
<br>
<br>
<br>
#### 9: Atualizar a senha de usuário
9.1: console: 
<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-H "Accept: application/json" \
	-X PUT \
	-d '{ "username": "julio", "password": "123456", "newPassword": "123" }' \
	--insecure \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/disassociateRole 
</code>
</pre>
<br>9.2: HTTP Response:
<br>9.2.1: Status Code: [ 200, 401, 404, 417 ] 
<br>9.2.2: Body: 
<br>9.3: Regras: 
<br>
<br>
<br>
#### 10: Detalhamento de dados de autenticação:
10.1: console: 
<pre>
<code>
curl \
	--insecure \ 
	-X GET \
	-H "Authorization: Bearer [JWT TOKEN]" \
	https://localhost:8443/Collab19/OAuth/v0.0.1/private/Account/OAuthDetails
</code>
</pre>
<br>10.2: HTTP Response:
<br>10.2.1: Status Code: [ 200, 400, 401, 404, 417 ] 
<br>10.2.2: Body:
<br>10.3: Regras: --
<br>

