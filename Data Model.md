# Collabore

##### A project to help fight against covid19



## Data Model (Classes)



1. Account (for Universal Authentication and Authorization):

   ```json
   {
   	"name": "String", // Required
   	"username": "String", // Required
   	"password": "String", // Required
   	"newPassword": "String", // Transient
   	"email": "String", // Required
   	"roles":  "Array" // Required; an array of String (the user role names)
   }
   ```
   
   
   
2. Citizen

   ```json
   { 
   	"username": "String", // Required
   	"birthday": "Number",
   	"gender": "Number", // Required; 0: Male, 1: Female
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
   		"preExistingDisease": "String", // Required
   		"anyMedicationUsage": "String", // Required
   		"contactWithForeigners": "Boolean", // Required
   		"knowsRecommendations": "Boolean", // Required
   		"symptoms": "Boolean", // Required
   		"contactWithInfected": "Boolean",
   		"visitedAnyHealthCenter": "Boolean" // Required
   	},
   	"economicProfile": {
   		"incomeRange": "Number", // Required
   		"occupation": "String" // Required
   	},
   	"socialProfile": {
   		"placeOfWork": "String", // Required
   		"qttOfPeopleInYourResidentialUnit": "Number" // Required
   	},
   	"status": "Boolean" // Required; for app control usage
   }
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

   