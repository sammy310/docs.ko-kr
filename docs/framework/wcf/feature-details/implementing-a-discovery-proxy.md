---
title: 검색 프록시 구현
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141006"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="0028c-102">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="0028c-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="0028c-103">이 단원에서는 검색 프록시를 구현하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="0028c-104">검색 프록시는 서비스의 리포지토리를 포함하는 독립 실행형 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="0028c-105">클라이언트는 검색 프록시를 쿼리하여 해당 검색 프록시가 인식하는 검색 가능한 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="0028c-106">프록시를 서비스로 채우는 방식은 구현자의 재량에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="0028c-107">예를 들어 검색 프록시가 기존 서비스 리포지토리에 연결하여 해당 정보를 검색 가능하게 만들거나, 관리자가 관리 API를 사용하여 프록시에 검색 가능한 서비스를 추가하거나, 검색 프록시가 알림 기능을 사용하여 해당 내부 캐시를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="0028c-108">WCF 구현은 프록시를 손쉽게 바인딩할 수 있는 기본 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="0028c-109">이러한 API를 사용하면 기존 리포지토리 위에 검색 프록시 헤드를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="0028c-110">여기서 구현된 검색 프록시도 다른 WCF 서비스와 마찬가지로 검색 가능하게 만들어 클라이언트가 해당 검색 프록시의 엔드포인트를 찾을 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0028c-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0028c-111">In This Section</span></span>  
 [<span data-ttu-id="0028c-112">방법: 검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="0028c-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="0028c-113">검색 프록시를 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="0028c-114">방법: 검색 프록시에 등록할 검색 가능한 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="0028c-115">검색 프록시에 등록할 검색 가능한 WCF 서비스를 구현 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="0028c-116">방법: 검색 프록시를 사용 하 여 서비스를 검색 하는 클라이언트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="0028c-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="0028c-117">서비스에 대 한 검색 하려면 검색 프록시를 사용 하는 WCF 클라이언트 응용 프로그램을 구현 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="0028c-118">방법: 검색 프록시 테스트</span><span class="sxs-lookup"><span data-stu-id="0028c-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="0028c-119">이전 세 항목에서 작성한 코드를 테스트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0028c-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0028c-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="0028c-120">See also</span></span>

- [<span data-ttu-id="0028c-121">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="0028c-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [<span data-ttu-id="0028c-122">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="0028c-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
