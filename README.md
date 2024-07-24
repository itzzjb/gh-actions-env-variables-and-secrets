# Environment Variables

There might be dynamic values that we need to change. Some values like database name and password may need to change depending on the environment that we are in.

> Testing database for testing environment and production database for production environment, likewise.

So, we store those type of data as environment variables and give the values in the application run-time.

Normally, we define environment variables in all caps letters.

ex:

- MONGODB_USERNAME
- MONGODB_PASSWORD
- MONGODB_DB_NAME

In Github Actions we would need to provide values to those environment variables in our workflow.

# Secrets

Some environment variables like credentials (username and password) are not supposed to be exposed. Because everyone that access to the remote repository will be able to see those credentials (from Github Repository).

That's why we need to store those environment variables as Secrets. These are also environment variables, but stored such that no one can access them and no one can see them.

In Github there are couple of ways to store secrets

- If you are in a organization account we can store secretes organization level
- Or we can add secrets in repository level as well (repository -> settings -> secrets -> actions -> repository secrets)

> Repository secretes will be available for all workflows that will be executed in this repository.

Sometimes we may need to use different values for the same environment variable name in different jobs that related to different environments.

For example the username and the password for the database may change depending on the stage we are in. Because for test job
we are using a separate testing database and for deploy we are using a separate production database.

So, we can define environments in Github, and have configurations (like secrets) for them.

To link to the environments to the job we need to use the `environments:` key.

Additionally to adding secrets to specific environments using Environment

- We can add specific reviewers to environments (without approval the workflow won't start)
- We can also add a wait timer (all the jobs pauses for specific time before it actually starts)
- And we can also add branch protection rules for the environment
