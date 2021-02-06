---
description: '자세한 정보: WCF의 보안 고려 사항'
title: WCF에서의 보안 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: d75ff0d6eede4a46a5b795873e83445a04532993
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632479"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="ced3b-103">WCF에서의 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ced3b-103">Security Considerations in WCF</span></span>

<span data-ttu-id="ced3b-104">이 단원의 항목에서는 WCF (Windows Communication Foundation) 응용 프로그램을 디자인할 때 고려해 야 할 다양 한 보안 관련 항목을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-104">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ced3b-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ced3b-105">In This Section</span></span>  

 [<span data-ttu-id="ced3b-106">정보 공개</span><span class="sxs-lookup"><span data-stu-id="ced3b-106">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="ced3b-107">정보가 공개되거나 공격 받을 수 있는 다양한 방법과 이러한 문제를 줄이는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-107">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="ced3b-108">권한 상승</span><span class="sxs-lookup"><span data-stu-id="ced3b-108">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="ced3b-109">초기에 부여된 권한을 벗어나는 공격자 인증 권한 제공에 따른 영향 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-109">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="ced3b-110">서비스 거부</span><span class="sxs-lookup"><span data-stu-id="ced3b-110">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="ced3b-111">시스템이 메시지를 적절하게 처리할 수 없는 경우 발생되는 결과 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-111">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="ced3b-112">변조</span><span class="sxs-lookup"><span data-stu-id="ced3b-112">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="ced3b-113">메시지 또는 메시지 배달 변경 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-113">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="ced3b-114">재생 공격</span><span class="sxs-lookup"><span data-stu-id="ced3b-114">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="ced3b-115">공격자가 두 당사자 간에 메시지 스트림을 복사하고, 하나 이상의 당사자에게 스트림을 재생하는 경우 발생하는 결과 및 이에 따른 문제를 줄이는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-115">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="ced3b-116">보안 세션에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ced3b-116">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="ced3b-117">보안 세션 구현 시 보안에 영향을 주는 다음 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-117">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="ced3b-118">지원 되지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="ced3b-118">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="ced3b-119">특정 측면의 보안을 지원하지 않고 방지하거나 고려해야 할 다양한 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ced3b-119">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ced3b-120">참고</span><span class="sxs-lookup"><span data-stu-id="ced3b-120">Reference</span></span>  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="ced3b-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ced3b-121">Related Sections</span></span>  

 [<span data-ttu-id="ced3b-122">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="ced3b-122">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="ced3b-123">참조</span><span class="sxs-lookup"><span data-stu-id="ced3b-123">See also</span></span>

- [<span data-ttu-id="ced3b-124">보안</span><span class="sxs-lookup"><span data-stu-id="ced3b-124">Security</span></span>](security.md)
