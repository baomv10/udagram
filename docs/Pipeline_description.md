
## Add scripts in package.json from the root of the project

- `npm run frontend:install`    - To install frontend dependencies.
- `npm run frontend:build`      - To build the Frontend.
- `npm run frontend:test`       - To test the Frontend.
- `npm run frontend:deploy`     - To deploy the project to S3.
- `npm run backend:install`     - To install backend dependencies.
- `npm run backend:build`       - To transpile the Backend.
- `npm run backend:deploy`      - To deploy the project to EB.

## Connect the Pipeline to Github

1. Create a public repository in Github.
2. Set the remote origin to point to Github repository.
3. Register with CircleCI using GitHub credentials.
4. Set up a new project in CircleCI dashboard using newly created GitHub repository.
5. Create .circleci/config.yml file in source code.
6. Commits/pushes to repo will trigger the CI/CD pipeline automatically.

## Environment Variables

Setup the following variables in the CircleCI:
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

## The order of the run jobs in Pipeline

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
