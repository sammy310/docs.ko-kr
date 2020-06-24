---
ms.openlocfilehash: 7723892a33bf7dd8e475b2f696db5d9ab287e182
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602755"
---

<span data-ttu-id="d127c-101">패키지 관리자 피드에 추가되는 패키지는 해킹 가능한 형식으로 명명됩니다(`{product}-{type}-{version}`).</span><span class="sxs-lookup"><span data-stu-id="d127c-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="d127c-102">**product**</span><span class="sxs-lookup"><span data-stu-id="d127c-102">**product**</span></span>\
<span data-ttu-id="d127c-103">설치할 .NET 제품의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-103">The type of .NET product to install.</span></span> <span data-ttu-id="d127c-104">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-104">Valid options are:</span></span>

  - <span data-ttu-id="d127c-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="d127c-105">dotnet</span></span>
  - <span data-ttu-id="d127c-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="d127c-106">aspnetcore</span></span>

- <span data-ttu-id="d127c-107">**type**</span><span class="sxs-lookup"><span data-stu-id="d127c-107">**type**</span></span>\
<span data-ttu-id="d127c-108">SDK와 런타임 중 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="d127c-109">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-109">Valid options are:</span></span>

  - <span data-ttu-id="d127c-110">sdk</span><span class="sxs-lookup"><span data-stu-id="d127c-110">sdk</span></span>
  - <span data-ttu-id="d127c-111">런타임</span><span class="sxs-lookup"><span data-stu-id="d127c-111">runtime</span></span>

- <span data-ttu-id="d127c-112">**version**</span><span class="sxs-lookup"><span data-stu-id="d127c-112">**version**</span></span>\
<span data-ttu-id="d127c-113">설치한 SDK 또는 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="d127c-114">이 문서에서는 항상 지원되는 최신 버전에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="d127c-115">유효한 옵션은 모든 릴리스된 버전입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="d127c-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="d127c-116">3.1</span><span class="sxs-lookup"><span data-stu-id="d127c-116">3.1</span></span>
  - <span data-ttu-id="d127c-117">3.0</span><span class="sxs-lookup"><span data-stu-id="d127c-117">3.0</span></span>
  - <span data-ttu-id="d127c-118">2.1</span><span class="sxs-lookup"><span data-stu-id="d127c-118">2.1</span></span>

  <span data-ttu-id="d127c-119">다운로드하려는 SDK/런타임을 Linux 배포판에서 사용할 수 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="d127c-120">지원되는 배포 목록은 [.NET Core 종속성 및 요구 사항](../linux.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d127c-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="d127c-121">예</span><span class="sxs-lookup"><span data-stu-id="d127c-121">Examples</span></span>

- <span data-ttu-id="d127c-122">ASP.NET Core 3.1 런타임 설치: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="d127c-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="d127c-123">.NET Core 2.1 런타임 설치: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="d127c-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="d127c-124">.NET Core 3.1 SDK 설치: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="d127c-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="d127c-125">패키지가 없음</span><span class="sxs-lookup"><span data-stu-id="d127c-125">Package missing</span></span>

<span data-ttu-id="d127c-126">패키지-버전 조합이 작동하지 않는다면 사용할 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="d127c-127">예를 들어, ASP.NET Core SDK는 존재하지 않습니다. SDK 구성 요소는 .NET Core SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="d127c-128">값 `aspnetcore-sdk-2.2`는 올바르지 않으며, 올바른 값은 `dotnet-sdk-2.2`입니다.</span><span class="sxs-lookup"><span data-stu-id="d127c-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="d127c-129">.NET Core에서 지원하는 Linux 배포 목록은 [.NET Core 종속성 및 요구 사항](../linux.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d127c-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../linux.md).</span></span>
