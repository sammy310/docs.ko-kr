---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032520"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="bdcf9-101">호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider</span><span class="sxs-lookup"><span data-stu-id="bdcf9-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="bdcf9-102">ASP.NET Core가 재생에 대해 추가 비용을 지불하도록 하는 과정에서 `ObjectPoolProvider`가 기본 종속성 세트에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="bdcf9-103">`ObjectPoolProvider`에 의존하는 특정 구성 요소가 이제 해당 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="bdcf9-104">토론은 [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bdcf9-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bdcf9-105">Version introduced</span></span>

<span data-ttu-id="bdcf9-106">3.0</span><span class="sxs-lookup"><span data-stu-id="bdcf9-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bdcf9-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="bdcf9-107">Old behavior</span></span>

<span data-ttu-id="bdcf9-108">`WebHostBuilder`에서는 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bdcf9-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="bdcf9-109">New behavior</span></span>

<span data-ttu-id="bdcf9-110">`WebHostBuilder`에서는 더 이상 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bdcf9-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="bdcf9-111">Reason for change</span></span>

<span data-ttu-id="bdcf9-112">이러한 변경으로 인해 ASP.NET Core가 더 많은 비용을 지불하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bdcf9-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bdcf9-113">Recommended action</span></span>

<span data-ttu-id="bdcf9-114">구성 요소에 `ObjectPoolProvider`가 필요한 경우 `IServiceCollection`을 통해 종속성에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdcf9-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="bdcf9-115">범주</span><span class="sxs-lookup"><span data-stu-id="bdcf9-115">Category</span></span>

<span data-ttu-id="bdcf9-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bdcf9-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bdcf9-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bdcf9-117">Affected APIs</span></span>

<span data-ttu-id="bdcf9-118">없음</span><span class="sxs-lookup"><span data-stu-id="bdcf9-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
