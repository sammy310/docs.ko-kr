---
description: '자세한 정보: 재생 공격'
title: 재생 공격
ms.date: 03/30/2017
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
ms.openlocfilehash: b367bd6238f85471871c59b393a8f28a40c4ddba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632856"
---
# <a name="replay-attacks"></a><span data-ttu-id="dc9a5-103">재생 공격</span><span class="sxs-lookup"><span data-stu-id="dc9a5-103">Replay Attacks</span></span>

<span data-ttu-id="dc9a5-104">공격자가 두 당사자 간에 메시지 스트림을 복사 하 고 하나 이상의 당사자에 게 스트림을 재생 하는 경우 *재생 공격이* 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-104">A *replay attack* occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="dc9a5-105">완화되지 않은 경우 공격을 받기 쉬운 컴퓨터는 스트림을 올바른 메시지로 처리하여 항목에 대한 중복 주문과 같은 잘못된 결과의 범위에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-105">Unless mitigated, the computers subject to the attack process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a><span data-ttu-id="dc9a5-106">바인딩이 반사 공격을 받기 쉬운 경우</span><span class="sxs-lookup"><span data-stu-id="dc9a5-106">Bindings May Be Subject to Reflection Attacks</span></span>  

 <span data-ttu-id="dc9a5-107">*리플렉션 공격은* 메시지를 받는 사람에 게 회신으로 보낸 것 처럼 메시지를 다시 보낸 사람에 게 다시 재생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-107">*Reflection attacks* are replays of messages back to a sender as if they came from the receiver as the reply.</span></span> <span data-ttu-id="dc9a5-108">WCF (Windows Communication Foundation) 메커니즘에서 표준 *재생 검색* 은이를 자동으로 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-108">The standard *replay detection* in the Windows Communication Foundation (WCF) mechanism does not automatically handle this.</span></span>  
  
 <span data-ttu-id="dc9a5-109">WCF 서비스 모델은 메시지를 요청 하 고 응답 메시지에 서명 된 헤더를 필요로 하는 서명 된 메시지 ID를 추가 하기 때문에 기본적으로 리플렉션 공격이 완화 됩니다 `relates-to` .</span><span class="sxs-lookup"><span data-stu-id="dc9a5-109">Reflection attacks are mitigated by default because the WCF service model adds a signed message ID to request messages and expects a signed `relates-to` header on response messages.</span></span> <span data-ttu-id="dc9a5-110">따라서 요청 메시지를 응답으로 재생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-110">Consequently, the request message cannot be replayed as a response.</span></span> <span data-ttu-id="dc9a5-111">보안 RM(신뢰할 수 있는 메시지) 시나리오에서 반사 공격은 다음과 같은 이유로 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-111">In secure reliable message (RM) scenarios, reflection attacks are mitigated because:</span></span>  
  
- <span data-ttu-id="dc9a5-112">시퀀스 만들기 및 시퀀스 만들기 응답 메시지 스키마는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-112">The create sequence and create sequence response message schemas are different.</span></span>  
  
- <span data-ttu-id="dc9a5-113">단면 시퀀스의 경우 클라이언트가 보내는 시퀀스 메시지는 클라이언트가 그러한 메시지를 인식할 수 없으므로 재생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-113">For simplex sequences, sequence messages the client sends cannot be replayed back to it because the client cannot understand such messages.</span></span>  
  
- <span data-ttu-id="dc9a5-114">이중 시퀀스의 경우 두 시퀀스 ID는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-114">For duplex sequences, the two sequence IDs must be unique.</span></span> <span data-ttu-id="dc9a5-115">따라서 나가는 시퀀스 메시지를 들어오는 시퀀스 메시지로 재생할 수 없습니다(모든 시퀀스 헤더 및 본문도 서명됨).</span><span class="sxs-lookup"><span data-stu-id="dc9a5-115">Thus, an outgoing sequence message cannot be replayed back as an incoming sequence message (all sequence headers and bodies are signed, too).</span></span>  
  
 <span data-ttu-id="dc9a5-116">반사 공격을 받기 쉬운 바인딩은 WS-Addressing이 없는 바인딩 즉, WS-Addressing이 사용되지 않는 바인딩을 사용자 지정하고 대칭 키 기반 보안을 사용하는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-116">The only bindings that are susceptible to reflection attacks are those without WS-Addressing: custom bindings that have WS-Addressing disabled and use the symmetric key-based security.</span></span> <span data-ttu-id="dc9a5-117"><xref:System.ServiceModel.BasicHttpBinding>은 기본적으로 WS-Addressing을 사용하지 않지만, 이 공격에 노출될 수 있는 방식으로는 대칭 키 기반 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-117">The <xref:System.ServiceModel.BasicHttpBinding> does not use WS-Addressing by default, but it does not use symmetric key-based security in a way that allows it to be vulnerable to this attack.</span></span>  
  
 <span data-ttu-id="dc9a5-118">사용자 지정 바인딩을 완화하는 것은 보안 컨텍스트를 설정하지 않거나 WS-Addressing 헤더를 요청하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-118">The mitigation for custom bindings is to not establish security context or to require WS-Addressing headers.</span></span>  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a><span data-ttu-id="dc9a5-119">웹 팜: 공격자가 여러 노드에 요청 재생</span><span class="sxs-lookup"><span data-stu-id="dc9a5-119">Web Farm: Attacker Replays Request to Multiple Nodes</span></span>  

 <span data-ttu-id="dc9a5-120">클라이언트는 웹 팜에 구현된 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-120">A client uses a service that is implemented on a Web farm.</span></span> <span data-ttu-id="dc9a5-121">공격자는 팜의 한 노드로 보내진 요청을 팜의 다른 노드에 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-121">An attacker replays a request that was sent to one node in the farm to another node in the farm.</span></span> <span data-ttu-id="dc9a5-122">또한, 서비스를 다시 시작하는 경우 재생 캐시가 플러시되어 공격자가 요청을 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-122">In addition, if a service is restarted, the replay cache is flushed, allowing an attacker to replay the request.</span></span> <span data-ttu-id="dc9a5-123">캐시에 이전에 사용된 메시지 서명 값이 있고 캐시가 재생되지 않으므로 그러한 서명은 한 번만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-123">(The cache contains used, previously seen message signature values and prevents replays so those signatures can be used only once.</span></span> <span data-ttu-id="dc9a5-124">재생 캐시는 웹 팜에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-124">Replay caches are not shared across a Web farm.)</span></span>  
  
 <span data-ttu-id="dc9a5-125">완화 방안은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-125">Mitigations include:</span></span>  
  
- <span data-ttu-id="dc9a5-126">상태 저장 보안 컨텍스트 토큰(보안 대화 사용 또는 사용 안 함)과 함께 메시지 모드 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-126">Use message mode security with stateful security context tokens (with or without secure conversation enabled).</span></span> <span data-ttu-id="dc9a5-127">자세한 내용은 [방법: 보안 세션에 대 한 보안 컨텍스트 토큰 만들기](how-to-create-a-security-context-token-for-a-secure-session.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-127">For more information, see [How to: Create a Security Context Token for a Secure Session](how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
- <span data-ttu-id="dc9a5-128">전송 수준 보안을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-128">Configure the service to use transport-level security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9a5-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc9a5-129">See also</span></span>

- [<span data-ttu-id="dc9a5-130">Security Considerations</span><span class="sxs-lookup"><span data-stu-id="dc9a5-130">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="dc9a5-131">정보 공개</span><span class="sxs-lookup"><span data-stu-id="dc9a5-131">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="dc9a5-132">권한 상승</span><span class="sxs-lookup"><span data-stu-id="dc9a5-132">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="dc9a5-133">서비스 거부</span><span class="sxs-lookup"><span data-stu-id="dc9a5-133">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="dc9a5-134">변조</span><span class="sxs-lookup"><span data-stu-id="dc9a5-134">Tampering</span></span>](tampering.md)
- [<span data-ttu-id="dc9a5-135">지원 되지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="dc9a5-135">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
