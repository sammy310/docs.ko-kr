---
title: ASP.NET Web API 2와 ASP.NET Core 비교
description: ASP.NET Web API 2 앱과 ASP.NET Core 앱 간의 웹 Api는 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 93aa917174bce24fdf924f6372312c3972473289
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401682"
---
# <a name="compare-aspnet-web-api-2-and-aspnet-core"></a><span data-ttu-id="f0032-103">ASP.NET Web API 2와 ASP.NET Core 비교</span><span class="sxs-lookup"><span data-stu-id="f0032-103">Compare ASP.NET Web API 2 and ASP.NET Core</span></span>

<span data-ttu-id="f0032-104">ASP.NET Core ASP.NET Web API 2에 대 한 반복적인 향상 기능을 제공 하지만 Web API 2를 사용 하는 개발자에 게 친숙 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-104">ASP.NET Core offers iterative improvements to ASP.NET Web API 2, but should feel familiar to developers who have used Web API 2.</span></span> <span data-ttu-id="f0032-105">ASP.NET Web API 2는 ASP.NET MVC와 함께 개발 되 고 배송 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-105">ASP.NET Web API 2 was developed and shipped alongside ASP.NET MVC.</span></span> <span data-ttu-id="f0032-106">이는 두 가지 방법으로 특성 라우팅 및 종속성 주입과 같은 비슷한 방식으로 접근 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-106">This meant the two approaches had similar-but-different approaches to things like attribute routing and dependency injection.</span></span> <span data-ttu-id="f0032-107">ASP.NET Core MVC와 Web Api는 더 이상 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-107">In ASP.NET Core, there's no longer any distinction between MVC and Web APIs.</span></span> <span data-ttu-id="f0032-108">ASP.NET MVC만 있습니다. 여기에는 보기 기반 시나리오, API 끝점 및 Razor Pages에 대 한 지원 (및 상태 검사 및 SignalR 같은 기타 변형)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-108">There's only ASP.NET MVC, which includes support for view-based scenarios, API endpoints, and Razor Pages (and other variations like health checks and SignalR).</span></span>

<span data-ttu-id="f0032-109">ASP.NET Core 내에서 일관 되 고 통합 될 뿐만 아니라, .NET Core에서 빌드된 Api는 ASP.NET Web API 2에 구축 된 Api 보다 훨씬 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-109">In addition to being consistent and unified within ASP.NET Core, APIs built in .NET Core are much easier to test than those built on ASP.NET Web API 2.</span></span> <span data-ttu-id="f0032-110">잠시 후에 [테스트 차이점](testing-differences.md) 을 더 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-110">We'll cover [testing differences](testing-differences.md) in more detail in a moment.</span></span> <span data-ttu-id="f0032-111">앱에 대 한 메모리 내 요청을 만들 수 있는를 만들 수 있는 테스트 호스트에서 ASP.NET Core 앱을 호스트 하는 기본 제공 지원은 `HttpClient` 자동화 된 테스트를 수행 하는 경우에 상당한 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-111">The built-in support for hosting ASP.NET Core apps, in a test host that can create an `HttpClient` that makes in-memory requests to the app, is a huge benefit when it comes to automated testing.</span></span>

<span data-ttu-id="f0032-112">ASP.NET Web API 2에서 ASP.NET Core로 마이그레이션하는 경우에는 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-112">When migrating from ASP.NET Web API 2 to ASP.NET Core, the transition is straightforward.</span></span> <span data-ttu-id="f0032-113">용량이 클 수 있는 용량이 클 경우 이러한 컨트롤러를 분리 하는 방법 중 하나는 [Ardalis](https://www.nuget.org/packages/Ardalis.ApiEndpoints/) NuGet 패키지를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-113">If you have large, bloated controllers, one approach you may consider to break them up is the use of the [Ardalis.ApiEndpoints](https://www.nuget.org/packages/Ardalis.ApiEndpoints/) NuGet packages.</span></span> <span data-ttu-id="f0032-114">이 패키지는 연결 된 요청 및 응답 유형을 적절 하 게 사용 하 여 각 끝점을 고유한 특정 클래스로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-114">This package breaks up each endpoint into its own specific class, with associated request and response types as appropriate.</span></span> <span data-ttu-id="f0032-115">이 접근 방식은 [보기 기반 코드 조직 보다 Razor Pages 제품과 동일한 많은 혜택을 제공](comparing-razor-pages-aspnet-mvc.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0032-115">This approach yields many of [the same benefits as Razor Pages offer over view-based code organization](comparing-razor-pages-aspnet-mvc.md).</span></span>

## <a name="references"></a><span data-ttu-id="f0032-116">참조</span><span class="sxs-lookup"><span data-stu-id="f0032-116">References</span></span>

- [<span data-ttu-id="f0032-117">ASP.NET Web API에서 ASP.NET Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f0032-117">Migrate from ASP.NET Web API to ASP.NET Core</span></span>](/aspnet/core/migration/webapi)
- [<span data-ttu-id="f0032-118">Ardalis NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="f0032-118">Ardalis.ApiEndpoints NuGet package</span></span>](https://www.nuget.org/packages/Ardalis.ApiEndpoints/)

>[!div class="step-by-step"]
><span data-ttu-id="f0032-119">[이전](comparing-razor-pages-aspnet-mvc.md)
>[다음](authentication-differences.md)</span><span class="sxs-lookup"><span data-stu-id="f0032-119">[Previous](comparing-razor-pages-aspnet-mvc.md)
[Next](authentication-differences.md)</span></span>
