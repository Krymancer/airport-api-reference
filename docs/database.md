# Database  Structure

Esse é uma representação visual da estrutura do banco de dados. Lembre-se que é só uma sugestão e você é livre para alterar como bem entender.

## Tables

### Flight

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| number | integer | Flight number | |
| departure | datetime | Departure date and time | |
| originAirport | integer | Origin airport id | Airport.id |
| destinationAirport | integer | Destination airport id | Airport.id |
| classes | integer | Classes for flight | Flight_Class.id |

### Airport

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| name | string | Airport name | |
| IATAcode | string | Airport IATA code | |
| city | integer | City id | City.id |

### City

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| name | string | City name | |
| state | string | City state | |

### Flight_Class

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| type | integer | Class type id | Class_Type.id |
| numberOfSeats | integer | Number of seats | |
| pricePerSeat | float | Price per seat | |
| flight | integer | Flight id | Flight.id |

### Class_Type

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| name | string | Class name | |

### Ticket

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| flightClass | integer | Flight class id | Flight_Class.id |
| passenger | integer | Passenger id | Passenger.id |
| baggage | integer | Baggage id | Baggage.id |

### Passenger

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| name | string | Passenger name | |
| cpf | string | Passenger CPF | |
| birthDate | datetime | Passenger birth date | |
| email | string | Passenger email | |

### Baggage

| Column | Type | Description | References |
| --- | --- | --- | --- |
| id | integer | Unique identifier | |
| ticket | integer | Ticket id | Ticket.id |
| number | integer | Baggage number | |
