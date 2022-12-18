# web-api-example

This project contains code for an example RESTful web API with create, read, update, and delete (CRUD) operations and data persistence. It is intended to serve as a foundation for developing more complex database interfaces in Python, and it can be run locally or deployed with Google App Engine. 

The sample data models represent fictional people and Covid-19 test results, which have a one-to-many relationship. Each person's Covid status is updated automatically based on their most recent test result.

Technologies:
-	PostgreSQL for RDBMS
-	Google App Engine and Google Cloud SQL for cloud deployment
-	Flask web framework
-	SQLAlchemy for ORM
-	marshmallow for data object serialization
-	Swagger for API design and documentation (OpenAPI Specification)

The app requires a PostgreSQL database connection to run. To set this up, add a file to the base directory called "postgres_uri.txt" containing the URI for the database that you would like to use.

For a local connection, the URI will look something like:

postgresql://<db_user>:<db_password>@localhost/<db_name>

For a Unix socket connection to Cloud SQL, the URI will look something like:

postgresql+psycopg2://<db_user>:<db_password>@<db_name>?host=<instance_unix_socket>/.s.PGSQL.5432

(NOTE: the query parameter for the socket, in this case "host," may vary depending on the driver. See the documentation at https://cloud.google.com/sql/docs/postgres/connect-overview for more information.)

Once the URI is configured, the app can be tested locally by running "main.py". When the app is run, Swagger will automatically build documentation and a user interface, which can be used to explore and test the API:
