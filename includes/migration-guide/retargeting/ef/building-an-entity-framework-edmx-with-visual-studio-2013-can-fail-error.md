---
ms.openlocfilehash: c5099f610569f7788bb829a2153006d20d8a4ea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615685"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a><span data-ttu-id="f79ed-101">Visual Studio 2013을 사용하여 Entity Framework edmx를 빌드할 때 EntityDeploySplit 또는 EntityClean 작업을 사용하면 MSB4062 오류로 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="f79ed-101">Building an Entity Framework edmx with Visual Studio 2013 can fail with error MSB4062 if using the EntityDeploySplit or EntityClean tasks</span></span>

#### <a name="details"></a><span data-ttu-id="f79ed-102">설명</span><span class="sxs-lookup"><span data-stu-id="f79ed-102">Details</span></span>

<span data-ttu-id="f79ed-103">MSBuild 12.0 도구(Visual Studio 2013 포함)가 MSBuild 파일 위치를 변경하여 이전 Entity Framework 대상 파일을 유효하지 않게 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-103">MSBuild 12.0 tools (included in Visual Studio 2013) changed MSBuild file locations, causing older Entity Framework targets files to be invalid.</span></span> <span data-ttu-id="f79ed-104">그 결과로 `EntityDeploySplit` 및 `EntityClean` 작업이 `Microsoft.Data.Entity.Build.Tasks.dll`을 찾을 수 없어 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-104">The result is that `EntityDeploySplit` and `EntityClean` tasks fail because they are unable to find `Microsoft.Data.Entity.Build.Tasks.dll`.</span></span> <span data-ttu-id="f79ed-105">이 줄바꿈은 .NET Framework의 변경 때문이 아닌 도구 집합(MSBuild/VS) 변경 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-105">Note that this break is because of a toolset (MSBuild/VS) change, not because of a .NET Framework change.</span></span> <span data-ttu-id="f79ed-106">이것은 단순히 .NET Framework를 업그레이드할 때가 아니라 개발자 도구를 업그레이드할 때에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-106">It will only occur when upgrading developer tools, not when merely upgrading the .NET Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f79ed-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f79ed-107">Suggestion</span></span>

<span data-ttu-id="f79ed-108">.NET Framework 4.6부터 Entity Framework 대상 파일은 새 MSBuild 레이아웃으로 작업하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-108">Entity Framework targets files are fixed to work with the new MSBuild layout beginning in the .NET Framework 4.6.</span></span> <span data-ttu-id="f79ed-109">해당 버전의 Framework로 업그레이드하면 이 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-109">Upgrading to that version of the Framework will fix this issue.</span></span> <span data-ttu-id="f79ed-110">또는 [이 해결 방법](https://stackoverflow.com/a/24249247/131944)을 대상 파일을 직접 패치하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f79ed-110">Alternatively, [this workaround](https://stackoverflow.com/a/24249247/131944) can be used to patch the targets files directly.</span></span>

| <span data-ttu-id="f79ed-111">이름</span><span class="sxs-lookup"><span data-stu-id="f79ed-111">Name</span></span>    | <span data-ttu-id="f79ed-112">값</span><span class="sxs-lookup"><span data-stu-id="f79ed-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f79ed-113">Scope</span><span class="sxs-lookup"><span data-stu-id="f79ed-113">Scope</span></span>   | <span data-ttu-id="f79ed-114">주요함</span><span class="sxs-lookup"><span data-stu-id="f79ed-114">Major</span></span>       |
| <span data-ttu-id="f79ed-115">버전</span><span class="sxs-lookup"><span data-stu-id="f79ed-115">Version</span></span> | <span data-ttu-id="f79ed-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f79ed-116">4.5.1</span></span>       |
| <span data-ttu-id="f79ed-117">형식</span><span class="sxs-lookup"><span data-stu-id="f79ed-117">Type</span></span>    | <span data-ttu-id="f79ed-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="f79ed-118">Retargeting</span></span> |
