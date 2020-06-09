---
title: '엔드포인트: 주소, 바인딩 및 계약'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 3ac7f0b165b99a1ed3702628958f7d4c7702f5b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593518"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>엔드포인트: 주소, 바인딩 및 계약

WCF (Windows Communication Foundation) 서비스와의 모든 통신은 서비스의 *끝점* 을 통해 수행 됩니다. 끝점은 WCF 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 합니다.

각 엔드포인트는 다음 네 가지 속성으로 구성됩니다.

- 엔드포인트를 찾을 위치를 나타내는 주소

- 클라이언트가 엔드포인트와 통신할 수 있는 방법을 지정하는 바인딩

- 사용 가능한 작업을 식별하는 계약

- 엔드포인트의 로컬 구현 세부 정보를 지정하는 동작 집합

이 항목에서는이 끝점 구조에 대해 설명 하 고 WCF 개체 모델에 표시 되는 방법에 대해 설명 합니다.

## <a name="the-structure-of-an-endpoint"></a>엔드포인트의 구조

각 엔드포인트는 다음으로 구성됩니다.

- 주소: 주소는 엔드포인트를 고유하게 식별하고 잠재 고객에게 서비스가 있는 위치를 알려 줍니다. 클래스에 의해 WCF 개체 모델에 표시 됩니다 <xref:System.ServiceModel.EndpointAddress> . <xref:System.ServiceModel.EndpointAddress> 클래스에는 다음이 포함됩니다.

  - 서비스의 주소를 나타내는 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 속성.

  - 서비스의 보안 ID 및 선택적 메시지 헤더의 컬렉션을 나타내는 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 속성. 선택적 메시지 헤더는 엔드포인트 확인 및 엔드포인트와의 상호 작용을 위해 자세한 추가 주소 지정 정보를 제공하는 데 사용합니다.

  자세한 내용은 [끝점 주소 지정](../specifying-an-endpoint-address.md)을 참조 하세요.

- 바인딩: 바인딩은 엔드포인트와 통신하는 방법을 지정합니다. 여기에는 다음이 포함됩니다.

  - 사용할 전송 프로토콜(예: TCP 또는 HTTP)

  - 메시지에 사용할 인코딩(예: 텍스트 또는 이진)

  - 필요한 보안 요구 사항(예: SSL 또는 SOAP 메시지 보안)

  자세한 내용은 [WCF 바인딩 개요](../bindings-overview.md)를 참조 하세요. 바인딩은 WCF 개체 모델에서 추상 기본 클래스로 표현 됩니다 <xref:System.ServiceModel.Channels.Binding> . 대부분의 시나리오의 경우 사용자는 시스템 제공 바인딩 중 하나를 사용할 수 있습니다. 자세한 내용은 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하세요.

- 계약: 계약에서는 엔드포인트가 클라이언트에 노출하는 기능을 간략하게 설명합니다. 계약에서는 다음을 지정합니다.

  - 클라이언트가 호출할 수 있는 작업

  - 메시지 형식

  - 작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터 형식

  - 클라이언트가 예상할 수 있는 처리 또는 응답 메시지 형식

  계약을 정의 하는 방법에 대 한 자세한 내용은 [서비스 계약 디자인](../designing-service-contracts.md)을 참조 하세요.

- 동작: 엔드포인트 동작을 사용하여 서비스 엔드포인트의 로컬 동작을 사용자 지정할 수 있습니다. 끝점 동작은 WCF 런타임 빌드 프로세스에 참여 하 여이를 구현 합니다. 엔드포인트 동작의 예는 <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> 속성이며, 이 속성을 사용하여 SOAP 또는 WSDL(웹 서비스 기술 언어) 주소 이외의 다른 수신 대기 주소를 지정할 수 있습니다. 자세한 내용은 [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md)를 참조 하세요.

## <a name="defining-endpoints"></a>엔드포인트 정의

구성을 통해 코드를 명령적으로 또는 선언적으로 사용하여 서비스의 엔드포인트를 지정할 수 있습니다. 자세한 내용은 [방법: 구성에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-configuration.md) 및 [방법: 코드에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-code.md)를 참조 하세요.

## <a name="in-this-section"></a>섹션 내용

이 단원에서는 바인딩, 엔드포인트 및 주소의 용도에 대해 설명하고 바인딩 및 엔드포인트를 구성하는 방법과 `ClientVia` 동작 및 `ListenUri` 속성을 사용하는 방법을 보여 줍니다.

[주소로](endpoint-addresses.md)\
WCF에서 끝점의 주소를 지정 하는 방법을 설명 합니다.

[바인딩하](bindings.md)\
바인딩을 사용하여 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 방법에 대해 설명합니다.

[계약은](contracts.md)\
계약이 서비스 메서드를 정의하는 방법에 대해 설명합니다.

[방법: 구성에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-configuration.md)\
구성에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.

[방법: 코드에서 서비스 끝점 만들기](how-to-create-a-service-endpoint-in-code.md)\
코드에서 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.

[방법: Svcutil.exe를 사용 하 여 컴파일된 서비스 코드 유효성 검사](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)\
[ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용 하 여 서비스를 호스팅하지 않고 서비스 구현 및 구성에서 오류를 검색 하는 방법을 설명 합니다.

## <a name="see-also"></a>참고 항목

- [서비스 구성](../configuring-services.md)
- [바인딩 확장명](../extending/extending-bindings.md)
