---
title: Reliable Messaging 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: ef45df0f1cae1f20cf34d07d154baee2cad34b29
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143447"
---
# <a name="reliable-messaging-protocol-version-10"></a>Reliable Messaging 프로토콜 버전 1.0

이 항목에서는 HTTP 전송을 사용 하 여 상호 운용에 필요한 WS-TRUST 메시징 2 월 2005 (버전 1.0) 프로토콜에 대 한 WCF (Windows Communication Foundation) 구현 세부 정보를 다룹니다. WCF는이 항목에서 설명 하는 제약 조건 및 설명에 따라 신뢰할 수 있는 메시징 사양을 따릅니다. WS-RELIABLEMESSAGING 버전 1.0 프로토콜은 WinFX를 사용 하 여 구현 됩니다.

WS-TRUST Messaging 2 월 2005 프로토콜은 WCF에서에 의해 구현 됩니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

편의상 이 항목에서는 다음 역할을 사용합니다.

- 개시자: WS-Reliable 메시지 시퀀스 만들기를 시작한 클라이언트입니다.

- 응답자: 개시자의 요청을 받은 서비스입니다.

이 문서에서는 다음 표에 있는 접두사와 네임스페이스를 사용합니다.

|접두사|네임스페이스|
|------------|---------------|
|wsrm|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a>메시징

### <a name="sequence-establishment-messages"></a>시퀀스 설정 메시지

WCF `CreateSequence` 는 및 `CreateSequenceResponse` 메시지를 구현 하 여 신뢰할 수 있는 메시지 시퀀스를 설정 합니다. 적용되는 제약 조건은 다음과 같습니다.

- B1101: WCF 개시자는 메시지에 선택적 Expires 요소를 생성 하지 않으며 `CreateSequence` , 메시지에 요소가 포함 된 경우 요소의 `CreateSequence` `Offer` 선택적 `Expires` 요소 `Offer` 입니다.

- B1102: 메시지에 액세스할 때 `CreateSequence` WCF는 `Responder` 두 `Expires` 요소 (있는 경우)를 보내고 받으며 해당 값을 사용 하지 않습니다.

WS-Reliable Messaging은 `Offer` 메커니즘을 사용하여 세션을 형성하는 상호 관련된 두 개의 역방향 시퀀스를 설정합니다.

- R1103: `CreateSequence`에 `Offer` 요소가 있는 경우 신뢰할 수 있는 메시징 응답자는 `CreateSequenceResponse` 요소가 포함된 `wsrm:Accept`와 함께 시퀀스 및 응답을 수락하여 상호 관련된 두 개의 역방향 시퀀스를 구성하거나 `CreateSequence` 요청을 거부해야 합니다.

- R1104: 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 애플리케이션 메시지는 `ReplyTo`의 `CreateSequence` 엔드포인트 참조로 보내야 합니다.

- R1105: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 엔드포인트 참조에는 8비트 형식과 일치하는 주소 값이 있어야 합니다.

  WCF 응답자는 `AcksTo` `ReplyTo` 시퀀스를 만들기 전에 및 EPRS의 URI 부분이 동일한 지 확인 합니다.

- R1106: `AcksTo`의 `ReplyTo` 및 `CreateSequence` 엔드포인트 참조에는 동일한 참조 매개 변수 집합이 있어야 합니다.

  WCF는를 적용 하지 않지만 및의 [참조 매개 변수]가 `AcksTo` `ReplyTo` `CreateSequence` 동일 하며, `ReplyTo` 승인 및 역방향 시퀀스 메시지에 대해 끝점 참조의 [참조 매개 변수]를 사용 한다고 가정 합니다.

- R1107: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 역방향 시퀀스로 이동하는 `SequenceAcknowledgement` 및 애플리케이션 메시지를 `ReplyTo`의 `CreateSequence` 엔드포인트 참조로 보내야 합니다.

- R1108: Offer 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `[address]`의 `wsrm:AcksTo` 요소에 대한 `wsrm:Accept` 엔드포인트 자식 요소의 `CreateSequenceResponse` 속성은 `CreateSequence`의 바이트별 대상 URI와 일치해야 합니다.

- R1109: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 개시자가 보낸 메시지 및 응답자의 메시지 승인을 같은 엔드포인트 참조로 보내야 합니다.

  WCF는 신뢰할 수 있는 메시징을 사용 하 여 개시자와 응답자 간에 신뢰할 수 있는 세션을 설정 합니다. WCF의 WS-TRUST 메시징 구현은 단방향, 요청-회신 및 전체 이중 메시징 패턴에 신뢰할 수 있는 세션을 제공 합니다. 에서 신뢰할 수 있는 메시징 `Offer` 메커니즘을 사용 하면 상호 관련 된 `CreateSequence` / `CreateSequenceResponse` 두 개의 역방향 시퀀스를 설정 하 고 모든 메시지 끝점에 적합 한 세션 프로토콜을 제공할 수 있습니다. WCF는 세션 무결성을 위한 종단 간 보호를 포함 하 여 세션에 대 한 보안 보장을 제공 하므로 같은 파티에 대 한 메시지가 동일한 대상에 도착 하는지 확인 하는 것이 실용적입니다. 이렇게 하면 애플리케이션 메시지에서 피기백킹이라고 하는 시퀀스 승인을 사용할 수 있습니다. 따라서 제약 조건 R1104, R1105 및 R1108가 WCF에 적용 됩니다.

`CreateSequence` 메시지의 예입니다.

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

 `CreateSequenceResponse` 메시지의 예입니다.

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

### <a name="sequence"></a>시퀀스

다음은 시퀀스에 적용되는 제약 조건의 목록입니다.

- B1201: WCF `xs:long` 는 최대 포함 값 9223372036854775807 보다 큰 시퀀스 번호를 생성 하 고 액세스 합니다.

- B1202: WCF는 항상의 동작 URI를 사용 하 여 비어 있는 마지막 메시지를 생성 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` 합니다.

- B1203: WCF는 `LastMessage` 작업 URI가이 아닌 경우 요소를 포함 하는 시퀀스 헤더를 사용 하 여 메시지를 받고 배달 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` 합니다.

시퀀스 헤더의 예입니다.

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

### <a name="ackrequested-header"></a>AckRequested 헤더

WCF는 `AckRequested` 헤더를 연결 유지 메커니즘으로 사용 합니다. WCF는 선택적 요소를 생성 하지 않습니다 `MessageNumber` . 요소가 포함 된 헤더를 사용 하 여 메시지를 받으면 `AckRequested` `MessageNumber` WCF는 `MessageNumber` 다음 예제와 같이 요소의 값을 무시 합니다.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement 헤더

WCF는 신뢰할 수 있는 메시징에 제공 된 시퀀스 승인에 피기백 메커니즘을 사용 합니다.

- R1401: `Offer` 메커니즘을 사용하여 두 개의 역방향 시퀀스가 설정된 경우 `SequenceAcknowledgement` 헤더가 받는 사람에게 전송된 애플리케이션 메시지에 포함될 수 있습니다.

- B1402: WCF는 메시지를 충족 하기 위해 시퀀스 메시지를 받기 전에 승인을 생성 해야 하는 경우 `AckRequested` `SequenceAcknowledgement` 다음 예제와 같이 0-0 범위를 포함 하는 헤더를 생성 합니다.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- B1403: WCF는 `SequenceAcknowledgement` 요소를 포함 `Nack` 하지만 요소를 지 원하는 헤더를 생성 하지 않습니다 `Nack` .

### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging 오류

다음은 WS-TRUST 메시징 오류의 WCF 구현에 적용 되는 제약 조건 목록입니다.

- B1501: WCF는 오류를 생성 하지 않습니다 `MessageNumberRollover` .

- B1502: WCF 끝점 `CreateSequenceRefused` 은 사양에 설명 된 대로 오류를 생성할 수 있습니다.

- B1503: 서비스 끝점이 해당 연결 제한에 도달 하 여 새 연결을 처리할 수 없는 경우 WCF는 `CreateSequenceRefused` `netrm:ConnectionLimitReached` 다음 예제와 같이 추가 오류 하위 코드를 생성 합니다.

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

### <a name="ws-addressing-faults"></a>WS-Addressing 오류

WS 신뢰할 수 있는 메시징에서 WS-ADDRESSING을 사용 하기 때문에 WCF WS-TRUST 메시징 구현 시 WS-ADDRESSING 오류가 발생할 수 있습니다. 이 섹션에서는 WCF가 신뢰할 수 있는 메시징 계층에서 명시적으로 생성 하는 WS-ADDRESSING 오류에 대해 설명 합니다.

- B1601: WCF는 다음 조건 중 하나에 해당 하는 경우 필요한 오류 메시지 주소 지정 헤더를 생성 합니다.

  - 메시지에 `Sequence` 헤더 및 `Action` 헤더가 없습니다.

  - `CreateSequence` 메시지에 `MessageId` 헤더가 없습니다.

  - `CreateSequence` 메시지에 `ReplyTo` 헤더가 없습니다.

- B1602: WCF는 헤더가 누락 된 메시지에 대 한 회신에서 지원 되지 않는 오류 작업을 생성 `Sequence` 하며, `Action` 신뢰할 수 있는 메시징 사양에서 인식할 수 없는 헤더를 포함 합니다.

- B1603: WCF는 끝점에서 `CreateSequence` 메시지의 주소 지정 헤더 검사를 기반으로 시퀀스를 처리 하지 않음을 나타내는 오류 끝점을 생성 합니다.

## <a name="protocol-composition"></a>프로토콜 구성

### <a name="composition-with-ws-addressing"></a>WS-Addressing을 사용하여 구성

WCF는 ws-addressing 2004/08 [WS-ADDR] 및 W3C WS-ADDRESSING 1.0 권장 사항 [WS-POLICY-CORE] 및 [WS-ADDRESSING-SOAP]의 두 가지 버전 주소를 지원 합니다.

WS-Reliable Messaging 사양에는 WS-Addressing 2004/08만 언급되어 있지만 WS-Addressing 버전만 사용하도록 제한되지는 않습니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- R2101:WS-Addressing 2004/08과 WS-Addressing 1.0 모두 WS-Reliable Messaging과 함께 사용할 수 있습니다.

- R2102: 단일 ws-addressing 버전은 메커니즘을 사용 하 여 상호 관련 된 지정 된 WS-TRUST 메시징 시퀀스 또는 상반 되는 시퀀스 쌍 전체에서 사용 해야 합니다 `wsrm:Offer` .

### <a name="composition-with-soap"></a>SOAP를 사용하여 구성

WCF는 신뢰할 수 있는 메시징에 SOAP 1.1 및 SOAP 1.2을 모두 사용할 수 있도록 지원 합니다.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>WS-Security 및 WS-SecureConversation을 사용하여 구성

WCF는 보안 전송 (HTTPS), WS-SECURITY를 사용한 컴퍼지션 및 ws-security (ws-security) 대화를 사용 하 여 WS-TRUST 메시징 시퀀스에 대 한 보호를 제공 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- R2301: 개별 메시지의 무결성과 기밀성 외에도 신뢰할 수 있는 메시징 시퀀스의 무결성을 보호 하기 위해 WCF에서는 WS-SECURITY 대화를 사용 해야 합니다.

- R2302:WS-Secure Conversation 세션은 WS-Reliable Messaging 시퀀스를 설정하기 전에 설정해야 합니다.

- R2303: WS-Reliable Messaging 시퀀스 수명이 WS-Secure Conversation 세션의 수명을 초과하는 경우 WS-Secure Conversation을 사용하여 설정한 `SecurityContextToken`을 해당 WS-Secure Conversation 갱신 바인딩을 사용하여 갱신해야 합니다.

- B2304:WS-Reliable Messaging 시퀀스 또는 한 쌍의 상호 관련된 역방향 시퀀스는 항상 단일 WS-SecureConversation 세션에 바인딩됩니다.

  WCF 소스는 `wsse:SecurityTokenReference` 메시지의 요소 확장성 섹션에서 요소를 생성 합니다 `CreateSequence` .

- R2305: WS-SECURITY 대화로 구성 된 경우 `CreateSequence` 메시지에는 요소가 포함 되어야 합니다 `wsse:SecurityTokenReference` .

## <a name="ws-reliable-messaging-ws-policy-assertion"></a>WS-Reliable Messaging WS-Policy Assertion

WCF는 WS 신뢰할 수 있는 메시징 WS-POLICY 어설션을 사용 하 여 `wsrm:RMAssertion` 끝점 기능을 설명 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- B3001: WCF는 `wsrm:RMAssertion` Ws-policy 어설션을 요소에 연결 `wsdl:binding` 합니다. WCF는 및 요소에 대 한 첨부 파일을 모두 지원 `wsdl:binding` `wsdl:port` 합니다.

- B3002: WCF는 WS-TRUST 메시징 어설션의 다음과 같은 선택적 속성을 지원 하 고 WCF에서이에 대 한 제어를 제공 합니다 `ReliableMessagingBindingElement` .

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  다음은 이에 대한 예입니다.

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a>흐름 제어 WS-Reliable Messaging 확장

WCF는 WS-TRUST 메시징 확장성을 사용 하 여 시퀀스 메시지 흐름에 대 한 선택적인 추가 제어 기능을 제공 합니다.

속성을로 설정 하 여 흐름 제어를 사용 하도록 설정 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> `true` 합니다. 다음은 WCF에 적용 되는 제약 조건의 목록입니다.

- B4001: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 WCF는 `netrm:BufferRemaining` 헤더의 요소 확장성에 요소를 생성 `SequenceAcknowledgement` 합니다.

- B4002: 신뢰할 수 있는 메시징 흐름 제어를 사용 하는 경우 `netrm:BufferRemaining` `SequenceAcknowledgement` 다음 예제와 같이 WCF는 요소를 헤더에 표시 하지 않아도 됩니다.

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

- B4003: WCF는를 사용 하 여 `netrm:BufferRemaining` 신뢰할 수 있는 메시징 대상이 버퍼링 할 수 있는 새 메시지 수를 표시 합니다.

- B4004: 신뢰할 수 있는 메시징 대상 응용 프로그램에서 메시지를 신속 하 게 받을 수 없을 때 전송 되는 메시지 수를 제한 WCF 신뢰할 수 있는 메시징 서비스입니다. 신뢰할 수 있는 메시징 대상은 메시지를 버퍼링하고 요소의 값을 0으로 줄입니다.

- B4005: WCF `netrm:BufferRemaining` 는 0에서 4096 사이의 정수 값을 생성 하 고 0에서 214748364 사이의 정수 값을 읽습니다 `xs:int` `maxInclusive` .

## <a name="message-exchange-patterns"></a>메시지 교환 패턴

이 섹션에서는 다른 메시지 교환 패턴에 대해 WS-TRUST 메시징을 사용 하는 경우 WCF의 동작에 대해 설명 합니다. 각 메시지 교환 패턴에 대해 다음 두 가지 배포 시나리오를 고려합니다.

- 주소를 지정할 수 없는 개시자: 개시자가 방화벽으로 보호됩니다. 응답자는 HTTP 응답에서만 개시자에게 메시지를 배달할 수 있습니다.

- 주소를 지정할 수 있는 개시자: 개시자와 응답자 모두 HTTP 요청을 받을 수 있습니다. 즉, 반대 방향의 HTTP 연결 두 개를 설정할 수 있습니다.

### <a name="one-way-non-addressable-initiator"></a>주소를 지정할 수 없는 단방향 개시자

#### <a name="binding"></a>바인딩

WCF는 한 개의 HTTP 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 RMS의 모든 메시지를 RMD에 전송 하 고 HTTP 응답을 사용 하 여 RMD의 모든 메시지를 RMS로 전송 합니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 제공이 `CreateSequence` 없는 메시지를 생성 합니다. WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에가 제공 하지 않도록 합니다. WCF 응답자는 `CreateSequence` 메시지와 함께 요청에 응답 합니다 `CreateSequenceResponse` .

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF 초기자는 `CreateSequence` 메시지 및 오류 메시지를 제외한 모든 메시지의 회신에 대 한 승인을 처리 합니다. WCF 응답자는 항상 시퀀스와 메시지에 대 한 응답에 독립 실행형 승인을 생성 합니다 `AckRequested` .

#### <a name="terminatesequence-message"></a>TerminateSequence 메시지

WCF는 `TerminateSequence` 단방향 작업으로 처리 합니다. 즉, http 응답에는 빈 본문과 http 202 상태 코드가 있습니다.

### <a name="one-way-addressable-initiator"></a>주소를 지정할 수 있는 단방향 개시자

#### <a name="binding"></a>바인딩

WCF는 인바운드 및 아웃 바운드 Http 채널을 통해 하나의 시퀀스를 사용 하 여 단방향 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 제공이 `CreateSequence` 없는 메시지를 생성 합니다. WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제품이 없는지 확인 합니다. WCF 응답자는 `CreateSequenceResponse` 끝점 참조로 주소가 지정 된 HTTP 요청에 메시지를 전송 합니다 `ReplyTo` .

### <a name="duplex-addressable-initiator"></a>주소를 지정할 수 있는 이중 개시자

#### <a name="binding"></a>바인딩

WCF는 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 완전 한 비동기 양방향 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다. WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다. WCF는 `CreateSequenceResponse` `CreateSequence` 의 끝점 참조로 주소가 지정 된 HTTP 요청에 대 한를 보냅니다 `ReplyTo` .

#### <a name="sequence-lifetime"></a>시퀀스 수명

WCF는 두 시퀀스를 완전 한 이중 세션으로 처리 합니다.

한 시퀀스에 오류가 발생 하는 오류를 생성 하면 WCF는 원격 끝점에서 두 시퀀스를 모두 오류를 예상 합니다. 한 시퀀스에 오류가 발생 하는 오류를 읽을 때 WCF는 두 시퀀스를 모두 오류를 발생 합니다.

WCF는 아웃 바운드 시퀀스를 닫고 인바운드 시퀀스에서 메시지를 계속 처리할 수 있습니다. 반대로, WCF는 인바운드 시퀀스의 닫기를 처리 하 고 아웃 바운드 시퀀스에서 메시지를 계속 보낼 수 있습니다.

### <a name="request-reply-non-addressable-initiator"></a>요청-회신, 주소를 지정할 수 없는 개시자

#### <a name="binding"></a>바인딩

WCF는 하나의 HTTP 채널에 대 한 두 개의 시퀀스를 사용 하는 단방향 및 요청-회신 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 요청 시퀀스의 메시지를 전송 하 고 HTTP 응답을 사용 하 여 회신 시퀀스의 메시지를 전송 합니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다. WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다. WCF 응답자는 `CreateSequence` 메시지와 함께 요청에 응답 합니다 `CreateSequenceResponse` .

#### <a name="one-way-message"></a>단방향 메시지

단방향 메시지 교환 프로토콜을 성공적으로 완료 하기 위해 WCF 초기자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 `SequenceAcknowledgement` http 응답에 대 한 독립 실행형 메시지를 받습니다. `SequenceAcknowledgement`는 전송된 메시지를 승인해야 합니다.

WCF 응답자는 승인, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.

#### <a name="two-way-messages"></a>양방향 메시지

양방향 메시지 교환 프로토콜을 완료 하기 위해 WCF 개시자는 HTTP 요청에 대 한 요청 시퀀스 메시지를 전송 하 고 HTTP 응답에 대 한 회신 시퀀스 메시지를 받습니다. 응답에 전송된 요청 시퀀스 메시지를 승인하는 `SequenceAcknowledgement`가 있어야 합니다.

WCF 응답자는 응용 프로그램 회신, 오류 또는 빈 본문과 HTTP 202 상태 코드가 포함 된 응답으로 요청에 회신할 수 있습니다.

단방향 메시지가 있고 애플리케이션이 회신하는 시간 때문에 요청 시퀀스 메시지의 시퀀스 번호와 응답 메시지의 시퀀스 번호는 상관 관계가 없습니다.

#### <a name="retrying-replies"></a>회신 다시 시도

WCF는 양방향 메시지 교환 프로토콜 상관 관계에 대 한 HTTP 요청-회신 상관 관계에 의존 합니다. 이로 인해 WCF 개시자는 요청 시퀀스 메시지가 승인 되는 경우, HTTP 응답이 승인, 사용자 메시지 또는 오류를 전달 하는 경우 요청 시퀀스 메시지를 다시 시도 하는 것을 중지 하지 않습니다. WCF 응답자는 회신이 상호 관련 된 요청의 HTTP 요청 레그에 대 한 회신을 다시 시도 합니다.

#### <a name="lastmessage-exchange"></a>LastMessage 교환

WCF 개시자는 HTTP 요청 레그에서 비어 있는 마지막 메시지를 생성 하 고 전송 합니다. WCF에는 응답이 필요 하지만 실제 응답 메시지는 무시 됩니다. WCF 응답자는 회신 시퀀스의 비어 있는 마지막 메시지를 사용 하 여 요청 시퀀스의 비어 있는 마지막 메시지에 응답 합니다.

WCF 응답자에서 작업 URI가 아닌 마지막 메시지를 수신 하는 경우 `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` wcf는 마지막 메시지를 사용 하 여 회신 합니다. 양방향 메시지 교환 프로토콜의 경우 마지막 메시지에 애플리케이션 메시지가 포함되어 있으며, 단방향 메시지 교환 프로토콜의 경우 마지막 메시지는 비어 있습니다.

WCF 응답자는 회신 시퀀스의 비어 있는 마지막 메시지에 대 한 승인이 필요 하지 않습니다.

#### <a name="terminatesequence-exchange"></a>TerminateSequence 교환

모든 요청이 유효한 회신을 받으면 WCF 개시자는 `TerminateSequence` HTTP 요청 레그에서 요청 시퀀스의 메시지를 생성 하 고 전송 합니다. WCF에는 응답이 필요 하지만 실제 응답 메시지는 무시 됩니다. WCF 응답자는 회신 시퀀스의 메시지를 사용 하 여 요청 시퀀스의 메시지에 응답 합니다 `TerminateSequence` `TerminateSequence` .

정상적인 종료 시퀀스에서 두 `TerminateSequence` 메시지 모두에 전체 범위의 `SequenceAcknowledgement`가 포함되어 있습니다.

### <a name="requestreply-addressable-initiator"></a>요청/회신, 주소를 지정할 수 있는 개시자

#### <a name="binding"></a>바인딩

WCF는 인바운드 및 아웃 바운드 HTTP 채널을 통해 두 개의 시퀀스를 사용 하 여 요청-회신 메시지 교환 패턴을 제공 합니다. WCF는 HTTP 요청을 사용 하 여 모든 메시지를 전송 합니다. 모든 HTTP 응답에는 빈 본문과 HTTP 202 상태 코드가 포함됩니다.

#### <a name="createsequence-exchange"></a>CreateSequence 교환

WCF 개시자는 제공이 `CreateSequence` 포함 된 메시지를 생성 합니다. WCF 응답자는 `CreateSequence` 시퀀스를 만들기 전에에 제안이 있는지 확인 합니다. WCF는 `CreateSequenceResponse` `CreateSequence` 의 끝점 참조로 주소가 지정 된 HTTP 요청에 대 한를 보냅니다 `ReplyTo` .

#### <a name="requestreply-correlation"></a>요청/회신 상관 관계

WCF 개시자는 모든 응용 프로그램 요청 메시지 `MessageId` 와 `ReplyTo` 끝점 참조를 확인 합니다. WCF 개시자는 `CreateSequence` `ReplyTo` 각 응용 프로그램 요청 메시지에 메시지의 끝점 참조를 적용 합니다. WCF 응답자는 들어오는 요청 메시지에 및가 필요 합니다 `MessageId` `ReplyTo` . WCF 응답자는 `CreateSequence` 및 모든 응용 프로그램 요청 메시지의 끝점 참조 URI가 동일한 지 확인 합니다.
