# Airflow-Workflow
Airflow Workflow is a platform designed for beginners to easily set up Airflow and run dags. 


## Before you begin

Follow these steps to install the necessary tools.

    Install Docker Community Edition (CE) on your workstation. Depending on the OS, you may need to configure your Docker instance to use 4.00 GB of memory for all containers to run properly. Please refer to the Resources section if using Docker for Windows or Docker for Mac for more information.

    Install Docker Compose v1.27.0 and newer on your workstation.


## Steps

1. Clone repo to local https://github.com/nawinto99/airflow-workflow.git
2. `cd airflow-workflow`
3. `mkdir -p ./logs ./plugins`
4. `SET AIRFLOW_UID=5000`
5. `SET AIRFLOW_GID=0`
6. To deploy Airflow on Docker Compose, fetch `docker-compose.yaml`
7. `docker-compose up airflow-init`
8. `docker-compose up`
9. The webserver available at: `http://localhost:8080`. The default account has the login `airflow` and the password `airflow`


## The docker-compose.yaml contains several service definitions:
- airflow-scheduler - The scheduler monitors all tasks and DAGs, then triggers the task instances once their dependencies are complete.
- airflow-webserver - The webserver available at http://localhost:8080.
- airflow-worker - The worker that executes the tasks given by the scheduler.
- airflow-init - The initialization service.
- flower - The flower app for monitoring the environment. It is available at http://localhost:5555.
- postgres - The database.
- redis - The redis - broker that forwards messages from scheduler to worker.

## Cleaning up
- To stop and delete containers, delete volumes with database data and download images, run:

  `docker-compose down --volumes --rmi all`

