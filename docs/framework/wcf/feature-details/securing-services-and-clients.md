---
description: '자세한 정보: 서비스 및 클라이언트 보안'
title: 서비스 및 클라이언트에 보안 설정
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: ff947e8bf975fd3fb3c6513ee0bf49bb21a951dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632635"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="ce6dd-103">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ce6dd-103">Securing Services and Clients</span></span>

<span data-ttu-id="ce6dd-104">이 섹션에서는 WCF (Windows Communication Foundation)의 보안 프로그래밍에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-104">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="ce6dd-105">일반적으로 여기에는 적절한 시스템 제공 바인딩 선택, 보안 요소의 속성 설정 및 서비스나 클라이언트에서 사용할 자격 증명을 검색하는 방법을 제어하는 서비스 동작의 속성 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-105">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="ce6dd-106">이러한 기술은 [일반적인 보안 시나리오](common-security-scenarios.md)에서와 같이 대부분의 시나리오에서 대부분의 사용자에 대 한 보안 요구 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-106">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](common-security-scenarios.md).</span></span> <span data-ttu-id="ce6dd-107">시나리오에 더 많은 기능이 필요한 경우에는 먼저 [사용자 지정 바인딩을 사용 하는 보안 기능](security-capabilities-with-custom-bindings.md)을 참조 하세요. 솔루션이 명확 하지 않은 경우 [보안 확장](../extending/extending-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-107">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../extending/extending-security.md).</span></span> <span data-ttu-id="ce6dd-108">풍부한 클레임을 사용 하는 시스템을 만들거나 상호 운용 하는 경우 [권한 부여](authorization-in-wcf.md)의 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-108">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce6dd-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ce6dd-109">In This Section</span></span>  

 [<span data-ttu-id="ce6dd-110">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ce6dd-110">Programming WCF Security</span></span>](programming-wcf-security.md)  
 <span data-ttu-id="ce6dd-111">메시지 보안을 설정하는 데 사용되는 프로그래밍 모델의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-111">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="ce6dd-112">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="ce6dd-112">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="ce6dd-113">전송 계층에서 메시지 보안을 설정하는 방법의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-113">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="ce6dd-114">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="ce6dd-114">Message Security</span></span>](message-security-in-wcf.md)  
 <span data-ttu-id="ce6dd-115">WCF (Windows Communication Foundation)에서 메시지 수준 보안을 사용 하는 이유를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-115">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="ce6dd-116">보안 세션</span><span class="sxs-lookup"><span data-stu-id="ce6dd-116">Secure Sessions</span></span>](secure-sessions.md)  
 <span data-ttu-id="ce6dd-117">WCF 세션의 보안을 유지 하는 데 필요한 고려 사항에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-117">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="ce6dd-118">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="ce6dd-118">Working with Certificates</span></span>](working-with-certificates.md)  
 <span data-ttu-id="ce6dd-119">X.509 인증서를 사용할 때 필요한 일반 작업 중 일부에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-119">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ce6dd-120">참고</span><span class="sxs-lookup"><span data-stu-id="ce6dd-120">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="ce6dd-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ce6dd-121">Related Sections</span></span>  

 [<span data-ttu-id="ce6dd-122">보안 개념</span><span class="sxs-lookup"><span data-stu-id="ce6dd-122">Security Concepts</span></span>](security-concepts.md)  
  
 [<span data-ttu-id="ce6dd-123">보안 확장</span><span class="sxs-lookup"><span data-stu-id="ce6dd-123">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="ce6dd-124">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="ce6dd-124">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
 [<span data-ttu-id="ce6dd-125">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="ce6dd-125">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="ce6dd-126">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="ce6dd-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="ce6dd-127">보안 확장</span><span class="sxs-lookup"><span data-stu-id="ce6dd-127">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="ce6dd-128">권한 부여</span><span class="sxs-lookup"><span data-stu-id="ce6dd-128">Authorization</span></span>](authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce6dd-129">참조</span><span class="sxs-lookup"><span data-stu-id="ce6dd-129">See also</span></span>

- [<span data-ttu-id="ce6dd-130">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ce6dd-130">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- <span data-ttu-id="ce6dd-131">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ce6dd-131">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
