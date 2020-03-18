---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77466110"
---

<span data-ttu-id="1ebad-101">패키지 관리자 피드에 추가되는 패키지는 해킹 가능한 형식으로 명명됩니다(`{product}-{type}-{version}`).</span><span class="sxs-lookup"><span data-stu-id="1ebad-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="1ebad-102">**product**</span><span class="sxs-lookup"><span data-stu-id="1ebad-102">**product**</span></span>\
<span data-ttu-id="1ebad-103">설치할 .NET 제품의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-103">The type of .NET product to install.</span></span> <span data-ttu-id="1ebad-104">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-104">Valid options are:</span></span>

  - <span data-ttu-id="1ebad-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="1ebad-105">dotnet</span></span>
  - <span data-ttu-id="1ebad-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="1ebad-106">aspnetcore</span></span>

- <span data-ttu-id="1ebad-107">**type**</span><span class="sxs-lookup"><span data-stu-id="1ebad-107">**type**</span></span>\
<span data-ttu-id="1ebad-108">SDK와 런타임 중 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="1ebad-109">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-109">Valid options are:</span></span>

  - <span data-ttu-id="1ebad-110">sdk</span><span class="sxs-lookup"><span data-stu-id="1ebad-110">sdk</span></span>
  - <span data-ttu-id="1ebad-111">런타임</span><span class="sxs-lookup"><span data-stu-id="1ebad-111">runtime</span></span>

- <span data-ttu-id="1ebad-112">**version**</span><span class="sxs-lookup"><span data-stu-id="1ebad-112">**version**</span></span>\
<span data-ttu-id="1ebad-113">설치한 SDK 또는 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="1ebad-114">이 문서에서는 항상 지원되는 최신 버전에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="1ebad-115">유효한 옵션은 모든 릴리스된 버전입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="1ebad-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="1ebad-116">3.1</span><span class="sxs-lookup"><span data-stu-id="1ebad-116">3.1</span></span>
  - <span data-ttu-id="1ebad-117">3.0</span><span class="sxs-lookup"><span data-stu-id="1ebad-117">3.0</span></span>
  - <span data-ttu-id="1ebad-118">2.1</span><span class="sxs-lookup"><span data-stu-id="1ebad-118">2.1</span></span>

  <span data-ttu-id="1ebad-119">다운로드하려는 SDK/런타임을 Linux 배포판에서 사용할 수 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="1ebad-120">지원되는 배포 목록은 [.NET Core 종속성 및 요구 사항](../dependencies.md?pivots=os-linux)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ebad-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="1ebad-121">예</span><span class="sxs-lookup"><span data-stu-id="1ebad-121">Examples</span></span>

- <span data-ttu-id="1ebad-122">ASP.NET Core 3.1 런타임 설치: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="1ebad-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="1ebad-123">.NET Core 2.1 런타임 설치: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="1ebad-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="1ebad-124">.NET Core 3.0 SDK 설치: `dotnet-sdk-3.0`</span><span class="sxs-lookup"><span data-stu-id="1ebad-124">Install the .NET Core 3.0 SDK: `dotnet-sdk-3.0`</span></span>

### <a name="package-missing"></a><span data-ttu-id="1ebad-125">패키지가 없음</span><span class="sxs-lookup"><span data-stu-id="1ebad-125">Package missing</span></span>

<span data-ttu-id="1ebad-126">패키지-버전 조합이 작동하지 않는다면 사용할 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="1ebad-127">예를 들어, ASP.NET Core SDK는 존재하지 않습니다. SDK 구성 요소는 .NET Core SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="1ebad-128">값 `aspnetcore-sdk-2.2`는 올바르지 않으며, 올바른 값은 `dotnet-sdk-2.2`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebad-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="1ebad-129">.NET Core에서 지원하는 Linux 배포 목록은 [.NET Core 종속성 및 요구 사항](../dependencies.md?pivots=os-linux)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ebad-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
