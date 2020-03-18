---
ms.openlocfilehash: b60f74947a537c602c7bd1a89587b76bd847c82a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937268"
---
### <a name="target-framework-net-framework-support-dropped"></a><span data-ttu-id="483b2-101">대상 프레임워크: .NET Framework 지원 삭제</span><span class="sxs-lookup"><span data-stu-id="483b2-101">Target framework: .NET Framework support dropped</span></span>

<span data-ttu-id="483b2-102">ASP.NET Core 3.0부터 .NET Framework는 지원되는 않는 대상 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-102">Starting with ASP.NET Core 3.0, .NET Framework is an unsupported target framework.</span></span>

#### <a name="change-description"></a><span data-ttu-id="483b2-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="483b2-103">Change description</span></span>

<span data-ttu-id="483b2-104">.NET Framework 4.8은 .NET Framework의 마지막 주 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-104">.NET Framework 4.8 is the last major version of .NET Framework.</span></span> <span data-ttu-id="483b2-105">새 ASP.NET Core 앱은 .NET Core를 기반으로 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-105">New ASP.NET Core apps should be built on .NET Core.</span></span> <span data-ttu-id="483b2-106">.NET Core 3.0 릴리스부터는 ASP.NET Core 3.0을 .NET Core의 일부로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-106">Starting with the .NET Core 3.0 release, you can think of ASP.NET Core 3.0 as being part of .NET Core.</span></span>

<span data-ttu-id="483b2-107">.NET Framework와 함께 ASP.NET Core를 사용하는 고객은 [2.1 LTS 릴리스](https://www.microsoft.com/net/download/dotnet-core/2.1)를 사용하여 완전히 지원되는 방식으로 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-107">Customers using ASP.NET Core with .NET Framework can continue in a fully supported fashion using the [2.1 LTS release](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span> <span data-ttu-id="483b2-108">2\.1에 대한 지원 및 서비스는 2021년 8월 21일까지 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-108">Support and servicing for 2.1 continues until at least August 21, 2021.</span></span> <span data-ttu-id="483b2-109">이 날짜는 [.NET 지원 정책](https://www.microsoft.com/net/platform/support-policy)에 따라 LTS 릴리스가 선언된 후 3년입니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-109">This date is three years after declaration of the LTS release per the [.NET Support Policy](https://www.microsoft.com/net/platform/support-policy).</span></span> <span data-ttu-id="483b2-110">**.NET Framework에서** ASP.NET Core 2.1 패키지에 대한 지원은 [다른 패키지 기반 ASP.NET 프레임워크에 대한 서비스 정책](https://dotnet.microsoft.com/platform/support/policy/aspnet)과 유사하게 무기한으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-110">Support for ASP.NET Core 2.1 packages **on .NET Framework** will extend indefinitely, similar to the [servicing policy for other package-based ASP.NET frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span></span>

<span data-ttu-id="483b2-111">.NET Framework에서 .NET Core로 포팅하는 방법에 대한 자세한 내용은 [.NET Core로 포팅](~/docs/core/porting/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="483b2-111">For more information about porting from .NET Framework to .NET Core, see [Porting to .NET Core](~/docs/core/porting/index.md).</span></span>

<span data-ttu-id="483b2-112">`Microsoft.Extensions` 패키지(예: 로깅, 종속성 주입 및 구성)와 Entity Framework Core는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-112">`Microsoft.Extensions` packages (such as logging, dependency injection, and configuration) and Entity Framework Core aren't affected.</span></span> <span data-ttu-id="483b2-113">.NET Standard를 계속 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-113">They'll continue to support .NET Standard.</span></span>

<span data-ttu-id="483b2-114">이러한 변경의 동기에 대한 자세한 내용은 [원래 블로그 게시물](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="483b2-114">For more information on the motivation for this change, see [the original blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="483b2-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="483b2-115">Version introduced</span></span>

<span data-ttu-id="483b2-116">3.0</span><span class="sxs-lookup"><span data-stu-id="483b2-116">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="483b2-117">이전 동작</span><span class="sxs-lookup"><span data-stu-id="483b2-117">Old behavior</span></span>

<span data-ttu-id="483b2-118">ASP.NET Core 앱은 .NET Core 또는 .NET Framework에서 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="483b2-119">새 동작</span><span class="sxs-lookup"><span data-stu-id="483b2-119">New behavior</span></span>

<span data-ttu-id="483b2-120">ASP.NET Core 앱은 .NET Core에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-120">ASP.NET Core apps can only be run on .NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="483b2-121">권장 조치</span><span class="sxs-lookup"><span data-stu-id="483b2-121">Recommended action</span></span>

<span data-ttu-id="483b2-122">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-122">Take one of the following actions:</span></span>

- <span data-ttu-id="483b2-123">앱을 ASP.NET Core 2.1에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-123">Keep your app on ASP.NET Core 2.1.</span></span>
- <span data-ttu-id="483b2-124">앱 및 종속성을 .NET Core로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="483b2-124">Migrate your app and dependencies to .NET Core.</span></span>

#### <a name="category"></a><span data-ttu-id="483b2-125">범주</span><span class="sxs-lookup"><span data-stu-id="483b2-125">Category</span></span>

<span data-ttu-id="483b2-126">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="483b2-126">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="483b2-127">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="483b2-127">Affected APIs</span></span>

<span data-ttu-id="483b2-128">None</span><span class="sxs-lookup"><span data-stu-id="483b2-128">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
