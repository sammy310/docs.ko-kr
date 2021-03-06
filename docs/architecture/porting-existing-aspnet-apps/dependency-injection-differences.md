---
title: ASP.NET MVC와 ASP.NET Core 간의 종속성 주입 차이
description: ASP.NET MVC 및 ASP.NET Core에서 종속성 주입이 작동 하는 방법, 차이점 및 ASP.NET MVC에서 ASP.NET Core로 마이그레이션하는 방법에 대해 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: aa1c7dd2f70e1a545352feb6560177bc6e2baa2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401778"
---
# <a name="dependency-injection-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="52f8c-103">ASP.NET MVC와 ASP.NET Core 간의 종속성 주입 차이</span><span class="sxs-lookup"><span data-stu-id="52f8c-103">Dependency injection differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="52f8c-104">ASP.NET MVC 또는 Web API에는 DI (종속성 주입)가 제공 되지 않지만 많은 앱은 IOC (반전 제어) 컨테이너를 사용 하 여 NuGet 패키지를 추가 함으로써이를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-104">Although dependency injection (DI) isn't built into ASP.NET MVC or Web API, many apps enable it by adding a NuGet package with an inversion of control (IOC) container.</span></span> <span data-ttu-id="52f8c-105">이러한 경우를 종속성 주입 또는 반전에 대해 DI 컨테이너 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-105">These are sometimes referred to as DI containers, for dependency injection (or inversion).</span></span> <span data-ttu-id="52f8c-106">ASP.NET MVC 앱에서 가장 많이 사용 되는 컨테이너 중 일부는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-106">Some of the most popular containers used in ASP.NET MVC apps include:</span></span>

- [<span data-ttu-id="52f8c-107">Autofac</span><span class="sxs-lookup"><span data-stu-id="52f8c-107">Autofac</span></span>](https://www.autofac.org/)
- [<span data-ttu-id="52f8c-108">Unity</span><span class="sxs-lookup"><span data-stu-id="52f8c-108">Unity</span></span>](https://unitycontainer.github.io/)
- [<span data-ttu-id="52f8c-109">Ninject</span><span class="sxs-lookup"><span data-stu-id="52f8c-109">Ninject</span></span>](http://www.ninject.org/)
- <span data-ttu-id="52f8c-110">[StructureMap](http://structuremap.github.io/) *(사용 되지 않음)*</span><span class="sxs-lookup"><span data-stu-id="52f8c-110">[StructureMap](http://structuremap.github.io/) *(deprecated)*</span></span>
- [<span data-ttu-id="52f8c-111">성 Windsor</span><span class="sxs-lookup"><span data-stu-id="52f8c-111">Castle Windsor</span></span>](http://www.castleproject.org/projects/windsor/)

<span data-ttu-id="52f8c-112">ASP.NET MVC 앱에서 DI를 사용 하지 않는 경우 ASP.NET Core에서 DI에 대 한 기본 제공 지원을 조사 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-112">If your ASP.NET MVC app isn't using DI, you will probably want to investigate the built-in support for DI in ASP.NET Core.</span></span> <span data-ttu-id="52f8c-113">DI는 앱에서 모듈의 느슨한 결합을 홍보 하 고 [SOLID](https://www.weeklydevtips.com/episodes/047)와 같은 원칙을 보다 효율적으로 테스트 하 고 준수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-113">DI promotes loose coupling of modules in your app and enables better testability and adherence to principles like [SOLID](https://www.weeklydevtips.com/episodes/047).</span></span>

<span data-ttu-id="52f8c-114">앱에서 DI를 사용 하는 경우 가장 좋은 조치는 사용 중인 컨테이너가 ASP.NET Core 지원 하는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-114">If your app does use DI, then probably your best course of action is to see if the container you're using supports ASP.NET Core.</span></span> <span data-ttu-id="52f8c-115">그럴 경우이를 계속 사용할 수 있으며, 형식 매핑과 수명을 설명 하는 사용자 지정 구성 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-115">If so, you may be able to continue using it and your custom configuration rules describing your type mappings and lifetimes.</span></span>

<span data-ttu-id="52f8c-116">어떤 방법을 사용 하 든, 앱의 요구를 충족할 수 있으므로 ASP.NET Core와 함께 제공 되는 DI에 대 한 기본 제공 지원을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-116">Either way, you should consider using the built-in support for DI that ships with ASP.NET Core, as it may meet your app's needs.</span></span>

## <a name="dependency-injection-in-aspnet-core"></a><span data-ttu-id="52f8c-117">ASP.NET Core에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="52f8c-117">Dependency injection in ASP.NET Core</span></span>

<span data-ttu-id="52f8c-118">ASP.NET Core 앱에서 DI를 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-118">ASP.NET Core assumes apps will use DI.</span></span> <span data-ttu-id="52f8c-119">이는 프레임 워크에 기본 제공 되지 않지만 프레임 워크 기능을 ASP.NET Core 앱에 대 한 지원을 제공 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-119">It's not just built into the framework, but is required in order to bring support for framework features into your ASP.NET Core apps.</span></span> <span data-ttu-id="52f8c-120">앱 시작 시 `ConfigureServices` DI 컨테이너 (서비스 컬렉션/서비스 공급자)가 앱에서 만들고 삽입할 수 있는 모든 형식을 등록 해야 하는 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-120">In app startup, a call is made to `ConfigureServices` which is responsible for registering all of the types that the DI container (service collection/service provider) can create and inject in the app.</span></span> <span data-ttu-id="52f8c-121">Entity Framework Core, Id 및 MVC와 같은 기본 제공 ASP.NET Core 기능은 메서드에서 서비스로 구성 하 여 앱으로 가져옵니다 `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="52f8c-121">Built-in ASP.NET Core features like Entity Framework Core, Identity, and even MVC are brought into the app by configuring them as services in the `ConfigureServices` method.</span></span>

<span data-ttu-id="52f8c-122">앱은 기본 구현을 사용 하는 것 외에도 사용자 지정 컨테이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-122">In addition to using the default implementation, apps can still use custom containers.</span></span> <span data-ttu-id="52f8c-123">[설명서에서는 기본 서비스 컨테이너를 바꾸는 방법을 설명](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement)합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-123">The [documentation covers how to replace the default service container](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement).</span></span>

<span data-ttu-id="52f8c-124">DI는 ASP.NET Core의 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-124">DI is fundamental to ASP.NET Core.</span></span> <span data-ttu-id="52f8c-125">팀이이 연습에서 아직 익숙한 되지 않은 경우 앱을 포팅 하기 전에 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f8c-125">If your team isn't already well-versed in this practice, you'll want to understand it before porting your app.</span></span>

## <a name="references"></a><span data-ttu-id="52f8c-126">참조</span><span class="sxs-lookup"><span data-stu-id="52f8c-126">References</span></span>

- [<span data-ttu-id="52f8c-127">.NET의 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="52f8c-127">Dependency Injection in .NET</span></span>](../../core/extensions/dependency-injection.md)
- [<span data-ttu-id="52f8c-128">ASP.NET Core의 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="52f8c-128">Dependency Injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)

>[!div class="step-by-step"]
><span data-ttu-id="52f8c-129">[이전](serving-static-files.md)
>[다음](middleware-modules-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="52f8c-129">[Previous](serving-static-files.md)
[Next](middleware-modules-handlers.md)</span></span>
