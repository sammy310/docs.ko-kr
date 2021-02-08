---
description: '자세히 알아보기: COM 응용 프로그램과 통합'
title: COM 애플리케이션과 통합
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 7afee4bed334d7f392b73773f0981022a59170fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802803"
---
# <a name="integrating-with-com-applications"></a>COM 애플리케이션과 통합

Wcf 서비스 모니커를 사용 하 여 WCF (Windows Communication Foundation) 서비스를 기존 코드에 직접 통합할 수 있습니다. 서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [COM 애플리케이션과 통합 개요](integrating-with-com-applications-overview.md)  
 통합 프로세스의 주요 부분에 대한 개요를 제공합니다.  
  
 [방법: 서비스 모니커 등록 및 구성](how-to-register-and-configure-a-service-moniker.md)  
 COM 응용 프로그램 내에서 WCF 서비스 모니커를 사용 하려면 필요한 특성 사용 형식을 COM에 등록 하 고 필요한 바인딩 구성을 사용 하 여 COM 응용 프로그램과 모니커를 구성 합니다.  
  
 [방법: 등록하지 않고 Windows Communication Foundation 서비스 모니커 사용](use-the-wcf-service-moniker-without-registration.md)  
 WSDL(웹 서비스 기술 언어) 문서의 형태로 또는 WS-MetadataExchange 엔드포인트에서 계약 정의를 가져오는 방법에 대해 설명합니다.  
  
 [방법: WSDL 계약을 통해 서비스 모니커 사용](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 WCF WSDL 모니커를 사용 하 여 WCF 샘플을 호출 하는 방법을 설명 합니다.  
  
 [방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Mex 끝점을 지정 하는 WCF 모니커를 사용 하 여 WCF 샘플을 호출 하는 방법을 설명 합니다.  
  
 [방법: 채널 보안 자격 증명 지정](how-to-specify-channel-security-credentials.md)  
 WCF 서비스 모니커는 `IChannelCredentials` 채널 자격 증명을 지정 하는 다양 한 다른 방법을 허용 하는 인터페이스를 지원 합니다.  
  
## <a name="reference"></a>참고  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>참조

- [COM + 응용 프로그램과 통합](integrating-with-com-plus-applications.md)
