---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440426"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a><span data-ttu-id="00bae-101">데이터 보호: DataProtection.Blobs에서 새로운 Azure Storage API 사용</span><span class="sxs-lookup"><span data-stu-id="00bae-101">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>

<span data-ttu-id="00bae-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs`은 [Azure Storage 라이브러리](https://github.com/Azure/azure-storage-net)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="00bae-103">이러한 라이브러리는 해당 어셈블리, 패키지 및 네임 스페이스의 이름을 바꿨습니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="00bae-104">ASP.NET Core 3.0부터 `Azure.Extensions.AspNetCore.DataProtection.Blobs`는 새 `Azure.Storage.` 접두사가 지정된 API 및 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-104">Starting in ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` uses the new `Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="00bae-105">Azure Storage API에 대한 질문은 <https://github.com/Azure/azure-storage-net>을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="00bae-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="00bae-106">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00bae-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="00bae-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="00bae-107">Version introduced</span></span>

<span data-ttu-id="00bae-108">3.0</span><span class="sxs-lookup"><span data-stu-id="00bae-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="00bae-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="00bae-109">Old behavior</span></span>

<span data-ttu-id="00bae-110">패키지는 `WindowsAzure.Storage` NuGet 패키지를 참조했습니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>
<span data-ttu-id="00bae-111">패키지는 `Microsoft.Azure.Storage.Blob` NuGet 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-111">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="00bae-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="00bae-112">New behavior</span></span>

<span data-ttu-id="00bae-113">패키지는 `Azure.Storage.Blob` NuGet 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-113">The package references the `Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="00bae-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="00bae-114">Reason for change</span></span>

<span data-ttu-id="00bae-115">이 변경으로 인해 `Azure.Extensions.AspNetCore.DataProtection.Blobs`는 권장 Azure Storage 패키지로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-115">This change allows `Azure.Extensions.AspNetCore.DataProtection.Blobs` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="00bae-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="00bae-116">Recommended action</span></span>

<span data-ttu-id="00bae-117">ASP.NET Core 3.0과 함께 이전 Azure Storage API를 계속 사용해야 하는 경우 [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) 또는 [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/) 패키지에 직접 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-117">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the package [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) or [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span></span> <span data-ttu-id="00bae-118">이 패키지는 새 `Azure.Storage` API와 함께 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-118">This package can be installed alongside the new `Azure.Storage` APIs.</span></span>

<span data-ttu-id="00bae-119">대부분의 경우 업그레이드는 새 네임스페이스를 사용하도록 `using` 문만 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00bae-119">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a><span data-ttu-id="00bae-120">범주</span><span class="sxs-lookup"><span data-stu-id="00bae-120">Category</span></span>

<span data-ttu-id="00bae-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00bae-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="00bae-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="00bae-122">Affected APIs</span></span>

<span data-ttu-id="00bae-123">None</span><span class="sxs-lookup"><span data-stu-id="00bae-123">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
