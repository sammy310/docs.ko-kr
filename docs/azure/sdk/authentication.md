---
title: .NET용 Azure 라이브러리를 사용하여 인증
description: .NET용 Azure 라이브러리에 대한 인증
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: f6af813cd1423be8784b769b272756b2c8258392
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607872"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="172d5-103">.NET용 Azure 라이브러리를 사용하여 인증</span><span class="sxs-lookup"><span data-stu-id="172d5-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="172d5-104">연결 문자열을 사용하여 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="172d5-104">Connect to services with connection strings</span></span>

<span data-ttu-id="172d5-105">대부분의 Azure 서비스 라이브러리에는 인증을 위한 연결 문자열 또는 보안 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="172d5-106">예를 들어 SQL Database에서는 표준 SQL 연결 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-106">For example, SQL Database uses a standard SQL connection string:</span></span>

```csharp
var builder = new SqlConnectionStringBuilder();
builder.DataSource = "example.database.windows.net";
builder.InitialCatalog = "MyDatabase";
builder.UserID = "sampleuser@example"; // Format user ID as "user@server"
builder.Password = password;
builder.Encrypt = true;
builder.TrustServerCertificate = true;

using (var conn = new SqlConnection(builder.ConnectionString))
{
    conn.Open();
    // Do things with the connection...
    // ...
}
```

<span data-ttu-id="172d5-107">Azure Storage에서는 스토리지 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="172d5-108">서비스 연결 문자열은 [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues)와 같은 다른 Azure 서비스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-108">Service connection strings are used in other Azure services like [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="172d5-109">Azure Portal, CLI 또는 PowerShell을 사용하여 이러한 문자열을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-109">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="172d5-110">또한 .NET용 Azure 관리 라이브러리를 사용하여 코드에서 연결 문자열을 작성하는 리소스를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-110">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="172d5-111">이 코드 조각에서는 관리 라이브러리를 사용하여 스토리지 계정 연결 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-111">This snippet uses the management libraries to create a storage account connection string:</span></span>

```csharp
// Get a storage account
var storage = azure.StorageAccounts.GetByResourceGroup("myResourceGroup", "myStorageAccount");

// Extract the keys
var storageKeys = storage.GetKeys();

// Build the connection string
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storage.Name
        + ";AccountKey=" + storageKeys[0].Value
        + ";EndpointSuffix=core.windows.net";

// Connect
var account = CloudStorageAccount.Parse(storageConnectionString);

// Do things with the account here...
```

<span data-ttu-id="172d5-112">다른 라이브러리에서는 권한이 부여된 자격 증명을 사용하여 애플리케이션 실행 권한을 부여하는 [서비스 사용자](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)를 통해 애플리케이션을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-112">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="172d5-113">이 구성은 아래에서 나열하는 관리 라이브러리에 대한 개체 기반 인증 단계와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-113">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="172d5-114">.NET 인증에 대한 Azure 관리 라이브러리</span><span class="sxs-lookup"><span data-stu-id="172d5-114">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="172d5-115">이제 서비스 사용자를 만들었으므로 두 가지 옵션을 사용하여 리소스를 만들고 관리할 서비스 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-115">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="172d5-116">두 옵션에서는 모두 다음과 같은 NuGet 패키지를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-116">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="172d5-117">토큰 자격 증명을 사용하여 인증</span><span class="sxs-lookup"><span data-stu-id="172d5-117">Authenticate with token credentials</span></span>

<span data-ttu-id="172d5-118">첫 번째 방법은 코드에 토큰 자격 증명 개체를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-118">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="172d5-119">구성 파일, 레지스트리 또는 Azure Key Vault에 자격 증명을 안전하게 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-119">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="172d5-120">서비스 주체를 만들 때 JSON 출력에서 *clientId*, *clientSecret*, 및 *tenantId* 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-120">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="172d5-121">그런 다음 `Azure` 진입점 개체를 만들어 API 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-121">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="172d5-122">파일 기반 인증</span><span class="sxs-lookup"><span data-stu-id="172d5-122">File-based authentication</span></span>

<span data-ttu-id="172d5-123">파일 기반 인증을 사용하면 서비스 사용자 자격 증명을 일반 텍스트 파일에 저장하고 파일 시스템 내에서 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-123">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="172d5-124">파일의 내용을 읽고 `Azure` 끝점 개체를 만들어 API 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="172d5-124">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
