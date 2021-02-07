---
description: '다음에 대 한 자세한 정보: Windows Communication Foundation 보안'
title: Windows Communication Foundation 보안
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 8cf748504c85844f82f8941be1b60bb29478f730
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726795"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="6dd11-103">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="6dd11-103">Windows Communication Foundation Security</span></span>

<span data-ttu-id="6dd11-104">이 섹션의 항목에서는 WCF (Windows Communication Foundation) 보안 기능 및 이러한 기능을 사용 하 여 메시지를 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-104">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="6dd11-105">Windows Server AppFabric 및 보안에 대 한 자세한 내용은 [Windows Server Appfabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10)) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dd11-105">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dd11-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6dd11-106">In This Section</span></span>  

 [<span data-ttu-id="6dd11-107">보안 개요</span><span class="sxs-lookup"><span data-stu-id="6dd11-107">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="6dd11-108">WCF의 보안 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-108">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="6dd11-109">보안 개념</span><span class="sxs-lookup"><span data-stu-id="6dd11-109">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="6dd11-110">WCF 보안에 사용 되는 기본 용어 및 개념을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-110">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="6dd11-111">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="6dd11-111">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="6dd11-112">WCF를 사용 하 여 구성할 수 있는 시나리오 및 토폴로지를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-112">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="6dd11-113">보안 동작</span><span class="sxs-lookup"><span data-stu-id="6dd11-113">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="6dd11-114">보안에 영향을 주는 WCF 동작에 대한 개요를 제공합니다(예: 자격 증명 설정).</span><span class="sxs-lookup"><span data-stu-id="6dd11-114">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="6dd11-115">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="6dd11-115">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="6dd11-116">사용자 지정 보안 바인딩을 만드는 방법을 보여 주는 항목을 비롯한 바인딩의 보안 지향적인 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-116">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="6dd11-117">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6dd11-117">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="6dd11-118">WCF 보안 기능을 사용 하 여 메시지를 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-118">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="6dd11-119">인증</span><span class="sxs-lookup"><span data-stu-id="6dd11-119">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="6dd11-120">일반적인 인증 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-120">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="6dd11-121">권한 부여</span><span class="sxs-lookup"><span data-stu-id="6dd11-121">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="6dd11-122">보안 구현을 사용하여 일반적인 인증 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-122">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="6dd11-123">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="6dd11-123">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="6dd11-124">페더레이션 기본 사항 및 페더레이션 서버와 통신하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-124">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="6dd11-125">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="6dd11-125">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="6dd11-126">부분적으로 신뢰할 수 있는 시나리오를 실행 하는 경우 부분적으로 신뢰할 수 있는 시나리오 및 WCF 제한을 실행 하는 방법을 설명</span><span class="sxs-lookup"><span data-stu-id="6dd11-126">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="6dd11-127">감사</span><span class="sxs-lookup"><span data-stu-id="6dd11-127">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="6dd11-128">보안 이벤트를 감사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-128">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="6dd11-129">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="6dd11-129">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="6dd11-130">보안 WCF 응용 프로그램을 만드는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="6dd11-130">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6dd11-131">참고</span><span class="sxs-lookup"><span data-stu-id="6dd11-131">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="6dd11-132">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6dd11-132">Related Sections</span></span>  

 [<span data-ttu-id="6dd11-133">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="6dd11-133">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="6dd11-134">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6dd11-134">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="6dd11-135">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="6dd11-135">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="6dd11-136">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="6dd11-136">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dd11-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dd11-137">See also</span></span>

- [<span data-ttu-id="6dd11-138">애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="6dd11-138">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
