---
title: '방법: 클라이언트 자격 증명 형식 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: d62011728b6b03023ef4039480cea8dfa0ec8f02
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321295"
---
# <a name="how-to-specify-the-client-credential-type"></a>방법: 클라이언트 자격 증명 형식 지정
전송 또는 메시지 보안 모드를 설정한 후에는 클라이언트 자격 증명 형식을 설정할 수 있습니다. 이 속성은 인증을 위한 서비스에 제공해야 할 자격 증명 유형을 지정합니다. 보안 모드를 설정 하는 방법에 대 한 자세한 내용은 (클라이언트 자격 증명 형식을 설정 하는 데 필요한 단계) [방법: 보안 모드 설정](how-to-set-the-security-mode.md)을 참조 하세요.  
  
### <a name="to-set-the-client-credential-type-in-code"></a>클라이언트 자격 증명 형식을 코드로 설정하려면  
  
1. 서비스에서 사용할 바인딩의 인스턴스를 만듭니다. 이 예제에서는 <xref:System.ServiceModel.WSHttpBinding> 바인딩을 사용합니다.  
  
2. <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 속성을 적절한 값으로 설정합니다. 이 예제에서는 메시지 모드를 사용합니다.  
  
3. <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 속성을 적절한 값으로 설정합니다. 이 예제에서는 Windows 인증(<xref:System.ServiceModel.MessageCredentialType.Windows>)을 사용하도록 값을 설정합니다.  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>클라이언트 자격 증명 형식을 구성에 설정하려면  
  
1. [@No__t_1system serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 구성 파일에 추가 합니다.  
  
2. 자식 요소로 [\<bindings >](../configure-apps/file-schema/wcf/bindings.md) 요소를 추가 합니다.  
  
3. 적절한 바인딩을 추가합니다. 이 예제에서는 [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) 요소를 사용 합니다.  
  
4. [@No__t_1binding >](../misc/binding.md) 요소를 추가 하 고 `name` 특성을 적절 한 값으로 설정 합니다. 이 예제에서는 "SecureBinding"을 이름으로 사용합니다.  
  
5. `<security>` 바인딩을 추가합니다. `mode` 특성을 적절한 값으로 설정합니다. 이 예제에서는 `"Message"`로 설정합니다.  
  
6. 보안 모드의 결정에 따라 `<message>` 또는 `<transport>` 요소를 추가합니다. `clientCredentialType` 특성을 적절한 값으로 설정합니다. 이 예제에서는 `"Windows"`를 사용합니다.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>참조

- [서비스에 보안 설정](securing-services.md)
- [방법: 보안 모드 설정](how-to-set-the-security-mode.md)
