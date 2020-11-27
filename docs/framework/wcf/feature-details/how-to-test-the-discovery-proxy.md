---
title: '방법: 검색 프록시 테스트'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: b08e8561ceff9f0a427a9ea9acb2309772579853
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294666"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="3b869-102">방법: 검색 프록시 테스트</span><span class="sxs-lookup"><span data-stu-id="3b869-102">How to: Test the Discovery Proxy</span></span>

<span data-ttu-id="3b869-103">이 항목은 검색 프록시를 구현하는 방법에 대해 설명하는 네 항목 중 네 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="3b869-104">이전 항목인 [방법: 검색 프록시를 사용 하 여 서비스를 찾는 클라이언트 응용 프로그램 구현](client-app-discovery-proxy-to-find-a-service.md)에서는 검색 프록시를 사용 하 여 서비스를 찾은 다음 서비스를 호출 하는 WCF 클라이언트 응용 프로그램을 구현 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="3b869-105">이 항목에서는 검색 프록시, 서비스 및 클라이언트 애플리케이션이 올바로 작동하는지 확인하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="3b869-106">검색 프록시 실행</span><span class="sxs-lookup"><span data-stu-id="3b869-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="3b869-107">관리자 권한으로 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="3b869-108">"Windows 방화벽에서 이 프로그램의 일부 기능을 차단했습니다."라는 메시지가 포함된 대화 상자가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="3b869-109">이 메시지가 표시 되 면 **차단 해제** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="3b869-110">명령 프롬프트 내에서 검색 프록시인 DiscoveryProxy.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="3b869-111">DiscoveryProxy.exe에 다음 텍스트가 표시됩니다. `Proxy started. Hit Enter to exit`</span><span class="sxs-lookup"><span data-stu-id="3b869-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="3b869-112">검색 가능한 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="3b869-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="3b869-113">관리자 권한으로 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="3b869-114">명령 프롬프트 내에서 검색 가능한 서비스인 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="3b869-115">DiscoveryProxy.exe에 다음 텍스트가 표시 됩니다 `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` ..</span><span class="sxs-lookup"><span data-stu-id="3b869-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="3b869-116">클라이언트 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="3b869-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="3b869-117">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="3b869-118">명령 프롬프트 내에서 클라이언트 애플리케이션인 client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="3b869-119">몇 초 후에 클라이언트 애플리케이션에 &quot;Connecting to [Service-Endpoint]&quot;라는 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="3b869-120">service.exe에 "Greeting request received, I will respond."라는 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="3b869-121">client.exe에 "Hello Client!"라는 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="3b869-122">애플리케이션 종료</span><span class="sxs-lookup"><span data-stu-id="3b869-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="3b869-123">클라이언트 애플리케이션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="3b869-124">서비스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-124">Shut down the service.</span></span> <span data-ttu-id="3b869-125">검색 프록시에 다음 텍스트가 표시됩니다. `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`</span><span class="sxs-lookup"><span data-stu-id="3b869-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="3b869-126">검색 프록시를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b869-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b869-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b869-127">See also</span></span>

- [<span data-ttu-id="3b869-128">WCF Discovery 개요</span><span class="sxs-lookup"><span data-stu-id="3b869-128">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="3b869-129">방법: 검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="3b869-129">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="3b869-130">방법: 검색 프록시에 등록할 검색 가능한 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="3b869-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="3b869-131">방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="3b869-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
