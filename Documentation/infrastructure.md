## Archetichture Overview

![Alt text](/Screenshots/Diagram.PNG?raw=true "Title")

## Services in use:

This project relies on AWS for hosting the whole application.

1. RDS → for hosting DB
2. EB → For the backend and setting up the environment
3. S3 → for hostin the FE files

## infrastructure explained:

1. The client will visit the website hosted on S3 bucket. Then S3 wil send the files containing the FE.
2. The application on S3 will send a request containg any data requested by the user and the user sign in info, EB should send back a JWT and the requested files if login info is correct
3. The backend on EB will contact back and forth with the postgreSQL DB hosted on RDS to save new users or match login info
