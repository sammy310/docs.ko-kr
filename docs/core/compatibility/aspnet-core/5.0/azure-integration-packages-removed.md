---
title: '호환성이 손상되는 변경: Azure: Microsoft 접두사가 있는 Azure 통합 패키지가 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Azure: Microsoft 접두사가 있는 Azure 통합 패키지가 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b9f685b8c9fdcd73044f78840f2732809a0de710
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759990"
---
# <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="ba094-103">Azure: Microsoft 접두사가 있는 Azure 통합 패키지가 제거됨</span><span class="sxs-lookup"><span data-stu-id="ba094-103">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="ba094-104">ASP.NET Core와 Azure SDK 간의 통합을 제공하는 다음 `Microsoft.*` 패키지는 ASP.NET Core 5.0에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-104">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="ba094-105">[Azure Key Vault](/azure/key-vault/)를 [구성 시스템](/aspnet/core/fundamentals/configuration/)에 통합하는 [Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/)</span><span class="sxs-lookup"><span data-stu-id="ba094-105">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="ba094-106">Azure Key Vault를 [ASP.NET Core 데이터 보호 시스템](/aspnet/core/security/data-protection/introduction)에 통합하는 [Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/)</span><span class="sxs-lookup"><span data-stu-id="ba094-106">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="ba094-107">[Azure Blob Storage](/azure/storage/blobs/)를 ASP.NET Core 데이터 보호 시스템에 통합하는 [Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/)</span><span class="sxs-lookup"><span data-stu-id="ba094-107">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="ba094-108">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba094-108">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ba094-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ba094-109">Version introduced</span></span>

<span data-ttu-id="ba094-110">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ba094-110">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ba094-111">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ba094-111">Old behavior</span></span>

<span data-ttu-id="ba094-112">`Microsoft.*` 패키지가 Azure 서비스를 구성 및 데이터 보호 API와 통합했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-112">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ba094-113">새 동작</span><span class="sxs-lookup"><span data-stu-id="ba094-113">New behavior</span></span>

<span data-ttu-id="ba094-114">새 `Azure.*` 패키지가 Azure 서비스를 구성 및 데이터 보호 API와 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-114">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ba094-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ba094-115">Reason for change</span></span>

<span data-ttu-id="ba094-116">`Microsoft.*` 패키지에 다음과 같은 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-116">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="ba094-117">오래된 버전의 Azure SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-117">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="ba094-118">새 버전의 Azure SDK에 호환성이 손상되는 변경이 포함되어 간단한 업데이트를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-118">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="ba094-119">.NET Core 릴리스 일정에 연동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-119">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="ba094-120">패키지의 소유권을 Azure SDK 팀으로 이전하면 Azure SDK가 업데이트될 때 패키지 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-120">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ba094-121">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ba094-121">Recommended action</span></span>

<span data-ttu-id="ba094-122">ASP.NET Core 2.1 이상 프로젝트에서 이전 `Microsoft.*` 패키지를 새 `Azure.*` 패키지로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-122">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="ba094-123">이전</span><span class="sxs-lookup"><span data-stu-id="ba094-123">Old</span></span> | <span data-ttu-id="ba094-124">단추를 사용하여 새</span><span class="sxs-lookup"><span data-stu-id="ba094-124">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="ba094-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span><span class="sxs-lookup"><span data-stu-id="ba094-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="ba094-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span><span class="sxs-lookup"><span data-stu-id="ba094-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="ba094-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span><span class="sxs-lookup"><span data-stu-id="ba094-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

<span data-ttu-id="ba094-128">새 패키지는 호환성이 손상되는 변경을 포함하는 새 버전의 Azure SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-128">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="ba094-129">일반적인 사용 패턴은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-129">The general usage patterns are unchanged.</span></span> <span data-ttu-id="ba094-130">일부 오버로드 및 옵션은 기본 Azure SDK API의 변경 내용에 맞게 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-130">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="ba094-131">이전 패키지는</span><span class="sxs-lookup"><span data-stu-id="ba094-131">The old packages will:</span></span>

* <span data-ttu-id="ba094-132">.NET Core 2.1 및 3.1의 수명 동안 ASP.NET Core 팀에서 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-132">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="ba094-133">.NET 5에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba094-133">Not be included in .NET 5.</span></span>

<span data-ttu-id="ba094-134">프로젝트를 .NET 5로 업그레이드하는 경우 `Azure.*` 패키지로 전환하여 지원을 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="ba094-134">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ba094-135">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ba094-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
