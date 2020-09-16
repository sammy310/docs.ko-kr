---
title: Windows Communication Foundation 보안
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 9498358dd480487afcd3b746d14266e486c62d71
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546317"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="96545-102">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="96545-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="96545-103">이 섹션의 항목에서는 WCF (Windows Communication Foundation) 보안 기능 및 이러한 기능을 사용 하 여 메시지를 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="96545-104">Windows Server AppFabric 및 보안에 대 한 자세한 내용은 [Windows Server Appfabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10)) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96545-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96545-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="96545-105">In This Section</span></span>  
 [<span data-ttu-id="96545-106">보안 개요</span><span class="sxs-lookup"><span data-stu-id="96545-106">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="96545-107">WCF의 보안 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="96545-108">보안 개념</span><span class="sxs-lookup"><span data-stu-id="96545-108">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="96545-109">WCF 보안에 사용 되는 기본 용어 및 개념을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="96545-110">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="96545-110">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="96545-111">WCF를 사용 하 여 구성할 수 있는 시나리오 및 토폴로지를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="96545-112">보안 동작</span><span class="sxs-lookup"><span data-stu-id="96545-112">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="96545-113">보안에 영향을 주는 WCF 동작에 대한 개요를 제공합니다(예: 자격 증명 설정).</span><span class="sxs-lookup"><span data-stu-id="96545-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="96545-114">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="96545-114">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="96545-115">사용자 지정 보안 바인딩을 만드는 방법을 보여 주는 항목을 비롯한 바인딩의 보안 지향적인 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="96545-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="96545-116">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="96545-116">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="96545-117">WCF 보안 기능을 사용 하 여 메시지를 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="96545-118">인증</span><span class="sxs-lookup"><span data-stu-id="96545-118">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="96545-119">일반적인 인증 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96545-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="96545-120">권한 부여</span><span class="sxs-lookup"><span data-stu-id="96545-120">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="96545-121">보안 구현을 사용하여 일반적인 인증 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="96545-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="96545-122">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="96545-123">페더레이션 기본 사항 및 페더레이션 서버와 통신하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="96545-124">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="96545-124">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="96545-125">부분적으로 신뢰할 수 있는 시나리오를 실행 하는 경우 부분적으로 신뢰할 수 있는 시나리오 및 WCF 제한을 실행 하는 방법을 설명</span><span class="sxs-lookup"><span data-stu-id="96545-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="96545-126">감사</span><span class="sxs-lookup"><span data-stu-id="96545-126">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="96545-127">보안 이벤트를 감사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96545-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="96545-128">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="96545-128">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="96545-129">보안 WCF 응용 프로그램을 만드는 방법에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="96545-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96545-130">참고</span><span class="sxs-lookup"><span data-stu-id="96545-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="96545-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="96545-131">Related Sections</span></span>  
 [<span data-ttu-id="96545-132">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="96545-132">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="96545-133">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="96545-133">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="96545-134">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="96545-134">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="96545-135">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="96545-135">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="96545-136">참조</span><span class="sxs-lookup"><span data-stu-id="96545-136">See also</span></span>

- [<span data-ttu-id="96545-137">애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="96545-137">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
