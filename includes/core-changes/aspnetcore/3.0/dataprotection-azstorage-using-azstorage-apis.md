---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901646"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="2dc68-101">데이터 보호: DataProtection.AzureStorage는 새로운 Azure Storage API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="2dc68-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName>은 [Azure Storage 라이브러리](https://github.com/Azure/azure-storage-net)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="2dc68-103">이러한 라이브러리는 해당 어셈블리, 패키지 및 네임 스페이스의 이름을 바꿨습니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="2dc68-104">ASP.NET Core 3.0부터 `Microsoft.AspNetCore.DataProtection.AzureStorage`는 새 `Microsoft.Azure.Storage.` 접두사가 지정된 API 및 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="2dc68-105">Azure Storage API에 대한 질문은 <https://github.com/Azure/azure-storage-net>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2dc68-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="2dc68-106">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dc68-106">For discussion on this issue, see [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2dc68-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2dc68-107">Version introduced</span></span>

<span data-ttu-id="2dc68-108">3.0</span><span class="sxs-lookup"><span data-stu-id="2dc68-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2dc68-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="2dc68-109">Old behavior</span></span>

<span data-ttu-id="2dc68-110">패키지는 `WindowsAzure.Storage` NuGet 패키지를 참조했습니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2dc68-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="2dc68-111">New behavior</span></span>

<span data-ttu-id="2dc68-112">패키지는 `Microsoft.Azure.Storage.Blob` NuGet 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2dc68-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2dc68-113">Reason for change</span></span>

<span data-ttu-id="2dc68-114">이 변경으로 인해 `Microsoft.AspNetCore.DataProtection.AzureStorage`는 권장 Azure Storage 패키지로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2dc68-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="2dc68-115">Recommended action</span></span>

<span data-ttu-id="2dc68-116">ASP.NET Core 3.0과 함께 이전 Azure Storage API를 계속 사용해야 하는 경우 [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) 패키지에 직접 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="2dc68-117">이 패키지는 새 `Microsoft.Azure.Storage` API와 함께 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="2dc68-118">대부분의 경우 업그레이드는 새 네임스페이스를 사용하도록 `using` 문만 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dc68-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="2dc68-119">범주</span><span class="sxs-lookup"><span data-stu-id="2dc68-119">Category</span></span>

<span data-ttu-id="2dc68-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2dc68-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2dc68-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2dc68-121">Affected APIs</span></span>

<span data-ttu-id="2dc68-122">없음</span><span class="sxs-lookup"><span data-stu-id="2dc68-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
