---
ms.openlocfilehash: 370c6eb23a50ed388f0b10a5c5f4779ba2a1b144
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102623248"
---
### <a name="project-tools-now-included-in-sdk"></a><span data-ttu-id="a5897-101">이제 프로젝트 도구가 SDK에 포함됨</span><span class="sxs-lookup"><span data-stu-id="a5897-101">Project tools now included in SDK</span></span>

<span data-ttu-id="a5897-102">이제 .NET Core 2.1 SDK에 일반적인 CLI 도구가 포함되며 더 이상 프로젝트에서 해당 도구를 참조할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5897-102">The .NET Core 2.1 SDK now includes common CLI tooling, and you no longer need to reference these tools from the project.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a5897-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a5897-103">Change description</span></span>

<span data-ttu-id="a5897-104">.NET Core 2.0에서 프로젝트는 `<DotNetCliToolReference>` 프로젝트 설정을 사용하여 외부 .NET 도구를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a5897-104">In .NET Core 2.0, projects reference external .NET tools with the `<DotNetCliToolReference>` project setting.</span></span> <span data-ttu-id="a5897-105">.NET Core 2.1에서 해당 도구 중 일부는 .NET Core SDK에 포함되며 더 이상 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5897-105">In .NET Core 2.1, some of these tools are included with the .NET Core SDK, and the setting is no longer needed.</span></span> <span data-ttu-id="a5897-106">프로젝트에 해당 도구에 대한 참조를 포함하는 경우 다음과 같은 오류가 표시됩니다. **'Microsoft.EntityFrameworkCore.Tools.DotNet' 도구는 이제 .NET Core SDK에 포함됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a5897-106">If you include references to these tools in your project, you'll receive an error similar to the following: **The tool 'Microsoft.EntityFrameworkCore.Tools.DotNet' is now included in the .NET Core SDK.**</span></span>

<span data-ttu-id="a5897-107">이제 도구가 .NET Core 2.1 SDK에 포함됨:</span><span class="sxs-lookup"><span data-stu-id="a5897-107">Tools now included in .NET Core 2.1 SDK:</span></span>

| <span data-ttu-id="a5897-108">\<DotNetCliToolReference> 값</span><span class="sxs-lookup"><span data-stu-id="a5897-108">\<DotNetCliToolReference> value</span></span>                   | <span data-ttu-id="a5897-109">도구</span><span class="sxs-lookup"><span data-stu-id="a5897-109">Tool</span></span>                                                                                                            |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `Microsoft.DotNet.Watcher.Tools`               | `dotnet-watch`               |
| `Microsoft.Extensions.SecretManager.Tools`     | [<span data-ttu-id="a5897-110">dotnet-user-secrets</span><span class="sxs-lookup"><span data-stu-id="a5897-110">dotnet-user-secrets</span></span>](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-user-secrets/README.md) |
| `Microsoft.Extensions.Caching.SqlConfig.Tools` | [<span data-ttu-id="a5897-111">dotnet-sql-cache</span><span class="sxs-lookup"><span data-stu-id="a5897-111">dotnet-sql-cache</span></span>](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-sql-cache/README.md)       |
| `Microsoft.EntityFrameworkCore.Tools.DotNet`   | [<span data-ttu-id="a5897-112">dotnet-ef</span><span class="sxs-lookup"><span data-stu-id="a5897-112">dotnet-ef</span></span>](/ef/core/miscellaneous/cli/dotnet)                                                                  |

#### <a name="version-introduced"></a><span data-ttu-id="a5897-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a5897-113">Version introduced</span></span>

<span data-ttu-id="a5897-114">.NET Core SDK 2.1.300</span><span class="sxs-lookup"><span data-stu-id="a5897-114">.NET Core SDK 2.1.300</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a5897-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a5897-115">Recommended action</span></span>

<span data-ttu-id="a5897-116">프로젝트에서 `<DotNetCliToolReference>` 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a5897-116">Remove the `<DotNetCliToolReference>` setting from your project.</span></span>

#### <a name="category"></a><span data-ttu-id="a5897-117">범주</span><span class="sxs-lookup"><span data-stu-id="a5897-117">Category</span></span>

<span data-ttu-id="a5897-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="a5897-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5897-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a5897-119">Affected APIs</span></span>

<span data-ttu-id="a5897-120">N/A</span><span class="sxs-lookup"><span data-stu-id="a5897-120">N/A</span></span>
