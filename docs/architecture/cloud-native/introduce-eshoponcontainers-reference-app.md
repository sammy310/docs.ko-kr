---
title: EShopOnContainers 참조 앱 소개
description: ASP.NET Core 및 Azure에 대 한 eShopOnContainers Cloud 기본 마이크로 서비스 참조 앱 소개
ms.date: 01/19/2021
ms.openlocfilehash: 35aa92794d8488c3de60f42af52654c4c26aad82
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505676"
---
# <a name="introducing-eshoponcontainers-reference-app"></a><span data-ttu-id="38f37-103">EShopOnContainers 참조 앱 소개</span><span class="sxs-lookup"><span data-stu-id="38f37-103">Introducing eShopOnContainers reference app</span></span>

<span data-ttu-id="38f37-104">Microsoft는 업계 최고의 커뮤니티 전문가와 협력 하 여 완전 한 기능을 갖춘 클라우드 기본 마이크로 서비스 참조 응용 프로그램 eShopOnContainers를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-104">Microsoft, in partnership with leading community experts, has produced a full-featured cloud-native microservices reference application, eShopOnContainers.</span></span> <span data-ttu-id="38f37-105">이 응용 프로그램은 .NET 및 Docker를 사용 하 고 필요에 따라 Azure, Kubernetes 및 Visual Studio를 사용 하 여 온라인 storefront를 빌드하기 위해 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-105">This application is built to showcase using .NET and Docker, and optionally Azure, Kubernetes, and Visual Studio, to build an online storefront.</span></span>

![eShopOnContainers 샘플 앱 스크린샷.](./media/eshoponcontainers-sample-app-screenshot.png)

<span data-ttu-id="38f37-107">**그림 2-1**.</span><span class="sxs-lookup"><span data-stu-id="38f37-107">**Figure 2-1**.</span></span> <span data-ttu-id="38f37-108">eShopOnContainers 샘플 앱 스크린샷.</span><span class="sxs-lookup"><span data-stu-id="38f37-108">eShopOnContainers Sample App Screenshot.</span></span>

<span data-ttu-id="38f37-109">이 챕터를 시작 하기 전에 [eShopOnContainers 참조 응용 프로그램](https://github.com/dotnet-architecture/eShopOnContainers)을 다운로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-109">Before starting this chapter, we recommend that you download the [eShopOnContainers reference application](https://github.com/dotnet-architecture/eShopOnContainers).</span></span> <span data-ttu-id="38f37-110">이렇게 하는 경우 제공 된 정보를 따라 작업을 수행 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-110">If you do so, it should be easier for you to follow along with the information presented.</span></span>

## <a name="features-and-requirements"></a><span data-ttu-id="38f37-111">기능 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="38f37-111">Features and requirements</span></span>

<span data-ttu-id="38f37-112">응용 프로그램의 기능 및 요구 사항에 대 한 검토를 시작 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-112">Let's start with a review of the application's features and requirements.</span></span> <span data-ttu-id="38f37-113">EShopOnContainers 응용 프로그램은 t-shirts 및 커피 머그잔와 같은 다양 한 물리적 제품을 판매 하는 온라인 상점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-113">The eShopOnContainers application represents an online store that sells various physical products like t-shirts and coffee mugs.</span></span> <span data-ttu-id="38f37-114">이전에 모든 항목을 구입한 경우 스토어를 사용 하는 환경은 상대적으로 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-114">If you've bought anything online before, the experience of using the store should be relatively familiar.</span></span> <span data-ttu-id="38f37-115">다음은 스토어에서 구현 하는 몇 가지 기본 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-115">Here are some of the basic features the store implements:</span></span>

- <span data-ttu-id="38f37-116">카탈로그 항목 나열</span><span class="sxs-lookup"><span data-stu-id="38f37-116">List catalog items</span></span>
- <span data-ttu-id="38f37-117">유형별로 항목 필터링</span><span class="sxs-lookup"><span data-stu-id="38f37-117">Filter items by type</span></span>
- <span data-ttu-id="38f37-118">브랜드 별 항목 필터링</span><span class="sxs-lookup"><span data-stu-id="38f37-118">Filter items by brand</span></span>
- <span data-ttu-id="38f37-119">시장 바구니에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="38f37-119">Add items to the shopping basket</span></span>
- <span data-ttu-id="38f37-120">바구니에서 항목 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="38f37-120">Edit or remove items from the basket</span></span>
- <span data-ttu-id="38f37-121">체크 아웃</span><span class="sxs-lookup"><span data-stu-id="38f37-121">Checkout</span></span>
- <span data-ttu-id="38f37-122">계정 등록</span><span class="sxs-lookup"><span data-stu-id="38f37-122">Register an account</span></span>
- <span data-ttu-id="38f37-123">로그인</span><span class="sxs-lookup"><span data-stu-id="38f37-123">Sign in</span></span>
- <span data-ttu-id="38f37-124">로그아웃</span><span class="sxs-lookup"><span data-stu-id="38f37-124">Sign out</span></span>
- <span data-ttu-id="38f37-125">주문 검토</span><span class="sxs-lookup"><span data-stu-id="38f37-125">Review orders</span></span>

<span data-ttu-id="38f37-126">응용 프로그램에는 다음과 같은 기능을 수행 하지 않는 요구 사항도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-126">The application also has the following non-functional requirements:</span></span>

- <span data-ttu-id="38f37-127">항상 사용 가능 해야 하며 증가 된 트래픽을 충족 하기 위해 자동으로 크기를 조정 해야 합니다 (그리고 트래픽 하위 면에서 한 번만 축소).</span><span class="sxs-lookup"><span data-stu-id="38f37-127">It needs to be highly available and it must scale automatically to meet increased traffic (and scale back down once traffic subsides).</span></span>
- <span data-ttu-id="38f37-128">발생 한 문제를 해결 하는 데 도움이 되는 상태 및 진단 로그에 대 한 사용 하기 쉬운 모니터링을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-128">It should provide easy-to-use monitoring of its health and diagnostic logs to help troubleshoot any issues it encounters.</span></span>
- <span data-ttu-id="38f37-129">CI/CD (연속 통합 및 배포) 지원을 포함 하 여 agile 개발 프로세스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-129">It should support an agile development process, including support for continuous integration and deployment (CI/CD).</span></span>
- <span data-ttu-id="38f37-130">응용 프로그램은 두 개의 웹 프런트 엔드 (기존 및 단일 페이지 응용 프로그램) 외에도 다양 한 종류의 운영 체제를 실행 하는 모바일 클라이언트 앱을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-130">In addition to the two web front ends (traditional and Single Page Application), the application must also support mobile client apps running different kinds of operating systems.</span></span>
- <span data-ttu-id="38f37-131">플랫폼 간 호스팅 및 플랫폼 간 개발을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-131">It should support cross-platform hosting and cross-platform development.</span></span>

![eShopOnContainers reference 응용 프로그램 개발 아키텍처.](./media/eshoponcontainers-development-architecture.png)

<span data-ttu-id="38f37-133">**그림 2-2**.</span><span class="sxs-lookup"><span data-stu-id="38f37-133">**Figure 2-2**.</span></span> <span data-ttu-id="38f37-134">eShopOnContainers reference 응용 프로그램 개발 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="38f37-134">eShopOnContainers reference application development architecture.</span></span>

<span data-ttu-id="38f37-135">EShopOnContainers 응용 프로그램은 ASP.NET Core MVC 서버 응용 프로그램 또는 적절 한 API 게이트웨이를 대상으로 하는 HTTPS를 통해 응용 프로그램에 액세스 하는 웹 또는 모바일 클라이언트에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-135">The eShopOnContainers application is accessible from web or mobile clients that access the application over HTTPS targeting either the ASP.NET Core MVC server application or an appropriate API Gateway.</span></span> <span data-ttu-id="38f37-136">API 게이트웨이는 개별 프런트 엔드 클라이언트에서 백 엔드 서비스를 분리 하 고 더 나은 보안을 제공 하는 것과 같은 여러 가지 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-136">API Gateways offer several advantages, such as decoupling back-end services from individual front-end clients and providing better security.</span></span> <span data-ttu-id="38f37-137">또한 응용 프로그램은 각 프런트 엔드 클라이언트에 대해 별도의 API 게이트웨이를 만드는 것을 권장 하는 백 엔드-프런트 엔드 (BFF) 라는 관련 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-137">The application also makes use of a related pattern known as Backends-for-Frontends (BFF), which recommends creating separate API gateways for each front-end client.</span></span> <span data-ttu-id="38f37-138">참조 아키텍처는 요청이 웹 또는 모바일 클라이언트에서 발생 하는지 여부에 따라 API 게이트웨이를 분리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-138">The reference architecture demonstrates breaking up the API gateways based on whether the request is coming from a web or mobile client.</span></span>

<span data-ttu-id="38f37-139">응용 프로그램의 기능은 다양 한 마이크로 서비스로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-139">The application's functionality is broken up into many distinct microservices.</span></span> <span data-ttu-id="38f37-140">인증 및 id를 담당 하 고, 제품 카탈로그에서 항목을 나열 하 고, 사용자의 쇼핑 바구니를 관리 하 고, 주문을 배치 하는 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-140">There are services responsible for authentication and identity, listing items from the product catalog, managing users' shopping baskets, and  placing orders.</span></span> <span data-ttu-id="38f37-141">이러한 각 개별 서비스에는 자체 영구 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-141">Each of these separate services has its own persistent storage.</span></span> <span data-ttu-id="38f37-142">모든 서비스가 상호 작용하는 단일 마스터 데이터 저장소는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-142">There's no single master data store with which all services interact.</span></span> <span data-ttu-id="38f37-143">대신, 필요에 따라 서비스와 메시지 버스를 사용 하 여 서비스 간의 조정 및 통신이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-143">Instead, coordination and communication between the services is done on an as-needed basis and by using a message bus.</span></span>

<span data-ttu-id="38f37-144">각 마이크로 서비스는 개별 요구 사항에 따라 다르게 디자인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-144">Each of the different microservices is designed differently, based on their individual requirements.</span></span> <span data-ttu-id="38f37-145">이러한 측면은 .NET을 사용 하 여 빌드하고 클라우드 용으로 설계 되었지만 기술 스택이 다를 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-145">This aspect means their technology stack may differ, although they're all built using .NET and designed for the cloud.</span></span> <span data-ttu-id="38f37-146">간단한 서비스는 기본 데이터 저장소에 대 한 기본 CRUD (만들기-읽기-업데이트-삭제) 액세스를 제공 하는 반면, 고급 서비스는 비즈니스 복잡성을 관리 하는 Domain-Driven 디자인 방법과 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-146">Simpler services provide basic Create-Read-Update-Delete (CRUD) access to the underlying data stores, while more advanced services use Domain-Driven Design approaches and patterns to manage business complexity.</span></span>

![다양 한 종류의 마이크로 서비스](./media/different-kinds-of-microservices.png)

<span data-ttu-id="38f37-148">**그림 2-3**.</span><span class="sxs-lookup"><span data-stu-id="38f37-148">**Figure 2-3**.</span></span> <span data-ttu-id="38f37-149">다양 한 종류의 마이크로 서비스.</span><span class="sxs-lookup"><span data-stu-id="38f37-149">Different kinds of microservices.</span></span>

## <a name="overview-of-the-code"></a><span data-ttu-id="38f37-150">코드 개요</span><span class="sxs-lookup"><span data-stu-id="38f37-150">Overview of the code</span></span>

<span data-ttu-id="38f37-151">마이크로 서비스를 사용 하기 때문에 eShopOnContainers 앱은 GitHub 리포지토리에서 매우 많은 개별 프로젝트와 솔루션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-151">Because it uses microservices, the eShopOnContainers app includes quite a few separate projects and solutions in its GitHub repository.</span></span> <span data-ttu-id="38f37-152">별도의 솔루션 및 실행 파일 외에도 다양 한 서비스는 로컬 개발 및 프로덕션 환경에서 자체 컨테이너 내에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-152">In addition to separate solutions and executable files, the various services are designed to run inside their own containers, both during local development and at runtime in production.</span></span> <span data-ttu-id="38f37-153">그림 2-4에는 다양 한 프로젝트를 구성 하는 전체 Visual Studio 솔루션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-153">Figure 2-4 shows the full Visual Studio solution, in which the various different projects are organized.</span></span>

![Visual Studio 솔루션의 프로젝트](./media/projects-in-visual-studio-solution.png)

<span data-ttu-id="38f37-155">**그림 2-4**.</span><span class="sxs-lookup"><span data-stu-id="38f37-155">**Figure 2-4**.</span></span> <span data-ttu-id="38f37-156">Visual Studio 솔루션의 프로젝트</span><span class="sxs-lookup"><span data-stu-id="38f37-156">Projects in Visual Studio solution.</span></span>

<span data-ttu-id="38f37-157">코드는 다양 한 마이크로 서비스를 지원 하도록 구성 되 고, 각 마이크로 서비스 내에서 코드는 도메인 논리, 인프라 문제, 사용자 인터페이스 또는 서비스 끝점으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-157">The code is organized to support the different microservices, and within each microservice, the code is broken up into domain logic, infrastructure concerns, and user interface or service endpoint.</span></span> <span data-ttu-id="38f37-158">대부분의 경우 각 서비스의 종속성은 프로덕션의 Azure 서비스 및 로컬 개발을 위한 대체 옵션으로 충족 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-158">In many cases, each service's dependencies can be fulfilled by Azure services in production, and alternative options for local development.</span></span> <span data-ttu-id="38f37-159">응용 프로그램의 요구 사항이 Azure 서비스에 매핑되는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-159">Let's examine how the application's requirements map to Azure services.</span></span>

## <a name="understanding-microservices"></a><span data-ttu-id="38f37-160">마이크로서비스 이해</span><span class="sxs-lookup"><span data-stu-id="38f37-160">Understanding microservices</span></span>

<span data-ttu-id="38f37-161">이 책에서는 Azure 기술을 사용 하 여 구축 된 클라우드 네이티브 응용 프로그램에 중점을 둘 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38f37-161">This book focuses on cloud-native applications built using Azure technology.</span></span> <span data-ttu-id="38f37-162">마이크로 서비스 모범 사례 및 마이크로 서비스 기반 응용 프로그램을 설계 하는 방법에 대 한 자세한 내용은 부록 설명서 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38f37-162">To learn more about microservices best practices and how to architect microservice-based applications, read the companion book, [.NET Microservices: Architecture for Containerized .NET Applications](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="38f37-163">[이전](candidate-apps.md)
>[다음](map-eshoponcontainers-azure-services.md)</span><span class="sxs-lookup"><span data-stu-id="38f37-163">[Previous](candidate-apps.md)
[Next](map-eshoponcontainers-azure-services.md)</span></span>
