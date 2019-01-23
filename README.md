# IBM Cloud App ID Postman Collection

This repo contains a Postman collection and environment configuration for invoking REST API of the IBM Coud App ID service. 

## Set-up

1. Clone the repo

2. Update `appid-production-us-south.postman_environment.json` with the following values:
    
    * IBMCLOUD_API_KEY - In order to consume App ID management API you'll need to have IBM Cloud IAM API key. The key can be obtained from either 
        * Creating service credentials in the App ID Dashboard. You will see `apikey` as one of the attributes of the generated credentials JSON object. 
        * Cloud IAM UI (https://cloud.ibm.com/iam#/serviceids). Create Service ID, assign ADMIN access policy to your App ID instance, generate API key.
        * IBM Cloud CLI (see the `ibmcloud iam api-key-create` command).

    * IBMCLOUD_IAM_SERVER_HOST - Preset to https://iam.cloud.ibm.com. There's no reason for you to change this. 

    * APPID_AUTH_SERVER_HOST - Preset to https://us-south.appid.cloud.ibm.com. You might need to change the region. Supported regions are `us-south`, `us-east`, `eu-gb`, `eu-de`, `au-syd`, `jp-tok`.

    * APPID_PROFILES_SERVER_HOST - Preset to https://us-south.appid.cloud.ibm.com. You might need to change the region. Supported regions are `us-south`, `us-east`, `eu-gb`, `eu-de`, `au-syd`, `jp-tok`.

    * APPID_MANAGEMENT_SERVER_HOST - Preset to https://us-south.appid.cloud.ibm.com. You might need to change the region. Supported regions are `us-south`, `us-east`, `eu-gb`, `eu-de`, `au-syd`, `jp-tok`.

    * APPID_TENANT_ID - The tenant ID, also known as instance ID, of your App ID instance. Use existing, or Create a new Application in the App ID dashboard to see your tenant ID. 

    * APPID_CLIENT_ID - The client ID of your Application. Use existing, or Create a new Application in the App ID dashboard to see your client ID. 

    * APPID_SECRET - The secret of your Application. Use existing, or Create a new Application in the App ID dashboard to see your secret. 

3. Open Postman and import `appid-production-us-south.postman_environment.json` and `app-id.postman_colletion.json`. 

4. Make sure `appid-production-us-south` environment is selected

## Usage

Use the APIs according to your scenarios. Note that many values are taken from the environment to simplify API invocation workflows. E.g. once you make the `App ID -> Cloud IAM -> Get Cloud IAM Token` request, the retrieved token will be saved in the envornment and used for all subsequent requests to management API automatically. Same goes for many other workflows. You can see the `Test` section of relevant requests to see the logic. 

Happy App IDing!

