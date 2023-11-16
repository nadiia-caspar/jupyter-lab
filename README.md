# Jupyter Notebook Environment

## Configure Jupyter environment with variables from `.env` file

Specify following environmental variables in `.env` file:

```shell
AWS_ACCESS_KEY_ID="<YOUR_ACCESS_KEY>"
AWS_SECRET_ACCESS_KEY="<AWS_SECRET_ACCESS_KEY>"
AWS_DEFAULT_REGION="eu-central-1"
AWS_REGION="eu-central-1"
AWS_ROLE_ARN="arn:aws:iam::<AWS_ACCOUNT_ID>:role/<YOUR_ASSUME_ROLE>"
AWS_ROLE_SESSION_NAME="<ANY_SESSION_NAME>"
MFA_SERIAL_NUMBER="arn:aws:iam::<AWS_SECUTIRY_ACCOUNT_ID>:mfa/<YOUR_MFA_NAME>"
```

## Run Jupyter Notebook with custom image

Build image with Dockerfile:

```shell
DOCKER_BUILDKIT=1 docker build \
    --progress=plain \
    --tag "jupyter_base_notebook:v0.0.1" .
```

Run Jupyter Notebook with custom image:

```shell
docker run --rm -p 8888:8888 -v "$PWD/work":/home/jovyan/work jupyter_base_notebook:v0.0.1
```

## Run with docker-compose

<https://dev.to/barbara/run-spark-locally-with-docker-4com>:

```shell
docker-compose up
docker-compose up --force-recreate --build # with force re-build
```
