---
description: '자세한 정보: 검색 프록시 구현'
title: 검색 프록시 구현
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: cfd897e114c99bcacb24e9981ee4a3e99e06636c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734037"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="033ce-103">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="033ce-103">Implementing a Discovery Proxy</span></span>

<span data-ttu-id="033ce-104">이 단원에서는 검색 프록시를 구현하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-104">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="033ce-105">검색 프록시는 서비스의 리포지토리를 포함하는 독립 실행형 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-105">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="033ce-106">클라이언트는 검색 프록시를 쿼리하여 해당 검색 프록시가 인식하는 검색 가능한 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-106">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="033ce-107">프록시를 서비스로 채우는 방식은 구현자의 재량에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-107">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="033ce-108">예를 들어 검색 프록시가 기존 서비스 리포지토리에 연결하여 해당 정보를 검색 가능하게 만들거나, 관리자가 관리 API를 사용하여 프록시에 검색 가능한 서비스를 추가하거나, 검색 프록시가 알림 기능을 사용하여 해당 내부 캐시를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-108">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="033ce-109">WCF 구현은 프록시를 손쉽게 바인딩할 수 있는 기본 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-109">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="033ce-110">이러한 API를 사용하면 기존 리포지토리 위에 검색 프록시 헤드를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-110">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="033ce-111">여기서 구현된 검색 프록시도 다른 WCF 서비스와 마찬가지로 검색 가능하게 만들어 클라이언트가 해당 검색 프록시의 엔드포인트를 찾을 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-111">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="033ce-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="033ce-112">In This Section</span></span>  

 [<span data-ttu-id="033ce-113">방법: 검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="033ce-113">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="033ce-114">검색 프록시를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-114">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="033ce-115">방법: 검색 프록시에 등록할 검색 가능한 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="033ce-115">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="033ce-116">검색 프록시에 등록 하는 검색 가능한 WCF 서비스를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-116">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="033ce-117">방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="033ce-117">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="033ce-118">검색 프록시를 사용 하 여 서비스를 검색 하는 WCF 클라이언트 응용 프로그램을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-118">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="033ce-119">방법: 검색 프록시 테스트</span><span class="sxs-lookup"><span data-stu-id="033ce-119">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="033ce-120">이전 세 항목에서 작성한 코드를 테스트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="033ce-120">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033ce-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="033ce-121">See also</span></span>

- [<span data-ttu-id="033ce-122">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="033ce-122">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="033ce-123">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="033ce-123">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
