# Collabore

##### A project to help fight against covid19



## Data Model (Classes)



1. Account (for Universal Authentication and Authorization):

   ```json
   {
   	"username": "String; Required",
   	"password": "String; Required",
   	"newPassword": "String; Transient",
   	"email": "String; Required", 
   	"roles":  "Array of String"
   }
   
   Tipos de valores para roles: "Cidadao", "Agente de Saude", "Comerciante"
   ** Considerar se necessário: "Agente de Saude" certamente, mais à frente, se desdobrará em outros tipos mais especializados
   ```
   
   
   
2. Citizen

   ```json
   { 
   	"username": "String; Required",
   	"birthday": "Number; Required",
   	"gender": "Number; Required",
   	"address": { 
   		"place": "String; Required",
   		"number": "String; Required",
   		"complement": "String", 
   		"district": "String; Required",
   		"state": "String; Required",
   		"zipCode": "String",
   		"lat": "Number",
   		"long": "Number"
   	},
   	"healthProfile": { 
   		"anyMedicationUsage": "String; Required",
   		"preExistingDisease": "String; Required",
   		"visitedAnyHealthCenter": "Boolean; Required",
   		"hasFever": "Boolean; Required",
   		"breathDifficulties": "Boolean; Required",
   		"contactWithInfected": "Boolean; Required",
   		"coryza": "Boolean",
   		"cough": "Boolean", 
   		"dryCough": "Boolean", 
   		"headache": "Boolean",
   	},
   	"economicProfile": {
   		"incomeRange": "Number", // Required
   	},
   	"socialProfile": {
   		"placeOfWork": "String; Required",
   		"qttOfPeopleInYourResidentialUnit": "Number; Required",
   		"occupation": "String"
   	},
   	"status": "Boolean; Required",
   	"healthStatus": "Boolean" 
   }
   
   Citizen.status: "valores possíveis: 0: ativo (valor padrão), 1: inativo"
   Citizen.gender: "valores possíveis: 0: masculino, 1: feminino"
   Citizen.healthStatus: "a regra de negócio para valorar esse atributo está no fluxo grama posto no repo Collab19/Docs: Fluxograma para NOTA TÉCNICA Nº 2 - 2020 - SESAP - SUAS - NUSBSESAP.pdf"
   ```

   

3. Merchant

   ```json
   {
       "username": "String; Required",
   	"name": "String; Required",
   	"cnpj": "String; Required",
   	"type": "Number; Required",
   	"address": { 
   		"place": "String; Required",
   		"number": "String; Required",
   		"complement": "String; Required", 
   		"district": "String; Required",
   		"state": "String; Required",
   		"zipCode": "String; Required",
   		"lat": "Number",
   		"long": "Number"
   	},
   	"open": "Boolean",
   	"status": "Number" // for app control usage
   }
   
   Merchant.type: "valores possíveis: 0: Farmácias, 1: Mercado (pequeno), 2: Super Mercado, 3: Unidades de Saúde; 4: Fornecedores de Alimentos para Entregas"
   Merchant.status: "valores possíveis: 0: ativo, 1: inativo"
   ```

   

4. Health Agent

   ```json
   {
   	"username": "String; Required",
   	"name": "String; Required",
   	"cpf": "String; Required",
   	"agency": "String; Required",
   	"city": "String; Required",
   	"state": "String; Required"
   }
   ```
   

   
5. Admin

   ```json
   {
       "username": "String; Required",
   	"name": "String",
   	"cpf": "String",
   	"username": "String",
   	"password": "String",
   	"profiles": "Array of String"
   }
   ```

   

6. Beacons

   ```json
   {
       "username": "String; Required; User.username fk",
       "criticalStatus": "Number; Required; inferred from the user's health profile",
   	"latitude": "Number; Required",
   	"longitude": "Number; Required",
   	"time": "Number; Required; timestamp (measurement every 5 minutes)"
   }
   ```

   