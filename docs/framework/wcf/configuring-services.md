---
title: WCF 서비스 구성
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 332a88530010197187ca3ea787e152b0c95a5514
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141590"
---
# <a name="configuring-wcf-services"></a>WCF 서비스 구성

서비스 계약을 디자인하고 구현했으면 서비스를 구성할 준비가 되었습니다. 여기서 서비스를 찾을 수 있는 주소, 메시지를 보내고 받는 데 사용하는 전송 및 메시지 인코딩, 서비스에 필요한 보안 형식 지정 등 서비스가 클라이언트에 노출되는 방법을 정의하고 사용자 지정할 수 있습니다.  
  
 여기서 사용되는 구성은 코드에서 명령적으로 또는 구성 파일을 사용하여 엔드포인트 주소, 사용된 전송 및 보안 체계 지정 같은 서비스의 다양한 측면을 정의하고 사용자 지정할 수 있는 모든 방식이 포함됩니다. 실제로 구성 작성은 WCF 응용 프로그램 프로그래밍의 주요 부분입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [단순화된 구성](simplified-configuration.md)  
 .NET Framework 4부터 WCF는 WCF 구성 요구 사항을 간소화 하는 새로운 기본 구성 모델과 함께 제공 됩니다. 특정 서비스에 대 한 WCF 구성을 제공 하지 않으면 런타임에서 기본 끝점, 바인딩 및 동작을 사용 하 여 서비스를 자동으로 구성 합니다.  
  
 [구성 파일을 사용하여 서비스 구성](configuring-services-using-configuration-files.md)  
 WCF (Windows Communication Foundation) 서비스는 .NET Framework 구성 기술을 사용 하 여 구성할 수 있습니다. 가장 일반적으로 XML 요소는 WCF 서비스를 호스팅하는 인터넷 정보 서비스 (IIS) 사이트의 web.config 파일에 추가 됩니다. 이 요소를 사용하여 엔드포인트 주소(서비스와의 통신에 사용되는 실제 주소) 등의 세부 사항을 컴퓨터별로 변경할 수 있습니다.  
  
 [바인딩](bindings.md)  
 또한 WCF에는 사용 되는 전송, 보안 및 메시지 인코딩과 같이 클라이언트와 서비스가 통신 하는 방법에 대 한 가장 기본적인 기능을 신속 하 게 선택할 수 있는 바인딩 형태로 여러 시스템 제공 일반 구성이 포함 되어 있습니다.  
  
 [엔드포인트](endpoints.md)  
 WCF 서비스와의 모든 통신은 서비스의 *끝점* 을 통해 수행 됩니다. 엔드포인트에는 계약, 바인딩에 지정된 구성 정보 및 서비스를 찾을 위치나 서비스 정보를 얻을 수 있는 위치를 나타내는 주소가 포함되어 있습니다.  
  
 [서비스에 보안 설정](securing-services.md)  
 WCF 및 기존 보안 메커니즘을 사용 하 여 모든 서비스에 기밀성, 무결성, 인증 및 권한 부여를 구현할 수 있습니다. 보안 성공 및 실패를 감사할 수도 있습니다.  
  
 [WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 다른 플랫폼 또는 운영 체제의 서비스 및 클라이언트와 상호 운용될 수 있는 서비스를 배포하기 위한 요구 사항은 WS-I Basic Profile 1.1 사양에 간략하게 설명되어 있습니다.  
  
## <a name="reference"></a>참고  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>관련 단원  
 [기본 프로그래밍 수명 주기](basic-programming-lifecycle.md)  
  
 [서비스 디자인 및 구현](designing-and-implementing-services.md)  
  
 [서비스 호스팅](hosting-services.md)  
  
 [클라이언트 빌드](building-clients.md)  
  
 [확장성 소개](introduction-to-extensibility.md)  
  
 [관리 및 진단](./diagnostics/index.md)  
  
## <a name="see-also"></a>참조

- [기본 WCF 프로그래밍](basic-wcf-programming.md)
- [개념적 개요](conceptual-overview.md)
- [WCF 기능 정보](./feature-details/index.md)
