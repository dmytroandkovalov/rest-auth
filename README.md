# REST Auth Microservice

[![Build Status](https://travis-ci.org/FreeElephants/rest-auth.svg?branch=master)](https://travis-ci.org/FreeElephants/rest-auth)

## Requirements
- docker v17.05 or higher
- current user in docker group or sudo

## Install, Configure and Run

...TBD... 

## Usage

### User Resource

#### Create User

```bash
POST /api/v1/users/{GUID}
{
    "login": "some login",
    "email": "some@email",
    "password": "password"
}
```

#### Get Public User Profile
```bash
GET /api/v1/users/{GUID}
```

### Auth Resource
#### Get JWT
```bash
GET /api/v1/auth/jwt 
HEADERS: Authorization: "{login}:{password}"
```

## Contributing
```bash
git clone git@github.com:FreeElephants/rest-auth.git
cd rest-auth
./tools/build-base.sh
./tools/build-dev.sh
./tools/composer.sh install
# for tests run
./tools/codeception.sh run
```

## Configuration (ENV Variables)

REST Auth service use next env variables with default values: 
```
REST_AUTH_DB_CONNECTION_URL=sqlite:////srv/rest-auth/db.sqlite # In doctine url connection format
REST_AUTH_DEV_MODE=true # Doctrine dev mode 
REST_AUTH_HTTP_HOST=127.0.0.1
REST_AUTH_PORT=8080
REST_AUTH_ADDRESS=0.0.0.0
REST_AUTH_ORIGIN=* # multiple values can be comma separated
```
