---
title: 보안 세션
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8f5cf9a965951bcc1049c2e96ae6cfa80b0113ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084974"
---
# <a name="secure-sessions"></a><span data-ttu-id="b71d3-102">보안 세션</span><span class="sxs-lookup"><span data-stu-id="b71d3-102">Secure Sessions</span></span>
<span data-ttu-id="b71d3-103">Windows Communication Foundation (WCF)의 기능은 메시지는 전송 된 순서에서를 보장 하는 신뢰할 수 있는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="b71d3-104">이 단원의 항목에서는 신뢰할 수 있는 세션을 만들 때 고려해야 할 보안 관련 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="b71d3-105">신뢰할 수 있는 세션에 대 한 자세한 내용은 참조 하세요. [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b71d3-106">Windows XP에서 가장이 필요한 경우 상태 저장 SCT(보안 컨텍스트 토큰) 없이 보안 세션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="b71d3-107">상태 저장 SCT가 가장과 함께 사용되는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="b71d3-108">자세한 내용은 [지원 되지 않는 시나리오](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b71d3-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b71d3-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="b71d3-110">보안 대화 및 보안 세션</span><span class="sxs-lookup"><span data-stu-id="b71d3-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="b71d3-111">보안 대화 및 보안 세션은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="b71d3-112">이 항목에서는 보안 대화가 작동하는 방식과 패턴을 사용하는 시기와 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="b71d3-113">방법: 보안 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="b71d3-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="b71d3-114">기본적인 보안 세션 만들기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="b71d3-115">방법: 보안 컨텍스트 토큰이 보안 세션</span><span class="sxs-lookup"><span data-stu-id="b71d3-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="b71d3-116">클라이언트로 상태 및 세션을 관리할 웹 팜을 만드는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="b71d3-117">보안 세션에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b71d3-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="b71d3-118">보안 세션에 대해 고려할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b71d3-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b71d3-119">참조</span><span class="sxs-lookup"><span data-stu-id="b71d3-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="b71d3-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b71d3-120">Related Sections</span></span>  
 [<span data-ttu-id="b71d3-121">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="b71d3-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="b71d3-122">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="b71d3-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b71d3-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="b71d3-123">See also</span></span>

- [<span data-ttu-id="b71d3-124">방법: 메시지 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="b71d3-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="b71d3-125">재생 공격</span><span class="sxs-lookup"><span data-stu-id="b71d3-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="b71d3-126">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="b71d3-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
