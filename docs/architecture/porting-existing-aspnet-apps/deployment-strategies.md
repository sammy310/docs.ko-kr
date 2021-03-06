---
title: 배포 전략
description: ASP.NET에서 ASP.NET Core로 마이그레이션하는 동안 팀에서 사용할 수 있는 배포 전략은 무엇 인가요? 증분 마이그레이션은 원활한 최종 사용자 환경을 제공 하 여 .NET Framework 및 .NET Core 앱의 병렬 배포를 가능 하 게 할 수 있나요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 6691a4878205d6422cf8b6153353abefd9764d18
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401771"
---
# <a name="deployment-strategies"></a><span data-ttu-id="dd6b1-104">배포 전략</span><span class="sxs-lookup"><span data-stu-id="dd6b1-104">Deployment strategies</span></span>

<span data-ttu-id="dd6b1-105">ASP.NET Core에 대 한 대량 ASP.NET 앱의 마이그레이션을 계획할 때 고려해 야 할 사항은 새 앱을 배포 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-105">One consideration as you plan the migration of your large ASP.NET app to ASP.NET Core is how you'll deploy the new app.</span></span> <span data-ttu-id="dd6b1-106">ASP.NET를 사용 하 여 배포 옵션은 Windows의 IIS로 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-106">With ASP.NET, deployment options were limited to IIS on Windows.</span></span> <span data-ttu-id="dd6b1-107">ASP.NET Core를 사용 하면 훨씬 더 광범위 한 배포 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-107">With ASP.NET Core, a much wider array of deployment options is available.</span></span>

## <a name="cross-platform-options"></a><span data-ttu-id="dd6b1-108">플랫폼 간 옵션</span><span class="sxs-lookup"><span data-stu-id="dd6b1-108">Cross-platform options</span></span>

<span data-ttu-id="dd6b1-109">.NET Core는 Linux에서 실행 되기 때문에 이전에 고려 하지 않은 일부 호스팅 옵션을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-109">Because .NET Core runs on Linux, you'll find some hosting options available that weren't a consideration previously.</span></span> <span data-ttu-id="dd6b1-110">Linux 기반 호스트는 다음과 같은 경우에 더 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-110">Linux-based hosting may be preferable for the following reasons:</span></span>

* <span data-ttu-id="dd6b1-111">조직에 인프라 또는 전문 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-111">Your organization has infrastructure or expertise.</span></span>
* <span data-ttu-id="dd6b1-112">호스팅 공급자는 Linux 기반 호스팅을 위한 매력적인 기능 또는 가격 책정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-112">Hosting providers offer attractive features or pricing for Linux-based hosting.</span></span>

<span data-ttu-id="dd6b1-113">이러한 옵션에 대 한 도어를 위한 .NET Core가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-113">.NET Core opens to door to these options.</span></span>

## <a name="cloud-native-development"></a><span data-ttu-id="dd6b1-114">클라우드 네이티브 개발</span><span class="sxs-lookup"><span data-stu-id="dd6b1-114">Cloud native development</span></span>

<span data-ttu-id="dd6b1-115">오늘날 대부분의 조직에서는 소프트웨어 기능 중 일부에 대해 클라우드 플랫폼을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-115">Most organizations today are using cloud platforms for at least some of their software capabilities.</span></span> <span data-ttu-id="dd6b1-116">앱을 .NET Core로 마이그레이션하는 경우 앱을 클라우드 호스팅을 염두에 두면 의도적으로 작성 해야 하는지 여부를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-116">With an app migration to .NET Core, it's a good time to consider whether the app should be purposefully written with cloud hosting in mind.</span></span> <span data-ttu-id="dd6b1-117">이러한 *클라우드 네이티브* 앱은 서버를 사용 하지 않는, 마이크로 서비스 등의 클라우드 기능을 보다 효율적으로 적용할 수 있으며 배포 하는 방법 및 위치에 대 한 하위 수준 세부 정보에는 관심이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-117">Such *cloud native* apps are better able to apply cloud capabilities like serverless, microservices, and can be less concerned with the low-level details of how and where they may be deployed.</span></span>

<span data-ttu-id="dd6b1-118">[Azure에 대 한 클라우드 네이티브 .Net 응용 프로그램을 설계](../cloud-native/index.md)하 여이 무료 e-learning에서 클라우드 네이티브 앱 개발에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-118">Learn more about cloud native app development in this free e-book, [Architecting Cloud Native .NET Applications for Azure](../cloud-native/index.md).</span></span>

## <a name="leverage-containers"></a><span data-ttu-id="dd6b1-119">컨테이너 활용</span><span class="sxs-lookup"><span data-stu-id="dd6b1-119">Leverage containers</span></span>

<span data-ttu-id="dd6b1-120">최신 앱은 호스트 환경 간의 변형을 줄이기 위해 컨테이너를 활용 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-120">Modern apps often leverage containers as a means of reducing variation between hosting environments.</span></span> <span data-ttu-id="dd6b1-121">특정 컨테이너에 앱을 배포 하면 컨테이너에서 호스트 되는 앱은 개발자의 랩톱이 나 프로덕션 환경에서 실행 되는 경우와 동일 하 게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-121">By deploying an app to a particular container, the container-hosted app will run the same whether it's running on a developer's laptop or in production.</span></span> <span data-ttu-id="dd6b1-122">.Net Core로 마이그레이션하는 과정의 일환으로 앱이 컨테이너를 통해 컨테이너를 통해 배포 하는 것이 좋습니다. 전체 모놀리식로 또는 여러 개의 작은 컨테이너 화 된 apps로 분할 되어 있는지를 고려 하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-122">As part of a migration to .NET Core, it may make sense to consider whether the app would benefit from deployment via container, either as a full monolith or broken up into multiple smaller containerized apps.</span></span>

## <a name="side-by-side-deployment-options"></a><span data-ttu-id="dd6b1-123">Side-by-side 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="dd6b1-123">Side-by-side deployment options</span></span>

<span data-ttu-id="dd6b1-124">큰 .NET Framework 앱을 .NET Core로 마이그레이션하려면 상당한 노력이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-124">Migrating large .NET Framework apps to .NET Core often requires a substantial effort.</span></span> <span data-ttu-id="dd6b1-125">대부분의 조직에서는 전체 마이그레이션이 완료 되기 전에 프로덕션 환경에서 앱을 마이그레이션 및 배포할 수 있도록이 작업을 특정 방식으로 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-125">Most organizations will want to be able to break this effort up in some fashion, so that pieces of the app can be migrated and deployed in production before the entire migration is complete.</span></span> <span data-ttu-id="dd6b1-126">원래 ASP.NET 앱과 새로 마이그레이션된 ASP.NET Core 하위 앱을 나란히 실행 하는 것은 흔히 명시 된 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-126">Running both the original ASP.NET app and its newly-migrated ASP.NET Core sub-app(s) side by side is a frequently cited goal.</span></span> <span data-ttu-id="dd6b1-127">이는 [5 장에서](deployment-scenarios.md)설명 하는 IIS 라우팅 활용을 포함 하 여 다양 한 메커니즘을 통해 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-127">This can be achieved through a number of mechanisms including leveraging IIS routing, which is covered in [chapter 5](deployment-scenarios.md).</span></span> <span data-ttu-id="dd6b1-128">다른 옵션으로는 [프런트 엔드의 백 엔드](/azure/architecture/patterns/backends-for-frontends) 와 같은 앱 게이트웨이 또는 클라우드 디자인 패턴을 활용 하 여 ASP.NET 웹 api와 ASP.NET Core API 끝점의 집합을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-128">Other options include leveraging app gateways or cloud design patterns like [backends for frontends](/azure/architecture/patterns/backends-for-frontends) to manage sets of ASP.NET Web APIs and ASP.NET Core API endpoints.</span></span>

## <a name="iis-on-windows"></a><span data-ttu-id="dd6b1-129">Windows의 IIS</span><span class="sxs-lookup"><span data-stu-id="dd6b1-129">IIS on Windows</span></span>

<span data-ttu-id="dd6b1-130">Windows에서 실행 되는 IIS에서 앱을 계속 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-130">You can continue hosting your apps on IIS running on Windows.</span></span> <span data-ttu-id="dd6b1-131">이 옵션은 현재 배포 모델을 변경 하지 않고 ASP.NET Core 기능을 활용 하려는 고객을 위한 적절 한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-131">This is a fine option for customers who want to take advantage of ASP.NET Core features without changing their current deployment model.</span></span> <span data-ttu-id="dd6b1-132">ASP.NET Core로 이동 하는 것은 앱을 배포 하는 방법 및 위치와 관련 하 여 더 많은 옵션을 제공 하는 반면, Windows의 검증 된 IIS 조합을 사용 하는 상태에서 변경 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-132">While moving to ASP.NET Core provides more options in terms of how and where to deploy your apps, it doesn't require that you change from the status quo of using the proven combination of IIS on Windows.</span></span>

## <a name="other-options-on-windows"></a><span data-ttu-id="dd6b1-133">Windows의 기타 옵션</span><span class="sxs-lookup"><span data-stu-id="dd6b1-133">Other options on Windows</span></span>

<span data-ttu-id="dd6b1-134">필요한 경우 Docker 컨테이너 뿐만 아니라 Kestrel, HTTP.sys 및 IIS 호스트의 조합을 사용 하 여 Windows에서 앱 side-by-side 앱을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-134">You can host apps side-by-side apps on Windows using any combination of Kestrel, HTTP.sys, and IIS hosts, in addition to Docker containers, if needed.</span></span> <span data-ttu-id="dd6b1-135">응용 프로그램에 Windows 및 Linux 서비스 조합이 필요한 경우 [Wsl](/windows/wsl/about) 및/또는 linux Docker 컨테이너를 사용 하 여 windows 서버에서 호스팅하면 앱의 모든 부분을 호스트 하는 단일 서버 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd6b1-135">If your app requires a combination of Windows and Linux services, hosting on a Windows server with [WSL](/windows/wsl/about) and/or Linux Docker containers provides a single server solution to hosting all parts of the app.</span></span>

## <a name="references"></a><span data-ttu-id="dd6b1-136">참조</span><span class="sxs-lookup"><span data-stu-id="dd6b1-136">References</span></span>

- [<span data-ttu-id="dd6b1-137">호스트 및 배포 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dd6b1-137">Host and deploy ASP.NET Core</span></span>](/aspnet/core/host-and-deploy/)
- [<span data-ttu-id="dd6b1-138">IIS가 있는 Windows에서 ASP.NET Core 호스팅</span><span class="sxs-lookup"><span data-stu-id="dd6b1-138">Host ASP.NET Core on Windows with IIS</span></span>](/aspnet/core/host-and-deploy/iis/)
- [<span data-ttu-id="dd6b1-139">Azure App Service 및 IIS에 대 한 ASP.NET Core 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dd6b1-139">Troubleshooting ASP.NET Core on Azure App Service and IIS</span></span>](/aspnet/core/test/troubleshoot-azure-iis)

>[!div class="step-by-step"]
><span data-ttu-id="dd6b1-140">[이전](migrate-web-forms.md)
>[다음](additional-migration-resources.md)</span><span class="sxs-lookup"><span data-stu-id="dd6b1-140">[Previous](migrate-web-forms.md)
[Next](additional-migration-resources.md)</span></span>
