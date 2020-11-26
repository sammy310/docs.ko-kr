---
title: WCF에서 권한 부여
description: Windows 인증, x.509 인증서, 사용자 이름 및 암호와 같은 인증을 제공 하는 WCF의 여러 메커니즘에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: e2334a8c024238f38e1c927a278a4e25e7dabd9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247540"
---
# <a name="authentication-in-wcf"></a>WCF에서 권한 부여

다음 항목에서는 Windows 인증, x.509 인증서, 사용자 이름 및 암호 등의 인증을 제공 하는 Windows Communication Foundation (WCF)의 다양 한 메커니즘을 보여 줍니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [방법: ASP.NET 멤버 자격 공급자 사용](how-to-use-the-aspnet-membership-provider.md)  
 ASP.NET 기능에는 멤버 자격 및 역할 공급자, 인증에 필요한 사용자 이름/암호 쌍을 저장할 데이터베이스 및 권한 부여를 위한 사용자 역할이 포함되어 있습니다. 이 항목에서는 WCF 서비스가 동일한 데이터베이스를 사용 하 여 사용자를 인증 하 고 권한을 부여 하는 방법을 설명 합니다.  
  
 [방법: 사용자 지정 사용자 이름 및 암호에 대한 유효성 검사기 사용](how-to-use-a-custom-user-name-and-password-validator.md)  
 사용자 지정 사용자 이름/암호 유효성 검사기를 통합하는 방법에 대해 보여 줍니다.  
  
 [서비스 ID 및 인증](service-identity-and-authentication.md)  
 추가 보호 수단으로 클라이언트는 서비스의 예상 *id* 를 지정 하 여 서비스를 인증할 수 있습니다. 예상 ID 및 서비스에서 반환한 ID가 서로 일치하지 않으면 인증되지 않습니다.  
  
 [보안 협상 및 시간 제한](security-negotiation-and-timeouts.md)  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 클래스의 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> 속성을 사용하는 방법에 대해 설명합니다.  
  
 [Windows 인증 오류 디버깅](debugging-windows-authentication-errors.md)  
 Windows 인증을 사용할 때 일반적으로 발생하는 문제에 대해 중점적으로 설명합니다.  
  
## <a name="reference"></a>참고  

 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>관련 단원  

 [일반적인 보안 시나리오](common-security-scenarios.md)  
  
## <a name="see-also"></a>참고 항목

- [보안 개요](security-overview.md)
- [Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))
