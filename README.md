### Overview

A react app, configured with CI/CD. Using,

- `Docker`
- `Travis CI`
- `AWS Beanstalk`

### Run In Development Machine

---

- Run `docker-compose up --build`

### CI/CD for Production

---

- Update `.travis.yml` as followings,

  - `provider`, should be `elasticbeanstalk`, already configured and heavy lifting by the `Travis CI`
  - `region`, Where the `AWS Elastic Beanstalk` is being created
  - `app`, our `Elastic Beanstalk` app name
  - `env`, our `Elastic Beanstalk` environment name
  - `bucket_name`, automatically generated bucket name by the `Elastic Beanstalk`
  - `bucket_path`, same as the `app` name
  - `on -> branch`, on which branch code changes, we should re-deploy the code base
  - `credentials`, to get the credentials to access `Elastic Beanstalk` by `Travis CI`, we have to create a new IAM user with full programmatic access to `Elastic Beanstalk`. For security purpose, we will use the `Travis CI` environment variables to store our aws access key and secret.
