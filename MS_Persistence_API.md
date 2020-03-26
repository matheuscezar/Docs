## Descrição da API de Persistência

**URL BASE**: https://162.241.91.243:8443/Collab19/Persistence/v0.0.1/



### Beacon: URL/Collab19/Persistence/v0.0.1/Beacon

##### _Roles_: ROLE_COLLAB19\_CITIZEN

#### 1: Criar um beacon: 

------

1.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X POST \
	-d "{ 'username': 'String', 'criticalStatus': Number, 'latitude': Number, 'longitude': Number, 'time': Number  }" \
	https://localhost:8444/Collab19/Persistence/v0.0.1/Beacon
</code>
</pre>

1.2: HTTP Response:
<br>1.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>1.2.2: Body: retorna um objeto do tipo Beacon criado
<br>1.3: Regras: --
<br>
<br>
<br>

### Citizen: URL/Collab19/Persistence/v0.0.1/Citizen

#### _Roles_: ROLE\_COLLAB19\_CITIZEN

#### 1: Criar um Citizen:

------

1.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X POST 
    -H "Authorization: Bearer [TOKEN]" \
    -d "{ "username":"julio", "birthdate":1584978849566, "gender":0, "status":0, "healthStatus":1, "address":{ "place":"place b", "number":"1", "district":"district b", "city":"city b", "state":"state b", "country":"BRASIL" }, "healthProfile": { "preExistingDisease": "none", "hasFever":false, "breathDifficulties":false, "contactWithInfected":true }, "socialProfile": { "placeOfWork":"ufrn", "occupation":"software developer", "qttOfPeopleInYourResidentialUnit":3 } }"
    https://localhost:8444/Collab19/Persistence/v0.0.1/Citizen
</code>
</pre>

1.2: HTTP Response:
<br>1.2.1: Status Code: [ 201, 400, 401, 409, 417 ]
<br>1.2.2: Body: retorna um objeto do tipo Citizen criado
<br>1.3: Regras:
<br>
<br>
<br>

#### 2: Atualiar um Citizen

------

2.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X PUT 
    -H "Authorization: Bearer [TOKEN]" \
    -d "{ "id": "1234ijkrq38024342232r", "logVersion": 0, "username":"julio", "birthdate":1584978849566, "gender":0, "status":0, "healthStatus":1, "address":{ "place":"place b", "number":"1", "district":"district b", "city":"city b", "state":"state b", "country":"BRASIL" }, "healthProfile": { "preExistingDisease": "none", "hasFever":false, "breathDifficulties":false, "contactWithInfected":true }, "socialProfile": { "placeOfWork":"ufrn", "occupation":"software developer", "qttOfPeopleInYourResidentialUnit":3 } }"
    https://localhost:8444/Collab19/Persistence/v0.0.1/Citizen
</code>
</pre>

2.2: HTTP Response:
<br>2.2.1: Status Code: [ 201, 400, 401,  409, 417 ]
<br>2.2.2: Body: retorna um objeto do tipo Citizen atualizado
<br>2.3: Regras:
<br>
<br>
<br>

#### 3: Localizar Citizen pelo username

------

3.1: console: 

<pre>
<code>
curl \
    -X GET 
    -H "Authorization: Bearer [TOKEN]" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/Citizen/{Citizen.username}
</code>
</pre>

3.2: HTTP Response: 
<br>3.2.1: Status Code: [ 200, 401, 404, 417 ]
<br>3.2.2: Body: retorna um objeto do tipo Citizen encontrado
<br>3.3: Regras: 
<br>
<br>
<br>

### HealthAgent: URL/Collab19/Persistence/v0.0.1/HealthAgent

##### _Roles_: ROLE\_COLLAB19\_HEALTHAGENT

#### 1: Criar um HealthAgent

------

5.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X POST \
	-d "{ "cpf":"12345678-91", "name":"João Maria", "agency":"Agency Example", "city":"City Name", "state":"State de Exemplo", "status": 0 }"
	Base/Collab19/Persistence/v0.0.1/HealthAgent
</code>
</pre>

1.2: HTTP Response:
<br>1.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>1.2.2: Body: retorna um objeto do tipo Health Agent criado
<br>1.3: Regras:
<br>
<br>
<br>

#### 2: Atualizar um HealthAgent

------

2.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X PUT \
	-d "{ "id": "gtg3564gfrdf", "logVersion":0, "cpf":"12345678-91", "name":"João Maria", "agency":"Agency Example", "city":"City Name", "state":"State de Exemplo", "status": 0 }"
	Base/Collab19/Persistence/v0.0.1/HealthAgent
</code>
</pre>

2.2: HTTP Response:
<br>2.2.1: Status Code: [ 200, 400, 403, 409, 417 ]
<br>2.2.2: Body: retorna um objeto do tipo Health Agent atualizado
<br>2.3: Regras: 
<br>
<br>
<br>

#### 3: Localizar um HealthAgent pelo username

------

3.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/{username}
</code>
</pre>

3.2: HTTP Response:
<br>3.2.1: Status Code: [ 200, 403, 404, 417 ]
<br>3.2.2: Body: retorna um objeto do tipo Health Agent encontrado pelo {username}
<br>3.3: Regras: 
<br>
<br>

#### 4: Localizar um HealthAgent pelo status

------

4.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/status/{status}
</code>
</pre>

4.2: HTTP Response:
<br>4.2.1: Status Code: [ 200,  404, 417 ]
<br>4.2.2: Body: retorna uma lista de objetos do tipo Health Agent encontrada pelo {status}
<br>4.3: Regras: 
<br>
<br>
<br>

#### 5: Localizar um HealthAgent pela agencia

------

5.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/agency/{agency}
</code>
</pre>

5.2: HTTP Response:
<br>5.2.1: Status Code: [ 200,  404, 417 ]
<br>5.2.2: Body: retorna uma lista de objetos do tipo Health Agent encontrada pela {agency}
<br>5.3: Regras: 
<br>
<br>
<br>

#### 6: Localizar um HealthAgent pelo username

------

6.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Citizen/username/{username}
</code>
</pre>

6.2: HTTP Response:
<br>6.2.1: Status Code: [ 200,  404, 417 ]
<br>6.2.2: Body: retorna um objeto do tipo Citizen encontrada pelo {username}
<br>6.3: Regras: 
<br>


#### 7: Localizar HealthAgent pelo status da saúde

------

7.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Citizens/healthStatus/{healthStatus}
</code>
</pre>

7.2: HTTP Response:
<br>7.2.1: Status Code: [ 200,  404, 417 ]
<br>7.2.2: Body: retorna uma lista de objetos do tipo Citizen encontrada pelo {healthStatus}
<br>7.3: Regras:
<br>


#### 8: Localizar HealthAgent pelo status da saúde, endereço e pelo distrito

------

8.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Citizens/healthStatus/{healthStatus}/addressPlace/{addressPlace}/addressDistrict/{addressDistrict}
</code>
</pre>

8.2: HTTP Response:
<br>8.2.1: Status Code: [ 200,  404, 417 ]
<br>8.2.2: Body: retorna uma lista de objetos do tipo Citizen encontrada pelo {healthStatus} e pelo{addressPlace} e pelo {addressDistrict}
<br>8.3: Regras:
<br>


#### 9: Localizar HealthAgent pelo endereço e pelo distrito

------

9.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \	Base/Collab19/Persistence/v0.0.1/HealthAgent/Citizens/healthStatus/addressPlace/{addressPlace}/addressDistrict/{addressDistrict}
</code>
</pre>

9.2: HTTP Response:
<br>9.2.1: Status Code: [ 200,  404, 417 ]
<br>9.2.2: Body: retorna uma lista de objetos do tipo Citizen encontrada pelo {addressPlace} e pelo {addressDistrict}
<br>9.3: Regras:
<br>


#### 10: Localizar  Merchant pelo username

------

10.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Merchant/username/{username}
</code>
</pre>

10.2: HTTP Response:
<br>10.2.1: Status Code: [ 200,  404, 417 ]
<br>10.2.2: Body: retorna um de objeto do tipo Merchant encontrado pelo {username}
<br>10.3: Regras:
<br>


#### 11: Localizar Merchant pelo cnpj

------

11.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Merchant/cnpj/{cnpj}
</code>
</pre>

11.2: HTTP Response:
<br>11.2.1: Status Code: [ 200,  404, 417 ]
<br>11.2.2: Body: retorna um de objeto do tipo Merchant encontrado pelo {cnpj}
<br>11.3: Regras:
<br>


#### 12: Localizar Merchants pelo type

------

12.1: console: 

<pre><code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Merchants/type/{type}
</code></pre>

12.2: HTTP Response:
<br>12.2.1: Status Code: [ 200,  404, 417 ]
<br>12.2.2: Body: retorna uma lista de objetos do tipo Merchant encontrados pelo {type}
<br>12.3: Regras:
<br>


#### 13: Localizar Merchants pelo status

------

13.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Merchants/status/{status}
</code>
</pre>

13.2: HTTP Response:
<br>13.2.1: Status Code: [ 200,  404, 417 ]
<br>13.2.2: Body: retorna uma lista de objetos do tipo Merchant encontrados pelo {status}
<br>13.3: Regras:
<br>


#### 14: Localizar Merchants pelo addressPlace e pelo addressPlace

------

14.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Merchants/addressPlace/{addressPlace}/addressDistrict/{addressDistrict}

</code>
</pre>

14.2: HTTP Response:
<br>14.2.1: Status Code: [ 200,  404, 417 ]
<br>14.2.2: Body: retorna uma lista de objetos do tipo Merchant encontrados pelo {status} e pelo {adressPlace} e pelo {adressDistrict}
<br>14.3: Regras:
<br>


#### 15: Localizar Beacons pelo username

------

15.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Beacons/{username}

</code>
</pre>

15.2: HTTP Response:
<br>15.2.1: Status Code: [ 200,  404, 417 ]
<br>15.2.2: Body: retorna uma lista de objetos do tipo Beacon encontrado pelo {username}
<br>15.3: Regras:
<br>


#### 16: Localizar Beacons pelo username e pelo timeAfter

------

16.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Beacons/{username}/timeAfter/{time}

</code>
</pre>

16.2: HTTP Response:
<br>16.2.1: Status Code: [ 200,  404, 417 ]
<br>16.2.2: Body: retorna uma lista de objetos do tipo Beacon encontrado pelo {username} e pelo tempo após {time}
<br>16.3 Regras:
<br>


#### 17: Localizar Beacon pelo username e pelo timeBefore

------

17.1: console: 

<pre>
<code>curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/HealthAgent/Beacons/{username}/timeBefore/{time}
17.2: HTTP Response:
</code>
</pre>

<br>17.2.1: Status Code: [ 200,  404, 417 ]
<br>17.2.2: Body: retorna uma lista de objetos do tipo Beacon encontrado pelo {username} e pelo tempo antes {time}
<br>17.3 Regras:
<br>

#### 18: Criar um CareUnit:

------

18.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X POST 
    -H "Authorization: Bearer [TOKEN]" \
    -d "{ "name":"clovis sarinho", "phone": "(84) 97884 9566", "specialization": "traumas", "status":0, "address":{ "place":"place b", "number":"1", "district":"district b", "city":"city b", "state":"state b", "country":"BRASIL" } }" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/HealthAgent/CareUnit
</code>
</pre>


18.2: HTTP Response:
<br>18.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>18.2.2: Body: retorna um objeto do tipo Citizen criado
<br>18.3: Regras:
<br>
<br>
<br>

#### 19: Atualiar um Citizen

------

19.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X PUT 
    -H "Authorization: Bearer [TOKEN]" \
    -d "{ "id": "asdf322w3sf3255w6", "logVersion": 0, "name":"clovis sarinho", "phone": "(84) 97884 9566", "specialization": "traumas", "status":0, "address":{ "place":"place b", "number":"1", "district":"district b", "city":"city b", "state":"state b", "country":"BRASIL" } }" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/HealthAgent/CareUnit
</code>
</pre>


19.2: HTTP Response:
<br>19.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>19.2.2: Body: retorna um objeto do tipo Citizen atualizado
<br>19.3: Regras: --



## Merchant: URL/Collab19/Persistence/v0.0.1/Merchant

##### _Roles_: ROLE\_COLLAB19\_MERCHANT

#### 1: Criar um Merchant

------

1.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X POST \
	-d {"username":"teste123", "cnpj":"123456", "name":"João Maria", "type":0, "description":"description example", "status":0 }
	Base/Collab19/Persistence/v0.0.1/Merchant
</code>
</pre>

1.2: HTTP Response:
<br>1.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>1.2.2: Body: retorna um objeto do tipo Merchant criado
<br>1.3: Regras:
<br>
<br>
<br>

#### 2: Editar um Merchant

------

2.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X PUT \
	-d {"id":"fsdfs464", "logVersion":0, "username":"teste123", "cnpj":"123456", "name":"João Maria", "type":0, "description":"description example", "status":0 }
	Base/Collab19/Persistence/v0.0.1/Citizen/
</code>
</pre>

2.2: HTTP Response:
<br>2.2.1: Status Code: [ 201, 400, 403, 409, 417 ]
<br>2.2.2: Body: retorna um objeto do tipo Merchant editado
<br>2.3: Regras:
<br>
<br>
<br>


#### 3: Localizar Merchant pelo username

------

3.1: console: 

<pre>
<code>
curl \
	-H "Content-Type: application/json" \
	-X GET \
	Base/Collab19/Persistence/v0.0.1/Merchant/{username}
</code>
</pre>

3.2: HTTP Response:
<br>3.2.1: Status Code: [ 200,  403,  417 ]
<br>3.2.2: Body: retorna um objeto do tipo Merchant encontrado
<br>3.3: Regras:
<br>
<br>
<br>

## CareUnit: URL/Collab19/Persistence/v0.0.1/CareUnit

##### _Roles_: ROLE_COLLAB19\_CITIZEN, ROLE\_COLLAB19\_MERCHANT, ROLE\_COLLAB19\_HEALTHAGENT

#### 1: Localizar Citizen pelo username

------

1.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X GET 
    -H "Authorization: Bearer [TOKEN]" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/CareUnit/{CareUnit.name}
</code>
</pre>

1.2: HTTP Response: 
<br>1.2.1: Status Code: [ 200, 401, 404, 417 ]
<br>1.2.2: Body: retorna um objeto do tipo Citizen encontrado
<br>1.3: Regras: 
<br>
<br>
<br>

#### 2: Localizar CareUnits por especialização

------

2.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X GET 
    -H "Authorization: Bearer [TOKEN]" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/CareUnit/specialization/{CareUnit.specialization}
</code>
</pre>

2.2: HTTP Response: 
<br>2.2.1: Status Code: [ 200, 401, 404, 417 ]
<br>2.2.2: Body: retorna uma lista de objetos do tipo CareUnit encontrados
<br>2.3: Regras: 
<br>
<br>
<br>

#### 3: Localizar CareUnits por fone

------

3.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X GET 
    -H "Authorization: Bearer [TOKEN]" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/CareUnit/phone/{CareUnit.phone}
</code>
</pre>

3.2: HTTP Response: 
<br>3.2.1: Status Code: [ 200, 401, 404, 417 ]
<br>3.2.2: Body: retorna uma lista de objetos do tipo CareUnit encontrados
<br>3.3: Regras: 
<br>
<br>
<br>

#### 4: Localizar CareUnits por bairro (district)

------

4.1: console: 

<pre>
<code>
curl \
	--insecure \
    -X GET 
    -H "Authorization: Bearer [TOKEN]" \
    https://localhost:8444/Collab19/Persistence/v0.0.1/CareUnit/addressDistrict/{CareUnit.addressDistrict}
</code>
</pre>

4.2: HTTP Response: 
<br>4.2.1: Status Code: [ 200, 401, 404, 417 ]
<br>4.2.2: Body: retorna uma lista de objetos do tipo CareUnit encontrados
<br>4.3: Regras: 
<br>
<br>
<br>
