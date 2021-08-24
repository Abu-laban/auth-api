# auth-api

## LAB - 08

### Deployment Test

**Author: Tariq Abu-Laban**

- [tests report](https://github.com/Abu-laban/auth-api/actions).
- [back-end](https://tariq-auth-api.herokuapp.com/).
- [pull request](https://github.com/Abu-laban/auth-api/pull/1).

**Setup**

`.env` **requirements**

- `PORT` - Port Number

- `DATABASE_URL` = Postgres DB

- `SECRET` = JWT SECRET

**Running the app**

- `npm start`

- Endpoint: `/signup`

> `{"username": "Anolla","password": "Haddad","role": "editor"}`

- Returns Object

        {
      "user": {
          "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IkFub2xsYSIsImlhdCI6MTYyOTgyNzY2OH0.g6yFVvdIcUntqUh2sudMh2DL-dD92T3mJlcNP3Qengo",
          "capabilities": [
              "read",
              "create",
              "update"
          ],
          "id": 2,
          "username": "Anolla",
          "password": "$2b$10$L3.OUeGN06spOf.O0P6AfuXNpmGtwwJ.MvjE1vD8OayKPiDMzbukO",
          "role": "editor",
          "updatedAt": "2021-08-24T17:54:27.896Z",
          "createdAt": "2021-08-24T17:54:27.896Z"
      },
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IkFub2xsYSIsImlhdCI6MTYyOTgyNzY2OH0.g6yFVvdIcUntqUh2sudMh2DL-dD92T3mJlcNP3Qengo"

  }

- Endpoint: `/signin`

> - Username `Ibrahim`
> - Password `Swaiss`

- Returns Object

        {
      "user": {
          "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IklicmFoaW0iLCJpYXQiOjE2Mjk4Mjg5ODd9.EOfSMKwQzROq-e4_-s2r4hXK0OCoedU2EnXmpVGb_E4",
          "capabilities": [
              "read"
          ],
          "id": 3,
          "username": "Ibrahim",
          "password": "$2b$10$tfoQMx7ObfHVbMYhXiLJMOvIkulFP2W2dWQaKU25LJBFTMaGjrhfm",
          "role": "user",
          "updatedAt": "2021-08-24T18:16:26.553Z",
          "createdAt": "2021-08-24T18:16:26.553Z"
      },
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IklicmFoaW0iLCJpYXQiOjE2Mjk4Mjg5ODd9.EOfSMKwQzROq-e4_-s2r4hXK0OCoedU2EnXmpVGb_E4"

  }

- Endpoint: `/users`

> - Token `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IlRhcmlxIiwiaWF0IjoxNjI5ODI3NTg2fQ.Od6iwITxnQeWu37QKQIzay6m3Bao8X3KF23HwGtXFTg`

- Returns Object

  [
  "Tariq",
  "Anolla",
  "Ibrahim",
  "test"
  ]

> - Token `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IklicmFoaW0iLCJpYXQiOjE2Mjk4Mjg5ODd9.EOfSMKwQzROq-e4_-s2r4hXK0OCoedU2EnXmpVGb_E4`

- Returns Object

{
"status": 500,
"message": "Access Denied"
}

- Endpoint: `/secret`

> - Token `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRhcmlxIiwiaWF0IjoxNjI5NzQyMjI0fQ.D9UrhPQz9PBb5hLcm-LBkcWQoqb0ckA2gvn7Cc7UJ48`

- Returns Object

Welcome to the secret area!

- Endpoint: `/api/v1/food`

- Returns Object

        [
        {
        "id": 1,
        "name": "Kiwi",
        "calories": 61,
        "type": "fruit",
        "createdAt": "2021-08-24T17:44:17.318Z",
        "updatedAt": "2021-08-24T17:46:52.637Z"
        },
        {
        "id": 3,
        "name": "Potato",
        "calories": 77,
        "type": "vegetable",
        "createdAt": "2021-08-24T18:12:57.054Z",
        "updatedAt": "2021-08-24T18:12:57.054Z"
        }
        ]

- Endpoint: `/api/v2/clothes`

> - Token `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IklicmFoaW0iLCJpYXQiOjE2Mjk4Mjg5ODd9.EOfSMKwQzROq-e4_-s2r4hXK0OCoedU2EnXmpVGb_E4`

- Returns Object

        [
        {
        "id": 1,
        "name": "Skirts",
        "color": "black",
        "size": "M",
        "createdAt": "2021-08-24T17:49:48.718Z",
        "updatedAt": "2021-08-24T17:50:49.862Z"
        }
        ]

**Tests**

- Unit Tests: `npm run test`
- Lint Tests: `npm run lint`

**UML**

![UML](uml.jpeg)
