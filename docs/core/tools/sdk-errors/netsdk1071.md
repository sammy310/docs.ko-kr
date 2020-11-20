---
title: 'NETSDK1071: ‘{0}’에 대한 PackageReference에서 `{1}`의 버전을 지정했습니다.'
description: 버전이 있는 프레임워크에 포함된 메타패키지에 대한 PackageReference의 문제를 해결하는 방법입니다.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445710"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a><span data-ttu-id="cae7e-103">NETSDK1071: 프레임워크에 포함되는 메타패키지에 대한 PackageReference 버전을 명시적으로 관리했습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-103">NETSDK1071: Explicitly versioned PackageReference to a metapackage that would be included with the framework.</span></span>

<span data-ttu-id="cae7e-104">**이 문서의 적용 대상:** ✔️ .NET 5.0.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="cae7e-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="cae7e-105">.NET SDK에서 NETSDK1071 경고를 실행하면 PackageReference에 지정된 메타패키지의 버전과 TargetFramework 속성을 통해 암시적으로 참조되는 해당 메타패키지의 버전 간에 버전 충돌이 나중에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-105">When the .NET SDK issues warning NETSDK1071, it suggests there may be a version conflict in the future between the version of a metapackage specified in a PackageReference and the version of that metapackage as implicitly referenced via a TargetFramework property:</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="cae7e-106">TargetFramework는 메타패키지 버전을 자동으로 가져오므로 버전이 다르면 충돌하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-106">Since the TargetFramework automatically brings in a version of the metapackage, the versions will conflict should they ever differ.</span></span>

<span data-ttu-id="cae7e-107">해결 방법:</span><span class="sxs-lookup"><span data-stu-id="cae7e-107">To resolve this:</span></span>

1. <span data-ttu-id="cae7e-108">.NET Core 또는 .NET Standard를 대상으로 지정하는 경우 프로젝트 파일에서 `Microsoft.NETCore.App` 또는 `NETStandard.Library`에 대한 명시적 참조를 방지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-108">Consider, when targeting .NET Core or .NET Standard, avoiding explicit references to `Microsoft.NETCore.App` or `NETStandard.Library` in your project file.</span></span>
2. <span data-ttu-id="cae7e-109">.NET Core를 대상으로 지정할 때 특정 버전의 런타임이 필요한 경우 메타패키지를 직접 참조하는 대신 `<RuntimeFrameworkVersion>` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-109">If you need a specific version of the runtime when targeting .NET Core, use the `<RuntimeFrameworkVersion>`property instead of referencing the metapackage directly.</span></span> <span data-ttu-id="cae7e-110">예를 들어 [자체 포함 배포](../../deploying/index.md#publish-self-contained)를 사용하고 1.0.0 LTS 런타임의 특정 패치가 필요한 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-110">As an example, this could happen if you're using [self-contained deployments](../../deploying/index.md#publish-self-contained) and need a specific patch of the 1.0.0 LTS runtime.</span></span>
3. <span data-ttu-id="cae7e-111">.NET Standard를 대상으로 지정할 때 특정 버전의 `NetStandard.Library`가 필요한 경우 `<NetStandardImplicitPackageVersion>` 속성을 사용하고 필요한 버전으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-111">If you need a specific version of `NetStandard.Library` when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set it to the version you need.</span></span>
4. <span data-ttu-id="cae7e-112">.NET Framework 프로젝트에서 `Microsoft.NETCore.App` 또는 `NETSTandard.Library`에 대한 참조를 명시적으로 추가하거나 업데이트하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cae7e-112">Don't eplicitly add or update references to either `Microsoft.NETCore.App` or `NETSTandard.Library` in .NET Framework projects.</span></span> <span data-ttu-id="cae7e-113">NuGet은 .NET Standard 기반 NuGet 패키지를 사용할 때 필요한 `NETStandard.Library`의 모든 버전을 자동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-113">NuGet automatically installs any version of `NETStandard.Library` you need when using a .NET Standard-based NuGet package.</span></span>
5. <span data-ttu-id="cae7e-114">.NET Core SDK에서 적절한 버전을 자동으로 선택하므로 .NET Core 2.1+을 사용할 때 `Microsoft.AspNetCore.App` 또는 `Microsoft.AspNetCore.All`에 대한 버전을 지정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cae7e-114">Do not specify a version for `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` when using .NET Core 2.1+, as the .NET Core SDK automatically selects the appropriate version.</span></span> <span data-ttu-id="cae7e-115">(참고: 프로젝트에서 `Microsoft.NET.Sdk.Web`도 사용하면 .NET Core 2.1을 대상으로 지정할 때만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-115">(Note: This only works when targeting .NET Core 2.1 if the project also uses `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="cae7e-116">이 문제는 .NET Core 2.2 SDK에서 해결되었습니다.)</span><span class="sxs-lookup"><span data-stu-id="cae7e-116">This problem was resolved in the .NET Core 2.2 SDK.)</span></span>
6. <span data-ttu-id="cae7e-117">경고를 표시하지 않으려면 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cae7e-117">If you want the warning to go away, you can also disable it:</span></span>

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
