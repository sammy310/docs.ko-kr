---
title: 서비스 및 클라이언트에 보안 설정
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120733"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="64d3c-102">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="64d3c-102">Securing Services and Clients</span></span>
<span data-ttu-id="64d3c-103">이 섹션의 정보는 Windows Communication Foundation (WCF)에서 보안 프로그래밍에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="64d3c-104">일반적으로 여기에는 적절한 시스템 제공 바인딩 선택, 보안 요소의 속성 설정 및 서비스나 클라이언트에서 사용할 자격 증명을 검색하는 방법을 제어하는 서비스 동작의 속성 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="64d3c-105">이러한 기법에 표시 된 대로 대부분의 시나리오에서 대부분의 사용자의 보안 요구 사항을 다루는 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="64d3c-106">시나리오에 더 많은 기능이 필요한 경우 먼저 참조 [사용자 지정 바인딩을 사용 하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)솔루션은 명백 하는 경우 참조 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="64d3c-107">(만들거나와 상호 운용) 하는 경우 다양 한 클레임을 사용 하는 시스템에서 항목을 참조 하세요 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64d3c-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="64d3c-108">In This Section</span></span>  
 [<span data-ttu-id="64d3c-109">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="64d3c-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="64d3c-110">메시지 보안을 설정하는 데 사용되는 프로그래밍 모델의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="64d3c-111">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="64d3c-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="64d3c-112">전송 계층에서 메시지 보안을 설정하는 방법의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="64d3c-113">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="64d3c-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="64d3c-114">Windows Communication Foundation (WCF)에서 메시지 수준 보안을 사용 하는 이유를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="64d3c-115">보안 세션</span><span class="sxs-lookup"><span data-stu-id="64d3c-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="64d3c-116">WCF 세션을 보호 하는 경우 필수 고려 사항 논의 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="64d3c-117">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="64d3c-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="64d3c-118">X.509 인증서를 사용할 때 필요한 일반 작업 중 일부에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="64d3c-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="64d3c-119">참조</span><span class="sxs-lookup"><span data-stu-id="64d3c-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="64d3c-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="64d3c-120">Related Sections</span></span>  
 [<span data-ttu-id="64d3c-121">보안 개념</span><span class="sxs-lookup"><span data-stu-id="64d3c-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="64d3c-122">보안 확장</span><span class="sxs-lookup"><span data-stu-id="64d3c-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="64d3c-123">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="64d3c-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="64d3c-124">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="64d3c-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="64d3c-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="64d3c-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="64d3c-126">보안 확장</span><span class="sxs-lookup"><span data-stu-id="64d3c-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="64d3c-127">권한 부여</span><span class="sxs-lookup"><span data-stu-id="64d3c-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="64d3c-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="64d3c-128">See also</span></span>

- [<span data-ttu-id="64d3c-129">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="64d3c-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="64d3c-130">Windows Server AppFabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="64d3c-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
