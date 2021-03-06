---
title: ASP.NET MVC와 ASP.NET Core 간의 테스트 옵션 비교
description: ASP.NET MVC 앱과 ASP.NET Core apps 간에 테스트는 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: f0907d09df058c07ed993c251868f00bc28b0736
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401688"
---
# <a name="compare-testing-options-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="f17a9-103">ASP.NET MVC와 ASP.NET Core 간의 테스트 옵션 비교</span><span class="sxs-lookup"><span data-stu-id="f17a9-103">Compare testing options between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="f17a9-104">ASP.NET MVC 앱은 컨트롤러의 단위 테스트를 지원 하지만이 방법은 라우팅, 권한 부여, 모델 바인딩, 모델 유효성 검사, 필터 등의 많은 MVC 기능을 생략 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-104">ASP.NET MVC apps support unit testing of controllers, but this approach often omits many MVC features like routing, authorization, model binding, model validation, filters, and more.</span></span> <span data-ttu-id="f17a9-105">컨트롤러 작업 자체 내의 논리 외에 이러한 MVC 기능을 테스트 하기 위해 앱을 배포 하 고 Selenium와 같은 도구를 사용 하 여 테스트 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-105">To test these MVC features in addition to the logic within the controller action itself, frequently the app would need to be deployed and then tested with a tool like Selenium.</span></span> <span data-ttu-id="f17a9-106">이러한 테스트는 전체 앱을 호스트 하 고 실행할 필요 없이 실행 될 수 있는 일반적인 단위 테스트 보다 비용이 많이 들고, 불안정, 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-106">These tests are substantially more expensive, more brittle, and slower than typical unit tests that can be run without the need for hosting and running the entire app.</span></span>

<span data-ttu-id="f17a9-107">ASP.NET Core 컨트롤러는 ASP.NET MVC 컨트롤러와 마찬가지로 [단위 테스트할 수](/aspnet/core/mvc/controllers/testing) 있지만 동일한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-107">[ASP.NET Core controllers can be unit tested](/aspnet/core/mvc/controllers/testing) just like ASP.NET MVC controllers, but with the same limitations.</span></span> <span data-ttu-id="f17a9-108">그러나 [ASP.NET Core는 빠르고 쉽게 만들 수 있는 통합 테스트도 지원](/aspnet/core/test/integration-tests) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-108">However, [ASP.NET Core supports fast, easy-to-author integration tests](/aspnet/core/test/integration-tests) as well.</span></span> <span data-ttu-id="f17a9-109">통합 테스트는 클래스에 의해 호스팅되며 `TestHost` 일반적으로 `WebApplicationFactory` 응용 프로그램 종속성을 재정의 하거나 대체할 수 있는 사용자 지정에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-109">Integration tests are hosted by a `TestHost` class and are typically configured in a custom `WebApplicationFactory` that can override or replace app dependencies.</span></span> <span data-ttu-id="f17a9-110">예를 들어, 통합 테스트 중에 앱은 다른 데이터 원본을 대상으로 하며, 가짜 또는 모의 구현을 사용 하 여 전자 메일을 보내는 서비스를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-110">For instance, frequently during integration tests the app will target a different data source and may replace services that send emails with fake or mock implementations.</span></span>

<span data-ttu-id="f17a9-111">ASP.NET MVC 및 Web API는 ASP.NET Core에서 사용할 수 있는 통합 테스트 시나리오와 같은 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-111">ASP.NET MVC and Web API did not support anything like the integration testing scenarios available in ASP.NET Core.</span></span> <span data-ttu-id="f17a9-112">모든 마이그레이션 작업에서 새로 마이그레이션한 시스템에 대해 통합 테스트를 작성 하 여 예상 대로 작동 하는지 확인 하는 시간을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-112">In any migration effort, you should allocate time to write some integration tests for your newly migrated system to ensure it's working as expected and continues to do so.</span></span> <span data-ttu-id="f17a9-113">마이그레이션하기 전에 웹 앱 논리 테스트를 작성 하지 않은 경우에도 ASP.NET Core으로 이동할 때이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f17a9-113">Even if you weren't writing tests of your web app logic before the migration, you should strongly consider doing so as you move to ASP.NET Core.</span></span>

## <a name="references"></a><span data-ttu-id="f17a9-114">참조</span><span class="sxs-lookup"><span data-stu-id="f17a9-114">References</span></span>

- [<span data-ttu-id="f17a9-115">ASP.NET MVC 애플리케이션에 대한 단위 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="f17a9-115">Creating Unit Tests for ASP.NET MVC Applications</span></span>](/aspnet/mvc/overview/older-versions-1/unit-testing/creating-unit-tests-for-asp-net-mvc-applications-cs)
- [<span data-ttu-id="f17a9-116">ASP.NET Core에서 컨트롤러 논리 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="f17a9-116">Unit test controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
- [<span data-ttu-id="f17a9-117">ASP.NET Core의 통합 테스트</span><span class="sxs-lookup"><span data-stu-id="f17a9-117">Integration tests in ASP.NET Core</span></span>](/aspnet/core/test/integration-tests)

>[!div class="step-by-step"]
><span data-ttu-id="f17a9-118">[이전](signalr-differences.md)
>[다음](migrate-large-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="f17a9-118">[Previous](signalr-differences.md)
[Next](migrate-large-solutions.md)</span></span>
