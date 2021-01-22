---
title: 마이크로 서비스 주소 지정 기능 및 서비스 레지스트리
description: 마이크로 서비스 아키텍처에서 컨테이너 이미지 레지스트리의 역할을 이해합니다.
ms.date: 01/13/2021
ms.openlocfilehash: 363a307d44d30125563863bbe3ebeb5f5b9ad2bc
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188415"
---
# <a name="microservices-addressability-and-the-service-registry"></a><span data-ttu-id="47c51-103">마이크로 서비스 주소 지정 기능 및 서비스 레지스트리</span><span class="sxs-lookup"><span data-stu-id="47c51-103">Microservices addressability and the service registry</span></span>

<span data-ttu-id="47c51-104">각 마이크로 서비스에는 해당 위치를 확인하는 데 사용되는 고유한 이름(URL)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-104">Each microservice has a unique name (URL) that's used to resolve its location.</span></span> <span data-ttu-id="47c51-105">마이크로 서비스는 어디서 실행되든지 주소 지정 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-105">Your microservice needs to be addressable wherever it's running.</span></span> <span data-ttu-id="47c51-106">특정 마이크로 서비스를 실행 중인 컴퓨터에 대해 고려해야 하는 경우 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-106">If you have to think about which computer is running a particular microservice, things can go bad quickly.</span></span> <span data-ttu-id="47c51-107">현재 위치를 검색할 수 있도록 DNS가 특정 컴퓨터에 대한 URL을 확인하는 것과 동일한 방법으로 마이크로 서비스에 고유한 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-107">In the same way that DNS resolves a URL to a particular computer, your microservice needs to have a unique name so that its current location is discoverable.</span></span> <span data-ttu-id="47c51-108">마이크로 서비스에는 실행되는 인프라와 독립적인 주소 지정 가능 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-108">Microservices need addressable names that make them independent from the infrastructure that they're running on.</span></span> <span data-ttu-id="47c51-109">해당 접근 방식은 [서비스 레지스트리](https://microservices.io/patterns/service-registry.html)가 있어야 하기 때문에 서비스 배포 방법과 검색 방법 간에 상호 작용이 필요함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-109">This approach implies that there's an interaction between how your service is deployed and how it's discovered, because there needs to be a [service registry](https://microservices.io/patterns/service-registry.html).</span></span> <span data-ttu-id="47c51-110">동일한 맥락에서 한 컴퓨터가 실패하는 경우 레지스트리 서비스는 서비스가 지금 실행 중인 위치를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-110">In the same vein, when a computer fails, the registry service must be able to indicate where the service is now running.</span></span>

<span data-ttu-id="47c51-111">[서비스 레지스트리 패턴](https://microservices.io/patterns/service-registry.html)은 서비스 검색의 핵심 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-111">The [service registry pattern](https://microservices.io/patterns/service-registry.html) is a key part of service discovery.</span></span> <span data-ttu-id="47c51-112">레지스트리는 서비스 인스턴스의 네트워크 위치를 포함하는 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-112">The registry is a database containing the network locations of service instances.</span></span> <span data-ttu-id="47c51-113">서비스 레지스트리는 항상 사용 가능하고 최신 상태를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-113">A service registry needs to be highly available and up-to-date.</span></span> <span data-ttu-id="47c51-114">클라이언트는 서비스 레지스트리에서 가져온 네트워크 위치를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-114">Clients could cache network locations obtained from the service registry.</span></span> <span data-ttu-id="47c51-115">그러나 해당 정보가 결국 만료되고 클라이언트는 서비스 인스턴스를 더 이상 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-115">However, that information eventually goes out of date and clients can no longer discover service instances.</span></span> <span data-ttu-id="47c51-116">따라서 서비스 레지스트리는 복제 프로토콜을 사용하여 일관성을 유지하는 서버 클러스터로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-116">So, a service registry consists of a cluster of servers that use a replication protocol to maintain consistency.</span></span>

<span data-ttu-id="47c51-117">일부 마이크로 서비스 배포 환경(이후 섹션에서 다루는 클러스터라고 함)에서 서비스 검색은 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-117">In some microservice deployment environments (called clusters, to be covered in a later section), service discovery is built in.</span></span> <span data-ttu-id="47c51-118">예를 들어 Kubernetes(AKS) 환경을 갖춘 Azure Container Service는 서비스 인스턴스 등록 및 등록 취소를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-118">For example, an Azure Container Service with Kubernetes (AKS) environment can handle service instance registration and deregistration.</span></span> <span data-ttu-id="47c51-119">또한 서버 쪽 검색 라우터의 역할을 수행하는 각 클러스터 호스트에서 프록시를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47c51-119">It also runs a proxy on each cluster host that plays the role of server-side discovery router.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47c51-120">추가 자료</span><span class="sxs-lookup"><span data-stu-id="47c51-120">Additional resources</span></span>

- <span data-ttu-id="47c51-121">**Chris Richardson. 패턴: 서비스 레지스트리** </span><span class="sxs-lookup"><span data-stu-id="47c51-121">**Chris Richardson. Pattern: Service registry** </span></span>\
  <https://microservices.io/patterns/service-registry.html>

- <span data-ttu-id="47c51-122">**Auth0 서비스 레지스트리** </span><span class="sxs-lookup"><span data-stu-id="47c51-122">**Auth0. The Service Registry** </span></span>\
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- <span data-ttu-id="47c51-123">**Gabriel Schenker 서비스 검색** </span><span class="sxs-lookup"><span data-stu-id="47c51-123">**Gabriel Schenker. Service discovery** </span></span>\
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
><span data-ttu-id="47c51-124">[이전](maintain-microservice-apis.md)
>[다음](microservice-based-composite-ui-shape-layout.md)</span><span class="sxs-lookup"><span data-stu-id="47c51-124">[Previous](maintain-microservice-apis.md)
[Next](microservice-based-composite-ui-shape-layout.md)</span></span>
