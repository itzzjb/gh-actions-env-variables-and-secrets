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

Action secretes will be available for all workflows that will be executed in this repository.
