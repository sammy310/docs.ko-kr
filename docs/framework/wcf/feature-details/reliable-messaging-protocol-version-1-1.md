---
title: 안정적인 메시징 프로토콜 버전 1.1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 9320787317131f42c4a82c6114a16fdea87567f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283307"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="487a6-102">안정적인 메시징 프로토콜 버전 1.1</span><span class="sxs-lookup"><span data-stu-id="487a6-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="487a6-103">이 항목에서는 HTTP 전송을 사용 하 여 상호 운용에 필요한 WS-RELIABLEMESSAGING 2 월 2007 (버전 1.1) 프로토콜에 대 한 WCF (Windows Communication Foundation) 구현 세부 정보를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="487a6-104">WCF는이 항목에서 설명 하는 제약 조건 및 설명과 함께 WS-RELIABLEMESSAGING 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="487a6-105">WS-RELIABLEMESSAGING 버전 1.1 프로토콜은 .NET Framework 3.5부터 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="487a6-106">WS-RELIABLEMESSAGING 2 월 2007 프로토콜은 WCF에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="487a6-107">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="487a6-108">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="487a6-109">응답자: 개시자의 요청을 받는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="487a6-110">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="487a6-111">접두사</span><span class="sxs-lookup"><span data-stu-id="487a6-111">Prefix</span></span>|<span data-ttu-id="487a6-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="487a6-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="487a6-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="487a6-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="487a6-114">netrm</span><span class="sxs-lookup"><span data-stu-id="487a6-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="487a6-115">s</span><span class="sxs-lookup"><span data-stu-id="487a6-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="487a6-116">wsa</span><span class="sxs-lookup"><span data-stu-id="487a6-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="487a6-117">wsse</span><span class="sxs-lookup"><span data-stu-id="487a6-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="487a6-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="487a6-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="487a6-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="487a6-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="487a6-120">wsp</span><span class="sxs-lookup"><span data-stu-id="487a6-120">wsp</span></span>|<span data-ttu-id="487a6-121">(WS-Policy 1.2 또는 WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="487a6-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="487a6-122">Messaging(메시징)</span><span class="sxs-lookup"><span data-stu-id="487a6-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="487a6-123">시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="487a6-123">Sequence Creation</span></span>

<span data-ttu-id="487a6-124">WCF는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현 하 여 신뢰할 수 있는 메시징 시퀀스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="487a6-125">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-125">The following constraints apply:</span></span>

- <span data-ttu-id="487a6-126">B1101: WCF 개시자는 `CreateSequence` 메시지의 `ReplyTo`, `AcksTo` 및 `Offer/Endpoint`와 동일한 끝점 참조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="487a6-127">R1102: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 엔드포인트 참조에는 8비트 형식과 일치하도록 동일한 문자열 표현을 포함하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="487a6-128">WCF 응답자는 시퀀스를 만들기 전에 `AcksTo`, `ReplyTo` 및 `Endpoint` 끝점 참조의 URI 부분이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="487a6-129">R1103: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 엔드포인트 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="487a6-130">WCF는를 적용 하지 않지만 `CreateSequence`에 대 한 `AcksTo`, `ReplyTo` 및 `Offer/Endpoint` 끝점 참조의 참조 매개 변수는 동일 하며, 승인 및 역방향 시퀀스 메시지에 대해 `ReplyTo` 끝점 참조의 참조 매개 변수를 사용 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="487a6-131">B1104: WCF 개시자는 `CreateSequence` 메시지에서 선택적 `Expires` 또는 `Offer/Expires` 요소를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="487a6-132">B1105: `CreateSequence` 메시지에 액세스할 때 WCF 응답자는 `CreateSequence` 요소의 `Expires` 값을 `CreateSequenceResponse` 요소의 `Expires` 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="487a6-133">그렇지 않으면 WCF 응답자는 `Expires` 및 `Offer/Expires` 값을 읽고 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="487a6-134">B1106: `CreateSequenceResponse` 메시지에 액세스할 때 WCF 개시자는 선택적 `Expires` 값을 읽지만 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="487a6-135">B1107: WCF 시작자 및 응답자는 항상 `CreateSequence/Offer` 및 `CreateSequenceResponse` 요소에 선택적 `IncompleteSequenceBehavior` 요소를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="487a6-136">B1108: WCF는 `IncompleteSequenceBehavior` 요소의 `DiscardFollowingFirstGap` 및 `NoDiscard` 값만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="487a6-137">WS-ReliableMessaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="487a6-138">B1109: `CreateSequence`에 `Offer` 요소가 포함 된 경우 WCF 응답자는 `Accept` 요소 없이 `CreateSequenceResponse` 응답 하 여 제공 된 시퀀스를 거부 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="487a6-139">B1110: 신뢰할 수 있는 메시징 응답기에서 제공 된 시퀀스를 거부 하는 경우 WCF 초기자는 새로 설정 된 시퀀스에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="487a6-140">B1111: `CreateSequence`에 `Offer` 요소가 포함 되지 않은 경우 양방향 WCF 응답자는 `CreateSequenceRefused` 오류에 응답 하 여 제공 된 시퀀스를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="487a6-141">R1112: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]` 엔드포인트 참조의 `CreateSequenceResponse/Accept/AcksTo` 속성은 `CreateSequence` 메시지 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="487a6-142">R1113: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자에서 응답자로 이동하는 두 시퀀스의 모든 메시지를 같은 엔드포인트 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="487a6-143">WCF는 ws-reliablemessaging을 사용 하 여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="487a6-144">WCF WS-RELIABLEMESSAGING 구현은 단방향, 요청-회신 및 전체 이중 메시징 패턴에 대 한 신뢰할 수 있는 세션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="487a6-145">ph x="1" /&gt; 및 `Offer`에서 WS-ReliableMessaging `CreateSequence` 메커니즘을 사용하면 상호 관련된 두 개의 역방향 시퀀스를 설정하고 모든 메시지 엔드포인트에 적합한 세션 프로토콜을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="487a6-146">WCF는 세션 무결성을 위한 종단 간 보호를 포함 하 여 세션에 대 한 보안 보장을 제공 하므로 같은 파티에 대 한 메시지가 동일한 대상에 도착 하는지 확인 하는 것이 실용적입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="487a6-147">이렇게 하면 애플리케이션 메시지에서 &quot;피기백킹&quot;이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="487a6-148">따라서 제약 조건 R1102, R1112 및 R1113가 WCF에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="487a6-149">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-149">An example of a `CreateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>
    <wsa:ReplyTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
      </wsrm:AcksTo>
      <wsrm:Offer>
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>
        <wsrm:Endpoint>
          <wsa:Address>http://Business456.com/clientA</wsa:Address>
        </wsrm:Endpoint>
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      </wsrm:Offer>
    </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="487a6-150">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-150">An example of a `CreateSequenceResponse` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      <wsrm:Accept>
        <wsrm:AcksTo>
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>
        </wsrm:AcksTo>
      </wsrm:Accept>
    </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="closing-a-sequence"></a><span data-ttu-id="487a6-151">시퀀스 닫기</span><span class="sxs-lookup"><span data-stu-id="487a6-151">Closing a Sequence</span></span>

<span data-ttu-id="487a6-152">WCF는 신뢰할 수 있는 메시징 원본에서 시작 된 종료를 위해 `CloseSequence` 및 `CloseSequenceResponse` 메시지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="487a6-153">WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않으며 WCF 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상 종료를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="487a6-154">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-154">The following constraints apply:</span></span>

- <span data-ttu-id="487a6-155">B1201: WCF 신뢰할 수 있는 메시징 소스는 항상 시퀀스를 종료 하는 `CloseSequence` 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="487a6-156">B1202: 신뢰할 수 있는 메시징 소스는 시퀀스 메시지 전체 범위의 승인을 기다린 다음 `CloseSequence` 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="487a6-157">B1203: 시퀀스에 메시지가 있으면 신뢰할 수 있는 메시징 소스에는 항상 선택적 `LastMsgNumber` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="487a6-158">R1204: 신뢰할 수 있는 메시징 대상은 `CloseSequence` 메시지를 보내어 종료를 시작하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="487a6-159">B1205: `CloseSequence` 메시지가 수신 되 면 WCF 신뢰할 수 있는 메시징 소스는 시퀀스를 불완전 하 게 간주 하 고 오류를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="487a6-160">`CloseSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-160">An example of a `CloseSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
    </wsrm:CloseSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="487a6-161">예제 `CloseSequenceResponse` 메시지:</span><span class="sxs-lookup"><span data-stu-id="487a6-161">Example `CloseSequenceResponse` message:</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:CloseSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence-termination"></a><span data-ttu-id="487a6-162">시퀀스 종료</span><span class="sxs-lookup"><span data-stu-id="487a6-162">Sequence Termination</span></span>

<span data-ttu-id="487a6-163">WCF는 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 완료 한 후 `TerminateSequence/TerminateSequenceResponse` 핸드셰이크를 주로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="487a6-164">WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않으며 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상이 시작한 종료를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="487a6-165">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-165">The following constraints apply:</span></span>

- <span data-ttu-id="487a6-166">B1301: WCF 개시자는 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 성공적으로 완료 한 후에만 `TerminateSequence` 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="487a6-167">R1302: WCF는 `LastMsgNumber` 요소가 지정 된 시퀀스에 대해 모든 `CloseSequence` 및 `TerminateSequence` 메시지에서 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="487a6-168">즉, `LastMsgNumber`가 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 없거나, 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 있으며 이러한 메시지에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="487a6-169">B1303: `TerminateSequence` 핸드셰이크 이후 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="487a6-170">신뢰할 수 있는 메시징 소스에 `TerminateSequence` 메시지를 보내기 전의 최종 승인이 있으므로 신뢰할 수 있는 메시징 대상은 시퀀스가 종료되고 리소스를 즉시 회수함을 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="487a6-171">B1304: `CloseSequence/CloseSequenceResponse` 핸드셰이크 이전에 `TerminateSequence` 메시지를 수신 하는 경우 WCF 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지를 사용 하 여 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="487a6-172">신뢰할 수 있는 메시징 대상이 시퀀스에서 일치하지 않는 부분이 없음을 확인한 경우에는 클라이언트가 최종 승인을 받을 수 있도록 신뢰할 수 있는 메시징 대상이 애플리케이션 대상에서 지정한 시간 동안 기다린 다음 리소스를 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="487a6-173">그렇지 않은 경우 신뢰할 수 있는 메시징 대상이 리소스를 바로 회수하고 애플리케이션 대상에 `Faulted` 이벤트를 발생시켜 시퀀스에 오류가 발생하여 종료되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="487a6-174">`TerminateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-174">An example of a `TerminateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
      </wsrm:TerminateSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="487a6-175">예제 `TerminateSequenceResponse` 메시지:</span><span class="sxs-lookup"><span data-stu-id="487a6-175">Example `TerminateSequenceResponse` message:</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:TerminateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequences"></a><span data-ttu-id="487a6-176">시퀀스</span><span class="sxs-lookup"><span data-stu-id="487a6-176">Sequences</span></span>

<span data-ttu-id="487a6-177">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="487a6-178">B1401: WCF는 `xs:long`의 최대 포함 값 9223372036854775807 보다 큰 시퀀스 번호를 생성 하 고 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="487a6-179">`Sequence` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="487a6-180">승인 요청</span><span class="sxs-lookup"><span data-stu-id="487a6-180">Request Acknowledgement</span></span>

<span data-ttu-id="487a6-181">WCF는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="487a6-182">`AckRequested` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="487a6-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="487a6-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="487a6-184">WCF는 신뢰할 수 있는 메시징에 제공 된 시퀀스 승인에 "피기백" 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="487a6-185">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-185">The following constraints apply:</span></span>

- <span data-ttu-id="487a6-186">R1601: `Offer` 메커니즘을 사용 하 여 두 개의 역방향 시퀀스가 설정 된 경우 `SequenceAcknowledgement` 헤더는 의도 한 받는 사람에 게 전송 된 모든 응용 프로그램 메시지에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="487a6-187">원격 엔드포인트에서는 피기백된 `SequenceAcknowledgement` 헤더에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="487a6-188">B1602: WCF는 `Nack` 요소를 포함 하는 `SequenceAcknowledgement` 헤더를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="487a6-189">WCF는 각 `Nack` 요소에 시퀀스 번호가 포함 되어 있는지 확인 하지만, 그렇지 않은 경우에는 `Nack` 요소와 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="487a6-190">`SequenceAcknowledgement` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="487a6-191">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="487a6-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="487a6-192">다음은 WS-RELIABLEMESSAGING 오류의 WCF 구현에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="487a6-193">적용되는 제약 조건은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-193">The following constraints apply:</span></span>

- <span data-ttu-id="487a6-194">B1701: WCF는 `MessageNumberRollover` 오류를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="487a6-195">B1702: SOAP 1.2를 통해 서비스 끝점이 해당 연결 제한에 도달 하 여 새 연결을 처리할 수 없는 경우 WCF는 다음 예제와 같이 중첩 된 `CreateSequenceRefused` 오류 하위 코드 `netrm:ConnectionLimitReached`생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>
  </s:Header>
  <s:Body>
    <s:Fault>
      <s:Code>
        <s:Value>s:Receiver</s:Value>
        <s:Subcode>
          <s:Value>wsrm:CreateSequenceRefused</s:Value>
          <s:Subcode>
            <s:Value>netrm:ConnectionLimitReached</s:Value>
          </s:Subcode>
        </s:Subcode>
      </s:Code>
      <s:Reason>
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>
      </s:Reason>
    </s:Fault>
  </s:Body>
</s:Envelope>
```

### <a name="ws-addressing-faults"></a><span data-ttu-id="487a6-196">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="487a6-196">WS-Addressing Faults</span></span>

<span data-ttu-id="487a6-197">Ws-reliablemessaging은 WS-ADDRESSING을 사용 하기 때문에 WCF WS-RELIABLEMESSAGING 구현이 WS-ADDRESSING 오류를 생성 하 고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="487a6-198">이 섹션에서는 WCF에서 명시적으로 생성 하 고 ws-reliablemessaging 계층에서 전송 하는 WS-ADDRESSING 오류에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="487a6-199">B1801: WCF는 다음 조건 중 하나에 해당 하는 경우 `Message Addressing Header Required` 오류를 생성 하 고 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="487a6-200">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="487a6-201">`CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="487a6-202">`CreateSequenceResponse`, `CloseSequenceResponse` 또는 `TerminateSequenceResponse` 메시지에 `RelatesTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="487a6-203">B1802: WCF는 `Endpoint Unavailable` 오류를 생성 하 고 전송 하 여 `CreateSequence` 메시지의 주소 지정 헤더 검사를 기반으로 시퀀스를 처리할 수 있는 끝점을 수신 대기 하지 않음을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="487a6-204">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="487a6-205">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="487a6-206">WCF는 ws-addressing 2004/08 [WS-ADDR] 및 W3C WS-ADDRESSING 1.0 권장 사항 [WS-POLICY-CORE] 및 [WS-ADDRESSING-SOAP]의 두 가지 버전 주소를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="487a6-207">WS-ReliableMessaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="487a6-208">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="487a6-209">R2101: WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="487a6-210">R2102: 단일 버전의 WS-Addressing은 `Offer` 메커니즘을 사용하여 상호 관련된 한 쌍의 역방향 시퀀스 또는 제공된 WS-ReliableMessaging 시퀀스 전체에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="487a6-211">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-211">Composition with SOAP</span></span>

<span data-ttu-id="487a6-212">WCF는 신뢰할 수 있는 메시징을 사용 하 여 SOAP 1.1 및 SOAP 1.2을 모두 사용할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="487a6-213">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="487a6-214">WCF는 보안 전송 (HTTPS), WS-SECURITY를 사용 하 여 컴퍼지션 및 WS-SECURITY를 사용 하 여 구성 하는 ws-reliablemessaging 시퀀스에 대 한 보호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="487a6-215">WS-ReliableMessaging 1.1 프로토콜, WS-Security 1.1 및 WS-Secure Conversation 1.3 프로토콜을 함께 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="487a6-216">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="487a6-217">R2301: 개별 메시지의 무결성과 기밀성 뿐만 아니라 WS-RELIABLEMESSAGING 시퀀스의 무결성을 보호 하기 위해 WCF에서는 WS-SECURITY 대화를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="487a6-218">R2302: AWS 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="487a6-219">R2303: WS-ReliableMessaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="487a6-220">B2304: WS-RELIABLEMESSAGING 시퀀스 또는 상관 관계가 지정 된 역방향 시퀀스의 쌍은 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="487a6-221">R2305: WS-SECURITY 대화로 구성 된 경우 WCF 응답자는 `CreateSequence` 메시지에 `wsse:SecurityTokenReference` 요소와 `wsrm:UsesSequenceSTR` 헤더가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="487a6-222">`UsesSequenceSTR` 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="487a6-223">SSL/TLS 세션을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="487a6-224">WCF는 SSL/TLS 세션을 사용한 컴퍼지션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="487a6-225">B2401: WCF는 `wsrm:UsesSequenceSSL` 헤더를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="487a6-226">R2402: 신뢰할 수 있는 메시징 개시자는 `wsrm:UsesSequenceSSL` 헤더를 포함 하는 `CreateSequence` 메시지를 WCF 응답자에 게 보내지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="487a6-227">WS-Policy를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="487a6-227">Composition with WS-Policy</span></span>

<span data-ttu-id="487a6-228">WCF는 ws-policy 1.2 및 WS-POLICY 1.5의 두 가지 버전 정책을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="487a6-229">WS-ReliableMessaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="487a6-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="487a6-230">WCF는 ws-reliablemessaging WS 정책 어설션 `wsrm:RMAssertion`를 사용 하 여 끝점 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="487a6-231">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="487a6-232">B3001: WCF `wsrmn:RMAssertion` WS-POLICY 어설션을 `wsdl:binding` 요소에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="487a6-233">WCF는 `wsdl:binding` 및 `wsdl:port` 요소에 대 한 첨부 파일을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="487a6-234">B3002: WCF는 `wsp:Optional` 태그를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="487a6-235">B3003: `wsrmp:RMAssertion` WS-POLICY 어설션에 액세스할 때 WCF는 `wsp:Optional` 태그를 무시 하 고 WS-RM 정책을 필수로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="487a6-236">R3004: WCF는 SSL/TLS 세션을 사용 하 여 구성 하지 않으므로 WCF는 `wsrmp:SequenceTransportSecurity`를 지정 하는 정책을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="487a6-237">B3005: WCF는 항상 `wsrmp:DeliveryAssurance` 요소를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="487a6-238">B3006: WCF는 항상 `wsrmp:ExactlyOnce` 배달 보증을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="487a6-239">B3007: WCF는 ws-reliablemessaging 어설션의 다음 속성을 생성 하 고 읽고 WCF`ReliableSessionBindingElement`에서 해당 속성에 대 한 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="487a6-240">`RMAssertion`의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-240">An example of a `RMAssertion`.</span></span>

  ```xml
  <wsrmp:RMAssertion>
    <wsp:Policy>
      <wsrmp:SequenceSTR/>
      <wsrmp:DeliveryAssurance>
        <wsp:Policy>
          <wsrmp:ExactlyOnce/>
          <wsrmp:InOrder/>
        </wsp:Policy>
      </wsrmp:DeliveryAssurance>
    </wsp:Policy>
    <netrmp:InactivityTimeout Milliseconds="600000"/>
    <netrmp:AcknowledgementInterval Milliseconds="200"/>
  </wsrmp:RMAssertion>
  ```

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="487a6-241">흐름 제어 WS-ReliableMessaging 확장명</span><span class="sxs-lookup"><span data-stu-id="487a6-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="487a6-242">WCF는 WS-RELIABLEMESSAGING 확장성을 사용 하 여 시퀀스 메시지 흐름에 대 한 선택적인 추가 제어 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="487a6-243"><xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> 속성을 `true`설정 하 여 흐름 제어를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="487a6-244">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="487a6-245">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF는 다음 예제와 같이 `SequenceAcknowledgement` 헤더의 요소 확장성에 `netrm:BufferRemaining` 요소를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="487a6-246">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우에도 WCF는 `SequenceAcknowledgement` 헤더에 `netrm:BufferRemaining` 요소가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="487a6-247">B4003: WCF 신뢰할 수 있는 메시징 대상은 `netrm:BufferRemaining`를 사용 하 여 버퍼링 할 수 있는 새 메시지 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="487a6-248">B4004: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF 신뢰할 수 있는 메시징 소스는 `netrm:BufferRemaining` 값을 사용 하 여 메시지 전송을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="487a6-249">B4005: WCF는 0에서 4096 사이의 정수 값 `netrm:BufferRemaining` 생성 하 고 0과 `xs:int`의 `maxInclusive` 값 214748364 포괄 시간 사이의 정수 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="487a6-250">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="487a6-250">Message Exchange Patterns</span></span>

<span data-ttu-id="487a6-251">이 섹션에서는 다양 한 메시지 교환 패턴에 WS-RELIABLEMESSAGING을 사용 하는 경우 WCF의 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="487a6-252">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="487a6-253">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="487a6-254">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="487a6-255">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="487a6-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="487a6-256">바인딩</span><span class="sxs-lookup"><span data-stu-id="487a6-256">Binding</span></span>

<span data-ttu-id="487a6-257">WCF는 한 개의 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="487a6-258">WCF는 HTTP 요청을 사용 하 여 개시자의 모든 메시지를 응답자에 게 전송 하 고 HTTP 응답을 사용 하 여 응답자의 모든 메시지를 개시자에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="487a6-259">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-259">CreateSequence Exchange</span></span>

<span data-ttu-id="487a6-260">WCF 개시자는 HTTP 요청에 `Offer` 요소가 없는 `CreateSequence` 메시지를 전송 하 고 HTTP 응답에서 `CreateSequenceResponse` 메시지를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="487a6-261">WCF 응답자는 시퀀스를 만들고 HTTP 응답에 `Accept` 요소가 없는 `CreateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="487a6-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="487a6-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="487a6-263">WCF 초기자는 `CreateSequence` 메시지 및 오류 메시지를 제외 하 고 모든 메시지의 회신에 대 한 승인을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="487a6-264">WCF 응답자는 항상 HTTP 응답에 대 한 독립 실행형 승인을 모든 시퀀스 및 `AckRequested` 메시지에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="487a6-265">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-265">CloseSequence Exchange</span></span>

<span data-ttu-id="487a6-266">WCF 개시자는 HTTP 요청에 `CloseSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `CreateSequenceResponse` 메시지를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="487a6-267">WCF 응답자는 HTTP 응답에서 `CloseSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="487a6-268">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="487a6-269">WCF 개시자는 HTTP 요청에 `TerminateSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `TerminateSequenceResponse` 메시지를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="487a6-270">WCF 응답자는 HTTP 응답에서 `TerminateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="487a6-271">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="487a6-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="487a6-272">바인딩</span><span class="sxs-lookup"><span data-stu-id="487a6-272">Binding</span></span>

<span data-ttu-id="487a6-273">WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="487a6-274">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="487a6-275">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="487a6-276">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-276">CreateSequence Exchange</span></span>

<span data-ttu-id="487a6-277">WCF 개시자는 HTTP 요청에 `Offer` 요소가 없는 `CreateSequence` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="487a6-278">WCF 응답자는 시퀀스를 만들고 HTTP 요청에 `Accept` 요소가 없는 `CreateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="487a6-279">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="487a6-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="487a6-280">바인딩</span><span class="sxs-lookup"><span data-stu-id="487a6-280">Binding</span></span>

<span data-ttu-id="487a6-281">WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 완전 한 비동기 양방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="487a6-282">이 메시지 교환 패턴은 제한된 방식으로 `Request/Reply`, `Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="487a6-283">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="487a6-284">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="487a6-285">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-285">CreateSequence Exchange</span></span>

<span data-ttu-id="487a6-286">WCF 개시자는 HTTP 요청에 `Offer` 요소가 포함 된 `CreateSequence` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="487a6-287">WCF 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인 한 다음 시퀀스를 만들고 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="487a6-288">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="487a6-288">Sequence Lifetime</span></span>

<span data-ttu-id="487a6-289">WCF는 두 시퀀스를 하나의 완전히 이중 세션으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="487a6-290">한 시퀀스에 오류가 발생 하는 오류를 생성 하면 WCF는 원격 끝점에서 두 시퀀스를 모두 오류를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="487a6-291">한 시퀀스에 오류가 발생 하는 오류를 읽을 때 WCF는 두 시퀀스를 모두 오류를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="487a6-292">WCF는 아웃 바운드 시퀀스를 닫고 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="487a6-293">반대로, WCF는 인바운드 시퀀스의 닫기를 처리 하 고 아웃 바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="487a6-294">요청-회신 및 단방향의 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="487a6-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="487a6-295">바인딩</span><span class="sxs-lookup"><span data-stu-id="487a6-295">Binding</span></span>

<span data-ttu-id="487a6-296">WCF는 하나의 HTTP 채널에 대 한 두 개의 시퀀스를 사용 하는 단방향 및 요청-회신 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="487a6-297">WCF는 HTTP 요청을 사용 하 여 개시자의 모든 메시지를 응답자에 게 전송 하 고 HTTP 응답을 사용 하 여 응답자의 모든 메시지를 개시자에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="487a6-298">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-298">CreateSequence Exchange</span></span>

<span data-ttu-id="487a6-299">WCF 개시자는 HTTP 요청에 `Offer` 요소를 포함 하는 `CreateSequence` 메시지를 전송 하 고 HTTP 응답에서 `CreateSequenceResponse` 메시지를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="487a6-300">WCF 응답자는 시퀀스를 만들고 HTTP 응답에 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="487a6-301">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="487a6-301">One-way Message</span></span>

<span data-ttu-id="487a6-302">단방향 메시지 교환을 성공적으로 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="487a6-303">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="487a6-304">WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="487a6-305">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="487a6-305">Two Way Messages</span></span>

<span data-ttu-id="487a6-306">양방향 메시지 교환 프로토콜을 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="487a6-307">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="487a6-308">WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="487a6-309">단방향 메시지가 있고 애플리케이션이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="487a6-310">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="487a6-310">Retrying Replies</span></span>

<span data-ttu-id="487a6-311">WCF는 양방향 메시지 교환 프로토콜 상관 관계에 대 한 HTTP 요청-회신 상관 관계에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="487a6-312">이로 인해 WCF 개시자는 요청 시퀀스 메시지가 승인 되는 경우, HTTP 응답에 `SequenceAcknowledgement`, 응용 프로그램 회신 또는 오류가 전달 되는 경우 요청 시퀀스 메시지를 다시 시도 하는 것을 중지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="487a6-313">WCF 응답자는 회신이 상호 관련 된 요청의 HTTP 응답에 대 한 응답을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="487a6-314">CloseSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-314">CloseSequence Exchange</span></span>

<span data-ttu-id="487a6-315">모든 단방향 요청 시퀀스 메시지에 대해 모든 회신 시퀀스 메시지와 승인을 받은 후 WCF 개시자는 HTTP 요청에서 요청 시퀀스에 대 한 `CloseSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `CloseSequenceResponse`를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="487a6-316">요청 시퀀스를 닫으면 회신 시퀀스가 암시적으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="487a6-317">즉, WCF 개시자는 `CloseSequence` 메시지에 회신 시퀀스의 최종 `SequenceAcknowledgement`를 포함 하 고 회신 시퀀스에는 `CloseSequence` 교환이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="487a6-318">WCF 응답자는 모든 회신이 승인 되도록 하 고 HTTP 응답에서 `CloseSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="487a6-319">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="487a6-320">`CloseSequenceResponse` 메시지를 받은 후 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스에 대 한 `TerminateSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `TerminateSequenceResponse`를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="487a6-321">`CloseSequence` 교환과 마찬가지로 요청 시퀀스를 종료하면 회신 시퀀스가 암시적으로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="487a6-322">즉, WCF 개시자는 `TerminateSequence` 메시지에 회신 시퀀스의 최종 `SequenceAcknowledgement`를 포함 하 고 회신 시퀀스에는 `TerminateSequence` 교환이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="487a6-323">WCF 응답자는 HTTP 응답에서 `TerminateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="487a6-324">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="487a6-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="487a6-325">바인딩</span><span class="sxs-lookup"><span data-stu-id="487a6-325">Binding</span></span>

<span data-ttu-id="487a6-326">WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 요청-회신 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="487a6-327">이 메시지 교환 패턴은 제한된 방식으로 `Duplex, Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="487a6-328">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="487a6-329">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="487a6-330">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="487a6-330">CreateSequence Exchange</span></span>

<span data-ttu-id="487a6-331">WCF 개시자는 HTTP 요청에 `Offer` 요소가 포함 된 `CreateSequence` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="487a6-332">WCF 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인 한 다음 시퀀스를 만들고 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="487a6-333">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="487a6-333">Request/Reply Correlation</span></span>

<span data-ttu-id="487a6-334">다음 사항은 모든 상호 관련된 요청 및 회신에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="487a6-335">WCF를 사용 하면 모든 응용 프로그램 요청 메시지에 `ReplyTo` 끝점 참조 및 `MessageId`있습니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="487a6-336">WCF는 각 응용 프로그램 요청 메시지의 `ReplyTo`로 로컬 끝점 참조를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="487a6-337">로컬 엔드포인트 참조는 개시자에 대한 `CreateSequence` 메시지의 `ReplyTo`와 응답자에 대한 `CreateSequence` 메시지의 `To`입니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="487a6-338">WCF는 들어오는 요청 메시지에 `MessageId`와 `ReplyTo`를 사용 하도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="487a6-339">WCF는 모든 응용 프로그램 요청 메시지의 `ReplyTo` 끝점 참조의 URI가 앞에서 정의한 대로 로컬 끝점 참조와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="487a6-340">WCF는 `wsa` 요청/회신 상관 관계 규칙에 따라 모든 회신이 올바른 `RelatesTo` 및 `To` 헤더를 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="487a6-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
