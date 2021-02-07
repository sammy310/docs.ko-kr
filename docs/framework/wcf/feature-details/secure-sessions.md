---
description: '자세한 정보: 보안 세션'
title: 보안 세션
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8a4a2d23d5a27f5066bd5f004582829e499f714c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733075"
---
# <a name="secure-sessions"></a><span data-ttu-id="ef308-103">보안 세션</span><span class="sxs-lookup"><span data-stu-id="ef308-103">Secure Sessions</span></span>

<span data-ttu-id="ef308-104">WCF (Windows Communication Foundation) 기능은 메시지가 전송 된 순서 대로 수신 되도록 보장 하는 신뢰할 수 있는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-104">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="ef308-105">이 단원의 항목에서는 신뢰할 수 있는 세션을 만들 때 고려해야 할 보안 관련 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-105">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="ef308-106">신뢰할 수 있는 세션에 대 한 자세한 내용은 [세션 사용](../using-sessions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef308-106">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef308-107">Windows XP에서 가장이 필요한 경우 상태 저장 SCT(보안 컨텍스트 토큰) 없이 보안 세션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-107">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="ef308-108">상태 저장 SCT가 가장과 함께 사용되는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-108">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="ef308-109">자세한 내용은 [지원 되지 않는 시나리오](unsupported-scenarios.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-109">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef308-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ef308-110">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="ef308-111">보안 대화 및 보안 세션</span><span class="sxs-lookup"><span data-stu-id="ef308-111">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="ef308-112">보안 대화 및 보안 세션은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-112">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="ef308-113">이 항목에서는 보안 대화가 작동하는 방식과 패턴을 사용하는 시기와 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-113">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="ef308-114">방법: 보안 세션 만들기</span><span class="sxs-lookup"><span data-stu-id="ef308-114">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="ef308-115">기본적인 보안 세션 만들기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-115">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="ef308-116">방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기</span><span class="sxs-lookup"><span data-stu-id="ef308-116">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="ef308-117">클라이언트로 상태 및 세션을 관리할 웹 팜을 만드는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-117">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="ef308-118">보안 세션에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ef308-118">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="ef308-119">보안 세션에 대해 고려할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef308-119">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="ef308-120">참고</span><span class="sxs-lookup"><span data-stu-id="ef308-120">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="ef308-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ef308-121">Related Sections</span></span>  

 [<span data-ttu-id="ef308-122">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="ef308-122">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="ef308-123">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="ef308-123">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef308-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef308-124">See also</span></span>

- [<span data-ttu-id="ef308-125">방법: 메시지 재생 검색 사용</span><span class="sxs-lookup"><span data-stu-id="ef308-125">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="ef308-126">재생 공격</span><span class="sxs-lookup"><span data-stu-id="ef308-126">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="ef308-127">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="ef308-127">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
