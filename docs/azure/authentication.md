---
title: .NET용 Azure 라이브러리의 인증 이해
description: .NET용 Azure SDK를 사용하여 인증하는 다양한 방법을 설명합니다.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 5ed29d5485dc7f59bcc757c8903116edf6bd5d7d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174872"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a>.NET용 Azure SDK를 사용하여 인증

## <a name="recommended-azureidentity"></a>권장: Azure.Identity

.NET용 Azure SDK의 최신 패키지는 인증하는 데 일반적인 인증 패키지인 `Azure.Identity`를 사용합니다. 이 문서의 뒷부분에 설명된 다른 인증 메커니즘보다는 `Azure.Identity`를 사용하는 것이 좋습니다. `Azure.Identity`에서 제공하는 자격 증명을 지원하는 패키지에는 *Azure*로 시작하는 패키지 식별자가 있습니다. [자세한 내용은 .NET용 Azure SDK의 최신 릴리스를 참조하세요](https://azure.github.io/azure-sdk/releases/latest/index.html#net).

프로젝트에서 `Azure.Identity`를 사용하는 방법에 관한 자세한 내용은 [.NET용 Azure ID 클라이언트](/dotnet/api/overview/azure/identity-readme) 설명서를 참조하세요.

> [!TIP]
> Azure ID를 사용하여 Azure 리소스를 관리 및 액세스하는 방법의 예제는 [Azure ID, 리소스 관리 및 Storage 샘플](/samples/dotnet/samples/azure-identity-resource-management-storage/)을 참조하세요.

Azure.Identity를 지원하지 않는 라이브러리를 사용하여 인증하려면 이 항목의 나머지 부분을 참조하세요.

## <a name="access-azure-resources"></a>Azure 리소스 액세스

Key Vault에서 비밀을 검색하거나 Storage에 BLOB을 저장하는 등 Azure 리소스와 상호 작용하려면 대부분의 Azure 서비스 라이브러리에 인증을 위한 연결 문자열 또는 키가 있어야 합니다. 예를 들어 SQL Database는 [표준 SQL 연결 문자열](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core)을 사용합니다. 서비스 연결 문자열은 [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues)와 같은 다른 Azure 서비스에서 사용됩니다. Azure Portal, CLI 또는 PowerShell을 사용하여 이러한 문자열을 가져올 수 있습니다. 또한 .NET용 Azure 관리 라이브러리를 사용하여 코드에서 연결 문자열을 작성하는 리소스를 쿼리할 수도 있습니다.

연결 문자열을 사용하는 방법은 제품별로 다릅니다. [Azure 제품에 관한 설명서를 참조하세요](/azure/?product=featured).

## <a name="manage-azure-resources"></a>Azure 리소스 관리

[!include[Create service principal](includes/create-sp.md)]

이제 서비스 사용자를 만들었으므로 두 가지 옵션을 사용하여 리소스를 만들고 관리할 서비스 사용자를 인증할 수 있습니다.

두 옵션에서는 모두 다음과 같은 NuGet 패키지를 프로젝트에 추가해야 합니다.

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a>토큰 자격 증명을 사용하여 인증

첫 번째 방법은 코드에 토큰 자격 증명 개체를 작성하는 것입니다. 구성 파일, 레지스트리 또는 Azure Key Vault에 자격 증명을 안전하게 저장해야 합니다.

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

서비스 주체를 만들 때 JSON 출력에서 *clientId*, *clientSecret*, 및 *tenantId* 값을 사용합니다.

그런 다음 `Azure` 진입점 개체를 만들어 API 작업을 시작합니다.

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a>파일 기반 인증

파일 기반 인증을 사용하면 서비스 사용자 자격 증명을 일반 텍스트 파일에 저장하고 파일 시스템 내에서 보호할 수 있습니다.

[!include[File-based authentication](includes/file-based-auth.md)]

파일의 내용을 읽고 `Azure` 끝점 개체를 만들어 API 작업을 시작합니다.

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
