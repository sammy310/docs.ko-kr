---
description: '자세히 알아보기: 보안 확장'
title: 보안 확장
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 8dd514e16106ac5cdae072d92c7de66cefd39fe4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685727"
---
# <a name="extending-security"></a>보안 확장

새 클레임 형식 및 사용자 지정 토큰을 수용 하기 위해 WCF (Windows Communication Foundation)의 보안 인프라를 확장할 수 있습니다. 이 단원의 각 항목에서는 이를 수행하는 방법을 보여 줍니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
 [사용자 지정 자격 증명 및 자격 증명 유효성 검사](custom-credential-and-credential-validation.md)  
 사용자 지정 자격 증명의 유효성을 검사할 때 ID 모델을 사용하는 방법에 대해 설명합니다.  
  
 [사용자 지정 토큰](custom-tokens.md)  
 일반적으로 STS(보안 토큰 서비스)에서 발행된 토큰은 SAML 토큰입니다. 이 항목에서는 사용자 지정 토큰 형식에 대해 설명합니다.  
  
 [사용자 지정 권한 부여](custom-authorization.md)  
 사용자 지정 인증을 구현하는 방법에 대해 설명합니다.  
  
 [인증을 위해 서비스 ID 재정의](overriding-the-identity-of-a-service-for-authentication.md)  
 인증을 위해 서비스의 ID를 재지정하는 방법에 대해 설명합니다.  
  
 [방법: 사용자 지정 클라이언트 ID 검증 도구 만들기](how-to-create-a-custom-client-identity-verifier.md)  
 사용자 지정 엔드포인트 ID의 유효성을 검사하는 방법을 보여 줍니다.  
  
 [방법: 서명 및 암호화에 별도의 X.509 인증서 사용](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 일반적으로 메시지는 단일 인증서를 사용하여 서명되고 암호화됩니다. 이 항목에서는 필요한 경우 두 가지 인증서를 사용하는 방법에 대해 설명합니다.  
  
 [방법: X.509 인증서의 프라이빗 키에 대한 암호화 공급 기업 변경](change-cryptographic-provider-x509-certificate-private-key.md)  
 X.509 인증서의 개인 키를 제공 하는 데 사용 되는 암호화 공급자를 변경 하는 방법과 공급자를 WCF (Windows Communication Foundation) 프레임 워크에 통합 하는 방법에 대해 설명 합니다.  
  
## <a name="reference"></a>참고  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>관련 단원  

 [보안](../feature-details/security.md)  
  
 [기본 WCF 프로그래밍](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>참고 항목

- [보안 개요](../feature-details/security-overview.md)
