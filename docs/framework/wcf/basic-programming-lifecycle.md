---
title: 기본 프로그래밍 수명 주기
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: 6d9ea3b877e7c735cf789039b2a6956037372888
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782410"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="55509-102">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="55509-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="55509-103">Windows Communication Foundation (WCF) 응용 프로그램이 다른 응용 프로그램 플랫폼 또는 인터넷을 통해 컴퓨터의 동일한 지 여부를 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55509-103">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="55509-104">이 항목에서는 WCF 응용 프로그램을 빌드하는 데 필요한 작업을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-104">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="55509-105">작업 샘플 응용 프로그램을 참조 하세요 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="55509-106">기본 작업</span><span class="sxs-lookup"><span data-stu-id="55509-106">The Basic Tasks</span></span>  
 <span data-ttu-id="55509-107">수행할 기본 작업 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55509-107">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="55509-108">서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-108">Define the service contract.</span></span> <span data-ttu-id="55509-109">서비스 계약은 서비스 서명, 서비스 교환 날짜 및 계약에 필요한 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="55509-110">자세한 내용은 [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-110">For more information, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="55509-111">계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-111">Implement the contract.</span></span> <span data-ttu-id="55509-112">서비스 계약을 구현하려면 계약을 구현하는 클래스를 만들고 런타임에 필요한 사용자 지정 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="55509-113">자세한 내용은 [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-113">For more information, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="55509-114">엔드포인트 및 기타 동작 정보를 지정하여 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="55509-115">자세한 내용은 [서비스 구성](../../../docs/framework/wcf/configuring-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-115">For more information, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4. <span data-ttu-id="55509-116">서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-116">Host the service.</span></span> <span data-ttu-id="55509-117">자세한 내용은 [호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-117">For more information, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5. <span data-ttu-id="55509-118">클라이언트 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-118">Build a client application.</span></span> <span data-ttu-id="55509-119">자세한 내용은 [클라이언트 빌드](../../../docs/framework/wcf/building-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-119">For more information, see [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="55509-120">이 단원의 항목은 이 순서를 따르지만 일부 시나리오에서는 첫 번째 단계부터 시작하지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55509-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="55509-121">예를 들어 기존 서비스에 대한 클라이언트를 빌드하려면 5단계에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="55509-122">다른 사용자가 사용할 서비스를 빌드하는 경우 5단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="55509-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="55509-123">서비스 계약 개발에 익숙한 控 制 참조할 수 있습니다 [확장성 소개](../../../docs/framework/wcf/introduction-to-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="55509-124">서비스에 문제가 있으면 확인 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) 다른 같은 문제나 비슷한 문제가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55509-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55509-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="55509-125">See also</span></span>

- [<span data-ttu-id="55509-126">서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="55509-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
