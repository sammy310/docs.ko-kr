---
description: '자세한 정보: 신뢰할 수 있는 메시징 프로토콜 버전 1.0'
title: Reliable Messaging 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: dbd0184fd6ea9f92c96639d71088ac61bec20f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793599"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="0c98a-103">Reliable Messaging 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="0c98a-103">Reliable Messaging Protocol version 1.0</span></span>

<span data-ttu-id="0c98a-104">이 항목에서는 HTTP 전송을 사용 하 여 상호 운용에 필요한 WS-Reliable 메시징 2 월 2005 (버전 1.0) 프로토콜에 대 한 WCF (Windows Communication Foundation) 구현 세부 정보를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-104">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="0c98a-105">WCF는이 항목에서 설명 하는 제약 조건 및 설명과 함께 WS-Reliable 메시징 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-105">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="0c98a-106">WS-ReliableMessaging 버전 1.0 프로토콜은 WinFX부터 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-106">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the WinFX.</span></span>

<span data-ttu-id="0c98a-107">WS-Reliable 메시징 2 월 2005 프로토콜은 WCF에서에 의해 구현 됩니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="0c98a-107">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="0c98a-108">편의상 이 항목에서는 다음 역할을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-108">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="0c98a-109">개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-109">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>

- <span data-ttu-id="0c98a-110">응답자: 개시자의 요청을 받은 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-110">Responder: the service that receives the initiator's requests</span></span>

<span data-ttu-id="0c98a-111">이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-111">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="0c98a-112">접두사</span><span class="sxs-lookup"><span data-stu-id="0c98a-112">Prefix</span></span>|<span data-ttu-id="0c98a-113">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="0c98a-113">Namespace</span></span>|
|------------|---------------|
|<span data-ttu-id="0c98a-114">wsrm</span><span class="sxs-lookup"><span data-stu-id="0c98a-114">wsrm</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|<span data-ttu-id="0c98a-115">netrm</span><span class="sxs-lookup"><span data-stu-id="0c98a-115">netrm</span></span>|`http://schemas.microsoft.com/ws/2006/05/rm`|
|<span data-ttu-id="0c98a-116">초</span><span class="sxs-lookup"><span data-stu-id="0c98a-116">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|
|<span data-ttu-id="0c98a-117">wsa</span><span class="sxs-lookup"><span data-stu-id="0c98a-117">wsa</span></span>|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|<span data-ttu-id="0c98a-118">wsse</span><span class="sxs-lookup"><span data-stu-id="0c98a-118">wsse</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a><span data-ttu-id="0c98a-119">메시징</span><span class="sxs-lookup"><span data-stu-id="0c98a-119">Messaging</span></span>

### <a name="sequence-establishment-messages"></a><span data-ttu-id="0c98a-120">시퀀스 설정 메시지</span><span class="sxs-lookup"><span data-stu-id="0c98a-120">Sequence Establishment Messages</span></span>

<span data-ttu-id="0c98a-121">WCF `CreateSequence` 는 및 `CreateSequenceResponse` 메시지를 구현 하 여 신뢰할 수 있는 메시지 시퀀스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-121">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="0c98a-122">다음 제약 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-122">The following constraints apply:</span></span>

- <span data-ttu-id="0c98a-123">B1101: WCF 개시자는 메시지에 선택적 Expires 요소를 생성 하지 않으며 `CreateSequence` , 메시지에 요소가 포함 된 경우 요소의 `CreateSequence` `Offer` 선택적 `Expires` 요소 `Offer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-123">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>

- <span data-ttu-id="0c98a-124">B1102: 메시지에 액세스할 때 `CreateSequence` WCF는 `Responder` 두 `Expires` 요소 (있는 경우)를 보내고 받으며 해당 값을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-124">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>

<span data-ttu-id="0c98a-125">WS-Reliable Messaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-125">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="0c98a-126">R1103: `CreateSequence`에 `Offer` 요소가 있는 경우 신뢰할 수 있는 메시징 응답자는 `CreateSequenceResponse` 요소가 포함된 `wsrm:Accept`와 함께 시퀀스 및 응답을 수락하여 상호 관련된 두 개의 역방향 시퀀스를 구성하거나 `CreateSequence` 요청을 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-126">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>

- <span data-ttu-id="0c98a-127">R1104: 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 애플리케이션 메시지는 `ReplyTo`의 `CreateSequence` 엔드포인트 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-127">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="0c98a-128">R1105: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 엔드포인트 참조에는 8비트 형식과 일치하는 주소 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-128">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>

  <span data-ttu-id="0c98a-129">WCF 응답자는 `AcksTo` `ReplyTo` 시퀀스를 만들기 전에 및 EPRS의 URI 부분이 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-129">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>

- <span data-ttu-id="0c98a-130">R1106: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 엔드포인트 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-130">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>

  <span data-ttu-id="0c98a-131">WCF는를 적용 하지 않지만 및의 [참조 매개 변수]가 `AcksTo` `ReplyTo` `CreateSequence` 동일 하며, `ReplyTo` 승인 및 역방향 시퀀스 메시지에 대해 끝점 참조의 [참조 매개 변수]를 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-131">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="0c98a-132">R1107: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 애플리케이션 메시지를 `ReplyTo`의 `CreateSequence` 엔드포인트 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-132">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="0c98a-133">R1108: Offer 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]`의 `wsrm:AcksTo` 요소에 대한 `wsrm:Accept` 엔드포인트 자식 요소의 `CreateSequenceResponse` 속성은 `CreateSequence`의 바이트별 대상 URI와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-133">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>

- <span data-ttu-id="0c98a-134">R1109: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자가 보낸 메시지 및 응답자의 메시지 승인을 같은 엔드포인트 참조로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-134">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>

  <span data-ttu-id="0c98a-135">WCF는 WS-Reliable 메시징을 사용 하 여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-135">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="0c98a-136">WCF의 WS-Reliable 메시징 구현은 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-136">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="0c98a-137">의 WS-Reliable 메시징 `Offer` 메커니즘을 `CreateSequence` / `CreateSequenceResponse` 사용 하면 상호 관련 된 두 개의 역방향 시퀀스를 설정 하 고 모든 메시지 끝점에 적합 한 세션 프로토콜을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-137">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="0c98a-138">WCF는 세션 무결성을 위한 종단 간 보호를 포함 하 여 세션에 대 한 보안 보장을 제공 하므로 같은 파티에 대 한 메시지가 동일한 대상에 도착 하는지 확인 하는 것이 실용적입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-138">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="0c98a-139">이렇게 하면 애플리케이션 메시지에서 피기백킹이라고 하는 시퀀스 승인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-139">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="0c98a-140">따라서 제약 조건 R1104, R1105 및 R1108가 WCF에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-140">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>

<span data-ttu-id="0c98a-141">`CreateSequence` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-141">An example of a `CreateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence
    </a:Action>
    <a:ReplyTo>
      <a:Address>
         http://Business456.com/clientA
      </a:Address>
    </a:ReplyTo>
    <a:MessageID>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:MessageID>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
       <wsa:Address>
         http://Business456.com/clientA
       </wsa:Address>
     </wsrm:AcksTo>
     <wsrm:Offer>
      <wsrm:Identifier>
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496
      </wsrm:Identifier>
     </wsrm:Offer>
   </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="0c98a-142">`CreateSequenceResponse` 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-142">An example of a `CreateSequenceResponse` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse
    </a:Action>
    <a:RelatesTo>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:RelatesTo>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
   <wsrm:CreateSequenceResponse>
    <Identifier>
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386
    </Identifier>
    <Accept>
    <AcksTo>
      <a:Address>
        http://BusinessABC.com/serviceA
      </a:Address>
    </AcksTo>
    </Accept>
   </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence"></a><span data-ttu-id="0c98a-143">시퀀스</span><span class="sxs-lookup"><span data-stu-id="0c98a-143">Sequence</span></span>

<span data-ttu-id="0c98a-144">다음은 시퀀스에 적용되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-144">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="0c98a-145">B1201: WCF `xs:long` 는 최대 포함 값 9223372036854775807 보다 큰 시퀀스 번호를 생성 하 고 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-145">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

- <span data-ttu-id="0c98a-146">B1202: WCF는 항상의 동작 URI를 사용 하 여 비어 있는 마지막 메시지를 생성 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-146">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

- <span data-ttu-id="0c98a-147">B1203: WCF는 `LastMessage` 작업 URI가이 아닌 경우 요소를 포함 하는 시퀀스 헤더를 사용 하 여 메시지를 받고 배달 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-147">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

<span data-ttu-id="0c98a-148">시퀀스 헤더의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-148">An example of a Sequence Header.</span></span>

```xml
<wsrm:Sequence>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
  <wsrm:MessageNumber>
    10
  </wsrm:MessageNumber>
  <wsrm:LastMessage/>
 </wsrm:Sequence>
```

### <a name="ackrequested-header"></a><span data-ttu-id="0c98a-149">AckRequested 헤더</span><span class="sxs-lookup"><span data-stu-id="0c98a-149">AckRequested Header</span></span>

<span data-ttu-id="0c98a-150">WCF는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-150">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="0c98a-151">WCF는 선택적 요소를 생성 하지 않습니다 `MessageNumber` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-151">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="0c98a-152">요소가 포함 된 헤더를 사용 하 여 메시지를 받으면 `AckRequested` `MessageNumber` WCF는 `MessageNumber` 다음 예제와 같이 요소의 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-152">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="0c98a-153">SequenceAcknowledgement 헤더</span><span class="sxs-lookup"><span data-stu-id="0c98a-153">SequenceAcknowledgement Header</span></span>

<span data-ttu-id="0c98a-154">WCF는 WS-Reliable 메시징에 제공 된 시퀀스 승인에 피기백 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-154">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>

- <span data-ttu-id="0c98a-155">R1401: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `SequenceAcknowledgement` 헤더가 받는 사람에게 전송된 애플리케이션 메시지에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-155">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>

- <span data-ttu-id="0c98a-156">B1402: WCF는 메시지를 충족 하기 위해 시퀀스 메시지를 받기 전에 승인을 생성 해야 하는 경우 `AckRequested` `SequenceAcknowledgement` 다음 예제와 같이 0-0 범위를 포함 하는 헤더를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-156">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="0c98a-157">B1403: WCF는 `SequenceAcknowledgement` 요소를 포함 `Nack` 하지만 요소를 지 원하는 헤더를 생성 하지 않습니다 `Nack` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-157">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="0c98a-158">WS-ReliableMessaging 오류</span><span class="sxs-lookup"><span data-stu-id="0c98a-158">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="0c98a-159">다음은 WS-Reliable 메시징 오류의 WCF 구현에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-159">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>

- <span data-ttu-id="0c98a-160">B1501: WCF는 오류를 생성 하지 않습니다 `MessageNumberRollover` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-160">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="0c98a-161">B1502: WCF 끝점 `CreateSequenceRefused` 은 사양에 설명 된 대로 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-161">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>

- <span data-ttu-id="0c98a-162">B1503: 서비스 끝점이 해당 연결 제한에 도달 하 여 새 연결을 처리할 수 없는 경우 WCF는 `CreateSequenceRefused` `netrm:ConnectionLimitReached` 다음 예제와 같이 추가 오류 하위 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-162">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

  ```xml
  <s:Envelope>
    <s:Header>
      <wsa:Action>
        http://schemas.xmlsoap.org/ws/2005/08/addressing/fault
      </wsa:Action>
    </s:Header>
    <s:Body>
      <s:Fault>
        <s:Code>
          <s:Value>
            s:Receiver
          </s:Value>
          <s:Subcode>
            <s:Value>
              wsrm:CreateSequenceRefused
            </s:Value>
            <s:Subcode>
              <s:Value>
                netrm:ConnectionLimitReached
              </s:Value>
            </s:Subcode>
          </s:Subcode>
        </s:Code>
        <s:Reason>
          <s:Text xml:lang="en">
            [Reason]
          </s:Text>
        </s:Reason>
      </s:Fault>
    </s:Body>
  </s:Envelope>
  ```

### <a name="ws-addressing-faults"></a><span data-ttu-id="0c98a-163">WS-Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="0c98a-163">WS-Addressing Faults</span></span>

<span data-ttu-id="0c98a-164">WS-Reliable 메시징에서 WS-ADDRESSING을 사용 하기 때문에 WCF WS-Reliable 메시징 구현에서 WS-Addressing 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-164">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="0c98a-165">이 섹션에서는 WCF가 WS-Reliable 메시징 계층에서 명시적으로 생성 하는 WS-Addressing 오류에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-165">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>

- <span data-ttu-id="0c98a-166">B1601: WCF는 다음 조건 중 하나에 해당 하는 경우 필요한 오류 메시지 주소 지정 헤더를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-166">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>

  - <span data-ttu-id="0c98a-167">메시지에 `Sequence` 헤더 및 `Action` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-167">A message is missing a `Sequence` header and an `Action` header.</span></span>

  - <span data-ttu-id="0c98a-168">`CreateSequence` 메시지에 `MessageId` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-168">A `CreateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="0c98a-169">`CreateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-169">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>

- <span data-ttu-id="0c98a-170">B1602: WCF는 헤더가 누락 된 메시지에 대 한 회신에서 지원 되지 않는 오류 작업을 생성 하 `Sequence` 고 `Action` WS-Reliable 메시징 사양에서 인식할 수 없는 헤더를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-170">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>

- <span data-ttu-id="0c98a-171">B1603: WCF는 끝점에서 `CreateSequence` 메시지의 주소 지정 헤더 검사를 기반으로 시퀀스를 처리 하지 않음을 나타내는 오류 끝점을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-171">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="0c98a-172">프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="0c98a-172">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="0c98a-173">WS-Addressing을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="0c98a-173">Composition with WS-Addressing</span></span>

<span data-ttu-id="0c98a-174">WCF는 두 가지 버전의 WS-ADDRESSING을 지원 합니다. WS-Addressing 2004/08 [WS-ADDR] 및 W3C WS-Addressing 1.0 권장 사항 [WS-addr] 및 [WS-ADDRESSING-SOAP].</span><span class="sxs-lookup"><span data-stu-id="0c98a-174">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="0c98a-175">WS-Reliable Messaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-175">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="0c98a-176">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-176">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="0c98a-177">R2101:WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-177">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="0c98a-178">R2102: 단일 버전의 WS-Addressing는 지정 된 WS-Reliable 메시징 시퀀스 또는 메커니즘을 사용 하 여 상호 관련 된 역방향 시퀀스 쌍을 통해 사용 해야 합니다 `wsrm:Offer` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-178">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="0c98a-179">SOAP를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="0c98a-179">Composition with SOAP</span></span>

<span data-ttu-id="0c98a-180">WCF는 WS-Reliable 메시징에 SOAP 1.1 및 SOAP 1.2을 모두 사용할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-180">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="0c98a-181">WS-Security 및 WS-SecureConversation을 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="0c98a-181">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="0c98a-182">WCF는 보안 전송 (HTTPS), WS-SECURITY를 사용 하 여 컴퍼지션 및 WS-Secure 대화를 사용 하 여 컴퍼지션을 WS-Reliable 메시징 시퀀스를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-182">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="0c98a-183">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-183">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="0c98a-184">R2301: 개별 메시지의 무결성과 기밀성 뿐만 아니라 WS-Reliable 메시징 시퀀스의 무결성을 보호 하기 위해 WCF를 사용 하려면 WS-Secure 대화를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-184">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="0c98a-185">R2302:WS-Secure Conversation 세션은 WS-Reliable Messaging 시퀀스를 설정하기 전에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-185">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>

- <span data-ttu-id="0c98a-186">R2303: WS-Reliable Messaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-186">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="0c98a-187">B2304:WS-Reliable Messaging 시퀀스 또는 한 쌍의 상호 관련된 역방향 시퀀스는 항상 단일 WS-SecureConversation 세션에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-187">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

  <span data-ttu-id="0c98a-188">WCF 소스는 `wsse:SecurityTokenReference` 메시지의 요소 확장성 섹션에서 요소를 생성 합니다 `CreateSequence` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-188">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>

- <span data-ttu-id="0c98a-189">R2305: WS-Secure 대화로 구성 된 경우 메시지에는 `CreateSequence` 요소가 포함 되어야 합니다 `wsse:SecurityTokenReference` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-189">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>

## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="0c98a-190">WS-Reliable Messaging WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="0c98a-190">WS-Reliable Messaging WS-Policy Assertion</span></span>

<span data-ttu-id="0c98a-191">WCF는 WS-Reliable 메시징 WS-Policy 어설션을 사용 하 여 `wsrm:RMAssertion` 끝점 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-191">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="0c98a-192">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-192">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="0c98a-193">B3001: WCF `wsrm:RMAssertion` WS-Policy Assertion을 요소에 연결 `wsdl:binding` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-193">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="0c98a-194">WCF는 및 요소에 대 한 첨부 파일을 모두 지원 `wsdl:binding` `wsdl:port` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-194">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="0c98a-195">B3002: WCF는 WS-Reliable 메시징 어설션의 다음과 같은 선택적 속성을 지원 하 고 WCF에서이를 제어할 수 있도록 합니다 `ReliableMessagingBindingElement` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-195">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  <span data-ttu-id="0c98a-196">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-196">The following is an example.</span></span>

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="0c98a-197">흐름 제어 WS-Reliable Messaging 확장</span><span class="sxs-lookup"><span data-stu-id="0c98a-197">Flow Control WS-Reliable Messaging Extension</span></span>

<span data-ttu-id="0c98a-198">WCF는 WS-Reliable 메시징 확장성을 사용 하 여 시퀀스 메시지 흐름에 대 한 선택적 추가 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-198">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="0c98a-199">속성을로 설정 하 여 흐름 제어를 사용 하도록 설정 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-199">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="0c98a-200">다음은 WCF에 적용 되는 제약 조건의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-200">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="0c98a-201">B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF는 `netrm:BufferRemaining` 헤더의 요소 확장성에 요소를 생성 `SequenceAcknowledgement` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-201">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="0c98a-202">B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 `netrm:BufferRemaining` `SequenceAcknowledgement` 다음 예제와 같이 WCF는 요소를 헤더에 표시 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-202">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      http://fabrikam123.com/abc
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>
      8
    </netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="0c98a-203">B4003: WCF는를 사용 하 여 `netrm:BufferRemaining` 신뢰할 수 있는 메시징 대상이 버퍼링 할 수 있는 새 메시지 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-203">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>

- <span data-ttu-id="0c98a-204">B4004: 신뢰할 수 있는 메시징 대상 응용 프로그램에서 메시지를 신속 하 게 받을 수 없을 때 전송 되는 메시지 수를 제한 WCF 신뢰할 수 있는 메시징 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-204">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="0c98a-205">신뢰할 수 있는 메시징 대상은 메시지를 버퍼링하고 요소의 값을 0으로 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-205">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>

- <span data-ttu-id="0c98a-206">B4005: WCF `netrm:BufferRemaining` 는 0에서 4096 사이의 정수 값을 생성 하 고 0에서 214748364 사이의 정수 값을 읽습니다 `xs:int` `maxInclusive` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-206">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="0c98a-207">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="0c98a-207">Message Exchange Patterns</span></span>

<span data-ttu-id="0c98a-208">이 섹션에서는 여러 메시지 교환 패턴에 WS-Reliable Messaging이 사용 되는 경우 WCF의 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-208">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="0c98a-209">각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-209">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="0c98a-210">주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-210">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="0c98a-211">주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-211">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="0c98a-212">주소를 지정할 수 없는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="0c98a-212">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="0c98a-213">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c98a-213">Binding</span></span>

<span data-ttu-id="0c98a-214">WCF는 한 개의 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-214">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="0c98a-215">WCF는 HTTP 요청을 사용 하 여 RMS의 모든 메시지를 RMD에 전송 하 고 HTTP 응답을 사용 하 여 RMD의 모든 메시지를 RMS로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-215">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="0c98a-216">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-216">CreateSequence Exchange</span></span>

<span data-ttu-id="0c98a-217">WCF 개시자는 제공이 `CreateSequence` 없는 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-217">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="0c98a-218">WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에가 제공 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-218">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="0c98a-219">WCF 응답자는 `CreateSequence` 메시지와 함께 요청에 응답 합니다 `CreateSequenceResponse` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-219">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="0c98a-220">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="0c98a-220">SequenceAcknowledgement</span></span>

<span data-ttu-id="0c98a-221">WCF 초기자는 `CreateSequence` 메시지 및 오류 메시지를 제외한 모든 메시지의 회신에 대 한 승인을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-221">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="0c98a-222">WCF 응답자는 항상 시퀀스와 메시지에 대 한 응답에 독립 실행형 승인을 생성 합니다 `AckRequested` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-222">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>

#### <a name="terminatesequence-message"></a><span data-ttu-id="0c98a-223">TerminateSequence 메시지</span><span class="sxs-lookup"><span data-stu-id="0c98a-223">TerminateSequence message</span></span>

<span data-ttu-id="0c98a-224">WCF는 `TerminateSequence` 단방향 작업으로 처리 합니다. 즉, http 응답에는 빈 본문과 http 202 상태 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-224">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="0c98a-225">주소를 지정할 수 있는 단방향 개시자</span><span class="sxs-lookup"><span data-stu-id="0c98a-225">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="0c98a-226">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c98a-226">Binding</span></span>

<span data-ttu-id="0c98a-227">WCF는 인바운드 및 아웃 바운드 Http 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-227">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="0c98a-228">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-228">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c98a-229">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-229">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="0c98a-230">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-230">CreateSequence Exchange</span></span>

<span data-ttu-id="0c98a-231">WCF 개시자는 제공이 `CreateSequence` 없는 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-231">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="0c98a-232">WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제품이 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-232">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="0c98a-233">WCF 응답자는 `CreateSequenceResponse` 끝점 참조로 주소가 지정 된 HTTP 요청에 메시지를 전송 합니다 `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-233">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="0c98a-234">주소를 지정할 수 있는 이중 개시자</span><span class="sxs-lookup"><span data-stu-id="0c98a-234">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="0c98a-235">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c98a-235">Binding</span></span>

<span data-ttu-id="0c98a-236">WCF는 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 완전 한 비동기 양방향 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-236">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="0c98a-237">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-237">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c98a-238">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-238">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="0c98a-239">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-239">CreateSequence Exchange</span></span>

<span data-ttu-id="0c98a-240">WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-240">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c98a-241">WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-241">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="0c98a-242">WCF는 `CreateSequenceResponse` `CreateSequence` 의 끝점 참조로 주소가 지정 된 HTTP 요청에 대 한를 보냅니다 `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-242">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="0c98a-243">시퀀스 수명</span><span class="sxs-lookup"><span data-stu-id="0c98a-243">Sequence Lifetime</span></span>

<span data-ttu-id="0c98a-244">WCF는 두 시퀀스를 완전 한 이중 세션으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-244">WCF treats the two sequences as one fully duplex session.</span></span>

<span data-ttu-id="0c98a-245">한 시퀀스에 오류가 발생 하는 오류를 생성 하면 WCF는 원격 끝점에서 두 시퀀스를 모두 오류를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-245">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="0c98a-246">한 시퀀스에 오류가 발생 하는 오류를 읽을 때 WCF는 두 시퀀스를 모두 오류를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-246">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="0c98a-247">WCF는 아웃 바운드 시퀀스를 닫고 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-247">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="0c98a-248">반대로, WCF는 인바운드 시퀀스의 닫기를 처리 하 고 아웃 바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-248">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="0c98a-249">요청-회신, 주소를 지정할 수 없는 개시자</span><span class="sxs-lookup"><span data-stu-id="0c98a-249">Request-Reply, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="0c98a-250">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c98a-250">Binding</span></span>

<span data-ttu-id="0c98a-251">WCF는 하나의 HTTP 채널에 대 한 두 개의 시퀀스를 사용 하는 단방향 및 요청-회신 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-251">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="0c98a-252">WCF는 HTTP 요청을 사용 하 여 요청 시퀀스의 메시지를 전송 하 고 HTTP 응답을 사용 하 여 회신 시퀀스의 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-252">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="0c98a-253">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-253">CreateSequence Exchange</span></span>

<span data-ttu-id="0c98a-254">WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-254">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c98a-255">WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-255">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="0c98a-256">WCF 응답자는 `CreateSequence` 메시지와 함께 요청에 응답 합니다 `CreateSequenceResponse` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-256">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="0c98a-257">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="0c98a-257">One-way Message</span></span>

<span data-ttu-id="0c98a-258">단방향 메시지 교환 프로토콜을 성공적으로 완료 하기 위해 WCF 초기자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 `SequenceAcknowledgement` http 응답에 대 한 독립 실행형 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-258">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="0c98a-259">`SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-259">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="0c98a-260">WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-260">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="0c98a-261">양방향 메시지</span><span class="sxs-lookup"><span data-stu-id="0c98a-261">Two Way Messages</span></span>

<span data-ttu-id="0c98a-262">양방향 메시지 교환 프로토콜을 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-262">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="0c98a-263">응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-263">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="0c98a-264">WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-264">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="0c98a-265">단방향 메시지가 있고 애플리케이션이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-265">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="0c98a-266">회신 다시 시도</span><span class="sxs-lookup"><span data-stu-id="0c98a-266">Retrying Replies</span></span>

<span data-ttu-id="0c98a-267">WCF는 양방향 메시지 교환 프로토콜 상관 관계에 대 한 HTTP 요청-회신 상관 관계에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-267">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="0c98a-268">이로 인해 WCF 개시자는 요청 시퀀스 메시지가 승인 되는 경우, HTTP 응답이 승인, 사용자 메시지 또는 오류를 전달 하는 경우 요청 시퀀스 메시지를 다시 시도 하는 것을 중지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-268">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="0c98a-269">WCF 응답자는 회신이 상호 관련 된 요청의 HTTP 요청 레그에 대 한 회신을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-269">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>

#### <a name="lastmessage-exchange"></a><span data-ttu-id="0c98a-270">LastMessage 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-270">LastMessage Exchange</span></span>

<span data-ttu-id="0c98a-271">WCF 개시자는 HTTP 요청 레그에서 비어 있는 마지막 메시지를 생성 하 고 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-271">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="0c98a-272">WCF에는 응답이 필요 하지만 실제 응답 메시지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-272">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="0c98a-273">WCF 응답자는 회신 시퀀스의 비어 있는 마지막 메시지를 사용 하 여 요청 시퀀스의 비어 있는 마지막 메시지에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-273">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>

<span data-ttu-id="0c98a-274">WCF 응답자에서 작업 URI가 아닌 마지막 메시지를 수신 하는 경우 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` wcf는 마지막 메시지를 사용 하 여 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-274">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="0c98a-275">양방향 메시지 교환 프로토콜의 경우 마지막 메시지에 애플리케이션 메시지가 포함되어 있으며, 단방향 메시지 교환 프로토콜의 경우 마지막 메시지는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-275">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>

<span data-ttu-id="0c98a-276">WCF 응답자는 회신 시퀀스의 비어 있는 마지막 메시지에 대 한 승인이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-276">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="0c98a-277">TerminateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-277">TerminateSequence Exchange</span></span>

<span data-ttu-id="0c98a-278">모든 요청이 유효한 회신을 받으면 WCF 개시자는 `TerminateSequence` HTTP 요청 레그에서 요청 시퀀스의 메시지를 생성 하 고 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-278">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="0c98a-279">WCF에는 응답이 필요 하지만 실제 응답 메시지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-279">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="0c98a-280">WCF 응답자는 회신 시퀀스의 메시지를 사용 하 여 요청 시퀀스의 메시지에 응답 합니다 `TerminateSequence` `TerminateSequence` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-280">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>

<span data-ttu-id="0c98a-281">정상적인 종료 시퀀스에서 두 `TerminateSequence` 메시지 모두에 전체 범위의 `SequenceAcknowledgement`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-281">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="0c98a-282">요청/회신, 주소를 지정할 수 있는 개시자</span><span class="sxs-lookup"><span data-stu-id="0c98a-282">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="0c98a-283">바인딩</span><span class="sxs-lookup"><span data-stu-id="0c98a-283">Binding</span></span>

<span data-ttu-id="0c98a-284">WCF는 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 요청-회신 메시지 교환 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-284">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="0c98a-285">WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-285">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c98a-286">모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-286">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="0c98a-287">CreateSequence 교환</span><span class="sxs-lookup"><span data-stu-id="0c98a-287">CreateSequence Exchange</span></span>

<span data-ttu-id="0c98a-288">WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-288">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c98a-289">WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-289">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="0c98a-290">WCF는 `CreateSequenceResponse` `CreateSequence` 의 끝점 참조로 주소가 지정 된 HTTP 요청에 대 한를 보냅니다 `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-290">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="0c98a-291">요청/회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="0c98a-291">Request/Reply Correlation</span></span>

<span data-ttu-id="0c98a-292">WCF 개시자는 모든 응용 프로그램 요청 메시지 `MessageId` 와 `ReplyTo` 끝점 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-292">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="0c98a-293">WCF 개시자는 `CreateSequence` `ReplyTo` 각 응용 프로그램 요청 메시지에 메시지의 끝점 참조를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-293">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="0c98a-294">WCF 응답자는 들어오는 요청 메시지에 및가 필요 합니다 `MessageId` `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="0c98a-294">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="0c98a-295">WCF 응답자는 `CreateSequence` 및 모든 응용 프로그램 요청 메시지의 끝점 참조 URI가 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c98a-295">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
