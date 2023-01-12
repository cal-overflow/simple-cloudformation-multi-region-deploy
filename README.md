# Basic Cloudformation stack deployed to multiple regions
An example GitHub actions workflow for provisioning a Cloudformation stack in multiple AWS regions.


### Authenticating GitHub with AWS
You can configure GitHub actions to deploy the stack whenever changes are made to the `main` branch. \
Although the workflow is already written, there are other steps required to have this deploy complete in a desired AWS account.

### 1. Create an IAM Role
In your AWS Account, create a new IAM Role with the permissions you deem necessary. This must include [Cloudformation](https://aws.amazon.com/cloudformation/). Refer to GitHub's docs for [Configuring OpenID Connect in AWS](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services) for guidance.


### 2. Add essential secrets to your GitHub repository.

Add the following secrets via **Repository settings** > **Secrets** > **Actions**.

  - `IAM_ROLE_ARN` containing your IAM Role ARN from step 1.

### 5. Trigger a deploy
To trigger a deploy, simply commit changes to the `main` branch.
