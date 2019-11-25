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
# <a name="reliable-messaging-protocol-version-11"></a>안정적인 메시징 프로토콜 버전 1.1

이 항목에서는 HTTP 전송을 사용 하 여 상호 운용에 필요한 WS-RELIABLEMESSAGING 2 월 2007 (버전 1.1) 프로토콜에 대 한 WCF (Windows Communication Foundation) 구현 세부 정보를 다룹니다. WCF는이 항목에서 설명 하는 제약 조건 및 설명과 함께 WS-RELIABLEMESSAGING 사양을 따릅니다. WS-RELIABLEMESSAGING 버전 1.1 프로토콜은 .NET Framework 3.5부터 구현 됩니다.

WS-RELIABLEMESSAGING 2 월 2007 프로토콜은 WCF에서 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>에 의해 구현 됩니다.

편의상 이 항목에서는 다음 역할을 사용합니다.

- 개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.

- 응답자: 개시자의 요청을 받는 서비스입니다.

 이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.

|접두사|네임스페이스|
|-|-|
|wsrm|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|
|s|http://www.w3.org/2003/05/soap-envelope|
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|wsrmp|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|netrmp|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|wsp|(WS-Policy 1.2 또는 WS-Policy 1.5)|

## <a name="messaging"></a>Messaging(메시징)

### <a name="sequence-creation"></a>시퀀스 만들기

WCF는 `CreateSequence` 및 `CreateSequenceResponse` 메시지를 구현 하 여 신뢰할 수 있는 메시징 시퀀스를 설정 합니다. 적용되는 제약 조건은 다음과 같습니다.

- B1101: WCF 개시자는 `CreateSequence` 메시지의 `ReplyTo`, `AcksTo` 및 `Offer/Endpoint`와 동일한 끝점 참조를 사용 합니다.

- R1102: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 엔드포인트 참조에는 8비트 형식과 일치하도록 동일한 문자열 표현을 포함하는 주소 값이 있어야 합니다.

  - WCF 응답자는 시퀀스를 만들기 전에 `AcksTo`, `ReplyTo` 및 `Endpoint` 끝점 참조의 URI 부분이 동일한 지 확인 합니다.

- R1103: `AcksTo` 메시지의 `ReplyTo`, `Offer/Endpoint` 및 `CreateSequence` 엔드포인트 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.

  - WCF는를 적용 하지 않지만 `CreateSequence`에 대 한 `AcksTo`, `ReplyTo` 및 `Offer/Endpoint` 끝점 참조의 참조 매개 변수는 동일 하며, 승인 및 역방향 시퀀스 메시지에 대해 `ReplyTo` 끝점 참조의 참조 매개 변수를 사용 하는 것으로 가정 합니다.

- B1104: WCF 개시자는 `CreateSequence` 메시지에서 선택적 `Expires` 또는 `Offer/Expires` 요소를 생성 하지 않습니다.

- B1105: `CreateSequence` 메시지에 액세스할 때 WCF 응답자는 `CreateSequence` 요소의 `Expires` 값을 `CreateSequenceResponse` 요소의 `Expires` 값으로 사용 합니다. 그렇지 않으면 WCF 응답자는 `Expires` 및 `Offer/Expires` 값을 읽고 무시 합니다.

- B1106: `CreateSequenceResponse` 메시지에 액세스할 때 WCF 개시자는 선택적 `Expires` 값을 읽지만 사용 하지는 않습니다.

- B1107: WCF 시작자 및 응답자는 항상 `CreateSequence/Offer` 및 `CreateSequenceResponse` 요소에 선택적 `IncompleteSequenceBehavior` 요소를 생성 합니다.

- B1108: WCF는 `IncompleteSequenceBehavior` 요소의 `DiscardFollowingFirstGap` 및 `NoDiscard` 값만 사용 합니다.

  - WS-ReliableMessaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.

- B1109: `CreateSequence`에 `Offer` 요소가 포함 된 경우 WCF 응답자는 `Accept` 요소 없이 `CreateSequenceResponse` 응답 하 여 제공 된 시퀀스를 거부 하는 방법입니다.

- B1110: 신뢰할 수 있는 메시징 응답기에서 제공 된 시퀀스를 거부 하는 경우 WCF 초기자는 새로 설정 된 시퀀스에 오류가 발생 합니다.

- B1111: `CreateSequence`에 `Offer` 요소가 포함 되지 않은 경우 양방향 WCF 응답자는 `CreateSequenceRefused` 오류에 응답 하 여 제공 된 시퀀스를 거부 합니다.

- R1112: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]` 엔드포인트 참조의 `CreateSequenceResponse/Accept/AcksTo` 속성은 `CreateSequence` 메시지 바이트별 대상 URI와 일치해야 합니다.

- R1113: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자에서 응답자로 이동하는 두 시퀀스의 모든 메시지를 같은 엔드포인트 참조로 보내야 합니다.

WCF는 ws-reliablemessaging을 사용 하 여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 합니다. WCF WS-RELIABLEMESSAGING 구현은 단방향, 요청-회신 및 전체 이중 메시징 패턴에 대 한 신뢰할 수 있는 세션을 제공 합니다. ph x="1" /&gt; 및 `Offer`에서 WS-ReliableMessaging `CreateSequence` 메커니즘을 사용하면 상호 관련된 두 개의 역방향 시퀀스를 설정하고 모든 메시지 엔드포인트에 적합한 세션 프로토콜을 제공합니다. WCF는 세션 무결성을 위한 종단 간 보호를 포함 하 여 세션에 대 한 보안 보장을 제공 하므로 같은 파티에 대 한 메시지가 동일한 대상에 도착 하는지 확인 하는 것이 실용적입니다. 이렇게 하면 애플리케이션 메시지에서 &quot;피기백킹&quot;이라고 하는 시퀀스 승인을 사용할 수 있습니다. 따라서 제약 조건 R1102, R1112 및 R1113가 WCF에 적용 됩니다.

`CreateSequence` 메시지의 예입니다.

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

`CreateSequenceResponse` 메시지의 예입니다.

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

### <a name="closing-a-sequence"></a>시퀀스 닫기

WCF는 신뢰할 수 있는 메시징 원본에서 시작 된 종료를 위해 `CloseSequence` 및 `CloseSequenceResponse` 메시지를 사용 합니다. WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않으며 WCF 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상 종료를 지원 하지 않습니다. 적용되는 제약 조건은 다음과 같습니다.

- B1201: WCF 신뢰할 수 있는 메시징 소스는 항상 시퀀스를 종료 하는 `CloseSequence` 메시지를 보냅니다.

- B1202: 신뢰할 수 있는 메시징 소스는 시퀀스 메시지 전체 범위의 승인을 기다린 다음 `CloseSequence` 메시지를 보냅니다.

- B1203: 시퀀스에 메시지가 있으면 신뢰할 수 있는 메시징 소스에는 항상 선택적 `LastMsgNumber` 요소가 포함됩니다.

- R1204: 신뢰할 수 있는 메시징 대상은 `CloseSequence` 메시지를 보내어 종료를 시작하면 안 됩니다.

- B1205: `CloseSequence` 메시지가 수신 되 면 WCF 신뢰할 수 있는 메시징 소스는 시퀀스를 불완전 하 게 간주 하 고 오류를 보냅니다.

 `CloseSequence` 메시지의 예입니다.

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

예제 `CloseSequenceResponse` 메시지:

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

### <a name="sequence-termination"></a>시퀀스 종료

WCF는 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 완료 한 후 `TerminateSequence/TerminateSequenceResponse` 핸드셰이크를 주로 사용 합니다. WCF 신뢰할 수 있는 메시징 대상은 종료를 시작 하지 않으며 신뢰할 수 있는 메시징 소스는 신뢰할 수 있는 메시징 대상이 시작한 종료를 지원 하지 않습니다. 적용되는 제약 조건은 다음과 같습니다.

- B1301: WCF 개시자는 `CloseSequence/CloseSequenceResponse` 핸드셰이크를 성공적으로 완료 한 후에만 `TerminateSequence` 메시지를 보냅니다.

- R1302: WCF는 `LastMsgNumber` 요소가 지정 된 시퀀스에 대해 모든 `CloseSequence` 및 `TerminateSequence` 메시지에서 일치 하는지 확인 합니다. 즉, `LastMsgNumber`가 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 없거나, 모든 `CloseSequence` 및 `TerminateSequence` 메시지에 있으며 이러한 메시지에서 동일합니다.

- B1303: `TerminateSequence` 핸드셰이크 이후 `CloseSequence/CloseSequenceResponse` 메시지를 받을 때 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지로 응답합니다. 신뢰할 수 있는 메시징 소스에 `TerminateSequence` 메시지를 보내기 전의 최종 승인이 있으므로 신뢰할 수 있는 메시징 대상은 시퀀스가 종료되고 리소스를 즉시 회수함을 인식하고 있습니다.

- B1304: `CloseSequence/CloseSequenceResponse` 핸드셰이크 이전에 `TerminateSequence` 메시지를 수신 하는 경우 WCF 신뢰할 수 있는 메시징 대상은 `TerminateSequenceResponse` 메시지를 사용 하 여 응답 합니다. 신뢰할 수 있는 메시징 대상이 시퀀스에서 일치하지 않는 부분이 없음을 확인한 경우에는 클라이언트가 최종 승인을 받을 수 있도록 신뢰할 수 있는 메시징 대상이 애플리케이션 대상에서 지정한 시간 동안 기다린 다음 리소스를 회수합니다. 그렇지 않은 경우 신뢰할 수 있는 메시징 대상이 리소스를 바로 회수하고 애플리케이션 대상에 `Faulted` 이벤트를 발생시켜 시퀀스에 오류가 발생하여 종료되었음을 알려 줍니다.

`TerminateSequence` 메시지의 예입니다.

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

예제 `TerminateSequenceResponse` 메시지:

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

### <a name="sequences"></a>시퀀스

다음은 시퀀스에 적용되는 제약 조건의 목록입니다.

- B1401: WCF는 `xs:long`의 최대 포함 값 9223372036854775807 보다 큰 시퀀스 번호를 생성 하 고 액세스 합니다.

`Sequence` 헤더의 예입니다.

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a>승인 요청

WCF는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용 합니다.

`AckRequested` 헤더의 예입니다.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF는 신뢰할 수 있는 메시징에 제공 된 시퀀스 승인에 "피기백" 메커니즘을 사용 합니다. 적용되는 제약 조건은 다음과 같습니다.

- R1601: `Offer` 메커니즘을 사용 하 여 두 개의 역방향 시퀀스가 설정 된 경우 `SequenceAcknowledgement` 헤더는 의도 한 받는 사람에 게 전송 된 모든 응용 프로그램 메시지에 포함 될 수 있습니다. 원격 엔드포인트에서는 피기백된 `SequenceAcknowledgement` 헤더에 액세스할 수 있어야 합니다.

- B1602: WCF는 `Nack` 요소를 포함 하는 `SequenceAcknowledgement` 헤더를 생성 하지 않습니다. WCF는 각 `Nack` 요소에 시퀀스 번호가 포함 되어 있는지 확인 하지만, 그렇지 않은 경우에는 `Nack` 요소와 값을 무시 합니다.

 `SequenceAcknowledgement` 헤더의 예입니다.

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging 오류

다음은 WS-RELIABLEMESSAGING 오류의 WCF 구현에 적용 되는 제약 조건의 목록입니다. 적용되는 제약 조건은 다음과 같습니다.

- B1701: WCF는 `MessageNumberRollover` 오류를 생성 하지 않습니다.

- B1702: SOAP 1.2를 통해 서비스 끝점이 해당 연결 제한에 도달 하 여 새 연결을 처리할 수 없는 경우 WCF는 다음 예제와 같이 중첩 된 `CreateSequenceRefused` 오류 하위 코드 `netrm:ConnectionLimitReached`생성 합니다.

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

### <a name="ws-addressing-faults"></a>WS-Addressing 오류

Ws-reliablemessaging은 WS-ADDRESSING을 사용 하기 때문에 WCF WS-RELIABLEMESSAGING 구현이 WS-ADDRESSING 오류를 생성 하 고 전송할 수 있습니다. 이 섹션에서는 WCF에서 명시적으로 생성 하 고 ws-reliablemessaging 계층에서 전송 하는 WS-ADDRESSING 오류에 대해 설명 합니다.

- B1801: WCF는 다음 조건 중 하나에 해당 하는 경우 `Message Addressing Header Required` 오류를 생성 하 고 전송 합니다.

  - `CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `MessageId` 헤더가 없습니다.

  - `CreateSequence`, `CloseSequence` 또는 `TerminateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.

  - `CreateSequenceResponse`, `CloseSequenceResponse` 또는 `TerminateSequenceResponse` 메시지에 `RelatesTo` 헤더가 없습니다.

- B1802: WCF는 `Endpoint Unavailable` 오류를 생성 하 고 전송 하 여 `CreateSequence` 메시지의 주소 지정 헤더 검사를 기반으로 시퀀스를 처리할 수 있는 끝점을 수신 대기 하지 않음을 표시 합니다.

## <a name="protocol-composition"></a>프로토콜 구성

### <a name="composition-with-ws-addressing"></a>WS-Addressing을 사용하여 구성

WCF는 ws-addressing 2004/08 [WS-ADDR] 및 W3C WS-ADDRESSING 1.0 권장 사항 [WS-POLICY-CORE] 및 [WS-ADDRESSING-SOAP]의 두 가지 버전 주소를 지원 합니다.

WS-ReliableMessaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- R2101: WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.

- R2102: 단일 버전의 WS-Addressing은 `Offer` 메커니즘을 사용하여 상호 관련된 한 쌍의 역방향 시퀀스 또는 제공된 WS-ReliableMessaging 시퀀스 전체에서 사용할 수 있어야 합니다.

### <a name="composition-with-soap"></a>SOAP를 사용하여 구성

WCF는 신뢰할 수 있는 메시징을 사용 하 여 SOAP 1.1 및 SOAP 1.2을 모두 사용할 수 있도록 지원 합니다.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>WS-Security 및 WS-SecureConversation을 사용하여 구성

WCF는 보안 전송 (HTTPS), WS-SECURITY를 사용 하 여 컴퍼지션 및 WS-SECURITY를 사용 하 여 구성 하는 ws-reliablemessaging 시퀀스에 대 한 보호를 제공 합니다. WS-ReliableMessaging 1.1 프로토콜, WS-Security 1.1 및 WS-Secure Conversation 1.3 프로토콜을 함께 사용해야 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- R2301: 개별 메시지의 무결성과 기밀성 뿐만 아니라 WS-RELIABLEMESSAGING 시퀀스의 무결성을 보호 하기 위해 WCF에서는 WS-SECURITY 대화를 사용 해야 합니다.

- R2302: AWS 시퀀스를 설정 하기 전에 보안 대화 세션을 설정 해야 합니다.

- R2303: WS-ReliableMessaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.

- B2304: WS-RELIABLEMESSAGING 시퀀스 또는 상관 관계가 지정 된 역방향 시퀀스의 쌍은 항상 단일 Ws-secureconversation 세션에 바인딩됩니다.

- R2305: WS-SECURITY 대화로 구성 된 경우 WCF 응답자는 `CreateSequence` 메시지에 `wsse:SecurityTokenReference` 요소와 `wsrm:UsesSequenceSTR` 헤더가 포함 되어야 합니다.

 `UsesSequenceSTR` 헤더의 예입니다.

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a>SSL/TLS 세션을 사용하여 구성

WCF는 SSL/TLS 세션을 사용한 컴퍼지션을 지원 하지 않습니다.

- B2401: WCF는 `wsrm:UsesSequenceSSL` 헤더를 생성 하지 않습니다.

- R2402: 신뢰할 수 있는 메시징 개시자는 `wsrm:UsesSequenceSSL` 헤더를 포함 하는 `CreateSequence` 메시지를 WCF 응답자에 게 보내지 않아야 합니다.

### <a name="composition-with-ws-policy"></a>WS-Policy를 사용하여 구성

WCF는 ws-policy 1.2 및 WS-POLICY 1.5의 두 가지 버전 정책을 지원 합니다.

## <a name="ws-reliablemessaging-ws-policy-assertion"></a>WS-ReliableMessaging WS-Policy Assertion

WCF는 ws-reliablemessaging WS 정책 어설션 `wsrm:RMAssertion`를 사용 하 여 끝점 기능을 설명 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- B3001: WCF `wsrmn:RMAssertion` WS-POLICY 어설션을 `wsdl:binding` 요소에 연결 합니다. WCF는 `wsdl:binding` 및 `wsdl:port` 요소에 대 한 첨부 파일을 모두 지원 합니다.

- B3002: WCF는 `wsp:Optional` 태그를 생성 하지 않습니다.

- B3003: `wsrmp:RMAssertion` WS-POLICY 어설션에 액세스할 때 WCF는 `wsp:Optional` 태그를 무시 하 고 WS-RM 정책을 필수로 처리 합니다.

- R3004: WCF는 SSL/TLS 세션을 사용 하 여 구성 하지 않으므로 WCF는 `wsrmp:SequenceTransportSecurity`를 지정 하는 정책을 허용 하지 않습니다.

- B3005: WCF는 항상 `wsrmp:DeliveryAssurance` 요소를 생성 합니다.

- B3006: WCF는 항상 `wsrmp:ExactlyOnce` 배달 보증을 지정 합니다.

- B3007: WCF는 ws-reliablemessaging 어설션의 다음 속성을 생성 하 고 읽고 WCF`ReliableSessionBindingElement`에서 해당 속성에 대 한 제어를 제공 합니다.

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  `RMAssertion`의 예입니다.

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

## <a name="flow-control-ws-reliablemessaging-extension"></a>흐름 제어 WS-ReliableMessaging 확장명

WCF는 WS-RELIABLEMESSAGING 확장성을 사용 하 여 시퀀스 메시지 흐름에 대 한 선택적인 추가 제어 기능을 제공 합니다.

<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> 속성을 `true`설정 하 여 흐름 제어를 사용 하도록 설정 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF는 다음 예제와 같이 `SequenceAcknowledgement` 헤더의 요소 확장성에 `netrm:BufferRemaining` 요소를 생성 합니다.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우에도 WCF는 `SequenceAcknowledgement` 헤더에 `netrm:BufferRemaining` 요소가 필요 하지 않습니다.

- B4003: WCF 신뢰할 수 있는 메시징 대상은 `netrm:BufferRemaining`를 사용 하 여 버퍼링 할 수 있는 새 메시지 수를 표시 합니다.

- B4004: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF 신뢰할 수 있는 메시징 소스는 `netrm:BufferRemaining` 값을 사용 하 여 메시지 전송을 제한 합니다.

- B4005: WCF는 0에서 4096 사이의 정수 값 `netrm:BufferRemaining` 생성 하 고 0과 `xs:int`의 `maxInclusive` 값 214748364 포괄 시간 사이의 정수 값을 읽습니다.

## <a name="message-exchange-patterns"></a>메시지 교환 패턴

이 섹션에서는 다양 한 메시지 교환 패턴에 WS-RELIABLEMESSAGING을 사용 하는 경우 WCF의 동작에 대해 설명 합니다. 각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.

- 주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.

- 주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.

### <a name="one-way-non-addressable-initiator"></a>주소를 지정할 수 없는 단방향 개시자

#### <a name="binding"></a>바인딩

WCF는 한 개의 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 개시자의 모든 메시지를 응답자에 게 전송 하 고 HTTP 응답을 사용 하 여 응답자의 모든 메시지를 개시자에 게 전송 합니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 HTTP 요청에 `Offer` 요소가 없는 `CreateSequence` 메시지를 전송 하 고 HTTP 응답에서 `CreateSequenceResponse` 메시지를 예상 합니다. WCF 응답자는 시퀀스를 만들고 HTTP 응답에 `Accept` 요소가 없는 `CreateSequenceResponse` 메시지를 전송 합니다.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF 초기자는 `CreateSequence` 메시지 및 오류 메시지를 제외 하 고 모든 메시지의 회신에 대 한 승인을 처리 합니다. WCF 응답자는 항상 HTTP 응답에 대 한 독립 실행형 승인을 모든 시퀀스 및 `AckRequested` 메시지에 전송 합니다.

#### <a name="closesequence-exchange"></a>CloseSequence 교환

WCF 개시자는 HTTP 요청에 `CloseSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `CreateSequenceResponse` 메시지를 예상 합니다. WCF 응답자는 HTTP 응답에서 `CloseSequenceResponse` 메시지를 전송 합니다.

#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환

WCF 개시자는 HTTP 요청에 `TerminateSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `TerminateSequenceResponse` 메시지를 예상 합니다. WCF 응답자는 HTTP 응답에서 `TerminateSequenceResponse` 메시지를 전송 합니다.

### <a name="one-way-addressable-initiator"></a>주소를 지정할 수 있는 단방향 개시자

#### <a name="binding"></a>바인딩

WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 HTTP 요청에 `Offer` 요소가 없는 `CreateSequence` 메시지를 전송 합니다. WCF 응답자는 시퀀스를 만들고 HTTP 요청에 `Accept` 요소가 없는 `CreateSequenceResponse` 메시지를 전송 합니다.

### <a name="duplex-addressable-initiator"></a>주소를 지정할 수 있는 이중 개시자

#### <a name="binding"></a>바인딩

WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 완전 한 비동기 양방향 메시지 교환 패턴을 제공 합니다. 이 메시지 교환 패턴은 제한된 방식으로 `Request/Reply`, `Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 HTTP 요청에 `Offer` 요소가 포함 된 `CreateSequence` 메시지를 전송 합니다. WCF 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인 한 다음 시퀀스를 만들고 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.

#### <a name="sequence-lifetime"></a>시퀀스 수명

WCF는 두 시퀀스를 하나의 완전히 이중 세션으로 처리 합니다.

한 시퀀스에 오류가 발생 하는 오류를 생성 하면 WCF는 원격 끝점에서 두 시퀀스를 모두 오류를 예상 합니다. 한 시퀀스에 오류가 발생 하는 오류를 읽을 때 WCF는 두 시퀀스를 모두 오류를 발생 합니다.

WCF는 아웃 바운드 시퀀스를 닫고 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다. 반대로, WCF는 인바운드 시퀀스의 닫기를 처리 하 고 아웃 바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.

### <a name="request-reply-and-one-way-non-addressable-initiator"></a>요청-회신 및 단방향의 주소를 지정할 수 없는 개시자

#### <a name="binding"></a>바인딩

WCF는 하나의 HTTP 채널에 대 한 두 개의 시퀀스를 사용 하는 단방향 및 요청-회신 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 개시자의 모든 메시지를 응답자에 게 전송 하 고 HTTP 응답을 사용 하 여 응답자의 모든 메시지를 개시자에 게 전송 합니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 HTTP 요청에 `Offer` 요소를 포함 하는 `CreateSequence` 메시지를 전송 하 고 HTTP 응답에서 `CreateSequenceResponse` 메시지를 예상 합니다. WCF 응답자는 시퀀스를 만들고 HTTP 응답에 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.

#### <a name="one-way-message"></a>단방향 메시지

단방향 메시지 교환을 성공적으로 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 독립 실행형 `SequenceAcknowledgement` 메시지를 받습니다. `SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.

WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.

#### <a name="two-way-messages"></a>양방향 메시지

양방향 메시지 교환 프로토콜을 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다. 응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.

WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.

단방향 메시지가 있고 애플리케이션이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.

#### <a name="retrying-replies"></a>회신 다시 시도

WCF는 양방향 메시지 교환 프로토콜 상관 관계에 대 한 HTTP 요청-회신 상관 관계에 의존 합니다. 이로 인해 WCF 개시자는 요청 시퀀스 메시지가 승인 되는 경우, HTTP 응답에 `SequenceAcknowledgement`, 응용 프로그램 회신 또는 오류가 전달 되는 경우 요청 시퀀스 메시지를 다시 시도 하는 것을 중지 하지 않습니다. WCF 응답자는 회신이 상호 관련 된 요청의 HTTP 응답에 대 한 응답을 다시 시도 합니다.

#### <a name="closesequence-exchange"></a>CloseSequence 교환

모든 단방향 요청 시퀀스 메시지에 대해 모든 회신 시퀀스 메시지와 승인을 받은 후 WCF 개시자는 HTTP 요청에서 요청 시퀀스에 대 한 `CloseSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `CloseSequenceResponse`를 예상 합니다.

요청 시퀀스를 닫으면 회신 시퀀스가 암시적으로 닫힙니다. 즉, WCF 개시자는 `CloseSequence` 메시지에 회신 시퀀스의 최종 `SequenceAcknowledgement`를 포함 하 고 회신 시퀀스에는 `CloseSequence` 교환이 포함 되지 않습니다.

WCF 응답자는 모든 회신이 승인 되도록 하 고 HTTP 응답에서 `CloseSequenceResponse` 메시지를 전송 합니다.

#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환

`CloseSequenceResponse` 메시지를 받은 후 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스에 대 한 `TerminateSequence` 메시지를 전송 하 고 HTTP 응답에 대 한 `TerminateSequenceResponse`를 예상 합니다.

`CloseSequence` 교환과 마찬가지로 요청 시퀀스를 종료하면 회신 시퀀스가 암시적으로 종료됩니다. 즉, WCF 개시자는 `TerminateSequence` 메시지에 회신 시퀀스의 최종 `SequenceAcknowledgement`를 포함 하 고 회신 시퀀스에는 `TerminateSequence` 교환이 포함 되지 않습니다.

WCF 응답자는 HTTP 응답에서 `TerminateSequenceResponse` 메시지를 전송 합니다.

### <a name="requestreply-addressable-initiator"></a>요청/회신, 주소를 지정할 수 있는 개시자

#### <a name="binding"></a>바인딩

WCF는 하나의 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 요청-회신 메시지 교환 패턴을 제공 합니다. 이 메시지 교환 패턴은 제한된 방식으로 `Duplex, Addressable` 개시자 메시지 교환 패턴과 혼합하여 사용할 수 있습니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 HTTP 요청에 `Offer` 요소가 포함 된 `CreateSequence` 메시지를 전송 합니다. WCF 응답자는 `CreateSequence`에 `Offer` 요소가 있는지 확인 한 다음 시퀀스를 만들고 `Accept` 요소를 사용 하 여 `CreateSequenceResponse` 메시지를 전송 합니다.

#### <a name="requestreply-correlation"></a>요청/회신 상관 관계

다음 사항은 모든 상호 관련된 요청 및 회신에 적용됩니다.

- WCF를 사용 하면 모든 응용 프로그램 요청 메시지에 `ReplyTo` 끝점 참조 및 `MessageId`있습니다.

- WCF는 각 응용 프로그램 요청 메시지의 `ReplyTo`로 로컬 끝점 참조를 적용 합니다. 로컬 엔드포인트 참조는 개시자에 대한 `CreateSequence` 메시지의 `ReplyTo`와 응답자에 대한 `CreateSequence` 메시지의 `To`입니다.

- WCF는 들어오는 요청 메시지에 `MessageId`와 `ReplyTo`를 사용 하도록 보장 합니다.

- WCF는 모든 응용 프로그램 요청 메시지의 `ReplyTo` 끝점 참조의 URI가 앞에서 정의한 대로 로컬 끝점 참조와 일치 하는지 확인 합니다.

- WCF는 `wsa` 요청/회신 상관 관계 규칙에 따라 모든 회신이 올바른 `RelatesTo` 및 `To` 헤더를 사용 하는지 확인 합니다.
