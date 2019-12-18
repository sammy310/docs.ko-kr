---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998800"
---

<span data-ttu-id="9c8e6-101">패키지 관리자 피드에 추가되는 패키지는 해킹 가능한 형식으로 명명됩니다(`{product}-{type}-{version}`).</span><span class="sxs-lookup"><span data-stu-id="9c8e6-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="9c8e6-102">**product**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-102">**product**</span></span>\
<span data-ttu-id="9c8e6-103">설치할 .NET 제품의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-103">The type of .NET product to install.</span></span> <span data-ttu-id="9c8e6-104">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-104">Valid options are:</span></span>

  - <span data-ttu-id="9c8e6-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="9c8e6-105">dotnet</span></span>
  - <span data-ttu-id="9c8e6-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="9c8e6-106">aspnetcore</span></span>

- <span data-ttu-id="9c8e6-107">**type**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-107">**type**</span></span>\
<span data-ttu-id="9c8e6-108">SDK와 런타임 중 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="9c8e6-109">유효한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-109">Valid options are:</span></span>

  - <span data-ttu-id="9c8e6-110">sdk</span><span class="sxs-lookup"><span data-stu-id="9c8e6-110">sdk</span></span>
  - <span data-ttu-id="9c8e6-111">런타임</span><span class="sxs-lookup"><span data-stu-id="9c8e6-111">runtime</span></span>

- <span data-ttu-id="9c8e6-112">**version**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-112">**version**</span></span>\
<span data-ttu-id="9c8e6-113">설치한 SDK 또는 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="9c8e6-114">이 문서에서는 항상 지원되는 최신 버전에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="9c8e6-115">유효한 옵션은 모든 릴리스된 버전입니다. 예:</span><span class="sxs-lookup"><span data-stu-id="9c8e6-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="9c8e6-116">3.0</span><span class="sxs-lookup"><span data-stu-id="9c8e6-116">3.0</span></span>
  - <span data-ttu-id="9c8e6-117">2.2</span><span class="sxs-lookup"><span data-stu-id="9c8e6-117">2.2</span></span>
  - <span data-ttu-id="9c8e6-118">2.1</span><span class="sxs-lookup"><span data-stu-id="9c8e6-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="9c8e6-119">예</span><span class="sxs-lookup"><span data-stu-id="9c8e6-119">Examples</span></span>

- <span data-ttu-id="9c8e6-120">.NET Core 2.2 SDK 설치: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="9c8e6-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="9c8e6-121">ASP.NET Core 3.0 런타임 설치: `aspnetcore-runtime-3.0`</span><span class="sxs-lookup"><span data-stu-id="9c8e6-121">Install the ASP.NET Core 3.0 runtime: `aspnetcore-runtime-3.0`</span></span>
- <span data-ttu-id="9c8e6-122">.NET Core 2.1 런타임 설치: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="9c8e6-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="9c8e6-123">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9c8e6-123">Troubleshoot</span></span>

<span data-ttu-id="9c8e6-124">패키지 조합이 작동하지 않는다면 사용할 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="9c8e6-125">예를 들어, ASP.NET Core SDK는 존재하지 않습니다. SDK 구성 요소는 .NET Core SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="9c8e6-126">값 `aspnetcore-sdk-2.2`는 올바르지 않으며, 올바른 값은 `dotnet-sdk-2.2`입니다.</span><span class="sxs-lookup"><span data-stu-id="9c8e6-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
