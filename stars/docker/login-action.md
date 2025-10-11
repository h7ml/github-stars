---
project: login-action
stars: 1281
description: GitHub Action to login against a Docker registry
url: https://github.com/docker/login-action
---

About
-----

GitHub Action to login against a Docker registry.

* * *

-   Usage
    -   Docker Hub
    -   GitHub Container Registry
    -   GitLab
    -   Azure Container Registry (ACR)
    -   Google Container Registry (GCR)
    -   Google Artifact Registry (GAR)
    -   AWS Elastic Container Registry (ECR)
    -   AWS Public Elastic Container Registry (ECR)
    -   OCI Oracle Cloud Infrastructure Registry (OCIR)
    -   Quay.io
    -   DigitalOcean
    -   Authenticate to multiple registries
-   Customizing
    -   inputs
-   Contributing

Usage
-----

### Docker Hub

When authenticating to Docker Hub with GitHub Actions, use a personal access token. Don't use your account password.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ vars.DOCKERHUB\_USERNAME }}
          password: ${{ secrets.DOCKERHUB\_TOKEN }}

### GitHub Container Registry

To authenticate to the GitHub Container Registry, use the `GITHUB_TOKEN` secret.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to GitHub Container Registry
        uses: docker/login-action@v3
        with:
          registry: ghcr.io
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB\_TOKEN }}

You may need to manage write and read access of GitHub Actions for repositories in the container settings.

You can also use a personal access token (PAT) with the appropriate scopes.

### GitLab

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to GitLab
        uses: docker/login-action@v3
        with:
          registry: registry.gitlab.com
          username: ${{ vars.GITLAB\_USERNAME }}
          password: ${{ secrets.GITLAB\_PASSWORD }}

If you have Two-Factor Authentication enabled, use a Personal Access Token instead of a password.

### Azure Container Registry (ACR)

Create a service principal with access to your container registry through the Azure CLI and take note of the generated service principal's ID (also called _client ID_) and password (also called _client secret_).

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to ACR
        uses: docker/login-action@v3
        with:
          registry: <registry-name>.azurecr.io
          username: ${{ vars.AZURE\_CLIENT\_ID }}
          password: ${{ secrets.AZURE\_CLIENT\_SECRET }}

> Replace `<registry-name>` with the name of your registry.

### Google Container Registry (GCR)

> Google Artifact Registry is the evolution of Google Container Registry. As a fully-managed service with support for both container images and non-container artifacts. If you currently use Google Container Registry, use the information on this page to learn about transitioning to Google Artifact Registry.

You can authenticate with workload identity federation or a service account.

#### Workload identity federation

Configure the workload identity federation for GitHub Actions in Google Cloud, see here. Your service account must have permission to push to GCR. Use the `google-github-actions/auth` action to authenticate using workload identity as shown in the following example:

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
    -
      name: Authenticate to Google Cloud
      id: auth
      uses: google-github-actions/auth@v1
      with:
        token\_format: access\_token
        workload\_identity\_provider: <workload\_identity\_provider>
        service\_account: <service\_account>
    -
      name: Login to GCR
      uses: docker/login-action@v3
      with:
        registry: gcr.io
        username: oauth2accesstoken
        password: ${{ steps.auth.outputs.access\_token }}

> Replace `<workload_identity_provider>` with configured workload identity provider. For steps to configure, see here.

> Replace `<service_account>` with configured service account in workload identity provider which has access to push to GCR

#### Service account based authentication

Use a service account with permission to push to GCR and configure access control. Download the key for the service account as a JSON file. Save the contents of the file as a secret named `GCR_JSON_KEY` in your GitHub repository. Set the username to `_json_key`.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to GCR
        uses: docker/login-action@v3
        with:
          registry: gcr.io
          username: \_json\_key
          password: ${{ secrets.GCR\_JSON\_KEY }}

### Google Artifact Registry (GAR)

You can authenticate with workload identity federation or a service account.

#### Workload identity federation

Your service account must have permission to push to GAR. Use the `google-github-actions/auth` action to authenticate using workload identity as shown in the following example:

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Authenticate to Google Cloud
        id: auth
        uses: google-github-actions/auth@v1
        with:
          token\_format: access\_token
          workload\_identity\_provider: <workload\_identity\_provider>
          service\_account: <service\_account>
      -
        name: Login to GAR
        uses: docker/login-action@v3
        with:
          registry: <location>-docker.pkg.dev
          username: oauth2accesstoken
          password: ${{ steps.auth.outputs.access\_token }}

> Replace `<workload_identity_provider>` with configured workload identity provider

> Replace `<service_account>` with configured service account in workload identity provider which has access to push to GCR

> Replace `<location>` with the regional or multi-regional location of the repository where the image is stored.

#### Service account based authentication

Use a service account with permission to push to GAR and configure access control. Download the key for the service account as a JSON file. Save the contents of the file as a secret named `GAR_JSON_KEY` in your GitHub repository. Set the username to `_json_key`, or `_json_key_base64` if you use a base64-encoded key.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to GAR
        uses: docker/login-action@v3
        with:
          registry: <location>-docker.pkg.dev
          username: \_json\_key
          password: ${{ secrets.GAR\_JSON\_KEY }}

> Replace `<location>` with the regional or multi-regional location of the repository where the image is stored.

### AWS Elastic Container Registry (ECR)

Use an IAM user with the ability to push to ECR with `AmazonEC2ContainerRegistryPowerUser` managed policy for example. Download the access keys and save them as `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` as secrets in your GitHub repo.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to ECR
        uses: docker/login-action@v3
        with:
          registry: <aws-account-number>.dkr.ecr.<region>.amazonaws.com
          username: ${{ vars.AWS\_ACCESS\_KEY\_ID }}
          password: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}

If you need to log in to Amazon ECR registries associated with other accounts, you can use the `AWS_ACCOUNT_IDS` environment variable:

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to ECR
        uses: docker/login-action@v3
        with:
          registry: <aws-account-number>.dkr.ecr.<region>.amazonaws.com
          username: ${{ vars.AWS\_ACCESS\_KEY\_ID }}
          password: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}
        env:
          AWS\_ACCOUNT\_IDS: 012345678910,023456789012

> Only available with AWS CLI version 1

You can also use the Configure AWS Credentials action in combination with this action:

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v4
        with:
          aws-access-key-id: ${{ vars.AWS\_ACCESS\_KEY\_ID }}
          aws-secret-access-key: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}
          aws-region: <region>
      -
        name: Login to ECR
        uses: docker/login-action@v3
        with:
          registry: <aws-account-number>.dkr.ecr.<region>.amazonaws.com

> Replace `<aws-account-number>` and `<region>` with their respective values.

### AWS Public Elastic Container Registry (ECR)

Use an IAM user with permission to push to ECR Public, for example using managed policies. Download the access keys and save them as `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` secrets in your GitHub repository.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to Public ECR
        uses: docker/login-action@v3
        with:
          registry: public.ecr.aws
          username: ${{ vars.AWS\_ACCESS\_KEY\_ID }}
          password: ${{ secrets.AWS\_SECRET\_ACCESS\_KEY }}
        env:
          AWS\_REGION: <region>

> Replace `<region>` with its respective value (default `us-east-1`).

### OCI Oracle Cloud Infrastructure Registry (OCIR)

To push into OCIR in specific tenancy the username must be placed in format `<tenancy>/<username>` (in case of federated tenancy use the format `<tenancy-namespace>/oracleidentitycloudservice/<username>`).

For password create an auth token. Save username and token as a secrets in your GitHub repo.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to OCIR
        uses: docker/login-action@v3
        with:
          registry: <region>.ocir.io
          username: ${{ vars.OCI\_USERNAME }}
          password: ${{ secrets.OCI\_TOKEN }}

> Replace `<region>` with their respective values from availability regions

### Quay.io

Use a Robot account with permission to push to a Quay.io repository.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to Quay.io
        uses: docker/login-action@v3
        with:
          registry: quay.io
          username: ${{ vars.QUAY\_USERNAME }}
          password: ${{ secrets.QUAY\_ROBOT\_TOKEN }}

### DigitalOcean Container Registry

Use your DigitalOcean registered email address and an API access token to authenticate.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to DigitalOcean Container Registry
        uses: docker/login-action@v3
        with:
          registry: registry.digitalocean.com
          username: ${{ vars.DIGITALOCEAN\_USERNAME }}
          password: ${{ secrets.DIGITALOCEAN\_ACCESS\_TOKEN }}

### Authenticate to multiple registries

To authenticate against multiple registries, you can specify the login-action step multiple times in your workflow:

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ vars.DOCKERHUB\_USERNAME }}
          password: ${{ secrets.DOCKERHUB\_TOKEN }}
      -
        name: Login to GitHub Container Registry
        uses: docker/login-action@v3
        with:
          registry: ghcr.io
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB\_TOKEN }}

You can also use the `registry-auth` input for raw authentication to registries, defined as YAML objects. Each object can contain `registry`, `username`, `password` and `ecr` keys similar to current inputs:

Warning

We don't recommend using this method, it's better to use the action multiple times as shown above.

name: ci

on:
  push:
    branches: main

jobs:
  login:
    runs-on: ubuntu-latest
    steps:
      -
        name: Login to registries
        uses: docker/login-action@v3
        with:
          registry-auth: |
            - username: ${{ vars.DOCKERHUB\_USERNAME }}
              password: ${{ secrets.DOCKERHUB\_TOKEN }}
            - registry: ghcr.io
              username: ${{ github.actor }}
              password: ${{ secrets.GITHUB\_TOKEN }}

Customizing
-----------

### inputs

The following inputs can be used as `step.with` keys:

Name

Type

Default

Description

`registry`

String

`docker.io`

Server address of Docker registry. If not set then will default to Docker Hub

`username`

String

Username for authenticating to the Docker registry

`password`

String

Password or personal access token for authenticating the Docker registry

`ecr`

String

`auto`

Specifies whether the given registry is ECR (`auto`, `true` or `false`)

`logout`

Bool

`true`

Log out from the Docker registry at the end of a job

`registry-auth`

YAML

Raw authentication to registries, defined as YAML objects

Note

The `registry-auth` input is mutually exclusive with `registry`, `username`, `password` and `ecr` inputs.

Contributing
------------

Want to contribute? Awesome! You can find information about contributing to this project in the CONTRIBUTING.md
