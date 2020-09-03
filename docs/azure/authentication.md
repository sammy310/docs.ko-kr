---
title: .NET용 Azure 라이브러리의 인증 이해
description: .NET용 Azure SDK를 사용하여 인증하는 다양한 방법을 설명합니다.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: bc2fce919d88a528f21df9f561cbe33e1119762a
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811381"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="06f39-103">.NET용 Azure SDK를 사용하여 인증</span><span class="sxs-lookup"><span data-stu-id="06f39-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="06f39-104">권장: Azure.Identity</span><span class="sxs-lookup"><span data-stu-id="06f39-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="06f39-105">.NET용 Azure SDK의 최신 패키지는 인증하는 데 일반적인 인증 패키지인 `Azure.Identity`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="06f39-106">이 문서의 뒷부분에 설명된 다른 인증 메커니즘보다는 `Azure.Identity`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="06f39-107">`Azure.Identity`에서 제공하는 자격 증명을 지원하는 패키지는 `Azure.Core`를 기준으로 빌드되며 *Azure*로 시작하는 패키지 식별자를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-107">Packages supporting the credentials provided by `Azure.Identity` are built on top of `Azure.Core` and have package identifiers starting with *Azure*.</span></span> <span data-ttu-id="06f39-108">`Azure.Core`를 사용하는 패키지의 인벤토리에 대해서는 [패키지 목록을 참조하세요](packages.md).</span><span class="sxs-lookup"><span data-stu-id="06f39-108">[See the package list](packages.md) for an inventory of packages that use `Azure.Core`.</span></span>

<span data-ttu-id="06f39-109">프로젝트에서 `Azure.Identity`를 사용하는 방법에 관한 자세한 내용은 [.NET용 Azure ID 클라이언트](/dotnet/api/overview/azure/identity-readme) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06f39-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="06f39-110">Azure ID를 사용하여 Azure 리소스를 관리 및 액세스하는 방법의 예제는 [Azure ID, 리소스 관리 및 Storage 샘플](/samples/dotnet/samples/azure-identity-resource-management-storage/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06f39-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="06f39-111">Azure.Identity를 지원하지 않는 라이브러리를 사용하여 인증하려면 이 항목의 나머지 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06f39-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="06f39-112">Azure 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="06f39-112">Access Azure resources</span></span>

<span data-ttu-id="06f39-113">Key Vault에서 비밀을 검색하거나 Storage에 BLOB을 저장하는 등 Azure 리소스와 상호 작용하려면 대부분의 Azure 서비스 라이브러리에 인증을 위한 연결 문자열 또는 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="06f39-114">예를 들어 SQL Database는 [표준 SQL 연결 문자열](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-114">For example, SQL Database uses a [standard SQL connection string](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="06f39-115">서비스 연결 문자열은 [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues)와 같은 다른 Azure 서비스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="06f39-116">Azure Portal, CLI 또는 PowerShell을 사용하여 이러한 문자열을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="06f39-117">또한 .NET용 Azure 관리 라이브러리를 사용하여 코드에서 연결 문자열을 작성하는 리소스를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="06f39-118">연결 문자열을 사용하는 방법은 제품별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="06f39-119">[Azure 제품에 관한 설명서를 참조하세요](/azure/?product=featured).</span><span class="sxs-lookup"><span data-stu-id="06f39-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="06f39-120">Azure 리소스 관리</span><span class="sxs-lookup"><span data-stu-id="06f39-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="06f39-121">이제 서비스 사용자를 만들었으므로 두 가지 옵션을 사용하여 리소스를 만들고 관리할 서비스 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="06f39-122">두 옵션에서는 모두 다음과 같은 NuGet 패키지를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="06f39-123">토큰 자격 증명을 사용하여 인증</span><span class="sxs-lookup"><span data-stu-id="06f39-123">Authenticate with token credentials</span></span>

<span data-ttu-id="06f39-124">첫 번째 방법은 코드에 토큰 자격 증명 개체를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="06f39-125">구성 파일, 레지스트리 또는 Azure Key Vault에 자격 증명을 안전하게 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="06f39-126">서비스 주체를 만들 때 JSON 출력에서 *clientId*, *clientSecret*, 및 *tenantId* 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="06f39-127">그런 다음 `Azure` 진입점 개체를 만들어 API 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

<span data-ttu-id="06f39-128">JSON 출력의 *subscriptionId*를 `Azure` 개체에 명시적으로 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-128">It is recommended that you explicitly provide the *subscriptionId* from the JSON output to the `Azure` object:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithSubscription(subscriptionId);
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="06f39-129">파일 기반 인증</span><span class="sxs-lookup"><span data-stu-id="06f39-129">File-based authentication</span></span>

<span data-ttu-id="06f39-130">파일 기반 인증을 사용하면 서비스 사용자 자격 증명을 일반 텍스트 파일에 저장하고 파일 시스템 내에서 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-130">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="06f39-131">파일의 내용을 읽고 `Azure` 끝점 개체를 만들어 API 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="06f39-131">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
