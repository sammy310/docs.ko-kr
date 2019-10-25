---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394155"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="e9777-101">호스팅: Windows Hosting Bundle에서 AspNetCoreModule V1이 제거됨</span><span class="sxs-lookup"><span data-stu-id="e9777-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="e9777-102">ASP.NET Core 3.0부터 Windows Hosting Bundle에는 ANCM(AspNetCoreModule) V1이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="e9777-103">ANCM V2는 ANCM OutOfProcess와 역호환되며 ASP.NET Core 3.0 앱에서 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="e9777-104">자세한 내용은 [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9777-104">For discussion, see [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e9777-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e9777-105">Version introduced</span></span>

<span data-ttu-id="e9777-106">3.0</span><span class="sxs-lookup"><span data-stu-id="e9777-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e9777-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="e9777-107">Old behavior</span></span>

<span data-ttu-id="e9777-108">ANCM V1은 Windows Hosting Bundle에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e9777-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="e9777-109">New behavior</span></span>

<span data-ttu-id="e9777-110">ANCM V1은 Windows Hosting Bundle에 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e9777-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e9777-111">Reason for change</span></span>

<span data-ttu-id="e9777-112">ANCM V2는 ANCM OutOfProcess와 역호환되며 ASP.NET Core 3.0 앱에서 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e9777-113">권장 작업</span><span class="sxs-lookup"><span data-stu-id="e9777-113">Recommended action</span></span>

<span data-ttu-id="e9777-114">ASP.NET Core 3.0 앱에서 ANCM V2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="e9777-115">ANCM V1이 필요한 경우 ASP.NET Core 2.1 또는 2.2 Windows Hosting Bundle을 사용하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="e9777-116">이 변경으로 인해 다음과 같은 ASP.NET Core 3.0 앱이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="e9777-117">`<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`에서 ANCM V1을 사용하도록 명시적으로 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="e9777-118">`<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`를 사용하여 사용자 지정 *web .config* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9777-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="e9777-119">범주</span><span class="sxs-lookup"><span data-stu-id="e9777-119">Category</span></span>

<span data-ttu-id="e9777-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e9777-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e9777-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e9777-121">Affected APIs</span></span>

<span data-ttu-id="e9777-122">없음</span><span class="sxs-lookup"><span data-stu-id="e9777-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
