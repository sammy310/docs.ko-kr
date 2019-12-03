---
title: 검색 라우터 서비스
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 09309b23d2a3cc672811c2f617e6fb81a2b4e021
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74712293"
---
# <a name="discovery-router-service"></a><span data-ttu-id="d606f-102">검색 라우터 서비스</span><span class="sxs-lookup"><span data-stu-id="d606f-102">Discovery Router Service</span></span>
<span data-ttu-id="d606f-103">이 샘플에서는 검색 메시지를 다른 엔드포인트에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d606f-104">데모</span><span class="sxs-lookup"><span data-stu-id="d606f-104">Demonstrates</span></span>  
 <span data-ttu-id="d606f-105">검색 라우팅</span><span class="sxs-lookup"><span data-stu-id="d606f-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d606f-106">토론</span><span class="sxs-lookup"><span data-stu-id="d606f-106">Discussion</span></span>  
 <span data-ttu-id="d606f-107">클라이언트에서 프록시를 사용하여 서비스를 찾으려고 하며 프록시에서는 이러한 서비스를 인식하지 못하지만 다른 프록시는 인식하는 경우에 검색 라우팅이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="d606f-108">이 프록시에서는 이 클라이언트의 검색 패킷을 두 번째 프록시에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="d606f-109">두 번째 프록시에서는 서비스를 찾고 원래 클라이언트에 응답을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="d606f-110">이 샘플의 클라이언트에서는 검색 라우팅 구성 요소에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="d606f-111">이 메시지는 검색 라우터의 특정 엔드포인트에 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="d606f-112">그런 다음 라우터에서 해당 메시지를 UDP 멀티캐스트 엔드포인트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="d606f-113">프로브 메시지는 멀티캐스트 엔드포인트로 이동하며 UDP 멀티캐스트 주소에서 수신 대기하는 서비스는 해당 검색 라우터에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="d606f-114">검색 라우터에서는 응답을 수집하여 클라이언트로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d606f-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d606f-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d606f-116">샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-116">Build the sample.</span></span>  
  
2. <span data-ttu-id="d606f-117">DiscoveryRouter 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-117">Run the DiscoveryRouter executable.</span></span>  
  
3. <span data-ttu-id="d606f-118">빌드 디렉터리에서 서비스 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-118">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="d606f-119">클라이언트 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-119">Run the client executable.</span></span> <span data-ttu-id="d606f-120">그러면 클라이언트에서는 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d606f-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d606f-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d606f-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="d606f-123">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d606f-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d606f-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
