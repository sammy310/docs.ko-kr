---
title: ServiceDescription 및 WSDL 참조
ms.date: 03/30/2017
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
ms.openlocfilehash: 11a5d65026d13db56d1d349c130861094c3e123b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253884"
---
# <a name="servicedescription-and-wsdl-reference"></a>ServiceDescription 및 WSDL 참조

이 항목에서는 WCF (Windows Communication Foundation)에서 WSDL (웹 서비스 기술 언어) 문서를 인스턴스와 매핑하는 방법에 대해 설명 합니다 <xref:System.ServiceModel.Description.ServiceDescription> .  
  
## <a name="how-servicedescription-maps-to-wsdl-11"></a>ServiceDescription에서 WSDL 1.1에 매핑하는 방법  

 WCF를 사용 하 여 <xref:System.ServiceModel.Description.ServiceDescription> 서비스에 대 한 인스턴스에서 WSDL 문서를 내보낼 수 있습니다. WSDL 문서는 메타데이터 엔드포인트를 게시할 때 서비스에 대해 자동으로 생성됩니다.  
  
 <xref:System.ServiceModel.Description.ServiceEndpoint> 형식을 사용하여 WSDL 문서에서 <xref:System.ServiceModel.Description.ContractDescription>, <xref:System.ServiceModel.Channels.Binding> 및 `WsdlImporter` 인스턴스를 가져올 수도 있습니다.  
  
 WCF에서 내보낸 WSDL 문서는 외부 XML 스키마 문서에서 사용 되는 모든 XML 스키마 정의를 가져옵니다. 서비스에서 데이터 형식에 사용되는 대상 네임스페이스마다 별도의 XML 스키마 문서를 내보냅니다. 마찬가지로 서비스 계약에 사용되는 대상 네임스페이스마다 별도의 WSDL 문서를 내보냅니다.  
  
### <a name="servicedescription"></a>ServiceDescription  

 <xref:System.ServiceModel.Description.ServiceDescription> 인스턴스는 `wsdl:service` 요소에 매핑됩니다. <xref:System.ServiceModel.Description.ServiceDescription> 인스턴스에는 각각 개별 <xref:System.ServiceModel.Description.ServiceEndpoint> 요소에 매핑되는 `wsdl:port` 인스턴스의 컬렉션이 포함되어 있습니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|`wsdl:service` /@name 서비스에 대 한 값입니다.|  
|`Namespace`|서비스의 `wsdl:service` 정의에 대한 targetNamespace입니다.|  
|`Endpoints`|서비스에 대한 `wsdl:port` 정의입니다.|  
  
### <a name="serviceendpoint"></a>ServiceEndpoint  

 <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스는 `wsdl:port` 요소에 매핑됩니다. <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스에는 주소, 바인딩 및 계약이 포함되어 있습니다.  
  
 ph x="1" /&gt; 인터페이스를 구현하는 엔드포인트 동작은 연결되는 엔드포인트에 대한 `wsdl:port` 요소를 수정할 수 있습니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|끝점 `wsdl:port` /@name 의 값과 `wsdl:binding` /@name 끝점 바인딩의 값입니다.|  
|`Address`|엔드포인트의 `wsdl:port` 정의에 대한 주소입니다.<br /><br /> 엔드포인트에 대한 전송에 따라 주소 형식이 결정됩니다. 예를 들어 WCF 지원 전송의 경우 SOAP 주소 또는 끝점 참조일 수 있습니다.|  
|`Binding`|엔드포인트에 대한 `wsdl:binding` 정의입니다.<br /><br /> `wsdl:binding`정의와 달리 WCF의 바인딩은 하나의 계약과 연결 되지 않습니다.|  
|`Contract`|엔드포인트에 대한 `wsdl:portType` 정의입니다.|  
|`Behaviors`|ph x="1" /&gt; 인터페이스를 구현하는 엔드포인트 동작은 엔드포인트에 대한 `wsdl:port`를 수정할 수 있습니다.|  
  
### <a name="bindings"></a>바인딩  

 `ServiceEndpoint` 인스턴스에 대한 바인딩 인스턴스가 `wsdl:binding` 정의에 매핑됩니다. `wsdl:binding`특정 정의와 연결 되어야 하는 정의와 달리 `wsdl:portType` WCF 바인딩은 계약과는 독립적입니다.  
  
 바인딩은 바인딩 요소의 컬렉션으로 구성됩니다. 각 요소는 엔드포인트가 클라이언트와 통신하는 방법의 일부를 설명합니다. 또한 바인딩에는 엔드포인트에 대한 <xref:System.ServiceModel.Channels.MessageVersion> 및 <xref:System.ServiceModel.EnvelopeVersion>을 나타내는 <xref:System.ServiceModel.Channels.AddressingVersion>이 있습니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|엔드포인트에 대한 기본 이름에 사용되며, 계약 이름을 밑줄로 구분하여 연결한 바인딩 이름입니다.|  
|`Namespace`|`targetNamespace` 정의에 대한 `wsdl:binding`입니다.<br /><br /> 가져오기에서는 정책이 WSDL 포트에 연결되어 있으면 가져온 바인딩 네임스페이스가 `targetNamespace` 정의에 대한 `wsdl:port`에 매핑됩니다.|  
|`BindingElementCollection`() 메서드에 의해 반환되는 `CreateBindingElements`|`wsdl:binding` 정의에 대한 다양한 도메인별 확장명(일반적으로 정책 어설션)입니다.|  
|`MessageVersion`|엔드포인트에 대한 `EnvelopeVersion` 및 `AddressingVersion`입니다.<br /><br /> `MessageVersion.None`이 지정된 경우 WSDL 바인딩은 SOAP 바인딩을 포함하지 않고 WSDL 포트는 WS-Addressing 콘텐츠를 포함하지 않습니다. 이 설정은 일반적으로 POX(Plain Old XML) 엔드포인트에 사용됩니다.|  
  
#### <a name="bindingelements"></a>BindingElements  

 엔드포인트 바인딩에 대한 바인딩 요소는 정책 어설션과 같은 `wsdl:binding`의 다양한 WSDL 확장에 매핑됩니다.  
  
 바인딩에 대한 <xref:System.ServiceModel.Channels.TransportBindingElement>에 따라 SOAP 바인딩에 대한 전송 URI(Uniform Resource Identifier)가 결정됩니다.  
  
#### <a name="addressingversion"></a>AddressingVersion  

 바인딩의 `AddressingVersion`은 `wsd:port`에 사용되는 주소 지정 버전에 매핑됩니다. WCF는 SOAP 1.1 및 SOAP 1.2 주소와 WS-Addressing 08/2004 및 WS-Addressing 1.0 끝점 참조를 지원 합니다.  
  
#### <a name="envelopeversion"></a>EnvelopeVersion  

 바인딩의 `EnvelopeVersion`은 `wsdl:binding`에 사용되는 SOAP 버전에 매핑됩니다. WCF는 SOAP 1.1 및 SOAP 1.2 바인딩을 지원 합니다.  
  
### <a name="contracts"></a>계약  

 <xref:System.ServiceModel.Description.ContractDescription> 인스턴스에 대한 `ServiceEndpoint` 인스턴스가 `wsdl:portType`에 매핑됩니다. `ContractDescription` 인스턴스는 지정된 계약에 대한 모든 작업을 설명합니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|`wsdl:portType` /@name 계약에 대 한 값입니다.|  
|`Namespace`|`wsdl:portType` 정의에 대한 targetNamespace입니다.|  
|`SessionMode`|`wsdl:portType` /@msc:usingSession 계약에 대 한 값입니다. 이 특성은 WSDL 1.1에 대 한 WCF 확장입니다.|  
|`Operations`|계약에 대한 `wsdl:operation` 정의입니다.|  
  
### <a name="operations"></a>작업  

 인스턴스는에 <xref:System.ServiceModel.Description.OperationDescription> 매핑됩니다 `wsdl:portType` / `wsdl:operation` . `OperationDescription`에는 작업에 대한 메시지를 설명하는 `MessageDescription` 인스턴스 컬렉션이 포함되어 있습니다.  
  
 `OperationDescription`이 WSDL 문서에 매핑되는 방법에 주로 관여하는 작업 동작은 `DataContractSerializerOperationBehavior` 및 `XmlSerializerOperationBehavior`입니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` /@name 작업의 값입니다.|  
|`ProtectionLevel`|이 작업의 `wsdl:binding/wsdl:operation` 메시지에 연결된 보안 정책의 보호 어설션입니다.|  
|`IsInitiating`|`wsdl:portType` / `wsdl:operation` /@msc:isInitiating 작업의 값입니다. 이 특성은 WSDL 1.1에 대 한 WCF 확장입니다.|  
|`IsTerminating`|`wsdl:portType` / `wsdl:operation` /@msc:isTerminating 작업의 값입니다. 이 특성은 WSDL 1.1에 대 한 WCF 확장입니다.|  
|`Messages`|`wsdl:portType` / `wsdl:operation` / `wsdl:input` `wsdl:portType` / `wsdl:operation` / `wsdl:output` 작업에 대 한 및 메시지입니다.|  
|`Faults`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` 작업에 대 한 정의입니다.|  
|`Behaviors`|`DataContractSerializerOperationBehavior` 및 `XmlSerializerOperationBehavior`는 작업 바인딩과 작업 메시지를 처리합니다.|  
  
#### <a name="the-datacontractserializeroperationbehavior"></a>DataContractSerializerOperationBehavior  

 작업에 대한 `DataContractSerializerOperationBehavior`는 해당 작업에 대한 WSDL 메시지 및 바인딩을 내보내는 `IWsdlExportExtension` 구현입니다. XML 스키마 형식은 `XsdDataContractExporter`를 사용하여 내보냅니다. 또한 `DataContractSerializerOperationBehavior`는 해당 작업에 대한 용도, 스타일, 스키마 내보내기 및 가져오기를 결정합니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`DataContractFormatAttribute`|`Style`이 특성의 속성은 `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style 작업에 대 한 값에 매핑됩니다.<br /><br /> `DataContractSerializerOperationBehavior`는 WSDL에서 스키마 형식의 리터럴 사용만 지원합니다.|  
  
#### <a name="the-xmlserializeroperationbehavior"></a>XmlSerializerOperationBehavior  

 작업에 대한 `XmlSerializerOperationBehavior`는 해당 작업에 대한 WSDL 메시지 및 바인딩을 내보내는 `IWsdlExportExtension` 구현입니다. XML 스키마 형식은 `XmlSchemaExporter`를 사용하여 내보냅니다. 또한 `XmlSerializerOperationBehavior`는 해당 작업에 대한 용도, 스타일, 스키마 내보내기 및 가져오기를 결정합니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`XmlSerializerFormatAttribute`|`Style`이 특성의 속성은 `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style 작업에 대 한 값에 매핑됩니다.<br /><br /> `Use`이 특성의 속성은 `wsdl:binding` / `wsdl:operation` / `soap:operation` /@use 작업의 모든 메시지에 대 한/* 값에 매핑됩니다.|  
  
### <a name="messages"></a>메시지  

 `MessageDescription`인스턴스는 `wsdl:message` `wsdl:portType` / `wsdl:operation` / `wsdl:input` 또는 `wsdl:portType` / `wsdl:operation` / `wsdl:output` 작업의 메시지에서 참조 하는에 매핑됩니다. `MessageDescription`에는 본문과 헤더가 있습니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Action`|작업에 대한 SOAP 또는 WS-Addressing 동작입니다.<br /><br /> "*" 동작 문자열을 사용하는 작업은 WSDL에 표시되지 않습니다.|  
|`Direction`|`MessageDirection.Input`은 `wsdl:input`에 매핑됩니다.<br /><br /> `MessageDirection.Output`은 `wsdl:output`에 매핑됩니다.|  
|`ProtectionLevel`|이 메시지의 `wsdl:message` 정의에 연결되는 보안 정책의 보호 어설션입니다.|  
|`Body`|메시지의 메시지 본문입니다.|  
|`Headers`|메시지의 헤더입니다.|  
|`ContractDescription.Name`, `OperationContract.Name`|내보내기 시 값을 파생 하는 데 사용 `wsdl:message` /@name 됩니다.|  
  
#### <a name="message-body"></a>메시지 본문  

 `MessageBodyDescription`인스턴스는 `wsdl:message` / `wsdl:part` 메시지 본문에 대 한 정의에 매핑됩니다. 메시지 본문은 wrapped 또는 bare입니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`WrapperName`|스타일이 RPC가 아닌 경우이 `WrapperName` `wsdl:message` / `wsdl:part` @name "parameters"로 설정 된에서 참조 하는 요소 이름에 매핑됩니다.|  
|`WrapperNamespace`|스타일이 RPC가 아닌 경우는 `WrapperNamespace` `wsdl:message` / `wsdl:part` @name "parameters"로 설정 된의 요소 네임 스페이스에 매핑됩니다.|  
|`Parts`|이 메시지 본문의 메시지 부분입니다.|  
|`ReturnValue`|래퍼 요소가 존재 하는 경우 (문서 래핑된 스타일 또는 RPC 스타일) 래퍼 요소의 자식 요소이 고, 그렇지 않으면 `wsdl:message` / `wsdl:part` 메시지의 첫 번째입니다.|  
  
#### <a name="message-parts"></a>메시지 부분  

 `MessagePartDescription`인스턴스는 `wsdl:message` / `wsdl:part` 메시지 파트가 가리키는 XML 스키마 형식 또는 요소에 매핑됩니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|메시지 부분의 `wsd:message` / `wsdl:part` /@name 값과 메시지 부분이 가리키는 요소의 이름입니다.|  
|`Namespace`|메시지 부분이 가리키는 요소의 네임스페이스입니다.|  
|`Index`|`wsdl:message` / `wsdl:part` 메시지에 대 한의 인덱스입니다.|  
|`ProtectionLevel`|이 메시지 부분의 `wsdl:message` 정의에 연결되는 보안 정책의 보호 어설션입니다. 정책은 특정 메시지 부분을 가리키는 매개 변수를 가집니다.|  
|`MessageType`|메시지 부분이 가리키는 요소의 XML 스키마 형식입니다.|  
  
#### <a name="message-headers"></a>메시지 헤더  

 `MessageHeaderDescription` 인스턴스는 메시지 부분에 대한 `soap:header` 바인딩에도 매핑되는 메시지 부분입니다.  
  
### <a name="faults"></a>오류  

 `FaultDescription`인스턴스는 `wsdl:portType` / `wsdl:operation` / `wsdl:fault` 정의와 관련 `wsdl:message` 정의에 매핑됩니다. `wsdl:message`는 연결된 WSDL 포트 형식과 동일한 대상 네임스페이스에 추가됩니다. `wsdl:message`에는 `DefaultType` 인스턴스의 `FaultDescription` 속성 값에 해당하는 XML 스키마 요소를 가리키는 "detail"이라는 단일 메시지 부분이 있습니다.  
  
|속성|WSDL 매핑|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` /@name 오류에 대 한 값입니다.|  
|`Namespace`|오류 정보 메시지 부분이 가리키는 XML 스키마 요소의 네임스페이스입니다.|  
|`Action`|오류에 대한 SOAP 또는 WS-Addressing 동작입니다.|  
|`ProtectionLevel`|이 오류의 `wsdl:message` 정의에 연결되는 보안 정책의 보호 어설션입니다.|  
|`DetailType`|세부 메시지 부분이 가리키는 요소의 XML 스키마 형식입니다.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|`wsdl:message`오류 메시지의 값을 파생 하는 데 사용 /@name 됩니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Description>
