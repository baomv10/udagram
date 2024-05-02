
### Dependencies

```
- Node v14.15.1 (LTS) or more recent. While older versions can work it is advisable to keep node to latest LTS version

- npm 6.14.8 (LTS) or more recent, Yarn can work but was not tested for this project

- AWS CLI v2, v1 can work but was not tested for this project

- AWS EB CLI

- AWS RDS database running Postgres.

- AWS S3 bucket for Frontend.

- AWS Elastic Beanstalk for Backend.

```

### AWS Cloud Setup

- RDS - Database Host: database-1.cfoajq8ckrnu.us-east-1.rds.amazonaws.com
- RDS - Database Port: 5432
- RDS - Database Name: postgres

- S3 Endpoint - Frontend: http://udagram-fe.s3-website-us-east-1.amazonaws.com/

- Elastic Beanstalk URL - Backend: http://udagram-api-dev22.us-east-1.elasticbeanstalk.com/

## Environment Variables

Setup the following variables in the .env file or in the cloud environments:
```
- PORT                = 8080
- POSTGRES_HOST       = <Database_Host>
- POSTGRES_PORT       = <Database_Port>
- POSTGRES_DB         = <Database_Name>
- POSTGRES_USERNAME   = <Database_Username>
- POSTGRES_PASSWORD   = <Database_Password>
- URL                 = <Frontend_Url>
- JWT_SECRET          = <>
- AWS_REGION          = <us-east-1>
- AWS_PROFILE         = <Default>
- AWS_BUCKET          = <Bucket_Name>
```

## Pipeline

From the root of the project:
- `npm run frontend:install`    - To install frontend dependencies.
- `npm run frontend:build`      - To build the Frontend.
- `npm run frontend:test`       - To test the Frontend.
- `npm run frontend:deploy`     - To deploy the project to S3.
- `npm run backend:install`     - To install backend dependencies.
- `npm run backend:build`       - To transpile the Backend.
- `npm run backend:deploy`      - To deploy the project to EB.

## CircleCi

The order of the run jobs:
- Setting Env Variables.
- Install NodeJS.
- Checkout Code & Cloning the Repo.
- Install AWS CLI v2.
- Frontend:
  - Install dependencies.
  - Build the angular.
  - Deploy the site to AWS S3.
- Backend:
  - Install dependencies.
  - Build the app.
  - Deploy the app to AWS Elastic Beanstalk.

### Installation

1. Go into the project directory - `cd udagram-frontend`
2. Install the dependencies - `npm install`
3. Start the frontend - `npm run start`
4. Open new terminal - `cd ../udagram-api`
5. Setup `.env`
6. Install the dependencies - `npm install`
7. start the backend - `npm run start`

## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1. `cd starter/udagram-frontend`
1. `npm run test`
1. `npm run e2e`

There are no Unit test on the back-end

### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

## License

[License](LICENSE.txt)
