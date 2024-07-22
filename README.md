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
