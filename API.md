# Collabore

##### A project to help fight against covid19



## API Description (_Version_: 0.0.1)



### Authentication Microservice

Important: _**Base**_ below is the base url for any endpoint presented here for Collabore.

|      | URL                                                          | HTTP Method | HTTP Message Header                                          | Table   | Response                                                     | Action                                                       |
| ---- | ------------------------------------------------------------ | ----------- | ------------------------------------------------------------ | ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | _Base_/Collab19/OAuth/v0.0.1/oauth/token/<br />grant_type=password<br />&username=String<br />&password=String<br /> | POST        | 1. _Request_:<br />Content-Type: "application/x-www-form-urlencoded"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Account | success status code: 200;<br />body: JWT object              | To do authentication account. if http status code is 200, returns JWT object. If not ok, 401 or 403 are possible returns http status code |
| 2    | _Base_/Collab19/OAuth/v0.0.1/public/Account                  | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Account | success status code: 201;<br />body: Account created         | Create new object of class Account in database. if http status code is 200, returns a object of type Account. Otherwise: 400, 401, 403, 409 (already exists a object), 417, 500 |
| 3    | _Base_/Collab19/OAuth/v0.0.1/public/Account/{username}       | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | Account | success status code: 200;<br />no body                       | checks for user existence. if ok, returns a empty String. if not ok, 404 for not found. otherwise: 400, 401, 403, 417, 500 |
| 4    | Base_/Collab19/OAuth/v0.0.1/private/Account/OAuthDetails     | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | Account | success status code: 200;<br />body: JSON JWT Account Details | if http status code is 200 it returns a object of Account. if not ok, http status code is 404 for not found. otherwise: 400, 401, 403, 417, 500 |
|      |                                                              |             |                                                              |         |                                                              |                                                              |
|      |                                                              |             |                                                              |         |                                                              |                                                              |
|      |                                                              |             |                                                              |         |                                                              |                                                              |





### Persistence Microservice

Important: _**Base**_ below is the base url for any endpoint presented here for Collabore.

|      | URL                                                       | HTTP Method | Media Type                                                   | Collection   | Response                                                     | Action                                                       |
| ---- | --------------------------------------------------------- | ----------- | ------------------------------------------------------------ | ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | _Base_/Collab19/Persistence/v0.0.1/Citizen                | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Citizens     | success status code: 201;<br />body: Citizen (with UID setted) | Register new object of class Citizen in DB                   |
| 2    | _Base_/Collab19/Persistence/v0.0.1/Citizen                | PUT         | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Citizens     | success status code: 200;<br />body: Citizen updated         | Update existing object of class Citizen in database          |
| 3    | _Base_/Collab19/Persistence/v0.0.1/Citizen/{username}     | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | Citizens     | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class Citizen in database by its username |
| 4    | _Base_/Collab19/Persistence/v0.0.1/Citizens               | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Citizens     | success status code: 200;<br />body: 0 or  more objects of class Citizen | Read existing objects according to the filter placed in the body of the request post message |
| 5    | _Base_/Collab19/Persistence/v0.0.1/Merchant               | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Merchants    | success status code: 201;<br />body: Merchant (with UID setted) | Register new object of class Citizen in DB                   |
| 6    | _Base_/Collab19/Persistence/v0.0.1/Merchant               | PUT         | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Merchants    | success status code: 200;<br />body: Merchant updated        | Update existing object of class Merchant in database         |
| 7    | _Base_/Collab19/Persistence/v0.0.1/Merchant/{username}    | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | Merchants    | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class Merchant in database by its username |
| 8    | _Base_/Collab19/Persistence/v0.0.1/Merchants              | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Merchants    | success status code: 200;<br />body: 0 or  more objects of class Merchant | Read existing objects according to the filter placed in the body of the request post message |
| 9    | _Base_/Collab19/Persistence/v0.0.1/HealthAgent            | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | HealthAgents | success status code: 201;<br />body: HealthAgent (with UID setted) | Register new object of class HealthAgent in DB               |
| 10   | _Base_/Collab19/Persistence/v0.0.1/HealthAgent            | PUT         | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | HealthAgents | success status code: 200;<br />body: Merchant updated        | Update existing object of class HealthAgent in database      |
| 11   | _Base_/Collab19/Persistence/v0.0.1/HealthAgent/{username} | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | HealthAgents | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class HealthAgents in database by its username |
| 12   | _Base_/Collab19/Persistence/v0.0.1/HealthAgents           | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | HealthAgents | success status code: 200;<br />body: 0 or  more objects of class HealthAgent | Read existing objects according to the filter placed in the body of the request post message |
| 13   | _Base_/Collab19/Persistence/v0.0.1/Beacon                 | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Beacons      | success status code: 201;<br />body: Beacon (with UID setted) | Register new object of class Beacon in DB                    |
| 14   | _Base_/Collab19/Persistence/v0.0.1/Beacon                 | PUT         | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Beacons      | success status code: 200;<br />body: Beacon updated          | Update existing object of class Beacon in database           |
| 15   | _Base_/Collab19/Persistence/v0.0.1/Beacon/{uid}           | GET         | 1. _Response_:<br />Accept: "application/json"<br />         | Beacons      | success status code: 200;<br />body: 0 or  1 Beacon          | Read a existing object of class Beacon in database by its uid |
| 16   | _Base_/Collab19/Persistence/v0.0.1/Beacons                | POST        | 1. _Request_:<br />Content-Type: "application/json"<br /><br />2. _Response_:<br />Accept: "application/json"<br /> | Beacons      | success status code: 200;<br />body: 0 or  more objects of class Beacon | Read existing objects according to the filter placed in the body of the request post message |
|      |                                                           |             |                                                              |              |                                                              |                                                              |
|      |                                                           |             |                                                              |              |                                                              |                                                              |
|      |                                                           |             |                                                              |              |                                                              |                                                              |



### GeoBeacon Microservice

Important: _**Base**_ below is the base url for any endpoint presented here for Collabore.

|      | URL                                     | HTTP Method | Media Type                                    | Collection | Response                                  | Action                                    |
| ---- | --------------------------------------- | ----------- | --------------------------------------------- | ---------- | ----------------------------------------- | ----------------------------------------- |
| 1    | _Base_/Collab19/GeoBeacon/v0.0.1/Beacon | POST        | application/json<br />to request and response | Beacons    | success status code: 201;<br />empty body | Register new object of class Beacon in DB |
|      |                                         |             |                                               |            |                                           |                                           |
|      |                                         |             |                                               |            |                                           |                                           |

