---
title: 인증을 위해 서비스 ID 재정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 5649ef4cc05c9c16b1f8f626ba5e2e584b0e52eb
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278914"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>인증을 위해 서비스의 ID를 재정의합니다.

일반적으로 선택한 클라이언트 자격 증명 형식에 따라 서비스 메타데이터에 노출되는 ID 형식이 결정되므로 서비스에 ID를 설정할 필요가 없습니다. 예를 들어 다음 구성 코드는 [ \<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) `clientCredentialType` 요소를 사용하고 특성을 Windows에 설정합니다.  

 다음 WSDL(웹 서비스 기술 언어) 단편에서는 이전에 정의한 엔드포인트의 ID를 보여 줍니다. 이 예제에서는 서비스가 특정 사용자 계정()username@contoso.com에서 자체 호스팅 서비스로 실행되므로 UPN(사용자 주체 이름) ID에는 계정 이름이 포함됩니다. UPN은 Windows 도메인의 사용자 로그인 이름이라고도 합니다.  

 ID 설정을 보여 주는 샘플 응용 프로그램에 대 한 [서비스 ID 샘플](../samples/service-identity-sample.md)을 참조 합니다. 서비스 ID에 대한 자세한 내용은 [서비스 ID 및 인증을](../feature-details/service-identity-and-authentication.md)참조하십시오.  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos 인증 및 ID  
 기본적으로 서비스가 Windows 자격 증명을 사용하도록 구성된 경우 [ \<사용자PrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) 또는 [ \<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) 요소를 포함하는 [ \<ID>](../../configure-apps/file-schema/wcf/identity.md) 요소가 WSDL에서 생성됩니다. 서비스가 `LocalSystem`에서 `LocalService` `NetworkService` 실행 중인 경우 SPN(서비스 주체 이름)은 기본적으로 호스트 `host/` \< *이름*> 형태로 생성됩니다. 서비스가 다른 계정에서 실행 중인 경우 WCF(Windows 통신 재단)는 \< *사용자 이름*>@<*도메인 이름*`>`의 형태로 UPN을 생성합니다. Kerberos 인증에서 서비스를 인증하려면 UPN 또는 SPN을 클라이언트에 제공해야 하므로 이 작업이 수행됩니다.  
  
 [Setpn](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)?redirectedfrom=MSDN) 도구를 사용하여 도메인에 있는 서비스 계정에 추가 SPN을 등록할 수도 있습니다. 그런 다음 SPN을 서비스 ID로 사용할 수 있습니다. 도구에 대한 자세한 내용은 [Setpn 개요를](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))참조하십시오.  
  
> [!NOTE]
> Windows 자격 증명 형식을 협상 없이 사용하려면 서비스의 사용자 계정이 Active Directory 도메인에 등록된 SPN에 대한 액세스 권한이 있어야 합니다. 다음과 같은 방법으로 이 작업을 수행할 수 있습니다.  
  
- NetworkService 또는 LocalSystem 계정을 사용하여 서비스를 실행합니다. 이러한 계정은 컴퓨터가 Active Directory 도메인에 가입할 때 설정된 컴퓨터 SPN에 액세스할 수 있으므로 WCF는 서비스의 메타데이터(WSDL)에서 서비스의 끝점 내에 적절한 SPN 요소를 자동으로 생성합니다.  
  
- 임의의 Active Directory 도메인 계정을 사용하여 서비스를 실행합니다. 이 경우 해당 도메인 계정의 SPN을 설정합니다. Setspn.exe 유틸리티 도구를 사용하여 이 작업을 수행할 수 있습니다. 서비스 계정에 대한 SPN을 만든 후 WCF를 구성하여 해당 SPN을 WSDL(메타데이터)을 통해 서비스의 클라이언트에 게시하도록 구성합니다. 이 작업은 애플리케이션 구성 파일이나 코드를 통해 노출된 엔드포인트에 대한 엔드포인트 ID를 설정하여 수행합니다.  
  
 SPN, Kerberos 프로토콜 및 Active Directory에 대한 자세한 내용은 [Windows용 Kerberos 기술 보충을](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10))참조하십시오.  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>SPN 또는 UPN이 빈 문자열인 경우  
 SPN 또는 UPN을 빈 문자열과 같게 설정하면 사용되는 보안 수준과 인증 모드에 따라 다른 많은 작업이 수행됩니다.  
  
- 전송 수준 보안을 사용하는 경우 NTLM(NT LanMan) 인증이 선택됩니다.  
  
- 메시지 수준 보안을 사용하는 경우 인증 모드에 따라 인증이 실패할 수 있습니다.  
  
- 모드를 사용하고 `spnego` 있고 특성이 `AllowNtlm` `false`'로 설정된 경우 인증실패합니다.  
  
- 모드를 사용하고 `spnego` 있고 특성이 `AllowNtlm` `true`으로 설정된 경우 UPN이 비어 있지만 SPN이 비어 있으면 인증이 실패합니다.  
  
- "단일 쇼트"라고도 하는 Kerberos direct를 사용하는 경우 인증이 실패합니다.  
  
### <a name="use-the-identity-element-in-configuration"></a>구성에서 \<요소의 id> 사용  
 이전에 표시된 `Certificate`바인딩에서 클라이언트 자격 증명 유형을 변경하는 경우 생성된 WSDL에는 다음 코드에 표시된 ID 값에 대한 Base64 직렬화된 X.509 인증서가 포함됩니다. 이는 Windows 이외의 모든 클라이언트 자격 증명 형식에 대한 기본값입니다.  

 구성에서 <`identity`> 요소를 사용하거나 코드에서 ID를 설정하여 기본 서비스 ID의 값을 변경하거나 ID 유형을 변경할 수 있습니다. 다음 구성 코드에서는 값 `contoso.com`으로 DNS(Domain Name System) ID를 설정합니다.  

### <a name="set-identity-programmatically"></a>프로그래밍 방식으로 ID 설정  
 WCF가 자동으로 ID를 결정하기 때문에 서비스는 ID를 명시적으로 지정할 필요가 없습니다. 그러나 WCF를 사용하면 필요한 경우 끝점에 ID를 지정할 수 있습니다. 다음 코드에서는 특정 DNS ID를 사용하여 새 서비스 엔드포인트를 추가합니다.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>참고 항목

- [방법: 사용자 지정 클라이언트 ID 검증 도구 만들기](how-to-create-a-custom-client-identity-verifier.md)
- [서비스 ID 및 인증](../feature-details/service-identity-and-authentication.md)
