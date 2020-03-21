# Collabore

##### A project to help fight against covid19



## Requirements (by Use Cases)



### I) Scenario

Pandemic due to covid19. Recommendations from health authorities: maximum social isolation, so that people stay in their homes or shelters and leave them only if necessary, for example, to buy food and medicines.



### II) User Roles

Citizen 

Merchant

Health Agent

Admin



### II) Use Cases

The application use cases are described below. Then a class diagram will be presented to describe the data with which the application must operate.



1. ##### Register

   **Citizen**: (a) home address, (b) social, (c) economic and (d) health profile:

   (a) place, number, district, city, state, country, zip code.

   (b) place of work or study, people live in same residential unit

   (c) income range, occupation

   (d) any type of pre-existing disease, taking any medication, contact with foreigners, knows medical recommendations, went to a health center in the last 15 days, symptoms of the disease, had contact with infected

   

   **Merchant**:

   (a) name of the establishment

   (b) address

   (c) type of commercial establishment

   (d) geo coordinates

   

   **Health Agent**: 

   (a) user name

   (b) cpf

   (c) authority agency

   (d) city

   (e) state

   

2. ##### Citizen Register Activation

   Some data analysis. Example: by the health authority to confer some degree of credibility of the data.

   

3. ##### Geo Coordinate Catch - Citizen

   Capture and record in a database coordinates of the citizen's location every 5 minutes
   
   
4. ##### Geo Coordinate Catch - Merchant

   Do it by merchant register

   

5. ##### Geo Info Views

   Present data captured on a map according to user profiles and filters of interest:

   **Citizen**: (1) Better routes and places, in terms of health security, so that he can move around the city; (2) Default Authorities Alerts; (3) Search for health service availability; (4) Looking for home maintenance products and services

   **Merchant**: View the degree/risk of contamination of the establishment; (2) Acceptance to Collab19 use incentive program;

   **Health Agent**: (1) Full access to data analysis in map, for example; (2) free access to consumption all data through Backend API; (3) citizen monitoring to prevent increasing risk; (4) brief communication channel with citizen

   
