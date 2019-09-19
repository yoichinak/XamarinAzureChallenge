# Xamarin Azure Challenge

Welcome to the Xamarin Azure Challenge.

The goal is to create an serverless [Azure Function](https://azure.microsoft.com/services/functions?WT.mc_id=xamarinazurechallenge-github-bramin) and connect it to a [Xamarin](https://dotnet.microsoft.com/apps/xamarin?WT.mc_id=xamarinazurechallenge-github-bramin) mobile app.

### Challenge Objectives

1. Create and publish a serverless [Azure Function](https://azure.microsoft.com/services/functions?WT.mc_id=xamarinazurechallenge-github-bramin)
2. Add the Azure Function url to the [Xamarin.Forms](https://docs.microsoft.com/xamarin/xamarin-forms?WT.mc_id=xamarinazurechallenge-github-bramin) application
3. Submit your entry from the Xamarin.Forms application to your Azure Function

## Task 0: Prerequisites

1. Create Azure Suscription
    * If you do not currently have an Azure subscription, sign up for a [free Azure account](https://azure.microsoft.com/free?WT.mc_id=xamarinazurechallenge-github-bramin) that includes a $200 Azure Credit
2. Install Visual Studio + Xamarin Tools
    * On PC, [follow these steps to install Visual Studio with Xamarin](https://docs.microsoft.com/xamarin/get-started/installation/windows?WT.mc_id=xamarinazurechallenge-github-bramin)
    * On Mac, [follow these steps to install Visual Studio for Mac with Xamarin](https://docs.microsoft.com/visualstudio/mac/installation?view=vsmac-2019&WT.mc_id=xamarinazurechallenge-github-bramin)


## Task 1: Create an Azure Function resource in Azure

### 1. Retrieve Source Code

We have two options to retrieve the code for the Xamarin Azure Challenge:
* Clone the repository
* Download the source code

#### 1a. Clone the repository

To [clone](https://git-scm.com/docs/git-clone) this repository, run this command in your favorite terminal:

``` bash
git clone https://github.com/xamarin/XamarinAzureChallenge.git
```

#### 1b. Download Source Code

To download the source clode, click this link: https://github.com/xamarin/XamarinAzureChallenge/archive/master.zip

### 2. Create Azure Function

After cloning the repository, we have 3 options to create and publish the Azure Function:

1. Use [Visual Studio to create the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio?WT.mc_id=xamarinazurechallenge-github-bramin)
2. Use [Azure Portal to create the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-function-app-portal)
3. Use [Azure CLI to create the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli?WT.mc_id=xamarinazurechallenge-github-bramin)


#### 2a. Use Visual Studio

> Prior to this step, ensure you have a valid Azure Subscription and are [logged into Visual Studio using your Azure account](https://docs.microsoft.com/visualstudio/ide/signing-in-to-visual-studio?view=vs-2019&WT.mc_id=xamarinazurechallenge-github-bramin#how-to-sign-in-to-visual-studio)

1. In Visual Studio go to the Solution Explorer and select XamarinAzureChallenge.Functions project.

![publish](https://user-images.githubusercontent.com/13558917/57552330-690b3280-7320-11e9-97e8-18531a238b5b.png)

 2. On the project, right-click and select **Publish**.

![start](https://user-images.githubusercontent.com/13558917/57552303-53960880-7320-11e9-958d-e44cf122bf6a.png)

3. In the Publish window, select **Azure Function App** > **Create New** > **Create Profile**

![start](https://user-images.githubusercontent.com/13558917/57551949-3280e800-731f-11e9-9d19-4f17b6a9c967.png)

4. In the **App Service Create New** window, input the following data:

- **Name**: XamarinAzureChallenge-[Your Last Name]
    - Note: The app name must be unique because it is used for the Azure Functions Url. This is why we'll append our Last Name.
- **Subscription**: [Select your Azure subscription]
- **Resource Group**: 
    - **New...**
        -  **New resource group name**: XamarinAzureChallenge
- **Location**: [Select the Azure Datacenter closest to you]
- **Azure Storage**: 
    - **New...**
        -  **Account name**: xamarinazurechallenge[Your Last Name]
            - Note: The Azure Storage Name must be unique which is why we append our Last Name.
        - **Location**: [Select the Azure Data Center closest to you]
        - **Account type**: Standard - Locally Rendundant Storage

![start](https://user-images.githubusercontent.com/13558917/57551835-e5047b00-731e-11e9-8feb-26a586e6f3af.png)

4. In the **App Service Create New** window, click on **Create**

5. Stand by while the Azure Function resource is created in Azure


#### 2b. Use Azure Portal

1. In your browser, naviagte to the [Azure Portal](http://portal.azure.com?WT.mc_id=xamarinazurechallenge-github-bramin) 

2. In the **Azure Portal**, on the left-hand menu, click **+ Create a resource**

> Note: If the toolbar is collapsed, it will be shown as a green **+**

![Create new resource](https://user-images.githubusercontent.com/13558917/64928580-1a3e3f80-d7cf-11e9-84e7-01ecf565de81.png)

3. In the **New** dashboard, in the search bar, type **functions**

4. In the **New** dashboard, in the search bar tap the **[Enter]** key

![Marketplace Search Functions](https://user-images.githubusercontent.com/13558917/64928584-1d393000-d7cf-11e9-852d-fad28d656ae3.png)

5. On the **Marketplace** search results, click **Function App**

![Function App](https://user-images.githubusercontent.com/13558917/64928586-1e6a5d00-d7cf-11e9-9334-08eabee77898.png)

6. On the **Marketplace > Function App** window, select **Create** 

![Create Functions App](https://user-images.githubusercontent.com/13558917/64928581-1ad6d600-d7cf-11e9-9805-829a665e5d88.png)

7. On the **Function App Create** page, enter the following information:

- **App name**: XamarinAzureChallenge-[Your Name]
    - Note: The app name must be unique because it is used for the Azure Functions Url. This is why we'll append our name.
    - In this example, I'm using "XamarinAzureChallenge-Brandon"
- **Subscription**: [Select your Azure Subscription]
- **Resource Group**:
    - [x] **Create new**
    - XamarinAzureChallenge
- **OS**: Windows
- **Hosting Plan**: Consumption Plan
- **Location**: [Select the Azure Datacenter closest to you]
- **Runtime Stack**: .NET Core
- **Storage**:
    - [x] **Create new**
    - xamarinazure[Your Name]
        - Note: The Storage name must be unique, which is why we append our name
        - In this example, I'm using "xamarinazurebrandon"

7. On the **Function App Create** page, Click **Create**

![Enter Functions App Data](https://user-images.githubusercontent.com/13558917/64928583-1ca09980-d7cf-11e9-83ad-df824d193d66.png)

8. On the **Azure Portal**, at the top of the page, tap the notifications button which is shaped like a bell

9. In the **Notifications** window, ensure it says **Deployment in progress...**

![Deployment in progress](https://user-images.githubusercontent.com/13558917/64928694-ce4cc400-d7e9-11e9-8b87-c57a5695d6b2.png)

10. Stand by until the deployment has suceeded

![Deployment Succeeded](https://user-images.githubusercontent.com/13558917/64928721-3b605980-d7ea-11e9-9996-89f7d0ff8ef1.png)

#### 2c. Use Azure CLI

> As a prerequisite, you must install [Azure Core Tools version 2.x](https://docs.microsoft.com/azure/azure-functions/functions-run-local?WT.mc_id=xamarinazurechallenge-github-bramin#v2) and [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?WT.mc_id=xamarinazurechallenge-github-bramin)) or [Azure Cloud Shell](https://shell.azure.com/bash?WT.mc_id=xamarinazurechallenge-github-bramin).

1. Open the terminal
  - [How to open the macOS Terminal](https://macpaw.com/how-to/use-terminal-on-mac)
  - [How to open the Windows Terminal](https://www.quora.com/How-do-I-open-terminal-in-windows)

2. In the terminal, enter the following command to login into Azure CLI:

```bash
az login
```

3. In the terminal, enter the following command to create a new Azure Resource Group:

```bash
az group create --name XamarinAzureChallenge --location westeurope
```

> **Note:** If you have more than one subscription you will need to especify the subscription where the resource groups will be created with `--subscription [your Azure Subscription ID]`
> - [How to find your Azure Subscription ID ](https://blogs.msdn.microsoft.com/mschray/2016/03/18/getting-your-azure-subscription-guid-new-portal?WT.mc_id=xamarinazurechallenge-github-bramin)

4. In the terminal, enter the following command to create a new Azure Storage Account:

```bash
az storage account create --name xamarinazure[Your Name] --location westeurope --resource-group XamarinAzureChallenge --sku Standard_LRS --subscription [Your Azure Subscription ID]
```
> Note: The storage name must be unique, which is why we append our name

5. In the terminal, enter the following command to navigate to the project folder `XamarinAzureChallenge.Functions` project folder.

```bash
cd [Your Path to XamarinAzureChallengeSource Code]\src\XamarinAzureChallenge\XamarinAzureChallenge.Functions
```

6. In the terminal, enter the following command to create a function app:

```bash
az functionapp create --resource-group XamarinAzureChallenge --consumption-plan-location westeurope --name XamarinAzureChallenge-[Your Name] --storage-account  xamarinazure[Your Name] --runtime dotnet --subscription [Your Azure Subscription ID]
```

> **Note:** The Azure Function name must be unique, which is why we append our name

## 3: Publish Code to Azure Function

After creating the Azure Function, it's time to publish our code to the cloud. For this, we have two options:

1. Use [Visual Studio on PC to publish the Azure Function](https://blogs.msdn.microsoft.com/benjaminperkins/2018/04/05/deploy-an-azure-function-created-from-visual-studio?WT.mc_id=xamarinazurechallenge-github-bramin).
2. Use [Visual Studio for Mac to publish the Azure Function](https://docs.microsoft.com/visualstudio/mac/publish-app-svc?WT.mc_id=xamarinazurechallenge-github-bramin)
3. Use [Azure CLI to publish the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli?WT.mc_id=xamarinazurechallenge-github-bramin)


### 3a. Use Visual Studio on PC

1. In Visual Studio on PC, open `XamarinAzureChallenge.sln`

2. In to Visual Studio, in the Solution Explorer, right-click on the `XamarinAzureChallenge.Functions` project

2. In the right-click menu, select in **Publish**

![publish](https://user-images.githubusercontent.com/13558917/65265720-82e33000-dadf-11e9-9a23-d910ac159790.png)

4. In the **Pick a publish target** window, select the following: 

- **Azure Functions Consumption Plan**
- [x] **Create New**

5. In the **Pick a publish target** window, select **Publish**

![Pick a publish target](https://user-images.githubusercontent.com/13558917/65265726-84145d00-dadf-11e9-9c14-716aaf2e3f18.png)

# TODO

6. In the **Create New** window, enter the following information:
- **Name:** XamarinAzureChallenge-[Your Name]
    -  **Note:** The Azure Function name must be unique, which is why we append our name
- **Subscription:** [Select your Azure Subscription]
- **Resource Group**
    - **New**
        - **New resource group name**: XamarinAzureChallenge
        - **OK**
- **Location:** [Select the Azure Data Center Closest To You]
- **Azure Storage**
    - **New**
        - **Account Name:** xamarinazure[Your Name]
            -  **Note:** The Azure Storage name must be unique, which is why we append our name
        - **Location:** [Select the Azure Data Center Closest To You]
        - **Account type:** Standard - Locally Redundant Storage
        - **OK**

7. In the **Create New** window, click **Create** 

![Create New App Service](https://user-images.githubusercontent.com/13558917/65271517-52a18e80-daeb-11e9-8854-972bce47134e.png)

8. Standby while Visual Studio publishes our code to our Azure Function

![Deploying](https://user-images.githubusercontent.com/13558917/65271519-533a2500-daeb-11e9-9a54-3a4b6afad613.png)

### 3c. Use Visual Studio for Mac

1. In Visual Studio for Mac, open `XamarinAzureChallenge.sln`

2. 

### 3c. Use Azure CLI

1. Open the terminal
  - [How to open the macOS Terminal](https://macpaw.com/how-to/use-terminal-on-mac)
  - [How to open the Windows Terminal](https://www.quora.com/How-do-I-open-terminal-in-windows)


2. In the terminal, enter the following command to navigate to the project folder `XamarinAzureChallenge.Functions` project folder.

```bash
cd [Your Path to XamarinAzureChallengeSource Code]\src\XamarinAzureChallenge\XamarinAzureChallenge.Functions
```

3.  In the terminal, enter the following command to publish our code our Azure Function:

```bash
func azure functionapp publish XamarinAzureChallenge-[Your Name]
```


## Task 2: Configuring the Xamarin App

### Retrieve Azure Function URL

After publishing our Azure Function, we are ready to configure our Xamarin app with the Azure Function URL.

1. In your browser, naviagte to the [Azure Portal](http://portal.azure.com?WT.mc_id=xamarinazurechallenge-github-bramin) 

# TODO

2. Go the Azure Portal and navigate to your Azure Function App.

2. Open the list of Functions and select SubmitChallengeFunction. On the right panel, go to Get function URL.

![AFEndpoint](https://user-images.githubusercontent.com/13558917/57551436-e97c6400-731d-11e9-8ac7-eb8ae884c69e.png)

3. Copy the URL.

![AFEndpoint2](https://user-images.githubusercontent.com/13558917/57551471-f8631680-731d-11e9-9e39-8b7f50f56534.png)

4. Open the solution *XamarinAzureChallenge.sln* and go to *UserDetailViewModel* class and paste the url in *Endpoint* variable:

![ViewModel](https://blobstoragesampleapp.blob.core.windows.net/photos/BaseViewModel.png)


## Task 3: Goal of this challenge

As you know, this code contains errors. Please find them and fix them to pass this challenge!

**Click [here](/doc/solution.md) to get the solution.**

## Task 4: Submit your information through Xamarin Application 

The next step is to run the Xamarin Application and fill the form with your information. If you followed all the steps, your personal information will be sent to the Azure Function. The Azure Function will send to our internal API the data to participate in the challenge. 

You can run the app in local using an emulator. You can find the instructions [here](https://docs.microsoft.com/xamarin/android/deploy-test/debugging/debug-on-emulator?tabs=windows&WT.mc_id=xamarinazurechallenge-github-bramin).

In addition, you can run the app in a physical device. To setting up and configure your device you can follow [these instrucions](https://docs.microsoft.com/xamarin/android/deploy-test/debugging/debug-on-device?tabs=windows&WT.mc_id=xamarinazurechallenge-github-bramin)


## Next Steps

Please, read the Terms and Conditions of this challenge to know more about the next steps. 

## Report an issue

If you found an issue with this challenge, please open an issue in GitHub. 

## Additional Resources

If you are interested in learning more about this topic, you can refer to the following resources:

* [Azure Function Documentation](https://docs.microsoft.com/azure/azure-functions?WT.mc_id=xamarinazurechallenge-github-bramin)
* [Xamarin Documentation](https://docs.microsoft.com/xamarin?WT.mc_id=xamarinazurechallenge-github-bramin)
* [Azure Samples + Xamarin](https://github.com/Azure-Samples?utf8=%E2%9C%93&q=Xamarin&type=&language=&WT.mc_id=xamarinazurechallenge-github-bramin)
