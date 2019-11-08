---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739077"
---
# <a name="binarymessageencoding"></a>binaryMessageEncoding \<
통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<binaryMessageEncoding >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|maxReadPoolSize|새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다. 더 큰 풀 크기를 사용 하면 더 큰 작업 집합의 비용으로 더 큰 작업을 수행할 수 있습니다. 기본값은 64입니다.|  
|maxSessionSize|인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다. 버퍼가 클수록 작업 집합의 크기에 따라 인코딩 속도가 향상 됩니다. 기본값은 2048입니다.|  
|maxWritePoolSize|새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다. 더 큰 풀 크기를 사용 하면 더 큰 작업 집합의 비용으로 더 큰 작업을 수행할 수 있습니다. 기본값은 16입니다.|  
|messageVersion|사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>주의  
 인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다. 디코딩은 역프로세스입니다. WCF (Windows Communication Foundation)는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM (메시지 전송 최적화 메커니즘)의 세 가지 인코딩 유형을 포함 합니다.  
  
 `binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다. 이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다. 이 인코딩은 메시지를 매우 빠르게 전송 하지만 WS-* 표준을 기반으로 하는 상호 운용성이 손실 됩니다.  
  
## <a name="example"></a>예제  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [메시지 인코딩](message-encoding.md)
- [메시지 인코더 선택](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
