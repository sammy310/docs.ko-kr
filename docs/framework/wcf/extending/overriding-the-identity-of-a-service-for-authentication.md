---
description: '자세한 정보: 인증을 위해 서비스 id 재정의'
title: 인증을 위해 서비스 ID 재정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: f83c10d75c4ea71170a76a7fd10efb33958f5b52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644166"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>인증을 위해 서비스 id 재정의

일반적으로 선택한 클라이언트 자격 증명 형식에 따라 서비스 메타데이터에 노출되는 ID 형식이 결정되므로 서비스에 ID를 설정할 필요가 없습니다. 예를 들어 다음 구성 코드에서는 요소를 사용 하 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 고 `clientCredentialType` 특성을 Windows로 설정 합니다.  

 다음 WSDL(웹 서비스 기술 언어) 단편에서는 이전에 정의한 엔드포인트의 ID를 보여 줍니다. 이 예제에서 서비스는 특정 사용자 계정 ()에서 자체 호스팅 서비스로 실행 되므로 username@contoso.com UPN (사용자 계정 이름) id에는 계정 이름이 포함 됩니다. UPN은 Windows 도메인에서 사용자 로그인 이름이 라고도 합니다.  

 Id 설정을 보여 주는 샘플 응용 프로그램은 [서비스 Id 샘플](../samples/service-identity-sample.md)을 참조 하세요. 서비스 id에 대 한 자세한 내용은 [서비스 id 및 인증](../feature-details/service-identity-and-authentication.md)을 참조 하세요.  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos 인증 및 ID  

 기본적으로 Windows 자격 증명을 사용 하도록 서비스를 구성 하면 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 또는 요소가 포함 된 요소가 [\<userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) WSDL에서 생성 됩니다. , 또는 계정으로 서비스를 실행 하는 경우 `LocalSystem` `LocalService` `NetworkService` `host/` \<*hostname*> 해당 계정이 컴퓨터의 spn 데이터에 액세스할 수 있으므로 spn (서비스 사용자 이름)이 기본적으로 형식으로 생성 됩니다. 서비스가 다른 계정으로 실행 되는 경우 WCF (Windows Communication Foundation)는 domainName 형식의 UPN을 생성 \<*username*> @<  `>` 합니다. Kerberos 인증에서 서비스를 인증하려면 UPN 또는 SPN을 클라이언트에 제공해야 하므로 이 작업이 수행됩니다.  
  
 [Setspn](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)) 도구를 사용 하 여 도메인의 서비스 계정으로 추가 SPN을 등록할 수도 있습니다. 그런 다음 SPN을 서비스 ID로 사용할 수 있습니다. 이 도구에 대 한 자세한 내용은 [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))를 참조 하십시오.  
  
> [!NOTE]
> Windows 자격 증명 형식을 협상 없이 사용하려면 서비스의 사용자 계정이 Active Directory 도메인에 등록된 SPN에 대한 액세스 권한이 있어야 합니다. 다음과 같은 방법으로 이 작업을 수행할 수 있습니다.  
  
- NetworkService 또는 LocalSystem 계정을 사용하여 서비스를 실행합니다. 이러한 계정에는 컴퓨터가 Active Directory 도메인에 가입할 때 설정 되는 컴퓨터 SPN에 대 한 액세스 권한이 있기 때문에 WCF는 서비스의 메타 데이터 (WSDL)에서 서비스의 끝점 내부에 적절 한 SPN 요소를 자동으로 생성 합니다.  
  
- 임의의 Active Directory 도메인 계정을 사용하여 서비스를 실행합니다. 이 경우 해당 도메인 계정의 SPN을 설정합니다. Setspn.exe 유틸리티 도구를 사용하여 이 작업을 수행할 수 있습니다. 서비스 계정에 대 한 SPN을 만든 후 해당 메타 데이터 (WSDL)를 통해 서비스의 클라이언트에 해당 SPN을 게시 하도록 WCF를 구성 합니다. 이 작업은 애플리케이션 구성 파일이나 코드를 통해 노출된 엔드포인트에 대한 엔드포인트 ID를 설정하여 수행합니다.  
  
 Spn, Kerberos 프로토콜 및 Active Directory에 대 한 자세한 내용은 [Windows 용 Kerberos 기술 보충 자료](/previous-versions/msp-n-p/ff649429(v=pandp.10))를 참조 하십시오.  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>SPN 또는 UPN이 빈 문자열인 경우  

 SPN 또는 UPN을 빈 문자열과 같게 설정하면 사용되는 보안 수준과 인증 모드에 따라 다른 많은 작업이 수행됩니다.  
  
- 전송 수준 보안을 사용하는 경우 NTLM(NT LanMan) 인증이 선택됩니다.  
  
- 메시지 수준 보안을 사용하는 경우 인증 모드에 따라 인증이 실패할 수 있습니다.  
  
- 모드를 사용 하 `spnego` 고 특성을 `AllowNtlm` 로 설정 하면 `false` 인증에 실패 합니다.  
  
- 모드를 사용 하 `spnego` 고 `AllowNtlm` 특성이로 설정 된 경우 `true` UPN이 비어 있지만 SPN이 비어 있으면 인증에 실패 합니다.  
  
- "단일 쇼트"라고도 하는 Kerberos direct를 사용하는 경우 인증이 실패합니다.  
  
### <a name="use-the-identity-element-in-configuration"></a>\<identity>구성에서 요소 사용  

 이전에에 표시 된 바인딩에서 클라이언트 자격 증명 형식을 변경 하면 `Certificate` 생성 된 WSDL에 다음 코드에 표시 된 것 처럼 id 값에 대 한 b a s e 64로 serialize 된 x.509 인증서가 포함 됩니다. 이는 Windows 이외의 모든 클라이언트 자격 증명 형식에 대한 기본값입니다.  

 `identity`구성의 <> 요소를 사용 하거나 코드에서 id를 설정 하 여 기본 서비스 id의 값을 변경 하거나 id 형식을 변경할 수 있습니다. 다음 구성 코드에서는 값 `contoso.com`으로 DNS(Domain Name System) ID를 설정합니다.  

### <a name="set-identity-programmatically"></a>프로그래밍 방식으로 Id 설정  

 WCF가 자동으로 결정 하므로 서비스에서 명시적으로 id를 지정할 필요가 없습니다. 그러나 WCF를 사용 하면 필요한 경우 끝점에 id를 지정할 수 있습니다. 다음 코드에서는 특정 DNS ID를 사용하여 새 서비스 엔드포인트를 추가합니다.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>참고 항목

- [방법: 사용자 지정 클라이언트 ID 검증 도구 만들기](how-to-create-a-custom-client-identity-verifier.md)
- [서비스 ID 및 인증](../feature-details/service-identity-and-authentication.md)
