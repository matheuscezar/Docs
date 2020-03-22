# Collabore

##### A project to help fight against covid19



## Data Model (Classes)



1. Account (for Universal Authentication and Authorization):

   ```json
   {
   	"username": "String", // Required
   	"password": "String", // Required
   	"newPassword": "String", // Transient
   	"email": "String", // Required
   	"roles":  "Array" // Required; an array of String (the user role names)
   }
   
   Tipos de valores para roles: [ "Cidadao", "Agente de Saude", "Comerciante", ]
   ** Considerar se necessário: "Agente de Saude" certamente, mais à frente, se desdobrará em outros tipos mais especializados
   ```
   
   
   
2. Citizen

   ```json
   { 
   	"username": "String", // Required
   	"birthday": "Number",
   	"gender": "Number", // Required; values 0: Male, 1: Female
   	"address": { 
   		"place": "String", // Required
   		"number": "String", // Required
   		"complement": "String", 
   		"district": "String", // Required
   		"state": "String", // Required
   		"zipCode": "String",
           "lat": "Number",
           "long": "Number"
   	},
   	"healthProfile": { 
   		"anyMedicationUsage": "String", // Required
   		"preExistingDisease": "String", // Required
   		"hasFever": "Boolean", // Required
   		"breathDifficulties": "Boolean", // Required
   		"contactWithInfected": "Boolean", // Required
   		"visitedAnyHealthCenter": "Boolean", // Required
           "coryza": Boolean,
           "cough": Boolean, 
           "dryCough": Boolean, 
           "headache": Boolean,
   	},
   	"economicProfile": {
   		"incomeRange": "Number", // Required
   	},
   	"socialProfile": {
   		"placeOfWork": "String", // Required
   		"qttOfPeopleInYourResidentialUnit": "Number", // Required
   		"occupation": "String" // Required
   	},
   	"status": "Boolean", // Required; for app control usage,
       "healthStatus": "Boolean" // será valorado a partir do que for preenchido no perfil de saúde do cadastro
   }
   
   Citizen.status: [ 0: ativo (valor padrão), 1: inativo ]; 
   ```

   

3. Merchant

   ```json
   {
   	"name": "String",
   	"cnpj": "String",
   	"type": "Number", // Required; product or service marketed at the establishment
   	"address": { 
   		"place": "String", // Required
   		"number": "String", // Required
   		"complement": "String", 
   		"district": "String", // Required
   		"state": "String", // Required
   		"zipCode": "String", // Required
           "lat": "Number",
           "long": "Number"
   	},
       "open": "Boolean",
       "status": "Number" // for app control usage
   }
   
   Merchant.type: [ 0: Farmácias, 1: Mercado (pequeno), 2: Super Mercado, 3: Unidades de Saúde; 4: Fornecedores de Alimentos para Entregas ]
   Merchant.status: [ 0: ativo, 1: inativo ]
   ```

   

4. Health Authority

   ```json
   {
   	"name": "String", // Required
   	"cpf": "String", // Required
   	"agency": "String", // Required
   	"username": "String", // Required
   	"password": "String", // Required
   	"city": "String",
   	"state": "String"
   }
   ```

   

5. Admin

   ```json
   {
   	"name": "String",
   	"cpf": "String",
   	"username": "String",
   	"password": "String",
   	"profiles": "Array" // Array of Strings
   }
   ```

   

6. Beacons

   ```json
   {
       "username": "String", // Required; User.username fk
       "criticalStatus": "Number", // Required; inferred from the user's health profile
   	"lat": "Number", // Required
   	"long": "Number", // Required
   	"time": "Number" // Required; timestamp (measurement every 5 minutes),
   }
   ```

   